# Awesome Agent

> A practical, evidence-oriented map for learning, designing, building, and evaluating AI agents.

There are already excellent lists of agent projects, papers, skills, and
harnesses. This project takes a complementary approach: every entry should
help answer a design question, not merely add another link.

**中文说明：** 这是一个面向 Agent 学习与设计实践的知识地图。我们不仅收集
框架和论文，也整理设计模式、工程权衡、评测方法、安全边界、学习网站和近期
高质量文章。欢迎提交资源，但请说明它解决什么问题、适合什么阶段，以及证据
在哪里。

## What belongs here?

We organize resources around the decisions an agent builder actually makes:

1. What is the task, environment, and success contract?
2. Should the system use a workflow, a single tool-using loop, or multiple agents?
3. What belongs in context, memory, retrieval, or external state?
4. How are tools, permissions, retries, and human handoffs constrained?
5. How do we observe, replay, evaluate, and secure the system?
6. Which claims are supported by benchmarks, real deployments, or only demos?

## Start here

### A compact learning path

| Stage | Learn | Suggested resources |
|---|---|---|
| 1. Foundations | Tool use, structured outputs, context, and failure modes | [ReAct](https://arxiv.org/abs/2210.03629), [Toolformer](https://arxiv.org/abs/2302.04761), [OpenAI: A practical guide to building agents](https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf) |
| 2. Agent patterns | Workflows, routing, parallelization, orchestrator-workers, evaluators | [Anthropic: Building effective agents](https://www.anthropic.com/research/building-effective-agents), [LangGraph](https://langchain-ai.github.io/langgraph/), [LlamaIndex Workflows](https://docs.llamaindex.ai/en/stable/module_guides/workflow/) |
| 3. Tool and protocol design | Tool schemas, permissions, interoperability, and state boundaries | [Model Context Protocol](https://modelcontextprotocol.io/), [OpenAI Agents SDK](https://openai.github.io/openai-agents-python/), [Google ADK](https://google.github.io/adk-docs/) |
| 4. Evaluation | Task success, trajectory quality, reliability, cost, and safety | [SWE-bench](https://www.swebench.com/), [τ-bench](https://github.com/sierra-research/tau2-bench), [AgentDojo](https://github.com/ethz-spylab/agentdojo), [BrowserGym](https://github.com/ServiceNow/BrowserGym) |
| 5. Production design | Observability, replay, guardrails, incident response, and governance | [OpenTelemetry](https://opentelemetry.io/), [OWASP Agentic AI Threats and Mitigations](https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations/), [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) |

### Design methods and patterns

- [Agentic patterns](https://github.com/nibzard/awesome-agentic-patterns) — a useful pattern catalogue to compare against concrete implementations.
- [Building effective agents](https://www.anthropic.com/research/building-effective-agents) — a clear distinction between simple workflows and autonomous agents.
- [OpenAI agent guide](https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf) — practical decomposition, tools, orchestration, and guardrails.
- [Google Agent Development Kit](https://google.github.io/adk-docs/) — an implementation-oriented view of agents, tools, sessions, and evaluation.
- [Microsoft AutoGen](https://microsoft.github.io/autogen/) — multi-agent conversation and event-driven design.
- [CrewAI](https://docs.crewai.com/) — role/task-oriented orchestration for teams of agents.
- [LangGraph](https://langchain-ai.github.io/langgraph/) — explicit graph/state modeling for controllable agent workflows.

### Papers worth knowing

- [ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629)
- [Toolformer: Language Models Can Teach Themselves to Use Tools](https://arxiv.org/abs/2302.04761)
- [Reflexion: Language Agents with Verbal Reinforcement Learning](https://arxiv.org/abs/2303.11366)
- [Generative Agents](https://arxiv.org/abs/2304.03442)
- [Voyager](https://arxiv.org/abs/2305.16291)
- [SWE-agent](https://arxiv.org/abs/2405.15793)
- [AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses](https://arxiv.org/abs/2406.13352)
- [τ-bench: A Benchmark for Tool-Agent-User Interaction in Real-World Domains](https://arxiv.org/abs/2406.12045)

### Learning websites and courses

- [Hugging Face Agents Course](https://huggingface.co/learn/agents-course/en/unit0/introduction)
- [DeepLearning.AI short courses](https://www.deeplearning.ai/short-courses/)
- [Full Stack Deep Learning](https://fullstackdeeplearning.com/)
- [Microsoft AI Agents for Beginners](https://github.com/microsoft/ai-agents-for-beginners)
- [Anthropic courses](https://github.com/anthropics/courses)
- [OpenAI Cookbook](https://cookbook.openai.com/)
- [Google Cloud Agent Development Kit resources](https://cloud.google.com/products/agent-builder)

### Existing lists we learn from

This repository is complementary to, and should credit, the broader ecosystem:

- [kyrolabs/awesome-agents](https://github.com/kyrolabs/awesome-agents) — projects and platforms.
- [nibzard/awesome-agentic-patterns](https://github.com/nibzard/awesome-agentic-patterns) — patterns.
- [Picrew/awesome-agent-harness](https://github.com/Picrew/awesome-agent-harness) — harness engineering.
- [luo-junyu/Awesome-Agent-Papers](https://github.com/luo-junyu/Awesome-Agent-Papers) — papers and surveys.
- [VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills) — skills and reusable capabilities.
- [WenyuChiou/awesome-agentic-ai-zh](https://github.com/WenyuChiou/awesome-agentic-ai-zh) — Chinese/trilingual learning roadmap.

## How we review an entry

Each addition should include:

- **Design question:** what decision does this resource inform?
- **Type:** paper, course, documentation, framework, benchmark, case study, or tool.
- **Maturity:** concept, research prototype, maintained project, or production evidence.
- **Evidence:** primary source, code, benchmark, deployment report, or explicit limitation.
- **Last checked:** date on which the link and basic status were verified.

We prefer primary sources, maintained documentation, reproducible examples, and
clear limitations. Popularity is useful for discovery, but stars are not evidence
of reliability.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). The short version: submit focused entries,
avoid duplicate lists, explain the design lesson, and do not turn marketing claims
into facts.

## Scope note

This is a curated learning and design guide, not a claim that any framework is
universally best. Agent systems change quickly; links and maintenance status should
be rechecked regularly. The initial catalogue was assembled on 2026-07-31.

## License

Content and curation are released under the [MIT License](LICENSE).
