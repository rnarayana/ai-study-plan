## AI Systems for Software Architects — 20-Week Roadmap (≈5 months, 10–12 hrs/week)

### Outcomes
- Design reliable AI features (RAG, agents) with **evals, guardrails, observability, and cost controls**.
- Build production-grade services in **.NET + Azure** (alternates in parentheses).
- Make sound architectural trade-offs that won’t go stale in 3–6 months.

---

## Month 1 — Foundations That Last (Weeks 1–4)

### Week 1 — Environment & “Hello, AI” (Architecture-first)
- Set up: **.NET 8/9**, `Microsoft.Extensions.AI` (unified AI façade), Azure subscription.
- Build a **console chat** app that can swap OpenAI/Azure OpenAI with minimal code changes.
- Read **production** guidance (rate limits, retries, timeouts, backoff, streaming).

  **References:** Microsoft.Extensions.AI overview and API (install, IChatClient) ([Microsoft Learn][1]); .NET quickstart chat app ([Microsoft Learn][2]); OpenAI production best practices (app hardening patterns) ([OpenAI Platform][3]).

### Week 2 — Retrieval 101: Embeddings & Vector Search
- Concepts: embeddings, distance metrics, **ANN indices**, hybrid vs pure vector, schema design.
- Hands-on: **Azure AI Search** vector index; simple semantic search; compare **pgvector** on Postgres to understand tradeoffs.

  **References:** Azure AI Search vector overview & how-to ([Microsoft Learn][4]); .NET vector samples and quickstart ([Microsoft Learn][5]); pgvector docs (overview & operations) ([GitHub][6], [Crunchy Data][7]).

### Week 3 — RAG End-to-End (Durable app pattern)
- Build a minimal **RAG** service: ingestion → chunking → index → retrieval → grounded answers with citations.
- Deploy in **Azure AI Foundry**; wire to your Week-2 vector store.

  **References:** Azure RAG concept page & step-by-step tutorial (Foundry SDK) ([Microsoft Learn][8]); “Chat with your data” .NET sample ([GitHub][9]).

### Week 4 — Evaluation & Basic Observability
- Add **quality gates**: answer relevance, groundedness, context precision/recall.
- Try **Azure RAG evaluators**; compare with **Ragas** and **TruLens**; log traces + token costs.

  **References:** Azure RAG evaluators (groundedness, retrieval) ([Microsoft Learn][10]); Ragas docs & quickstart ([Ragas][11]); TruLens docs/pyPI (eval + instrumentation) ([TruLens][12], [PyPI][13]); Langfuse observability overview (token & cost tracking) ([Langfuse][14]).

---

## Month 2 — Productionize RAG (Weeks 5–8)

### Week 5 — Retrieval Quality: Beyond “Hello, RAG”
- Implement **hybrid search**, **semantic reranking**, metadata filters; test chunking strategies.
- Work through a short course on **advanced RAG** and apply at least two improvements.

  **References:** Advanced RAG (DeepLearning.AI) ([DeepLearning.ai][15], [DeepLearning.AI - Learning Platform][16]); Azure vector query how-to + SDK samples (reranking & filtering patterns) ([Microsoft Learn][17], [GitHub][18]).

### Week 6 — Architect for Scale, Latency & Cost
- Rate limiting & **backpressure**, circuit breakers, request coalescing; **Provisioned Throughput Units (PTU)** vs on-demand; quota planning and SLOs.

  **References:** Azure OpenAI architecture best practices (Well-Architected) ([Microsoft Learn][19]); quota & limits and management guides ([Microsoft Learn][20]); PTU concepts & costing (Foundry) ([Microsoft Learn][21]); OpenAI production tips ([OpenAI Platform][3]).

### Week 7 — Security, Safety & Governance
- Threat-model your app with **OWASP LLM Top 10**; add **Content Safety** (user input & model output); configure PII detection and **prompt shields**.

  **References:** OWASP LLM Top 10 (official) ([OWASP Foundation][22]); Azure AI Content Safety overview & docs (guardrails, groundedness detection) ([Microsoft Learn][23]); Azure OpenAI data privacy (enterprise posture) ([Microsoft Learn][24]).

### Week 8 — Observability Deep-Dive
- Standardize traces/metrics with **OpenTelemetry GenAI** semantics; centralize traces (Langfuse or equivalent), track **latency, costs, eval scores**; create dashboards & budgets.

  **References:** OTel GenAI semantic conventions & concepts ([OpenTelemetry][25]); Langfuse OSS (observability & self-host) ([GitHub][26], [Langfuse][27]).

---

