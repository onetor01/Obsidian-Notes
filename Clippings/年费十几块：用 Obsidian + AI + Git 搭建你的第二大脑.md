---
title: "年费十几块：用 Obsidian + AI + Git 搭建你的第二大脑"
source: "https://zhuanlan.zhihu.com/p/2005335684941125084"
author:
  - "[[彼岸流天vx 同名]]"
published:
created: 2026-04-20
description: "AI 驱动的知识管理系统概念图 一杯奶茶的钱，就能拥有 AI 驱动的知识管理系统——带版本回退、云端同步。你大概已经用 Obsidian 写了不少笔记。你可能也试过 ChatGPT 或 DeepSeek 的网页版——润色文字、总结长文…"
tags:
  - "clippings"
---
![](https://pic1.zhimg.com/v2-b5fee71491ed5543ae7681b713e606d8_1440w.jpg)

AI 驱动的知识管理系统概念图

> 一杯奶茶的钱，就能拥有 AI 驱动的知识管理系统——带版本回退、云端同步。

你大概已经用 [Obsidian](https://zhida.zhihu.com/search?content_id=270290342&content_type=Article&match_order=1&q=Obsidian&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3NzY4MzMzNDEsInEiOiJPYnNpZGlhbiIsInpoaWRhX3NvdXJjZSI6ImVudGl0eSIsImNvbnRlbnRfaWQiOjI3MDI5MDM0MiwiY29udGVudF90eXBlIjoiQXJ0aWNsZSIsIm1hdGNoX29yZGVyIjoxLCJ6ZF90b2tlbiI6bnVsbH0.DkDr6Agy9hc5V-AAKPC9GXj6OxGowTqDLDE55lxofPw&zhida_source=entity) 写了不少笔记。你可能也试过 ChatGPT 或 [DeepSeek](https://zhida.zhihu.com/search?content_id=270290342&content_type=Article&match_order=1&q=DeepSeek&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3NzY4MzMzNDEsInEiOiJEZWVwU2VlayIsInpoaWRhX3NvdXJjZSI6ImVudGl0eSIsImNvbnRlbnRfaWQiOjI3MDI5MDM0MiwiY29udGVudF90eXBlIjoiQXJ0aWNsZSIsIm1hdGNoX29yZGVyIjoxLCJ6ZF90b2tlbiI6bnVsbH0.CJ_ct2zBmfiPxp0zIMsFliBh2_uzFOPwx5Q9BsUbvvM&zhida_source=entity) 的网页版——润色文字、总结长文、回答疑问。但有一个别扭的地方你一定感受过： **这两件事是断开的** 。

昨天你在 DeepSeek 网页版里让 AI 帮你把一篇论文的核心论点提炼出来，聊了三轮终于拿到满意的版本。切到 Obsidian，Ctrl+V 粘贴进读书笔记。今天又想让 AI 基于你过去三个月的读书笔记帮你写一份综述——但你得把十几篇笔记一篇篇打开，手动复制粘贴到聊天窗口。一来一回，上下文丢了大半，耐心也磨没了。

还有两个老毛病：笔记没有版本管理，上周删掉的那段话这周才发现还有用——但已经找不回来了；多设备同步呢？Obsidian Sync 每月 $48（约 3060 元），一年几百块，就为了"在家和公司同步一下笔记"。

**有一套方案，全年花费大约 5~15 块钱，能把这三个问题一次性解决。**

四个组件：

- • **Obsidian** ——你的笔记主场，免费
- • **[Copilot 插件](https://zhida.zhihu.com/search?content_id=270290342&content_type=Article&match_order=1&q=Copilot+%E6%8F%92%E4%BB%B6&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3NzY4MzMzNDEsInEiOiJDb3BpbG90IOaPkuS7tiIsInpoaWRhX3NvdXJjZSI6ImVudGl0eSIsImNvbnRlbnRfaWQiOjI3MDI5MDM0MiwiY29udGVudF90eXBlIjoiQXJ0aWNsZSIsIm1hdGNoX29yZGVyIjoxLCJ6ZF90b2tlbiI6bnVsbH0.DB1NWurBRg5bUaTmC8B0YrGpnmvLjxRoOug_uOD8w4E&zhida_source=entity)** ——把 AI 搬进 Obsidian 的桥梁，免费
- • **DeepSeek / [Kimi](https://zhida.zhihu.com/search?content_id=270290342&content_type=Article&match_order=1&q=Kimi&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3NzY4MzMzNDEsInEiOiJLaW1pIiwiemhpZGFfc291cmNlIjoiZW50aXR5IiwiY29udGVudF9pZCI6MjcwMjkwMzQyLCJjb250ZW50X3R5cGUiOiJBcnRpY2xlIiwibWF0Y2hfb3JkZXIiOjEsInpkX3Rva2VuIjpudWxsfQ.hWKrrR7nNJoirXFXCO2G2ZKJA-CFKFdV-h0oBLnaLfY&zhida_source=entity) API** ——国产大模型，价格低到离谱，按量计费
- • **Git + [GitHub](https://zhida.zhihu.com/search?content_id=270290342&content_type=Article&match_order=1&q=GitHub&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3NzY4MzMzNDEsInEiOiJHaXRIdWIiLCJ6aGlkYV9zb3VyY2UiOiJlbnRpdHkiLCJjb250ZW50X2lkIjoyNzAyOTAzNDIsImNvbnRlbnRfdHlwZSI6IkFydGljbGUiLCJtYXRjaF9vcmRlciI6MSwiemRfdG9rZW4iOm51bGx9.kjfowSTt6c7XYQ79tc10xfvDeO5ohIrnczneosvxY18&zhida_source=entity)** ——版本管理 + 云端同步，免费

下面手把手带你跑通全流程。不需要是程序员，但得愿意动手折腾半小时左右。

### 为什么你需要这套组合

![](https://pic2.zhimg.com/v2-983e9c7ed3b87be28cea48e687a7a209_1440w.jpg)

知识工作者的三大痛点

### 知识工作者的三个老大难

前面说的那些别扭，归根结底就三件事：

1. 1\. **AI 和笔记分家** ——每次切窗口复制粘贴，都是注意力的一次小型车祸
2. 2\. **改了就是改了** ——没有"回退到三天前"的按钮
3. 3\. **同步要交保护费** ——Obsidian Sync 一年 $4896（约 350700 元），只为在两台电脑间同步

### 四件套各管什么

| 组件 | 角色 | 费用 |
| --- | --- | --- |
| Obsidian | 笔记编辑器 | 免费 |
| Copilot 插件 | AI 的入口——对话、命令、全库语义问答 | 免费 |
| DeepSeek / Kimi API | AI 的大脑——理解你的问题、生成内容 | 约 0.2~3 元/百万 token |
| Git + GitHub | 时光机 + 传送门——版本回退 + 多设备同步 | 免费 |

粗略一算：正常使用强度下， **一年 AI 费用大约 5~15 元** ——详细拆解见后文"算一笔账"章节。

一杯奶茶的钱，一年的 AI 助理。

### 第一步：装上 Copilot 插件

![](https://pica.zhimg.com/v2-d90b4a91156e56cfa1436bec21acfe20_1440w.jpg)

Obsidian Copilot 插件安装示意

假设你已经有 Obsidian（没有的话去 obsidian.md 下载）。

1. 1\. 打开 Obsidian → **设置** → **第三方插件** → 关掉安全模式
2. 2\. 点 **浏览社区插件** ，搜索 **Copilot**
3. 3\. 找到作者是 Logan Yang 的那个， **安装 → 启用**

左侧边栏会多出一个对话气泡图标。点一下，右侧弹出聊天面板——不过现在还不能用，因为还没告诉它该找哪个 AI。

进入 **设置 → Copilot Settings** ，你会看到几块配置区域：

- • **API Keys** ：各家 AI 服务的钥匙
- • **Default Chat Model** ：默认用哪个模型
- • **Embedding Model** ：全库语义搜索用的向量模型
- • **Conversation Settings** ：聊天记录存哪儿、文件名格式

先不急填，下一步去拿 Key。

### 第二步：接入 DeepSeek——0.2 元就能聊一百万字

![](https://pica.zhimg.com/v2-4ffccbeaafc044c3eaf6e23555415b4a_1440w.jpg)

DeepSeek API 接入配置

DeepSeek 是目前国内最火的开源大模型之一。中文能力很强，API 价格低到让人怀疑是不是标错了。

### 拿到 API Key

1. 1\. 去 DeepSeek 开放平台 注册
2. 2\. 注册完系统直接送 **10 元免费额度** ——够你用几个月
3. 3\. 进控制台 → 左侧 **API Keys** → **创建 API Key**
4. 4\. **马上复制保存** 。这个 Key 只显示一次，关掉就没了

### 把 DeepSeek 塞进 Copilot

回到 Obsidian， **设置 → Copilot Settings → Basic Settings → API Keys → Set Keys** ：

1. 1\. 在 API 设置面板中，找到 DeepSeek 的输入框（如果有的话），直接粘贴 API Key
2. 2\. 或者——点击 **Add Model** ，选择 **Custom Model**
3. 3\. 填这些：
- • **Model Name** ： `deepseek-chat`
- • **Provider** ： `3rd party (openai-format)`
- • **Base URL** ： `https://api.deepseek.com` （Copilot 会自动处理 `/v1` 后缀，直接填根地址即可）
- • **API Key** ：刚才复制的那个
- 4\. 点 **Add Model**

> **DeepSeek 的好处** ：它兼容 OpenAI 格式，在 Copilot 里可以直接添加 API Key 就能用，配置非常简单。

想用深度思考模式？再加一个，Model Name 填 `deepseek-reasoner` ，其他都一样。注意 reasoner 的 token 消耗比 chat 高不少（思考过程也算 token），日常别挂它，需要时再切。

回到 **Basic Settings** ，把 **Default Chat Model** 选成 `deepseek-chat` ，点 **Save and Reload** 。

打开聊天面板，打个"你好"——如果 DeepSeek 搭理你了，配置就成了。

> **配置不成功怎么办？** 检查三个地方：① API Key 是否复制完整（没有多余空格）；② Base URL 是否拼写正确；③ DeepSeek 账户余额是否为正（新用户有 10 元免费额度，应该足够）。如果报 `stream_options` 相关的错误，可以尝试在插件目录的 `data.json` 中把对应模型的 `"stream"` 设为 `false` 。

### deepseek-chat 还是 deepseek-reasoner？

| 模型 | 脾气 | 什么时候用 |
| --- | --- | --- |
| deepseek-chat | 快，128K 上下文，输出最多 8K | 日常：润色、翻译、摘要、闲聊 |
| deepseek-reasoner | 慢但深，输出最多 64K，token 吃得多 | 较真的时候：长文写作、逻辑分析、数学推理 |

日常挂 `deepseek-chat` 就够用了。碰到复杂问题再临时切。

### 第三步：接入 Kimi——一次喂进去 20 万字

![](https://pic4.zhimg.com/v2-05d61c54bba665db0ba4b99269e18b19_1440w.jpg)

Kimi 超长上下文模型

Kimi 是月之暗面（Moonshot AI）的大模型。它的杀手锏是 **128K 超长上下文** ——差不多能一次性处理 20 万字。如果你手头有长篇论文、整本书的笔记要让 AI 消化，Kimi 比较对路。

### 拿到 API Key

1. 1\. 去 Kimi 开放平台 注册
2. 2\. 进控制台 → **账户管理** → 创建 API Key → 保存

### 塞进 Copilot

Kimi 跟 DeepSeek 不一样——Kimi 不是 Copilot 的内置 Provider，所以 **必须通过 Add Custom Model 来配置** ：

1. 1\. Copilot Settings → **Model 标签页** → 拉到底点 **Add Custom Model**
2. 2\. 填：
- • **Model Name** ： `kimi-latest` （最便宜的选项，1 元/百万 token）
- • **Provider** ： `3rd party (openai-format)`
- • **Base URL** ： `https://api.moonshot.cn/v1`
- • **API Key** ：Kimi 的 Key
- 3\. 点 **Add Model**

> **注意区别** ：DeepSeek 可以直接在 API Keys 面板添加 Key 就能用；Kimi 则需要走 Add Custom Model 流程，手动填写 Base URL 和模型名。操作多一步，但效果一样。  
> 碰到 CORS 报错？添加模型时把 **Enable CORS** 勾上。有些 API 服务不允许浏览器直接调用，Copilot 提供了代理绕过的口子。不过勾了 CORS 之后会失去流式输出——回复不再逐字蹦出来，而是等全部生成完一次性显示。

### 什么场景用哪个

| 干什么 | 选谁 | 为什么 |
| --- | --- | --- |
| 日常对话、翻译、改错别字 | DeepSeek chat | 便宜、快 |
| 啃长文——论文、书、长报告 | Kimi | 128K 长上下文更稳 |
| 想让 AI 多想一会儿 | DeepSeek reasoner | 专门做推理的 |
| 看图说话 | Kimi vision | 支持图片输入（需另行添加，Model Name 填 moonshot-v1-auto） |

这些模型可以同时挂在 Copilot 里，在聊天面板顶部的下拉菜单随时切换。

### 第四步：用 Git 给笔记上一道保险

![](https://pic1.zhimg.com/v2-2c4c6ecced88068c6207161d78bc6924_1440w.jpg)

Git 版本控制工作流

AI 能力到手了。接下来处理另外两个痛点—— **版本回退和多设备同步** 。

### 装 Git

- • **macOS** ：终端敲 `git --version` ，没装的话系统会弹窗让你装 Xcode Command Line Tools，跟着走就行
- • **Windows** ：去 [git-scm.com](https://link.zhihu.com/?target=http%3A//git-scm.com) 下载安装包，一路 Next
- • **Linux** ： `sudo apt install git` 或 `sudo dnf install git`

装完在终端跑一下 `git --version` ，看到版本号就对了。

如果是第一次用 Git，还需要告诉它你是谁（提交记录会用到）：

```
git config --global user.name "你的名字"
git config --global user.email "你的邮箱@example.com"
```

### 配 SSH 钥匙

SSH 密钥是你跟 GitHub 之间的通行证，配一次以后就不用每次输密码。

```
ssh-keygen -t ed25519 -C "你的邮箱@example.com"
```

一路回车。然后把公钥复制出来：

- • macOS： `pbcopy < ~/.ssh/id_ed25519.pub`
- • Windows： `clip < ~/.ssh/id_ed25519.pub`
- • Linux： `cat ~/.ssh/id_ed25519.pub` → 手动复制

登 GitHub → 头像 → Settings → SSH and GPG keys → New SSH key → 粘贴 → 保存。

**验证一下连接是否成功** ：

```
ssh -T git@github.com
```

看到 `Hi 你的用户名! You've successfully authenticated` 就对了。如果报 `Permission denied` ，检查一下 SSH 密钥是否正确添加到了 GitHub。

### 建一个私有仓库

GitHub 右上角 **+** → **New repository** ：

- • 名字随便起，比如 `my-obsidian-vault`
- • **选 Private** ——笔记是私密的
- • 不要勾 "Add a README file"
- • Create

### 把本地笔记库推上去

终端进入你的 Obsidian Vault 目录（不知道路径？打开 Obsidian → 左下角齿轮 → 关于 → 就能看到 Vault 的路径）：

```
cd /你的/Obsidian/Vault/路径
git init
git remote add origin git@github.com:你的用户名/my-obsidian-vault.git
```

先配个 `.gitignore` （在 Vault 根目录创建这个文件）：

```
# 工作区布局——每台电脑不同，不用同步
.obsidian/workspace.json
.obsidian/workspace-mobile.json

# 系统垃圾
.DS_Store
Thumbs.db

# Obsidian 回收站
.trash/

# Copilot 索引缓存——体积大，每台电脑本地重建
.copilot-index/

# Copilot 插件配置——含 API Key，不要同步
.obsidian/plugins/obsidian-copilot/data.json
```

然后第一次提交：

```
git add .
git commit -m "初始提交：导入笔记库"
git branch -M main
git push -u origin main
```

> `.obsidian/` 文件夹里的插件配置、主题设置、快捷键配置——这些是值得同步的。换台电脑 clone 下来，插件和设置都在。只要排除掉 `workspace.json` （窗口布局，每台电脑不一样）就好。

### 装 Obsidian Git 插件——让同步全自动

手动 `git add` 、 `git commit` 、 `git push` 当然可以，但谁想天天手敲命令？

1. 1\. Obsidian 插件市场搜 **Git** ，装那个作者是 Vinzent03 的
2. 2\. 启用后进设置，推荐配置：

| 设置项 | 推荐值 | 说明 |
| --- | --- | --- |
| Auto commit-and-sync interval | 15 | 每 15 分钟自动同步 |
| Auto commit-and-sync after stopping file edits | 开 | 停笔后自动存档 |
| Commit message template | 见下方说明 | 提交信息带时间戳 |
| Pull on startup | 开 | 每次打开先拉取远程更新 |
| Push on commit-and-sync | 开 | 提交后自动推到 GitHub |

> **Commit message template 怎么填？** 粘贴这段： `{{date:YYYY-MM-DD HH:mm}} 自动备份` （注意是两层花括号）。

搞定。你的笔记从此有了自动档——每 15 分钟一次快照，每次修改都有据可查，两台电脑通过 GitHub 自动保持同步。

### 用起来！5 个你今天就能试的场景

![](https://pic4.zhimg.com/v2-d84156af3fec5c6ae9a33be4338ccf87_1440w.jpg)

五个实用场景演示

装好了不等于会用。下面是 5 个拿来就能跑的场景。

### 场景 1：让 AI 帮你整理会议笔记

刚开完会，在 Obsidian 里记了一堆零散要点。想让 AI 帮你整理成像样的会议纪要。

打开那条会议笔记，在 Copilot 聊天框输入：

```
帮我把 {activeNote} 整理成结构化的会议纪要，包含：讨论要点、决议事项、待办清单
```

`{activeNote}` 是 Copilot 的内置变量，指"你当前打开的那篇笔记"。AI 会读取整篇内容，吐出一份结构清晰的纪要。

### 场景 2：对着笔记库提问——Vault QA

你记得之前在某条笔记里写过关于"用教别人的方式来深化学习"的内容，但忘了在哪儿。搜"费曼"搜不到，因为当时根本没写这两个字。

这就是 Vault QA 的用武之地。它用 Embedding（向量化）把你的笔记"翻译"成数字，然后用语义匹配而不是关键词匹配来搜索。

**配置 Embedding 模型** ：进入 Copilot Settings → **QA 标签页** → 设置 Embedding Model。有几个选择：

- • **完全免费（推荐）** ：安装 LM Studio，下载一个本地 Embedding 模型（推荐 `snowflake-arctic-embed-l-v2.0` ），在 LM Studio 里启动服务并开启 CORS，然后在 Copilot 中添加为自定义 Embedding 模型，Base URL 填 `http://localhost:1234/v1` 。数据不出本机，隐私最好
- • **花小钱省事** ：在 API Keys 里填上 OpenAI 的 Key，然后选 `text-embedding-3-small` （费用极低，约 0.02 美元/百万 token）。不想折腾本地模型的话，这是最省心的选择

配置好 Embedding 模型后：

1. 1\. 聊天面板顶部，切到 **Vault QA** 模式
2. 2\. 第一次用会自动索引你的笔记库，可能花几分钟
3. 3\. 直接问： `我之前写过关于"通过教学来加深理解"的学习方法，在哪条笔记里？`

Copilot 会翻遍你的笔记库，找到语义上最相关的条目，把相关内容摘出来回答你，还标注了来源笔记。不是瞎猜，是有据可查。

### 场景 3：自定义 Prompt 批量干活

你想给所有读书笔记加一个"三句话总结"。手动写？一百篇笔记写到手软。

1. 1\. `Ctrl/Cmd + P` → 输入 `Copilot: Add custom prompt`
2. 2\. 取名 `三句话总结` ，内容写：
```
阅读下面的笔记，用三句话概括核心观点，要求简洁、准确、不废话：

{activeNote}
```
1. 3\. 以后打开任意一篇笔记，在聊天框打 `/` ，选 `三句话总结` ，AI 立刻给你干活

想批量处理某个文件夹下的笔记？试试 `{FolderPath}` 变量。想处理带特定标签的？用 `{#读书笔记, #待整理}` 。

再举个例子——创建一个 `翻译中英` 的 Prompt：

```
将以下内容翻译成英文，保持原文的语气和格式，专有名词不翻译：

{}
```

这里 `{}` 代表你选中的文本。选中一段中文，右键选 `翻译中英` （或在聊天框用 `/` 调用），AI 立刻翻译。

而且——这些自定义 Prompt 本身也是 Vault 里的 Markdown 文件，也被 Git 管理。你的 AI 工作流本身也有版本控制。

### 场景 4：用 Git 找回误删的内容

昨晚手快删了一段，今天才意识到那段挺重要。

1. 1\. `Ctrl/Cmd + P` → `Git: Open source control view`
2. 2\. 找到那篇被改过的文件
3. 3\. 看差异视图——绿底是新增的，红底是删掉的
4. 4\. 从历史版本里把被删的段落复制回来

或者用 `Git: View file history` ，直接浏览某个文件的所有历史版本。

Git 每次提交都保留了完整快照。你配了 15 分钟自动提交，那最多只会丢 15 分钟的内容——比起"改了就再也找不回来"，好太多了。

### 场景 5：换电脑，无缝接上

新电脑到手，或者想在公司电脑上也用。

1. 1\. 装 Git、配好 SSH 密钥（跟前面一样的步骤）
2. 2\. 终端一行命令：  
	git clone git@github.com:你的用户名/my-obsidian-vault.git
3. 3\. Obsidian 打开这个文件夹
4. 4\. 插件配置已经跟着 `.obsidian/` 文件夹同步过来了——Git 插件直接能用
5. 5\. Copilot 的 API Key 需要重新填一下（密钥不要放在 Git 里）

两台电脑从此自动同步。打开 Obsidian 自动 Pull，编辑后自动 Push。

### 几个避坑提醒

![](https://pic1.zhimg.com/v2-9077df70a44674bd6210311bf555edd6_1440w.jpg)

常见问题与避坑指南

**一、.gitignore 怎么写才对？** 核心原则：笔记内容和插件配置要同步，工作区布局和缓存不要同步。前面给的那份 `.gitignore` 已经覆盖了常见场景（工作区文件、系统垃圾、Copilot 缓存和 API Key 配置）。如果你后续装了新插件产生了大体积缓存，记得也加进去。

**二、Prompt 命名别踩坑。** 自定义 Prompt 的名字里不要出现"空格-横杠-空格"这种组合（比如 `我的提示 - 测试` ），Copilot 可能识别不了。用中文直连就好： `会议纪要整理` 、 `三句话总结` 、 `翻译中英` 。

**三、多设备同步冲突怎么办？** 两台电脑同时改同一个文件，Git 会报冲突。最简单的预防办法是开启 Pull on Startup——每次打开 Obsidian 先拉最新版。万一真冲突了，文件里会出现 `<<<<<<<` 和 `>>>>>>>` 标记，手动选一个版本保留就行。养成习惯： **同一时间只在一台设备上编辑** ，编辑完等 15 分钟同步完再换设备。

**四、让 AI 始终用中文回复。** 进入 Copilot Settings → **Advanced Settings** ，找到 System Prompt 设置，加上一句"始终使用简体中文回复"。这样不管你问什么，AI 都不会突然蹦出一段英文。

**五、移动端怎么办？** Obsidian Git 插件在移动端（iOS/Android）的支持有限。如果你需要在手机上查看和编辑笔记，可以考虑两个方案：① 用 Obsidian Sync 作为移动端补充（可以只买一个月试试）；② 在 iOS 上用 Working Copy 这个 Git 客户端配合 Obsidian 使用。PC 端继续用 Git 免费同步，移动端按需选择。

**六、GitHub 访问不稳定？** 国内网络环境下， `git push` / `git pull` 偶尔会超时。几个缓解办法：① 本文已采用 SSH 连接，通常比 HTTPS 更稳；② 给终端配代理（搜索"终端走代理"有大量教程）；③ 如果实在不行，可以把仓库建在 Gitee 上，操作流程基本一致。

**七、笔记库有大量图片/附件？** Git 不擅长管理二进制大文件，图片多了仓库会快速膨胀。建议：① 在 Obsidian 设置中把附件统一放到一个文件夹（如 `attachments/` ），按需决定是否纳入 Git；② 图片特别多的话，考虑用 [Git LFS](https://zhida.zhihu.com/search?content_id=270290342&content_type=Article&match_order=1&q=Git+LFS&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3NzY4MzMzNDEsInEiOiJHaXQgTEZTIiwiemhpZGFfc291cmNlIjoiZW50aXR5IiwiY29udGVudF9pZCI6MjcwMjkwMzQyLCJjb250ZW50X3R5cGUiOiJBcnRpY2xlIiwibWF0Y2hfb3JkZXIiOjEsInpkX3Rva2VuIjpudWxsfQ.PA65GIMafxD4eV9UGQ54IfLrz7rSvMSlSteiEp2C53s&zhida_source=entity) 管理大文件；③ GitHub 免费私有仓库建议控制在 1GB 以内，纯文本笔记完全够用。

**八、隐私：你的笔记会经过第三方服务器。** 通过 API 调用 DeepSeek / Kimi 时，你发送的笔记内容会传到他们的服务器处理。大多数 API 服务承诺不会用用户数据训练模型（具体看各家隐私条款），但如果你的笔记涉及高度敏感信息（法律文书、医疗记录等），可以考虑纯离线方案：用 Ollama 在本地跑开源模型，Copilot 同样支持接入——AI 能力完全不出本机，只是需要一张还行的显卡。

### 算一笔账

![](https://pic1.zhimg.com/v2-90fe1f01fe4d6515dae09b9737b8c970_1440w.jpg)

费用对比分析

### 这套方案的年费

假设你每天跟 AI 聊 10 轮（已经不少了）：

| 项目 | 年消耗 | DeepSeek 费用 | Kimi（kimi-latest）费用 |
| --- | --- | --- | --- |
| 输入 token | ~183 万 | 0.37~3.65 元 | 1.83 元 |
| 输出 token | ~365 万 | 10.95 元 | 3.65 元 |
| 合计 | ~548 万 | 约 11~15 元/年 | 约 5.5 元/年 |

DeepSeek 的输入价取决于缓存命中率——经常聊类似话题的人，缓存命中率高，费用更低。Kimi 的 `kimi-latest` 不区分输入输出，统一 1 元/百万 token，算下来更便宜。

> **注** ：以上价格基于撰文时的官方定价，实际费用可能随平台调价而变化。建议以 DeepSeek 定价页 和 Kimi 定价页 的最新公示为准。

### 跟主流方案对比一下

| 方案 | 年费 | AI 能力 | 版本管理 | 数据归属 |
| --- | --- | --- | --- | --- |
| 本文方案 | 5~15 元 | 模型随你选，想换就换 | Git 完整历史 | 本地文件，你说了算 |
| ChatGPT Plus + Obsidian Sync | ~2000 元 | GPT-4o | 无 | 笔记本地，对话在 OpenAI |
| Notion AI | ~1200 元 | Notion 内置 | Notion 自带 | 全在 Notion 服务器上 |
| 语雀 AI | ~200 元 | 语雀内置 | 语雀自带 | 全在语雀服务器上 |

> 注：ChatGPT Plus 包含的功能远不止 API 调用（还有 DALL-E 绘图、代码解释器等），此处仅对比"AI 辅助笔记管理"这一场景的花费。

便宜了十几倍到上百倍。而且数据完全在你手里——笔记是本地 Markdown 文件，AI 的 Key 在你自己的账户里，同步走你自己的 GitHub。

当然得说清楚代价：初始配置要半小时左右，需要会一点终端操作，移动端的 Git 同步不如官方 Sync 顺滑。如果你追求完全零配置、拿来就用，Obsidian Sync 仍然是更省心的选择。

但如果你愿意花半小时折腾一下，换来的是—— **数据自主、模型自选、版本可追溯、同步不花钱** 。这笔账，怎么算都不亏。

### 小结

四个组件，三个问题，一次性解决：

| 问题 | 解法 | 年费 |
| --- | --- | --- |
| AI 和笔记分家 | Copilot 插件 + DeepSeek/Kimi API | 5~15 元 |
| 改了找不回来 | Git 版本管理 | 0 元 |
| 同步要花钱 | GitHub 免费仓库 | 0 元 |

年费：一杯奶茶。

打开你的 Obsidian，动手吧。

---

**下一步探索** ：

- • 试试 Copilot Plus 的 Projects Mode 和 Composer 功能（付费，按需考虑）
- • 创建更多自定义 Prompt——把你的日常文字工作自动化
- • 探索 Obsidian 的其他 AI 插件，比如 Smart Connections、Text Generator

发布于 2026-02-12 17:42・福建・包含 AI 辅助创作 作者对内容负责[Obsidian](https://www.zhihu.com/topic/21349840)[Git](https://www.zhihu.com/topic/19557710)[写作](https://www.zhihu.com/topic/19552516)