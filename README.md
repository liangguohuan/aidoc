# 🤖 当前接触过的AI 开发工具生态全景文档

> 梳理如下分类文档，便于快速选型与参考。

---

## 1️⃣ IDE / 代码编辑器（AI Native）

| 工具 | 核心特点 | 适用场景 | 定价 | 链接 |
|------|----------|----------|------|------|
| **Cursor** | AI结对编程，多模型支持，上下文管理中等 | 个人开发/小团队，追求人机协作流畅度 | [cursor.com](https://cursor.com) |
| **Windsurf** | Cascade深度代码理解，跨会话记忆，图生代码 | 大型代码库/企业团队，需持久上下文 | [codeium.com/windsurf](https://codeium.com/windsurf) |
| **Google Antigravity** | 多智能体协同，编辑器+终端+浏览器三端控制，UI测试 | 全栈开发/前端团队，Agent优先工作流 | [antigravity.google](https://antigravity.google) |
| **AWS Kiro** | 规范驱动开发（EARS语法），结构化任务拆解 | 需求明确/合规要求高的企业项目 | [kiro.dev](https://kiro.dev) |
| **Zed** | Rust编写，高性能，支持多模型集成 | 追求极致性能/轻量级编辑器用户 | [zed.dev](https://zed.dev) |
| **Qoder** | 阿里出品，Agentic编码平台，Repo Wiki深度代码理解 | 中文开发者/阿里生态用户，真实软件项目开发 | [qoder.com](https://qoder.com) |

> 📌 **选型建议**：
> - 追求"人机结对"体验 → **Cursor**
> - 大型项目/团队协作 → **Windsurf**
> - 全栈+UI测试+多智能体 → **Antigravity**
> - 规范驱动/文档先行 → **Kiro**
> - 高性能/开源偏好 → **Zed**
> - 中文优化/阿里生态 → **Qoder**

---

## 2️⃣ VSCode AI 插件

| 插件 | 功能亮点 | 支持模型 | 安装方式 |
|------|----------|----------|----------|
| **Cline** | 文件级操作、执行命令、多步计划、读写本地项目 | Claude/Gemini/OpenAI/本地模型 | VSCode扩展市场搜索 `Cline` |
| **RooCode** | Cline分叉升级版，支持DeepSeek/Qwen等国产模型，Agents自动编程 | 多模型+本地部署 | 扩展市场搜索 `Roo Code` 或 GitHub安装 |
| **GitHub Copilot** | 代码补全/聊天/测试生成，生态成熟 | GPT-5.4/Claude | 扩展市场或 [copilot.github.com](https://copilot.github.com) |

> 💡 **Cline/RooCode 配置要点**：
> 1. 安装插件后进入设置 → 配置 API Key（支持多提供商）
> 2. 推荐搭配本地模型（如 Ollama）实现隐私保护
> 3. RooCode 支持 `/init` 初始化项目上下文，提升代码理解准确率

---

## 3️⃣ 账号管理工具

> 解决多平台账号切换、配额监控、故障规避痛点

| 工具 | 核心能力 | 支持平台 项目地址 |
|------|----------|----------|----------|----------|
| **Antigravity-Manager** | ✅ 多账号统一管理/一键切换/配额监控/自动故障规避 ✅ 协议反代（OpenAI/Claude/Gemini）✅ 接入 Claude Code CLI | OpenAI / Claude / Gemini / 智谱等 | [lbjlaq/Antigravity-Manager](https://github.com/lbjlaq/Antigravity-Manager) |
| **cc-switch** | The All-in-One Manager for Claude Code, Codex, Gemini CLI, OpenCode & OpenClaw | Claude / Codex / Gemini | [farion1231/cc-switch](https://github.com/farion1231/cc-switch) |

> 🔧 **Antigravity-Manager 快速接入 Claude Code CLI**：
> ```bash
> # 1. 启动反代服务（默认端口 8045）
> # 2. 设置环境变量
> export ANTHROPIC_API_KEY="sk-antigravity"
> export ANTHROPIC_BASE_URL="http://127.0.0.1:8045"
> # 3. 启动 Claude Code
> claude
> ```
> 即可实现账号池调度 + 请求代理 + 日志统计一体化

---

## 4️⃣ CLI / 命令行工具

| 工具 | 描述 | 核心命令 | 适用场景 |
|------|------|----------|----------|
| **Claude Code** | Anthropic 官方 CLI，终端内结对编程 | `/model` 切换模型, `/init` 初始化, `/undo` 撤销 | 快速代码生成/调试/解释 |
| **Codex CLI** | OpenAI Codex 命令行版，开源可定制 | `/model`, `/approvals`, `/new` | 终端集成 + 自定义工作流 |
| **Gemini CLI** | Google Gemini 终端接口，支持多轮对话 | `gemini "query"` | 快速问答/脚本辅助 |
| **Qwen CLI** | 通义千问命令行工具，支持中文优化 | `qwen --model qwen-max "问题"` | 中文场景/阿里生态 |
| **OpenCode** | 🔥 开源 AI 编码代理，终端优先 + 多模型 + 隐私安全 | `opencode`, `/init`, `/undo`, `/share` | 开源爱好者/本地部署/多模型切换[[52]] |

> 🌟 **OpenCode 亮点**：
> - 100% 开源，不绑定任何模型提供商
> - 支持终端/桌面/IDE 三种使用形态
> - 内置 `/undo` 撤销修改、`/share` 分享对话等实用命令
> - 可通过 `opencode.ai/auth` 获取统一 API 密钥（OpenCode Zen）

---

## 5️⃣ 大模型平台 / Agent 框架

| 平台 | 定位 | 核心能力 | 开源/商业 |
|------|------|----------|-----------|
| **Hermes Agent** | 自进化 AI 助手，持久记忆+技能沉淀 | 跨会话记忆、技能系统、多消息平台接入（Telegram/Discord等） | ✅ 开源 (MIT) |
| **OpenClaw** | "数字员工"型助手，直接操作设备执行任务 | 文件管理/邮件处理/自动化脚本，支持 Linux/macOS/Windows | ✅ 开源 |
| **OpenCloud** | 云原生 AI 应用部署平台 | 一键部署 Dify/Coze 等，支持混合云架构 | 商业+开源组件 |
| **ModelScope (魔搭)** | 阿里大模型开放平台 | 千问系列模型、一键部署、微调工具链 | 免费+付费 |

> ⚖️ **Hermes vs OpenClaw 对比**：
> | 维度 | Hermes Agent | OpenClaw |
> |------|-------------|----------|
> | 核心定位 | 会成长的私人 AI 打工人 | 能执行任务的数字员工 |
> | 记忆机制 | 跨会话持久化+用户模型深化 | 任务级上下文 |
> | 执行能力 | 消息平台交互为主 | 直接操作文件系统/命令行 |
> | 适合场景 | 客服/助理/知识管理 | 自动化运维/批量处理 |

---

## 6️⃣ 客户端应用（本地大模型交互）

| 客户端 | 特点 | 支持模型 | 平台 |
|--------|------|----------|------|
| **Chatbox** | 开源可视化终端，支持本地模型+云API，隐私友好 | Ollama/LocalAI/OpenAI/Claude 等 | Win/macOS/Linux |
| **Cherry Studio** | 多模型集成+一问多答+知识库+内置300+助手，交互体验优 | 300+ 模型（OpenAI/Claude/Gemini/DeepSeek等） | Win/macOS/Linux |
| **Chatbox AI + Ollama** | 本地部署组合方案，零成本运行私有模型 | Llama3/Qwen/DeepSeek 等开源模型 | 全平台 |

> 💡 **本地部署推荐组合**：
> ```
> Ollama（模型服务） + Chatbox/Cherry Studio（前端） + 本地量化模型（如 Qwen2.5-7B-Instruct-Q4_K_M）
> ```
> 可实现完全离线、隐私安全的 AI 对话体验

---

## 7️⃣ 工作流 / 低代码平台

| 平台 | 定位 | 核心优势 | 适合人群 |
|------|------|----------|----------|
| **Coze**（字节） | 零代码 Bot 搭建，插件生态丰富 | 意图识别/多轮对话/一键发布到飞书/微信 | 产品经理/运营/非技术用户 |
| **Dify** | LLMOps + BaaS，支持混合云+微调 | API 工具链完整、企业级集成、支持本地模型 | 开发者/技术团队/企业中台 |
| **FastGPT** | 知识问答类 Agent 专精，Flow 可视化编排 | 深度定制能力强、支持复杂逻辑分支 | 知识管理/客服场景/企业定制 |

> 📊 **平台选型速查**：
> ```
> 快速上线 Bot → Coze
> 企业级 AI 中台 → Dify  
> 深度知识问答 → FastGPT
> 需要本地部署 → Dify > FastGPT > Coze
> ```
>[[17]]

---

## 8️⃣ 综合选型对比表

### 🔹 按使用角色推荐

| 角色 | 首选组合 | 备选方案 |
|------|----------|----------|
| **个人开发者** | Cursor + Cline + Chatbox | Zed + RooCode + Ollama |
| **小团队（<10人）** | Windsurf + Antigravity-Manager + Dify | Cursor + Coze + Cherry Studio |
| **企业技术团队** | Kiro/Antigravity + Dify + Hermes Agent | Qoder + FastGPT + 自建模型服务 |
| **非技术用户** | Coze + Cherry Studio | Dify 应用模板 + Chatbox |

### 🔹 按核心需求推荐

| 需求 | 推荐工具 | 关键理由 |
|------|----------|----------|
| 🎯 代码生成质量 | Cursor / Qoder | 上下文理解深，支持多文件修改 |
| 🔐 数据隐私 | OpenCode + Ollama + Chatbox | 全链路本地部署，无数据外传 |
| 🔄 多账号管理 | Antigravity-Manager | 统一调度+反代+健康监控一体化 |
| 🤖 Agent 自动化 | Hermes Agent / RooCode | 支持持久记忆+任务规划+工具调用 |
| 📚 知识库问答 | FastGPT + Cherry Studio | 向量检索+可视化编排+多模型对比 |
| 💰 成本控制 | Zed + OpenCode + 本地模型 | 开源免费+按需调用+无订阅压力 |

---

### Harness 软件工程 (DevOps)
企业级 CI/CD 流程、软件规模化交付，从传统的“自动化部署工具”进化为了 AI 原生软件交付平台，不仅是帮你“发版”的工具，还确保 AI 辅助开发不失控、不乱套的自动化治理框架。

---

## 🔗 资源链接汇总

### 📦 官方下载
- Cursor: https://cursor.com
- Windsurf: https://codeium.com/windsurf
- Antigravity: https://antigravity.google/
- Qoder: https://qoder.com
- Zed: https://zed.dev

### 🔧 开源项目
- Cline: https://github.com/cline/cline
- RooCode: https://github.com/RooCodeInc/Roo-Code
- OpenCode: https://github.com/anomalyco/opencode
- Antigravity-Manager: https://github.com/lbjlaq/Antigravity-Manager
- Cherry Studio: https://github.com/CherryHQ/cherry-studio
- Hermes Agent: https://github.com/NousResearch/Hermes-Agent

### 📚 学习资源
- OpenCode 中文文档: https://opencode.ai/docs/zh-cn/
- Qoder 文档: https://docs.qoder.com/zh
- Cherry Studio 指南: https://www.cherry-ai.com/docs
- Claude Code 中文站: https://claude-zh.cn/guide/codex

### 💬 社区交流
- Linux Do AI 板块: https://linux.do
- V2EX AI 讨论: https://v2ex.com/go/ai
- 阿里云开发者社区: https://developer.aliyun.com
- 智源社区: https://hub.baai.ac.cn/
