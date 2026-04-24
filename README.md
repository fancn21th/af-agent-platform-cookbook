# AF Agent Platform Cookbook


## 标记说明：

| 标记          | 含义                      |
| ----------- | ----------------------- |
| **✅ 强项**    | 明确是该产品的核心定位或优势          |
| **✅ 支持**    | 具备该能力，但不一定是最突出卖点        |
| **◐ 部分支持**  | 有相关能力，但需要组合、二次开发，或成熟度有限 |
| **— 弱/不突出** | 不是主要方向，或资料中不明显          |


## Agent 平台共性能力矩阵

| 共性能力                        | 能力说明                                         | AutoGPT                                                    | Dify                                  | LangChain / LangGraph                                     | AutoGen                                                                   | CrewAI                                        | Agno                                                       |
| --------------------------- | -------------------------------------------- | ---------------------------------------------------------- | ------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------- | --------------------------------------------- | ---------------------------------------------------------- |
| **Agent 抽象**                | 定义 Agent 的角色、目标、指令、任务和执行逻辑                   | ✅ 强项：最早以自主 Agent 出圈                                        | ✅ 支持：可基于函数调用或 ReAct 定义 Agent          | ✅ 强项：LangChain 是 Agent 工程生态，LangGraph 支持复杂 Agent workflow | ✅ 强项：面向 AI agents / multi-agent apps                                      | ✅ 强项：围绕 Agents、Crews、Tasks 构建                 | ✅ 强项：以 agents、teams、workflows 为核心                          |
| **工具调用 / Tool Use**         | Agent 调用搜索、API、数据库、代码执行、MCP、外部服务等工具          | ✅ 支持：通过 blocks / workflow 集成外部能力                           | ✅ 强项：内置 50+ 工具，也支持自定义工具               | ✅ 强项：工具调用生态成熟，适合代码集成                                      | ✅ 强项：支持 MCP、Docker code executor、扩展组件等                                    | ✅ 支持：agent 可使用 tools 完成任务                     | ✅ 支持：强调 agents 连接工具、知识和运行时                                 |
| **工作流编排**                   | 将 Agent 行为组织成步骤、分支、循环、条件、状态机                 | ✅ 强项：AutoGPT Platform 有 visual workflow / block            | ✅ 强项：可视化 workflow 是核心能力之一             | ✅ 强项：LangGraph 专门面向有状态、可控、可恢复的 agent workflow             | ✅ 支持：支持 deterministic / dynamic agent workflows                           | ✅ 强项：Flows 用于结构化、事件驱动工作流                      | ✅ 强项：支持 workflows，并可在 AgentOS 中运行管理                        |
| **多 Agent 协作**              | 多个 Agent 分角色协作，例如 researcher、writer、reviewer | ◐ 部分支持：更偏单 Agent / workflow 自动化                            | ◐ 部分支持：有 Agent 能力，但多 Agent 不是最强标签     | ✅ 支持：LangGraph 支持 multi-actor / multi-agent 应用            | ✅ 强项：AutoGen 是多 Agent 框架代表之一                                              | ✅ 强项：CrewAI 的核心就是 crews 多 Agent 协作            | ✅ 强项：明确定位 multi-agent systems                              |
| **RAG / Knowledge**         | 文档导入、切分、向量检索、知识库、引用来源                        | ◐ 部分支持：可通过 blocks/集成实现                                     | ✅ 强项：RAG Pipeline 是 Dify 核心能力         | ✅ 支持：LangChain 生态中 RAG 能力非常成熟                             | ◐ 部分支持：可通过扩展和工具接入                                                         | ✅ 支持：文档强调 knowledge 能力                        | ✅ 支持：AgentOS 可管理 knowledge                                 |
| **Memory / State**          | 会话记忆、长期记忆、任务状态、checkpoint、上下文恢复              | ◐ 部分支持                                                     | ✅ 支持：应用日志、会话和数据运营能力较完整                | ✅ 强项：LangGraph 有 persistence、checkpoint、durable execution | ✅ 支持：AgentChat / Core 支持有状态 agent 交互                                      | ✅ 支持：文档明确提到 memory                            | ✅ 强项：AgentOS 支持 sessions、memory、traces 等                   |
| **Human-in-the-loop**       | 在敏感工具调用、审批、关键决策前让人介入                         | ◐ 部分支持：可通过 workflow 节点设计实现                                 | ◐ 部分支持：可通过 workflow/应用设计实现            | ✅ 强项：LangGraph 明确支持 interrupt、人机审批和恢复                     | ✅ 支持：Microsoft Agent Framework 迁移文档提到 human-in-loop / request-response 模式 | ◐ 部分支持：可通过 flow 设计实现                          | ◐ 部分支持：可通过 workflow/control plane 设计实现                     |
| **可观测性 / Tracing**          | 查看 Agent 每一步做了什么、工具调用、token、错误、性能            | ✅ 支持：AutoGPT Platform 有 monitoring / analytics             | ✅ 强项：Dify 明确内置 observability / LLMOps | ✅ 强项：LangSmith 提供 tracing、evaluation、production metrics   | ✅ 支持：AutoGen / Agent Framework 体系有 observability 方向                       | ✅ 支持：文档强调 observability baked in              | ✅ 强项：AgentOS Control Plane 可查看 traces、sessions、performance |
| **评估 / Eval / Benchmark**   | 自动化测试、质量评估、数据集、回归测试                          | ✅ 支持：AutoGPT 生态有 agbenchmark 历史                            | ✅ 支持：LLMOps 支持基于生产数据和标注改进             | ✅ 强项：LangSmith 明确支持测试、评估、持续改进                             | ◐ 部分支持：可做，但不是 AutoGen 当前最突出的产品卖点                                          | ◐ 部分支持：更多依赖平台/自建流程                            | ◐ 部分支持：可结合 trace 和监控做，但不是最核心标签                             |
| **Prompt / Instruction 管理** | 管理系统提示词、角色提示、模板、版本、调试                        | ◐ 部分支持                                                     | ✅ 强项：Dify 有 Prompt IDE                | ✅ 支持：LangChain/LangSmith 支持 prompt 迭代和版本管理                | ✅ 支持：通过代码定义 agent instruction                                             | ✅ 支持：通过 agent/task 配置                         | ✅ 支持：通过 agent 配置和运行时管理                                     |
| **模型抽象 / 多模型支持**            | 支持 OpenAI、Claude、Gemini、开源模型、本地模型等           | ✅ 支持                                                       | ✅ 强项：Dify 支持多模型、多供应商和自托管              | ✅ 强项：LangChain 生态覆盖广                                      | ✅ 支持：通过 model client / extensions                                         | ✅ 支持：可连接不同模型提供商                               | ✅ 支持：支持多模型接入                                               |
| **低代码 / 可视化构建**             | 通过 UI 画布、表单、节点配置构建 Agent 应用                  | ✅ 强项：AutoGPT Platform 有 Agent Builder / graph editor       | ✅ 强项：Dify 是典型低代码 AI 应用平台              | ◐ 部分支持：LangGraph 本身代码优先，平台能力另算                            | ◐ 部分支持：AutoGen Studio 可做原型，但主框架代码优先                                       | ◐ 部分支持：主框架代码优先，企业平台另算                         | ◐ 部分支持：AgentOS 有控制台，但开发仍偏代码优先                              |
| **代码优先开发体验**                | 用 SDK / Python / TypeScript 构建复杂业务逻辑         | ✅ 支持                                                       | ◐ 部分支持：Dify 更偏平台化和低代码                 | ✅ 强项：LangChain/LangGraph 非常适合工程化开发                        | ✅ 强项：AutoGen 是编程框架                                                        | ✅ 强项：CrewAI 是代码优先框架                           | ✅ 强项：Agno 是 Pythonic、代码优先                                  |
| **运行时 / 部署能力**              | 将 Agent 作为 API、服务、应用部署到生产环境                  | ✅ 支持：AutoGPT Platform 有 server/frontend/deployment control | ✅ 强项：Dify 强调从原型到生产                    | ✅ 强项：LangGraph Platform / LangSmith 面向部署和运行               | ◐ 部分支持：AutoGen 更偏框架，新项目推荐 Microsoft Agent Framework                       | ◐/✅ 支持：文档定位 production ready，但具体企业运行时视版本/产品而定 | ✅ 强项：AgentOS Runtime + Control Plane 是核心卖点                 |
| **企业治理 / 权限 / 安全**          | 权限隔离、审计、私有化、数据安全、合规                          | ◐ 部分支持：平台化方向有，但生态成熟度需评估                                    | ✅ 支持：适合企业私有化/平台化部署                    | ✅ 强项：LangSmith / LangGraph Platform 面向企业生产环境              | ◐ 支持：AutoGen 维护模式；新项目更建议看 Microsoft Agent Framework                       | ◐/✅ 支持：企业版/AMP 方向更相关                          | ✅ 支持：AgentOS 强调数据不发送到 Agno、连接本地 runtime                    |
| **插件 / 扩展生态**               | 工具、模型、连接器、MCP、社区扩展                           | ✅ 支持                                                       | ✅ 强项：丰富集成和工具                          | ✅ 强项：LangChain 生态最大优势之一                                   | ✅ 支持：AutoGen 有 extensions、MCP、Docker executor 等                           | ✅ 支持：工具和 crew/flow 模式扩展                       | ✅ 支持：框架 + runtime + control plane 扩展                       |
| **适合非技术人员参与**               | 产品、运营、业务人员能否配置、调试、运营 AI 应用                   | ✅ 支持：平台 UI 有帮助                                             | ✅ 强项：Dify 最适合业务/产品共同参与                | ◐ 较弱：主要面向开发者                                              | ◐ 部分支持：AutoGen Studio 可原型，但整体偏开发者                                         | ◐ 较弱：主要面向开发者                                  | ◐ 部分支持：AgentOS 可测试/监控，但构建偏开发者                              |
| **适合复杂工程系统集成**              | 接入现有后端、权限、数据库、消息队列、业务流程                      | ✅ 支持                                                       | ✅ 支持：平台化集成能力强                         | ✅ 强项：代码优先 + graph workflow 适合复杂系统                         | ✅ 支持：事件驱动、多 Agent、分布式 runtime 方向                                          | ✅ 支持：适合多 Agent 自动化任务                          | ✅ 强项：runtime/control plane 思路适合工程化集成                       |


