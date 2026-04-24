# Agent Client / Agent Workspace / AI Assistant Workspace

Cherry Studio 和 LobeHub / LobeChat 可以看作 Agent 平台的一个细分领域，但它们和 Dify、LangGraph、Agno、CrewAI 这类“Agent 开发/运行平台”不是同一层级。

- 和 `平台` 简单对比

| 产品                            | 是否属于 Agent 平台生态     | 更准确的细分定位                            |
| ----------------------------- | ------------------- | ----------------------------------- |
| **Cherry Studio**             | 是，偏 Agent 客户端       | AI 助手客户端 / 多模型桌面端 / MCP 工具调用入口      |
| **LobeHub / LobeChat**        | 是，偏 Agent Workspace | Agent 工作空间 / 助理市场 / 多模型 AI 应用工作台    |
| **Dify**                      | 是，偏平台层              | 低代码 Agentic Workflow / AI 应用开发平台    |
| **LangGraph / Agno / CrewAI** | 是，偏框架层              | Agent 开发框架 / Runtime / 多 Agent 编排框架 |


- `Cherry` vs `Lobe`

| 共性能力            | Cherry Studio                   | LobeHub / LobeChat                        |
| --------------- | ------------------------------- | ----------------------------------------- |
| Agent 抽象        | ✅ 支持：多助手/角色配置                   | ✅ 强项：Agent Builder、Agent Market           |
| 多模型支持           | ✅ 强项                            | ✅ 强项，文档提到 70+ 模型                          |
| 工具调用            | ✅ 强项：MCP 客户端能力突出                | ✅ 强项：MCP 技能、工具生态                          |
| RAG / Knowledge | ✅/◐ 支持，偏客户端知识管理                 | ✅ 支持：资源库、知识上下文                            |
| Memory          | ◐ 支持，取决于配置和版本                   | ✅ 强项：Personal Memory                      |
| 多 Agent 协作      | ◐ 较弱                            | ✅ 支持：Agent Groups                         |
| Workflow 编排     | ◐ 较弱，不是 Dify/LangGraph 那种工作流平台  | ◐/✅ 支持：有工作流和群组协作概念，但不是传统 workflow engine  |
| 可视化低代码构建        | ✅ 支持助手配置                        | ✅ 支持 Agent Builder / Marketplace          |
| 生产部署 Runtime    | — 不突出                           | ◐ 自托管/工作区能力，但不是 Agno/LangGraph 那种 Runtime |
| 可观测性 / Trace    | — 不突出                           | ◐ 有思维链等能力，但不是专业 LLMOps                    |
| 企业治理            | ◐ Cherry Studio Enterprise 方向相关 | ◐/✅ Workspace、自托管方向相关                     |
| 终端用户体验          | ✅ 强项                            | ✅ 强项                                      |
| Agent 市场        | — 不突出                           | ✅ 强项                                      |


- `LobeHub`、`Cherry Studio` vs `Dify`

| 对比维度         | Cherry Studio / LobeHub | Dify                             |
| ------------ | ----------------------- | -------------------------------- |
| 核心用户         | 终端用户、个人、团队成员            | 应用开发者、产品、企业 AI 平台团队              |
| 核心场景         | 使用 AI 助手、组织对话、调用工具      | 构建 AI 应用、Agentic Workflow、RAG 应用 |
| 产品形态         | Client / Workspace      | App Platform / Workflow Platform |
| 交付对象         | 用户自己使用的助手               | 可发布给他人使用的 AI 应用                  |
| Workflow 能力  | 较轻                      | 较强                               |
| RAG Pipeline | 较轻                      | 较强                               |
| LLMOps       | 较轻                      | 较强                               |
| 多模型体验        | 强                       | 强                                |
| MCP 使用体验     | 强                       | 支持，但定位不同                         |
| 更像什么         | ChatGPT 客户端 + Agent 工作台 | AI 应用低代码开发平台                     |


- 三个竞争方向

| 方向                         | 代表产品                                                        | 竞争焦点                          |
| -------------------------- | ----------------------------------------------------------- | ----------------------------- |
| **开源自托管 AI Workspace**     | Open WebUI、LibreChat、AnythingLLM                            | 私有化、RAG、多用户、MCP、企业部署          |
| **桌面 AI Client**           | Cherry Studio、Chatbox、Jan、Msty                              | 多模型、本地模型、MCP、桌面体验、个人效率        |
| **Agent-native Workspace** | LobeHub、部分 AnythingLLM、未来的 ChatGPT Projects/Claude Projects | Agent 作为工作单元、多 Agent、记忆、任务、协作 |

- Cherry Studio 和 LobeHub 不是孤立产品。它们分别处在两个正在融合的方向上：

Cherry Studio:
桌面 AI Client → MCP Client → Personal Agent Client

LobeHub:
AI Chat Workspace → Agent Workspace → Multi-Agent Collaboration Workspace


- 发展趋势

AI Chat Client 正在向 Agent Workspace 演进；Agent Workspace 又在向团队协作、长期记忆、工具权限、任务执行和工作流管理演进。