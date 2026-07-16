# GitHub 中文主页实施计划

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 将 Cabbos 的 GitHub Profile README 重写为面向 AI Agent / LLM 全栈岗位的中文主页，并发布到 GitHub。

**Architecture:** 保持单文件 Markdown 主页，不引入动态图片或生成脚本。内容以身份定位、两个公开代表项目、能力范围、工程背景、AI 辅助研发方式和联系方式为主线，所有核心项目都指向公开证据。

**Tech Stack:** GitHub Flavored Markdown、Git、GitHub CLI、curl

---

## 文件结构

- Modify: `README.md` — GitHub Profile 的全部公开内容。
- Reference: `docs/superpowers/specs/2026-07-16-github-profile-readme-cn-design.md` — 已批准的内容边界与验收标准。

### Task 1: 重写中文 Profile README

**Files:**
- Modify: `README.md`

- [ ] **Step 1: 用已批准的中文内容替换 README**

```markdown
# 你好，我是张博 👋

**AI Agent / LLM 应用 / 全栈产品工程师**

5 年软件工程经验，长期参与蚂蚁生态企业级平台、低代码与数据产品建设。
目前专注于 AI Agent Runtime、本地大模型应用和端到端产品交付，能够覆盖前端、后端、桌面端、模型接入、部署上线与工程验收。

我熟练使用 Codex、Claude Code 等 AI 辅助工具提升研发效率；产品方向、架构拆解、关键决策与最终验收由我负责。

## 代表项目

### [Forge — 本地优先 AI Agent Workbench](https://github.com/Cabbos/forge)

面向真实软件项目构建的桌面端 Agent 工作台，不是对现有 CLI 或 SDK 的简单封装。

- 主导产品方向与 Runtime 架构，完成 Tauri 2 / Rust + React / TypeScript + Python / FastAPI 的端到端交付。
- 自研 Agent Loop、上下文压缩、文件与 Shell 工具、权限确认、运行时 Journal / Replay 和多模型 Provider 适配。
- 构建结构化运行证据、30+ 维度 Eval 和 78 项可执行验收门禁，让 Agent 运行结果可审计、可恢复、可回归。
- 通过前后端事件协议、契约测试和发布置信度报告，覆盖从产品界面到 Runtime、评测与发布的完整工程链路。

`Tauri 2` · `Rust` · `React` · `TypeScript` · `Python` · `FastAPI`

[查看源码](https://github.com/Cabbos/forge) · [产品预览](https://forge-five-mu.vercel.app)

### [vLLM Agent Gateway — 本地模型多协议网关](https://github.com/Cabbos/vllm-agent-gateway)

为本地 vLLM 构建统一接入层，让不同 Agent 客户端共享同一个本地模型服务。

- 兼容 OpenAI Chat / Responses、Anthropic Messages、Ollama、Gemini 与 Azure OpenAI 风格接口。
- 统一流式响应、工具调用、思考参数、模型别名和 PDF 输入，支持 Codex、Claude Code 等客户端接入。
- 完成 Windows / WSL2 + RTX 5090 环境下的 vLLM、Docker Compose、鉴权、健康检查与监控链路部署。
- 针对双并发场景进行 CUDA Graph A/B 优化，聚合吞吐从 `38.94 tok/s` 提升至 `300.75 tok/s`，约 `7.72×`。

`Python` · `FastAPI` · `vLLM` · `Docker` · `Linux / WSL2` · `CUDA`

[查看源码](https://github.com/Cabbos/vllm-agent-gateway)

## 能力范围

| 方向 | 能力 |
| --- | --- |
| AI Agent 工程 | Agent Runtime、Tool Calling、权限与确认、上下文管理、Memory、Trace / Replay、Eval、MCP、Skill、Hook |
| 全栈产品开发 | React、TypeScript、复杂工作台、Schema 驱动 UI、BFF、Python / FastAPI、Rust / Tauri、SQLite |
| 模型与服务部署 | vLLM、本地模型接入、多协议网关、Docker Compose、Linux / WSL2、GPU 推理、服务鉴权、监控与性能调优 |
| 工程交付 | 产品方案、架构设计、任务拆解、AI 辅助研发、测试门禁、发布验收、部署上线与问题定位 |

## 工程背景

在转向 AI Agent 产品之前，我长期参与蚂蚁生态企业级项目建设，积累了复杂前端系统、低代码平台、Schema 驱动渲染、BFF 编排、数据分析产品与工程化实践。

这段经历也影响了我对 Agent 产品的判断：不仅关注模型能否生成结果，更关注权限边界、运行状态、异常恢复、证据链路和真实业务流程中的可交付性。

## 当前方向

关注 **AI Agent 工程师、LLM 全栈工程师、AI 产品工程师和偏 AI 的全栈岗位**，尤其希望参与能够快速决策、持续交付真实产品的中小团队或初创公司。

## 联系我

- GitHub：[Cabbos](https://github.com/Cabbos)
- Email：[cabbos@163.com](mailto:cabbos@163.com)
```

- [ ] **Step 2: 检查 Markdown 基础格式**

Run:

```bash
git diff --check -- README.md
```

Expected: 命令退出码为 0，没有空白错误输出。

### Task 2: 验证内容与公开链接

**Files:**
- Test: `README.md`

- [ ] **Step 1: 验证必须删除的旧内容不存在**

Run:

```bash
if rg -n 'TikTok|RAG|code-cli|cabbos_pycode|Job Intel|Hot2Pub|Campaign Workspace' README.md; then exit 1; fi
```

Expected: 命令退出码为 0，没有匹配输出。

- [ ] **Step 2: 验证核心定位和项目内容存在**

Run:

```bash
rg -n 'AI Agent / LLM 应用 / 全栈产品工程师|蚂蚁生态|Forge|vLLM Agent Gateway|Codex、Claude Code|部署上线|7\.72×' README.md
```

Expected: 七类核心内容均有匹配结果。

- [ ] **Step 3: 验证公开仓库可访问**

Run:

```bash
gh repo view Cabbos/forge --json visibility,url >/dev/null
gh repo view Cabbos/vllm-agent-gateway --json visibility,url >/dev/null
curl -fsSL -o /dev/null https://forge-five-mu.vercel.app
```

Expected: 三条命令均退出码为 0。

- [ ] **Step 4: 检查最终差异**

Run:

```bash
git diff -- README.md
git status --short
```

Expected: README 仅包含已批准的中文主页改动；工作区没有无关文件变更。

### Task 3: 提交并发布主页

**Files:**
- Modify: `README.md`

- [ ] **Step 1: 提交中文主页**

Run:

```bash
git add README.md docs/superpowers/plans/2026-07-16-github-profile-readme-cn.md
git diff --cached --check
git commit -m "docs: publish Chinese GitHub profile"
```

Expected: 创建一个只包含 README 和实施计划的提交。

- [ ] **Step 2: 推送到 GitHub Profile 仓库**

Run:

```bash
git push origin main
```

Expected: `main` 成功推送到 `origin`。

- [ ] **Step 3: 验证线上 README**

Run:

```bash
gh api repos/Cabbos/Cabbos/readme --jq '.content' | base64 --decode | rg -n '你好，我是张博|Forge|vLLM Agent Gateway|蚂蚁生态|Codex、Claude Code'
```

Expected: 线上 README 同时匹配姓名、两个代表项目、蚂蚁生态经历和 AI 辅助研发说明。