## Month 3 — Agents & Orchestration (Weeks 9–12)

### Week 9 — Agentic Patterns (When & Why)
- Study **Azure agent orchestration patterns** (sequential, concurrent, group, handoff) and decide where agents add value over plain RAG.

  **References:** Azure Architecture Center (agent patterns) & Learn module ([Microsoft Learn][28]).

### Week 10 — Build a Small Agent (Tool-Using)
- Implement a **LangGraph** agent that can call tools (e.g., search, SQL) and hand off to your RAG retriever.

  **References:** LangGraph intro & reference docs ([LangChain][29], [GitHub][30]); Hugging Face Agents course unit on LangGraph ([Hugging Face][31]); Microsoft “Develop AI Agents on Azure” learning path ([Microsoft Learn][32]).

### Week 11 — Multi-Agent Orchestration & Handoffs
- Add **planner/worker** or **router/specialist** topology; implement human-in-the-loop approval for high-risk steps.

  **References:** Azure “Agent Factory” design patterns blog (use cases & patterns) ([Microsoft Azure][33]); LangGraph platform/quickstart for production deploys ([LangChain Docs][34]).

### Week 12 — Agentic Evals & Guardrails
- Extend your Week-4 eval harness to cover **tool correctness**, action safety, and handoff failures. Log to observability backend with session/user traces.

  **References:** TruLens (runtime evals + instrumenting agents) ([TruLens][12]); OTel GenAI events & metrics (attributes for tool calls) ([OpenTelemetry][25]).

---

## Month 4 — Enterprise Readiness (Weeks 13–16)

### Week 13 — Structured Outputs & Integration Contracts
- Enforce **JSON schemas** (strict mode), validation, retry/repair strategies; idempotent APIs; snapshot prompts & versions.

  **References:** Microsoft.Extensions.AI usage patterns & middleware (DI, tool invocation, telemetry hooks) ([Microsoft Learn][1]).

### Week 14 — Data Pipelines & Freshness
- Automate ingestion from **SQL/Blob/SharePoint**; CDC to vector store; content filters & **PII scrubbing**; rebuild strategies.

  **References:** Azure AI Search docs landing (concepts, enrichment, samples) ([Microsoft Learn][35]); .NET Search SDK patterns (indexing & clients) ([Microsoft Learn][36]).

### Week 15 — Compliance & Cloud Security Posture
- Apply **Azure OpenAI Security Baseline**, network isolation, key rotation, RBAC; review DPAs and data-flow diagrams.

  **References:** Azure OpenAI security baseline ([Microsoft Learn][37]); Azure OpenAI data privacy ([Microsoft Learn][24]).

### Week 16 — Performance, Cost & SLOs
- Token budgets, caching (semantic + response), streaming UX, batch jobs for heavy workloads; choose **PTU** for steady high-QPS paths.

  **References:** PTU concepts & cost planning; quota management ([Microsoft Learn][21]).

---

## Month 5 — Capstone (Weeks 17–20)

### Week 17 — Design Doc & KPIs
- Pick a business scenario (e.g., **Benefits Copilot** or **Tech Support Copilot**). Define **KQIs**: answer accuracy ≥ X, groundedness ≥ Y, p95 latency ≤ Z, cost per session ≤ ₹N.

  **References:** Azure Well-Architected for AI (design methodology & KPIs) ([Microsoft Learn][38]).

### Week 18 — Build
- Ship a **RAG + (optional) agent** service with evals, guardrails, traces, dashboards, and runbooks.

### Week 19 — Hardening & Load Tests
- Red team prompts; test quota exhaustion, cache stampedes, index rebuilds; verify SLOs and fallbacks.

  **References:** Azure OpenAI architecture best practices (reliability/cost) ([Microsoft Learn][19]); OWASP LLM Top 10 ([OWASP Foundation][22]).

### Week 20 — Launch, Docs & Handover
- User guide, failure modes, on-call playbook, backlog for vNext.

  **References:** .NET MAUI sample (if you want a quick UI) and AI app template (quick start) ([Microsoft Learn][39]).

---

### What I changed vs your three drafts (quick review)
- **Kept the durable core** (RAG, evals, security, observability) from your 1-year syllabus and compressed it into a **20-week** path.
- From your 5-month version, I **tightened the weekly outputs** and aligned them to **.NET + Azure** (your stack), keeping Python alternatives as drop-ins.
- From the earlier “practical plan,” I retained “**concepts over libraries**,” but replaced framework-specific depth with **design patterns** that survive framework churn (e.g., OTel GenAI semantics, OWASP LLM, Well-Architected guidance).

