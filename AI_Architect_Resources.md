# AI Architect Resources — Updated Plan (4–6 Months)

---

## 📘 Core Reading & References

* **OpenAI**

  * [Production best practices](https://platform.openai.com/docs/guides/production-best-practices)
  * [OpenAI Cookbook](https://cookbook.openai.com/)
  * [tiktoken tokenizer](https://github.com/openai/tiktoken)

* **.NET & Azure AI**

  * [.NET AI overview](https://learn.microsoft.com/dotnet/ai/microsoft-extensions-ai)
  * [Azure OpenAI for .NET](https://learn.microsoft.com/dotnet/api/overview/azure/ai.openai-readme)
  * [Azure AI for .NET developers](https://learn.microsoft.com/dotnet/ai/azure-ai-for-dotnet-developers)

* **Vector Search & RAG**

  * [Azure AI Search — RAG overview](https://learn.microsoft.com/azure/search/retrieval-augmented-generation-overview)
  * [Vector search quickstart](https://learn.microsoft.com/azure/search/search-get-started-vector)
  * [Hybrid search overview](https://learn.microsoft.com/azure/search/hybrid-search-overview)
  * [Chunking skill](https://learn.microsoft.com/azure/search/cognitive-search-skill-textsplit)
  * [Semantic chunking](https://learn.microsoft.com/azure/search/search-how-to-semantic-chunking)
  * [Hybrid ranking (RRF)](https://learn.microsoft.com/azure/search/hybrid-search-ranking)
  * [.NET RAG sample](https://learn.microsoft.com/samples/azure-samples/azure-search-openai-demo-csharp/azure-search-openai-demo-csharp/)

* **Evaluation & Observability**

  * [Ragas documentation](https://docs.ragas.io)
  * [TruLens GitHub](https://github.com/truera/trulens)
  * [Langfuse observability](https://langfuse.com/)
  * [OpenTelemetry GenAI conventions](https://opentelemetry.io/docs/specs/semconv/gen-ai/)

* **Security & Governance**

  * [OWASP Top 10 for LLMs (2025)](https://owasp.org/www-project-top-10-for-large-language-model-applications/assets/PDF/OWASP-Top-10-for-LLMs-v2025.pdf)
  * [Microsoft on Prompt Injection](https://learn.microsoft.com/semantic-kernel/concepts/prompts/prompt-injection-attacks)
  * [Azure Responsible AI](https://learn.microsoft.com/azure/architecture/example-scenario/ai/responsible-ai)
  * [Azure Well-Architected for AI](https://learn.microsoft.com/azure/well-architected/ai/)

* **Agents & Orchestration**

  * [LangGraph GitHub](https://github.com/langchain-ai/langgraph)
  * [Azure AI Agents](https://learn.microsoft.com/en-us/azure/ai-services/agents/overview)
  * [Agent orchestration patterns](https://learn.microsoft.com/en-us/azure/architecture/example-scenario/ai/agent-patterns)

* **MLOps & Classical ML**

  * [ML.NET learn hub](https://dotnet.microsoft.com/learn/ml-dotnet)
  * [ML.NET AutoML](https://learn.microsoft.com/dotnet/machine-learning/automated-machine-learning-mlnet)
  * [Azure MLOps v2 architecture](https://learn.microsoft.com/azure/architecture/ai-ml/guide/machine-learning-operations-v2)

---

## 🎓 Supplementary Learning

* **Prompt Engineering**: [DeepLearning.AI course](https://learn.deeplearning.ai/chatgpt-prompt-eng)
* **Transformers Intuition**: [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)
* **Stats/ML Basics**: [ISLR book](https://www.statlearning.com/)
* **Agents Intro**: [Hugging Face course](https://huggingface.co/learn/agents-course)

---

## 🛠️ Tooling Stack to Practice

| Area      | Tools & SDKs                                |
| --------- | ------------------------------------------- |
| LLMs      | OpenAI, Azure OpenAI, Mistral, LLaMA        |
| .NET AI   | Microsoft.Extensions.AI, Azure.AI.OpenAI    |
| Retrieval | Azure AI Search, pgvector, Weaviate, Qdrant |
| Eval/Obs  | Ragas, TruLens, Langfuse, OpenTelemetry     |
| Security  | OWASP LLM Top-10, Azure Content Safety      |
| Agents    | LangGraph, Azure AI Agents                  |
| MLOps     | ML.NET, AutoML, Azure ML Ops v2             |

---

## 📦 Capstone Suggestions

* **Internal AI Assistant** (summarize Teams/DevOps updates)
* **Enterprise RAG Service** (hybrid retrieval + evals)
* **Multi-Agent Planner/Worker System**
* **AI-enhanced DevOps Bot** (CI/CD assistant)