## 简化版结论

- 共性能力

| 核心能力层       | 对应能力                              |
| ----------- | --------------------------------- |
| **Agent 层** | Agent 抽象、多 Agent、角色/任务定义          |
| **编排层**     | Workflow、Graph、Flow、状态机、条件分支      |
| **工具层**     | Tool calling、API、MCP、代码执行、外部系统    |
| **知识层**     | RAG、Knowledge、文档检索、企业知识库          |
| **记忆层**     | Session、Memory、State、Checkpoint   |
| **控制层**     | Human-in-the-loop、审批、Guardrails   |
| **运营层**     | Observability、Tracing、Eval、LLMOps |
| **平台层**     | 部署、运行时、权限、安全、控制台、低代码 UI           |


- 产品定位

| 产品                        | 更像什么                                           |
| ------------------------- | ---------------------------------------------- |
| **Dify**                  | 低代码 AI 应用平台 / 企业 Agentic Workflow 平台           |
| **LangChain / LangGraph** | 代码优先的 Agent 工程框架 + 可控状态图编排                     |
| **CrewAI**                | 多 Agent 团队协作框架                                 |
| **Agno**                  | Pythonic 多 Agent 框架 + Runtime + Control Plane  |
| **AutoGen**               | 多 Agent 编程框架，但新项目需关注 Microsoft Agent Framework |
| **AutoGPT**               | 自主 Agent 先驱 + 可视化 Agent Workflow 平台            |