---

### Cross-check against practical university syllabi
- **CMU 17-634 Applied ML** (end-to-end pipelines and integration, not just algorithms). ([CMU Software Engineering][40])
- **CMU 10-601/10601** (strong balance of fundamentals + practice). ([CMU School of Computer Science][41])
- **Berkeley CS 194/294 LLM Agents** (agent abilities, tooling, and infra). ([rdi.berkeley.edu][42])  
  This gives confidence that focusing on RAG→evals→ops→agents is a **sensible, modern arc** for practitioners.

---

### Optional swaps (if you prefer Python)
- **LangChain/LangGraph + FastAPI** (instead of Microsoft.Extensions.AI): docs & platform refs. ([LangChain][43], [LangChain Docs][34])
- **Hugging Face LLM Course** for model & tokenization intuition. ([Hugging Face][44])

---

### Starter Reading/Watching (lightweight, reusable)
- Prompt engineering primer (short course). ([DeepLearning.ai][45])
- Azure OpenAI **Well-Architected** guidance (design decisions that last). ([Microsoft Learn][19])
- Vector search concepts and .NET samples. ([Microsoft Learn][4])

---

## References

[1]: https://learn.microsoft.com/en-us/dotnet/ai/microsoft-extensions-ai?utm_source=chatgpt.com "Microsoft.Extensions.AI libraries - .NET | Microsoft Learn"  
[2]: https://learn.microsoft.com/en-us/dotnet/ai/quickstarts/build-chat-app?utm_source=chatgpt.com "Quickstart - Build an AI chat app with .NET - .NET | Microsoft Learn"  
[3]: https://platform.openai.com/docs/guides/production-best-practices?utm_source=chatgpt.com "Production best practices - OpenAI API"  
[4]: https://learn.microsoft.com/en-us/azure/search/vector-search-overview?utm_source=chatgpt.com "Vector search - Azure AI Search | Microsoft Learn"  
[5]: https://learn.microsoft.com/en-us/azure/search/samples-dotnet?utm_source=chatgpt.com ".NET Samples - Azure AI Search | Microsoft Learn"  
[6]: https://github.com/pgvector/pgvector?utm_source=chatgpt.com "GitHub - pgvector/pgvector: Open-source vector similarity search for ..."  
[7]: https://access.crunchydata.com/documentation/pgvector/latest/?utm_source=chatgpt.com "pgvector - Crunchy Data"  
[8]: https://learn.microsoft.com/en-us/azure/ai-foundry/concepts/retrieval-augmented-generation?utm_source=chatgpt.com "Retrieval augmented generation in Azure AI Foundry portal - Azure AI ..."  
[9]: https://github.com/Azure-Samples/openai-chat-app-quickstart-dotnet?utm_source=chatgpt.com "Chat Application using Azure OpenAI (.NET) - GitHub"  
[10]: https://learn.microsoft.com/en-us/azure/ai-foundry/concepts/evaluation-evaluators/rag-evaluators?utm_source=chatgpt.com "Retrieval-augmented Generation (RAG) evaluators for generative AI ..."  
[11]: https://docs.ragas.io/en/latest/?utm_source=chatgpt.com "Ragas"  
[12]: https://www.trulens.org/docs/?utm_source=chatgpt.com "Documentation Index - TruLens"  
[13]: https://pypi.org/project/trulens/?utm_source=chatgpt.com "trulens · PyPI"  
[14]: https://langfuse.com/docs/observability/overview?utm_source=chatgpt.com "LLM Observability & Application Tracing (open source) - Langfuse"  
[15]: https://www.deeplearning.ai/short-courses/building-evaluating-advanced-rag/?utm_source=chatgpt.com "Building and Evaluating Advanced RAG Applications - DeepLearning.AI"  
[16]: https://learn.deeplearning.ai/courses/building-evaluating-advanced-rag/lesson/nwy74/introduction?utm_source=chatgpt.com "Building and Evaluating Advanced RAG - DeepLearning.AI"  
[17]: https://learn.microsoft.com/en-us/azure/search/vector-search-how-to-query?utm_source=chatgpt.com "Create a Vector Query - Azure AI Search | Microsoft Learn"  
[18]: https://github.com/Azure/azure-search-vector-samples?utm_source=chatgpt.com "Vector samples - Azure AI Search - GitHub"  
[19]: https://learn.microsoft.com/en-us/azure/well-architected/service-guides/azure-openai?utm_source=chatgpt.com "Architecture best practices for Azure OpenAI Service"  
[20]: https://learn.microsoft.com/en-us/azure/ai-foundry/openai/quotas-limits?utm_source=chatgpt.com "Azure OpenAI in Azure AI Foundry Models Quotas and Limits"  
[21]: https://learn.microsoft.com/en-us/azure/ai-foundry/openai/concepts/provisioned-throughput?utm_source=chatgpt.com "Provisioned throughput for Azure AI Foundry Models"  
[22]: https://owasp.org/www-project-top-10-for-large-language-model-applications/?utm_source=chatgpt.com "OWASP Top 10 for Large Language Model Applications"  
[23]: https://learn.microsoft.com/en-us/azure/ai-services/content-safety/overview?utm_source=chatgpt.com "What is Azure AI Content Safety? - Azure AI services"  
[24]: https://learn.microsoft.com/en-us/azure/ai-foundry/responsible-ai/openai/data-privacy?utm_source=chatgpt.com "Data, privacy, and security for Azure OpenAI Service"  
[25]: https://opentelemetry.io/docs/specs/semconv/gen-ai/?utm_source=chatgpt.com "Semantic conventions for generative AI systems - OpenTelemetry"  
[26]: https://github.com/langfuse/langfuse?utm_source=chatgpt.com "GitHub - langfuse: Open source LLM engineering platform"  
[27]: https://langfuse.com/self-hosting?utm_source=chatgpt.com "Self-host Langfuse (Open Source LLM Observability) - Langfuse"  
[28]: https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/ai-agent-design-patterns?utm_source=chatgpt.com "AI Agent Orchestration Patterns - Azure Architecture Center"  
[29]: https://www.langchain.com/langgraph?utm_source=chatgpt.com "LangGraph - LangChain"  
[30]: https://github.com/langchain-ai/langgraph/blob/main/docs/docs/reference/index.md?utm_source=chatgpt.com "langgraph/docs/docs/reference/index.md at main - GitHub"  
[31]: https://huggingface.co/learn/agents-course/unit2/langgraph/introduction?utm_source=chatgpt.com "Introduction to LangGraph - Hugging Face Agents Course"  
[32]: https://learn.microsoft.com/en-us/training/paths/develop-ai-agents-on-azure/?utm_source=chatgpt.com "Develop AI Agents on Azure - Training | Microsoft Learn"  
[33]: https://azure.microsoft.com/en-us/blog/agent-factory-the-new-era-of-agentic-ai-common-use-cases-and-design-patterns/?utm_source=chatgpt.com "Agent Factory: The new era of agentic AI—common use cases and design patterns"  
[34]: https://docs.langchain.com/langgraph?utm_source=chatgpt.com "Overview - Docs by LangChain"  
[35]: https://learn.microsoft.com/en-us/azure/search/?utm_source=chatgpt.com "Azure AI Search documentation | Microsoft Learn"  
[36]: https://learn.microsoft.com/en-us/azure/search/search-how-to-dotnet-sdk?utm_source=chatgpt.com "Use Azure.Search.Documents in .NET - Azure AI Search"  
[37]: https://learn.microsoft.com/en-us/security/benchmark/azure/baselines/azure-openai-security-baseline?utm_source=chatgpt.com "Azure security baseline for Azure OpenAI | Microsoft Learn"  
[38]: https://learn.microsoft.com/en-us/azure/well-architected/ai/?utm_source=chatgpt.com "AI Workload Documentation - Microsoft Azure Well-Architected Framework"  
[39]: https://learn.microsoft.com/en-us/samples/dotnet/maui-samples/simple-chat-client/?utm_source=chatgpt.com ".NET MAUI - Simple Chat Client - Code Samples | Microsoft Learn"  
[40]: https://mse.s3d.cmu.edu/0_documents/syllabi/sp2021/17634-applied-machine-learning.pdf?utm_source=chatgpt.com "17-634: Applied Machine Learning - mse.s3d.cmu.edu"  
[41]: https://www.cs.cmu.edu/~mgormley/courses/10601/syllabus.html?utm_source=chatgpt.com "Introduction to Machine Learning | 10-301 + 10-601 | Spring 2025"  
[42]: https://rdi.berkeley.edu/llm-agents/f24?utm_source=chatgpt.com "CS294/194-196 Large Language Model Agents"  
[43]: https://python.langchain.com/docs/introduction/?utm_source=chatgpt.com "Introduction | LangChain"  
[44]: https://huggingface.co/learn/llm-course/chapter1/1?utm_source=chatgpt.com "Introduction - Hugging Face LLM Course"  
[45]: https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/?utm_source=chatgpt.com "ChatGPT Prompt Engineering for Developers - DeepLearning.AI"
