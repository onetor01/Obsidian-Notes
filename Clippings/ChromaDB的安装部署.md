**ChromaDB 安装部署完整指南（2026年4月最新官方方式）**

ChromaDB 支持两种主要模式：
- **嵌入式（Embedded）**：简单但不适合生产长期记忆（进程重启可能丢数据）。
- **客户端-服务器模式（Client-Server）**：推荐用于 ADK 长期记忆（独立进程 + 持久化 + 多客户端访问）。

以下是**最实用**的两种部署方式（CLI + Docker），直接适用于你之前的 ADK `CustomMemoryService` 场景。

### 1. **最推荐本地/开发部署：使用 CLI 启动 Server（零 Docker，最简单）**

#### 步骤
1. **安装 Python 客户端（同时包含 CLI）**：
   ```bash
   pip install chromadb
   ```
   （最新版本 ≈ 1.5.8，2026年4月16日发布）

2. **创建数据目录并启动 Server**：
   ```bash
   mkdir -p ./chroma-data   # 持久化目录（重启不丢数据）
   
   chroma run --path ./chroma-data \
              --host 0.0.0.0 \     # 允许外部访问（ADK 同机或局域网）
              --port 8000
   ```

   - 后台运行（推荐）：
     ```bash
     nohup chroma run --path ./chroma-data --host 0.0.0.0 --port 8000 > chroma.log 2>&1 &
     ```
     或用 systemd / pm2 管理进程。

3. **验证运行**：
   ```bash
   curl http://localhost:8000/api/v2/heartbeat
   ```
   返回 `{"nanosecond heartbeat": ...}` 即成功。

4. **在 Python / ADK 中连接**（CustomMemoryService 使用）：
   ```python
   import chromadb
   
   client = chromadb.HttpClient(host="localhost", port=8000)
   # 测试
   print(client.heartbeat())
   ```

**优点**：安装简单、数据自动持久化到 `./chroma-data` 文件夹。

### 2. **生产推荐部署：Docker（稳定、可容器化）**

#### 步骤
1. **确保已安装 Docker**（Docker Desktop 或 Docker Engine）。

2. **启动 Chroma Server**（官方推荐命令）：
   ```bash
   docker run -d \
     --name chromadb \
     -v ./chroma-data:/data \          # 持久化卷（关键！）
     -p 8000:8000 \                    # 端口映射
     chromadb/chroma                   # 官方镜像（latest 标签）
   ```

   **完整推荐命令**（带日志和重启策略）：
   ```bash
   docker run -d \
     --name chromadb \
     --restart unless-stopped \
     -v $(pwd)/chroma-data:/data \
     -p 8000:8000 \
     chromadb/chroma
   ```

3. **可选：自定义配置**（如允许 reset、日志等）：
   ```bash
   # 创建配置文件
   cat > config.yaml << EOF
   allow_reset: true
   EOF
   
   docker run -d \
     -v ./chroma-data:/data \
     -v ./config.yaml:/config.yaml \
     -p 8000:8000 \
     chromadb/chroma
   ```

4. **docker-compose.yml 示例**（推荐生产使用）：
   ```yaml
   version: '3.8'
   services:
     chromadb:
       image: chromadb/chroma:latest
       container_name: chromadb
       restart: unless-stopped
       ports:
         - "8000:8000"
       volumes:
         - ./chroma-data:/data
       # environment:
       #   - CHROMA_OPEN_TELEMETRY__ENDPOINT=...  # 可选监控
   ```
   启动：`docker compose up -d`

5. **Python 客户端连接**（同上）：
   ```python
   client = chromadb.HttpClient(host="localhost", port=8000)  # 或服务器 IP
   ```

### 3. **ADK 集成小贴士**
- 在你的 `CustomMemoryService` 类里，用 `chromadb.HttpClient` 实现 `add_session_to_memory` 和 `search_memory`。
- 推荐用 **PersistentClient** 仅做本地测试，生产必须用 `HttpClient` + 上面部署的 Server。
- 数据目录 `./chroma-data` 里会自动生成 collections、向量索引等，备份时直接复制整个文件夹即可。

### 常见问题
- **端口被占用** → 改 `--port 8001` 并对应修改 HttpClient。
- **想用其他向量DB替代** → 也可以，但 Chroma 是 ADK 社区里最轻量的。
- **云部署** → 可以扔到 AWS/GCP/EC2 + Docker，或直接用官方 CloudFormation/Terraform（但你说不想依赖 Vertex AI，这里就不展开了）。

需要我给你**一个完整的 `CustomMemoryService` + Chroma 实现代码模板**（继承 `BaseMemoryService`，支持 user_id 隔离），还是 **docker-compose + ADK Runner 示例**？直接说，我马上贴！