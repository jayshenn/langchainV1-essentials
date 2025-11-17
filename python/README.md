# 🔗 LangChain 基础教程 Python 版


## 🚀 设置

### 前置要求

- 确保使用 Python 3.11 - 3.13 版本
- [uv](https://docs.astral.sh/uv/) 包管理器或 [pip](https://pypi.org/project/pip/)
- OpenAI API 密钥
- Node.js 和 npx（第 3 课笔记本中的 MCP 服务器需要）：
```bash
# 安装 Node.js（包含 npx）
# 在 macOS 上使用 Homebrew：
brew install node

# 在 Ubuntu/Debian 上：
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs

# 验证安装：
node --version
npx --version
```

### 安装步骤

下载课程仓库

```bash
# 克隆仓库，进入 'python' 目录
git clone https://github.com/langchain-ai/lca-langchainV1-essentials.git
cd ./lca-langchainV1-essentials/python
```

复制 example.env 文件

```bash
# 创建 .env 文件
cp example.env .env
```

直接在 .env 文件中插入 API 密钥，OpenAI（必需）和 [LangSmith](#langsmith-入门)（可选）

```bash
# 添加 OpenAI API 密钥
OPENAI_API_KEY=你的_openai_api_密钥
# 本课程使用 OpenAI 模型编写，但你也可以选择其他模型。
# 确保添加相应密钥并修改代码以调用你偏好的模型
#ANTHROPIC_API_KEY=你的_anthropic_api_密钥_如果你偏好使用

# LangSmith 追踪的可选 API 密钥
LANGSMITH_API_KEY=你的_langsmith_api_密钥
LANGSMITH_TRACING=true
LANGSMITH_PROJECT=langgraph-py-essentials
# 如果你使用欧盟实例：
LANGSMITH_ENDPOINT=https://eu.api.smith.langchain.com

```

创建虚拟环境并安装依赖
```bash
# 创建虚拟环境并安装依赖
uv sync
```

运行笔记本

```bash
# 直接使用 uv 运行 Jupyter 笔记本
uv run jupyter lab

# 或者如果你偏好激活虚拟环境
source .venv/bin/activate  # Windows 上使用: .venv\Scripts\activate
jupyter lab
```

可选：设置 [LangSmith Studio](https://docs.langchain.com/oss/python/langchain/studio)

```bash
# 将上面创建的 .env 文件复制到 studio 目录
cp .env ./studio/.

# 运行
langgraph dev
```

### LangSmith 入门

- 创建一个 [LangSmith](https://smith.langchain.com/) 账户
- 创建一个 LangSmith API 密钥
<img width="600" alt="Screenshot 2025-10-16 at 8 28 03 AM" src="https://github.com/user-attachments/assets/e39b8364-c3e3-4c75-a287-d9d4685caad5" />
<img width="600" alt="Screenshot 2025-10-16 at 8 29 57 AM" src="https://github.com/user-attachments/assets/2e916b2d-e3b0-4c59-a178-c5818604b8fe" />

# 📚 课程

本仓库包含九个简短的笔记本，作为 LangChain 中最常用功能的简要介绍，从新的 **Create Agent** 开始。

---

### `L1_fast_agent.ipynb` - 🤖 创建智能体 🤖
- 在本笔记本中，你将使用 LangChain 的 `create_agent` 仅用几行代码构建一个 SQL 智能体。
- 它演示了构建强大智能体是多么快速和简单。你可以轻松地将此智能体应用到自己的项目中。
- 你还将使用 **LangSmith Studio**，这是一个方便的可视化调试器，用于运行、托管和探索智能体。

---

### `L2-7.ipynb` - 🧱 构建模块 🧱
在第 2-7 课中，你将学习如何使用 LangChain 中的一些基本构建模块。这些课程解释并补充了 `create_agent`，在创建自己的智能体时会很有用。每节课都简洁而专注。

- **L2_messages.ipynb**：学习消息如何在智能体组件之间传递信息。
- **L3_streaming.ipynb**：学习如何使用流式传输减少用户感知延迟。
- **L4_tools.ipynb**：学习基本工具使用，通过自定义或预构建工具增强你的模型。
- **L5_tools_with_mcp.ipynb**：学习使用 LangChain MCP 适配器访问 MCP 工具世界。
- **L6_memory.ipynb**：学习如何赋予智能体在调用之间保持状态的能力。
- **L7_structuredOutput.ipynb**：学习如何从智能体产生结构化输出。

---

### `L8-9.ipynb` - 🪛 自定义你的智能体 🤖
第 2-7 课涵盖了开箱即用的功能。然而，`create_agent` 也支持通过 **中间件** 进行预构建和用户定义的自定义。本部分描述中间件，并包含两节课，重点介绍特定用例。

- **L8_dynamic.ipynb**：学习如何动态修改智能体的系统提示以响应变化的上下文。
- **L9_HITL.ipynb**：学习如何使用中断来启用人在环路（Human-in-the-Loop）交互。
