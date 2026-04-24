
```shell

# pgsql 链接
psql "postgresql://booster_insight_test@tc-sg-mindbooster.pgdb.domob-inc.com:5432/booster_insight_test"

# 在数据库添加插件
## 方法1：查看已安装的扩展（需要先 CREATE EXTENSION）
SELECT * FROM pg_extension WHERE extname = 'vector';

## 方法2：查看系统中可安装的扩展（无需安装即可检测）
SELECT * FROM pg_available_extensions WHERE name = 'vector';

## 添加/激活
CREATE EXTENSION IF NOT EXISTS vector;

## 验证安装成功
SELECT extversion FROM pg_extension WHERE extname = 'vector';
### 应返回类似 0.8.0
```