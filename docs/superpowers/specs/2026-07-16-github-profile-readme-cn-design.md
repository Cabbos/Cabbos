# GitHub 中文主页设计说明

## 目标

把 `Cabbos` 的 GitHub Profile README 改造成面向中小公司和初创团队的中文技术主页，让招聘方在较短时间内确认三件事：张博具备 AI Agent 产品主导能力、能完成全栈端到端交付、拥有本地大模型部署与性能优化实践。

## 定位

- 中文主标题：`你好，我是张博 👋`
- 职业定位：`AI Agent / LLM 应用 / 全栈产品工程师`
- 中文为主，保留必要的英文技术名词和仓库名称，不重复维护整段英文版本。
- 面向招聘转化，不堆叠装饰性徽章、访问量、连续提交统计或大幅动图。

## 信息结构

README 按以下顺序组织：

1. **个人定位**：用三句短文说明 5 年工程经验、蚂蚁生态企业级项目经历，以及当前的 AI Agent / 本地模型方向。
2. **代表项目**：只重点展示两个当前公开且可验证的仓库。
   - `Forge`：本地优先 AI Agent Workbench，自研 Agent Runtime，覆盖多模型接入、工具执行、权限控制、运行恢复、Eval 与发布门禁。
   - `vLLM Agent Gateway`：面向本地 vLLM 的多协议网关，覆盖 OpenAI、Anthropic、Ollama、Gemini 与 Azure 风格接口，并说明本地模型部署及吞吐优化实践。
3. **能力范围**：用紧凑表格说明 Agent 工程、全栈开发和部署上线三类能力。
4. **工程背景**：准确说明长期参与蚂蚁生态企业级平台、低代码、Schema 驱动 UI、BFF 与复杂前端工程的经验，不写成蚂蚁集团正式员工。
5. **AI 辅助研发**：说明熟练使用 Codex、Claude Code；产品方向、架构拆解、关键决策和验收由本人负责。
6. **求职与联系**：明确 AI Agent、LLM 全栈和偏 AI 的全栈岗位方向，保留 GitHub 与邮箱。

## 内容取舍

### 保留并强化

- Forge 与公开产品网站链接。
- vLLM Agent Gateway 及可核验的协议适配、部署和性能数据。
- React / TypeScript、Rust、Python / FastAPI、Tauri、Docker、Linux / WSL2 等与代表项目直接相关的技术。
- 产品方向、架构设计、工程拆解、部署上线和验收闭环能力。

### 删除

- 已放弃的 TikTok Shop Automation。
- 当前私有、失效或不适合作为公开证据的 `code-cli`、`cabbos_pycode`、Job Intel 等项目入口。
- 泛化的关键词堆叠、无证据的能力声明和冗长的项目功能列表。
- GitHub Stats、奖杯墙和装饰性 Badge。

## 表述边界

- 不把 AI 辅助生成的代码全部表述为本人逐行手写；强调本人对产品方向、架构、拆解、审查和验收负责。
- 不宣称 RAG 或向量数据库经验。
- 不写尚未完成的功能，也不在主页陈列产品限制或 TODO。
- 性能数字只采用已有部署记录：CUDA Graph A/B 中双并发聚合吞吐从 `38.94 tok/s` 提升到 `300.75 tok/s`，约 `7.72×`。
- 蚂蚁经历使用“长期参与蚂蚁生态企业级项目”表述，避免雇佣关系歧义。

## 验收标准

- README 以中文为主，首屏能看到姓名、岗位方向和核心能力。
- Forge 和 vLLM Agent Gateway 位于主页主要区域，链接指向公开仓库。
- 不出现 TikTok、RAG、`code-cli`、`cabbos_pycode`、Job Intel 或失效的公开链接。
- 至少出现一次蚂蚁生态经验、端到端交付、部署上线和 Codex / Claude Code 使用方式。
- Markdown 结构清晰，所有外部链接可解析，不依赖第三方动态统计图片。
