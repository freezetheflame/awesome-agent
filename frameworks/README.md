# Agent Framework Landscape

This is a curated map of agent frameworks, SDKs, protocols, runtimes, and
large open-source Agent applications. It is intentionally not a generic list of
every project with "agent" in its name.

The key distinction is architectural role:

- **SDK/runtime:** the primitives used to define, run, govern, and evaluate an agent;
- **orchestration framework:** a particular way to compose workflows or agents;
- **protocol/infrastructure:** the boundary between agents, tools, models, and operations;
- **Agent application:** a substantial product/repository built around an agent loop.

关注度数字是 GitHub API 在 **2026-07-31** 的快照，只用于发现项目，不代表质量、
稳定性或生产可用性。

## 1. SDKs and agent runtimes

| Project | Primary stack | Design center | GitHub signal |
|---|---|---|---:|
| [OpenAI Agents SDK](https://github.com/openai/openai-agents-python) | Python | lightweight agents, tools, handoffs, guardrails, tracing | 28.3k |
| [Claude Agent SDK](https://github.com/anthropics/claude-agent-sdk-python) | Python | Claude Code-style agent control and tool execution | 7.8k |
| [Google ADK](https://github.com/google/adk-python) | Python | code-first agents, sessions, evaluation, deployment | 21.0k |
| [Microsoft Agent Framework](https://github.com/microsoft/agent-framework) | Python/.NET | orchestration and deployment across Microsoft ecosystems | 12.5k |
| [Strands Agents](https://github.com/strands-agents/harness-sdk) | Python/TypeScript | model- and cloud-agnostic production harness | 6.7k |
| [PydanticAI](https://github.com/pydantic/pydantic-ai) | Python | typed, validated agent outputs and dependencies | 18.9k |
| [Semantic Kernel](https://github.com/microsoft/semantic-kernel) | C#/Python/Java | enterprise plugins, planners, memory, connectors | large, mature |
| [LlamaIndex](https://github.com/run-llama/llama_index) | Python/TS | data-connected agents, indexing, workflows | 51.2k |
| [Haystack](https://github.com/deepset-ai/haystack) | Python | modular pipelines, RAG, tool-using components | established |
| [smolagents](https://github.com/huggingface/smolagents) | Python | minimal agents that express actions as code | 28.6k |

Official docs to compare first: [OpenAI Agents SDK](https://openai.github.io/openai-agents-python/),
[Claude Agent SDK](https://docs.anthropic.com/en/docs/claude-code/sdk),
[Google ADK](https://google.github.io/adk-docs/),
[PydanticAI](https://ai.pydantic.dev/), and
[Semantic Kernel](https://learn.microsoft.com/en-us/semantic-kernel/).

## 2. Workflow and graph orchestration

| Project | Core idea | Best comparison axis | GitHub signal |
|---|---|---|---:|
| [LangGraph](https://github.com/langchain-ai/langgraph) | explicit state graphs and durable execution | controllability, checkpoints, human pauses | 38.5k |
| [LangChain](https://github.com/langchain-ai/langchain) | broad agent engineering platform | ecosystem breadth versus abstraction cost | 143k |
| [Mastra](https://github.com/mastra-ai/mastra) | TypeScript agents, workflows, and observability | full-stack TypeScript development | 26.8k |
| [Inngest AgentKit](https://github.com/inngest/agent-kit) | event-driven, durable agent steps | background jobs and retries | active |
| [DSPy](https://github.com/stanfordnlp/dspy) | declarative LM programs and optimization | programmatic prompt/agent optimization | large research community |
| [Haystack](https://github.com/deepset-ai/haystack) | composable pipeline graph | data/RAG workflow composition | established |

These are not interchangeable "agent frameworks": LangGraph emphasizes state
transitions, Mastra emphasizes TypeScript application development, Inngest
emphasizes durable execution, and DSPy emphasizes optimization of LM programs.

## 3. Multi-agent and role-based systems

| Project | Design idea | Important caveat | GitHub signal |
|---|---|---|---:|
| [AutoGen](https://github.com/microsoft/autogen) | event/conversation-based multi-agent collaboration | check the transition path to Microsoft Agent Framework | 60.1k |
| [CrewAI](https://github.com/crewAIInc/crewAI) | roles, tasks, crews, and flows | role prompts do not replace shared state contracts | 56.4k |
| [CAMEL](https://github.com/camel-ai/camel) | research-oriented society of agents | broad research surface; validate production fit | 17.5k |
| [MetaGPT](https://github.com/FoundationAgents/MetaGPT) | software-company roles and SOPs | opinionated role decomposition | high-visibility |
| [AgentScope](https://github.com/agentscope-ai/agentscope) | multi-agent applications with message abstractions | evaluate runtime and ecosystem fit | active |
| [OpenAI Swarm](https://github.com/openai/swarm) | educational handoffs and routines | experimental/educational, not a production guarantee | archived/experimental |

## 4. Protocols, tool boundaries, and operations

| Project | Role | Why it matters |
|---|---|---|
| [Model Context Protocol](https://github.com/modelcontextprotocol) | tool/context interoperability | standardizes how models discover and call external capabilities |
| [A2A](https://github.com/a2aproject/A2A) | agent-to-agent interoperability | defines remote agent collaboration boundaries |
| [OpenTelemetry](https://opentelemetry.io/) | traces and metrics | makes latency, tool calls, errors, and handoffs observable |
| [Langfuse](https://github.com/langfuse/langfuse) | LLM/agent observability | traces, evaluations, prompts, and cost analysis |
| [Arize Phoenix](https://github.com/Arize-ai/phoenix) | open-source observability/evaluation | inspect retrieval and agent traces |
| [Guardrails AI](https://github.com/guardrails-ai/guardrails) | validation and guardrails | constrain structured outputs and risky actions |
| [NeMo Guardrails](https://github.com/NVIDIA-NeMo/Guardrails) | programmable conversational rails | policy and dialogue flow boundaries |

Protocols and observability are supporting layers, not substitutes for an
execution model or an evaluation contract.

## 5. Large Agent applications and design references

These repositories are valuable because they expose the engineering trade-offs
of a substantial Agent product, not because they are drop-in SDKs.

| Project | Application focus | Design signal | GitHub signal |
|---|---|---|---:|
| [OpenHands](https://github.com/OpenHands/OpenHands) | software development agent | sandboxed actions, event streams, extensible runtime | 82.6k |
| [SWE-agent](https://github.com/SWE-agent/SWE-agent) | issue-to-code repair | benchmark-driven coding loop and tool interface | 20.0k |
| [Aider](https://github.com/Aider-AI/aider) | terminal pair programming | repository map, edit formats, test loop | 47.8k |
| [Cline](https://github.com/cline/cline) | IDE/CLI coding agent | user-visible approvals and tool execution | 65.3k |
| [Goose](https://github.com/block/goose) | extensible local coding agent | open model/tool/runtime integration | 52.0k |
| [Browser Use](https://github.com/browser-use/browser-use) | browser task automation | browser state grounding and action loop | 107k |
| [Letta](https://github.com/letta-ai/letta) | stateful agents and memory | explicit long-lived agent state | 24.0k |
| [Mem0](https://github.com/mem0ai/mem0) | memory layer for agents | memory extraction and retrieval as a service | high-visibility |
| [Open Interpreter](https://github.com/OpenInterpreter/open-interpreter) | natural-language computer control | local execution and interactive tool loop | high-visibility |

## 6. Benchmarks and evaluation infrastructure

| Project | What it measures |
|---|---|
| [SWE-bench](https://github.com/SWE-bench/SWE-bench) | software issue resolution in real repositories |
| [τ-bench](https://github.com/sierra-research/tau2-bench) | tool-agent-user interaction in realistic domains |
| [AgentDojo](https://github.com/ethz-spylab/agentdojo) | prompt-injection robustness and tool-use security |
| [BrowserGym](https://github.com/ServiceNow/BrowserGym) | web interaction environments and benchmarks |
| [AgentBench](https://github.com/THUDM/AgentBench) | multi-environment LLM agent evaluation |
| [GAIA](https://huggingface.co/gaia-benchmark) | general assistant reasoning with tools and multimodal inputs |

## Choosing a starting point

- Need typed Python and small surface area? Compare **PydanticAI**, **OpenAI
  Agents SDK**, and **smolagents**.
- Need explicit state, pause/resume, and durable workflows? Compare
  **LangGraph**, **Google ADK**, and **Microsoft Agent Framework**.
- Need data-heavy retrieval or document agents? Compare **LlamaIndex** and
  **Haystack**.
- Need role-based collaboration? Compare **CrewAI**, **AutoGen**, and **CAMEL**,
  then inspect whether a simpler workflow would suffice.
- Need to study a real coding agent? Start with **OpenHands**, **Cline**,
  **Aider**, **Goose**, and **SWE-agent**.
- Need interoperability? Start with **MCP** and **A2A**, then add tracing and
  policy at the action boundary.

## Curation policy

Every entry should identify the architectural role, primary design idea,
official repository/docs, maturity or caveat, and last-checked date. We do not
rank frameworks by stars. A large repository is a reason to inspect its design,
not proof that it is the right dependency.

Last checked: 2026-07-31.
