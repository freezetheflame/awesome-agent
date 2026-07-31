# Agent Papers by Design Question

这不是一份按发表年份排序的论文墙。每篇论文都放在它回答的设计问题
下面：Agent 如何行动、如何使用工具、如何规划和记忆、如何协作，以及如何
被可靠地评测。

## Reading order

如果刚开始学习，按这个顺序读：

1. [A Survey on Large Language Model based Autonomous Agents](https://arxiv.org/abs/2308.11432)
2. [ReAct](https://arxiv.org/abs/2210.03629)
3. [Toolformer](https://arxiv.org/abs/2302.04761)
4. [Reflexion](https://arxiv.org/abs/2303.11366)
5. [AutoGen](https://arxiv.org/abs/2308.08155) 或 [CAMEL](https://arxiv.org/abs/2303.17760)
6. 一个真实应用论文：[SWE-agent](https://arxiv.org/abs/2405.15793) 或 [WebArena](https://arxiv.org/abs/2307.13854)
7. [AgentDojo](https://arxiv.org/abs/2406.13352) 和 [τ-bench](https://arxiv.org/abs/2406.12045)

## 1. Surveys and conceptual foundations

| Paper | Design lesson | Read it for |
|---|---|---|
| [A Survey on Large Language Model based Autonomous Agents](https://arxiv.org/abs/2308.11432) | 统一观察、规划、行动、记忆和工具的 Agent 组件视角 | 建立术语和研究地图 |
| [The Rise and Potential of Large Language Model Based Agents](https://arxiv.org/abs/2309.07864) | 从能力、应用和风险看 Agent 系统 | 了解研究问题的全貌 |
| [LLM-based Multi-Agents: A Survey](https://arxiv.org/abs/2402.01680) | 多智能体通信、协作、辩论和角色分工 | 判断何时需要多个 Agent |
| [The AI Agent Index](https://aiagentindex.mit.edu/) | 以系统而非单一模型为对象记录 Agent | 比较公开系统的能力与风险披露 |

## 2. Tool use and action loops

| Paper | Design lesson | Read it for |
|---|---|---|
| [ReAct](https://arxiv.org/abs/2210.03629) | 交替进行推理和行动，让观察结果进入下一步决策 | 最基本的 tool-using loop |
| [MRKL Systems](https://arxiv.org/abs/2205.00445) | 语言模型与外部专家模块/工具路由结合 | 为什么模型不应独自承担所有能力 |
| [Toolformer](https://arxiv.org/abs/2302.04761) | 让模型学习何时调用 API 以及如何使用返回值 | 工具调用训练与调用时机 |
| [Gorilla](https://arxiv.org/abs/2305.15334) | 面向大量 API 的检索和调用 | 工具目录、参数选择和 API 漂移 |
| [ToolLLM](https://arxiv.org/abs/2307.16789) | 让 LLM 使用大量真实 API | 大规模工具使用与 ToolBench |
| [API-Bank](https://arxiv.org/abs/2304.08244) | 用 API 调用轨迹评测工具增强模型 | 工具调用数据与评测设计 |
| [ART](https://arxiv.org/abs/2303.09014) | 通过可组合的工具调用过程完成复杂任务 | 工具增强的模块化推理 |

## 3. Planning, search, reflection, and memory

| Paper | Design lesson | Read it for |
|---|---|---|
| [Tree of Thoughts](https://arxiv.org/abs/2305.10601) | 显式搜索多个中间思路并评估/回溯 | 何时树搜索值得额外成本 |
| [Graph of Thoughts](https://arxiv.org/abs/2308.09687) | 中间思路可以合并、循环和重组 | 比线性 Chain 更灵活的状态结构 |
| [Reflexion](https://arxiv.org/abs/2303.11366) | 用语言反馈形成跨轮次的反思记忆 | 反馈、失败复盘和自我改进 |
| [Self-Refine](https://arxiv.org/abs/2303.17651) | 同一个模型生成、批评、修订输出 | evaluator-optimizer 的最小形式 |
| [MemGPT](https://arxiv.org/abs/2310.08560) | 把上下文管理和长期记忆做成显式控制层 | Agent memory 与上下文分页 |
| [Generative Agents](https://arxiv.org/abs/2304.03442) | 记忆、检索、反思共同影响行为 | 社会模拟中的记忆架构 |
| [Voyager](https://arxiv.org/abs/2305.16291) | 自动课程、技能库和环境反馈组成持续学习循环 | 技能积累和开放环境探索 |
| [LLM+P](https://arxiv.org/abs/2304.11477) | 将语言模型与外部规划器结合 | 让 LLM 负责接口而非完整搜索 |

## 4. Multi-agent collaboration and role design

| Paper | Design lesson | Read it for |
|---|---|---|
| [CAMEL](https://arxiv.org/abs/2303.17760) | 通过角色扮演和 inception prompting 促成协作 | 角色对话的早期范式 |
| [AutoGen](https://arxiv.org/abs/2308.08155) | 用可编程对话和代理协议构建多 Agent 应用 | 多 Agent 消息编排 |
| [MetaGPT](https://arxiv.org/abs/2308.00352) | 把软件公司的 SOP 和角色映射为 Agent 协作 | 结构化角色与产物流 |
| [ChatDev](https://arxiv.org/abs/2307.07924) | 用沟通协议模拟软件开发团队 | 对话式协作的成本和边界 |
| [AgentVerse](https://arxiv.org/abs/2308.10848) | 统一多 Agent 环境和协作实验 | 多 Agent 实验平台 |
| [Magentic-One](https://arxiv.org/abs/2411.04468) | 通用多 Agent 编排器分解和监督复杂任务 | planner、specialist、进度监督 |
| [Agent-as-a-Judge](https://arxiv.org/abs/2410.10934) | Agent 也可以作为可审计的评估者 | 自动评测的偏差与验证 |

## 5. Coding, browser, and computer-use agents

| Paper | Design lesson | Read it for |
|---|---|---|
| [SWE-agent](https://arxiv.org/abs/2405.15793) | Agent-Computer Interface 的设计会显著影响代码任务 | 真实代码仓库中的工具边界 |
| [WebArena](https://arxiv.org/abs/2307.13854) | 在可控但真实感较强的网站环境评测 Agent | 浏览器 Agent 的任务与环境设计 |
| [Mind2Web](https://arxiv.org/abs/2306.06070) | 从真实网站轨迹学习通用 Web Agent | 跨网站泛化和操作轨迹 |
| [OSWorld](https://arxiv.org/abs/2404.07972) | 在真实计算机环境中完成开放任务 | GUI、文件和系统状态交互 |
| [GAIA](https://arxiv.org/abs/2311.12983) | 需要搜索、工具和多模态能力的通用助手任务 | 端到端助手能力评测 |
| [OpenHands](https://arxiv.org/abs/2407.16741) | 开放式软件开发 Agent 的运行时与工具环境 | 大型编码 Agent 的系统化构建 |
| [ChatDev](https://arxiv.org/abs/2307.07924) | 通过角色和沟通协议组织软件开发 | 多 Agent coding workflow |

## 6. Evaluation, reliability, and security

| Paper | Design lesson | Read it for |
|---|---|---|
| [AgentBench](https://arxiv.org/abs/2308.03688) | 跨环境评测比单一问答分数更接近 Agent 能力 | 多环境 benchmark 设计 |
| [τ-bench](https://arxiv.org/abs/2406.12045) | 工具、用户和策略共同构成真实交互任务 | tool-agent-user 评测与状态终态 |
| [AgentDojo](https://arxiv.org/abs/2406.13352) | Prompt injection 需要动态工具环境来测 | Agent 安全和攻击面 |
| [Agent Security Bench](https://arxiv.org/abs/2410.02644) | 从多个风险维度系统评估 Agent 安全 | 安全 benchmark 设计 |
| [SWE-bench](https://arxiv.org/abs/2310.06770) | 用真实 GitHub issue 测量代码修复能力 | 真实仓库、测试和 patch 评测 |
| [BrowserGym](https://arxiv.org/abs/2407.00664) | 用统一环境支撑多种 Web Agent 评测 | 可复现浏览器环境 |
| [TheAgentCompany](https://arxiv.org/abs/2412.14161) | 在完整软件公司环境中评测多步 Agent | 长任务、协作和工作流 |
| [Agent Laboratory](https://arxiv.org/abs/2409.13371) | 将科研过程拆为可协作的 Agent 工作流 | 科研 Agent 和端到端产物 |

## How to read a framework paper

不要只看 Demo。至少记录以下问题：

- Agent 的状态在哪里，谁能修改它？
- 工具调用是否有 schema、权限、超时和幂等语义？
- 失败、重试、暂停和人工接管如何表示？
- 评测测的是最终任务、过程轨迹、成本，还是安全边界？
- 论文结论是否来自真实环境、独立任务，还是手工示例？

论文链接以 arXiv/官方页面为主；标题、链接和分类最后检查于
2026-07-31。近期论文会继续进入本目录，但不会仅因“最新”而跳过复现和
证据边界检查。
