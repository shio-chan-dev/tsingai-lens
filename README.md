### ✅ `README.md`

```markdown
# TsingAI-Lens: 清华科研文献智能助手

**TsingAI-Lens** 是一个为清华场景定制的私有部署科研助手，基于 [MaxKB](https://github.com/RealityArchitect/MaxKB) 构建，面向科研人员提供一站式文献处理、语义问答、关键词抽取、知识图谱与思维导图自动生成的 AI 系统。

## 📌 项目目标

构建一个本地可部署、支持私有化文献管理的智能助手系统，具备以下能力：

- 支持多种文献格式（PDF、Word、TXT、Markdown 等）
- 从文献中自动提取摘要、关键词
- 对文献进行语义向量化和本地检索
- 支持自然语言问答
- 自动构建实体级知识图谱与思维导图
- 自动识别并归纳无量纲公式结构
- 可扩展对接到前端可视化或笔记系统（如 Obsidian、Logseq）

## 🧠 核心功能

| 模块 | 功能描述 |
|------|----------|
| 📄 文献导入 | 支持批量导入 PDF/DOCX/TXT/MD，自动分段切片 |
| 🏷️ 关键词提取 | 基于 KeyBERT/YAKE 的关键词抽取，支持领域词典增强 |
| 📚 本地知识库 | 使用 FAISS/Chroma 构建文献语义向量数据库 |
| 🔍 智能检索与问答 | 基于 RAG（检索增强生成）模型提供问答能力 |
| 🧠 知识图谱生成 | 使用实体识别与关系抽取构建图谱结构，支持可视化 |
| 🧭 思维导图输出 | 将图谱转换为主题导图视图，便于理解与展示 |
| 📐 无量纲公式归纳 | 自动抽取文中数理公式并转化为维度无关表达式 |

## 🛠️ 技术栈

- 后端：Python, FastAPI, LangChain, FAISS, PyMuPDF, spaCy
- 前端：React（可选），mindmap.js, D3.js
- 部署：Docker, Docker Compose
- 模型支持：OpenAI API / 本地 LLM（如 Mistral, Qwen）

## 🗂️ 项目结构

```

tsingai-lens/
├── backend/
│   ├── ingest/         # 文档导入与切片处理
│   ├── extractor/      # 关键词、实体、公式抽取模块
│   ├── retriever/      # 向量化与本地语义检索
│   ├── qna/            # 基于文献问答模块
│   ├── graph/          # 知识图谱与思维导图生成
│   └── api/            # FastAPI 接口封装
├── frontend/           # 图谱、导图、仪表盘可视化
├── config/             # 配置文件与模型路径
├── deploy/             # Docker、Nginx、启动脚本等
├── docs/               # 用户文档与部署指南
├── tests/              # 单元测试目录
├── requirements.txt    # Python 依赖
├── docker-compose.yml  # 一键部署配置
└── README.md

````

## 🚀 快速部署（开发模式）

```bash
# 克隆仓库
git clone https://github.com/your-org/tsingai-lens.git
cd tsingai-lens

# 创建 Python 虚拟环境
python3 -m venv venv
source venv/bin/activate

# 安装依赖
pip install -r requirements.txt

# 启动服务
uvicorn backend.api.main:app --reload
````
