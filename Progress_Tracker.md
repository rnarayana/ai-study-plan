
# 📈 AI Architect Learning Progress Tracker

Use this file to track your **weekly learning progress** across the 1-year syllabus.  
You can mark tasks as ✅ (done), 🚧 (in progress), or ⏳ (pending).  

---
## ✅ Usage

* Mark each week when complete.
* Capture notes, blockers, or design decisions in a separate log.

- ⏳ Not Started  
- 🚧 In Progress  
- ✅ Completed
- 
---

## 📅 Weeks 0–4 — Foundations

| Week | Focus                                 | Deliverable                                   | Done |
| ---- | ------------------------------------- | --------------------------------------------- | ---- |
| 0    | Environment setup (.NET, Azure, SDKs) | Local dev environment ready                   |⏳    |
| 1    | ML/LLM overview for architects        | One-page ML/LLM intuition summary             |⏳    |
| 2    | LLM system patterns & risks           | Checklist (prod patterns + OWASP LLM Top-10)  |⏳    |
| 3    | Prompting, tokens, cost/latency       | Prompt experiments + token budget analysis    |⏳    |
| 4    | First .NET AI app (console/chat)      | Console chatbot using Microsoft.Extensions.AI |⏳    |

---

## 📅 Weeks 5–8 — Retrieval & RAG

| Week | Focus                             | Deliverable                            | Done |
| ---- | --------------------------------- | -------------------------------------- | ---- |
| 5    | RAG mental model                  | Self-drawn RAG pipeline diagram        | ☐    |
| 6    | Azure AI Search (vector + hybrid) | Working demo with hybrid search        | ☐    |
| 7    | Chunking & embedding quality      | Retrieval metrics logged (recall/nDCG) | ☐    |
| 8    | RAG API in .NET                   | Minimal API `/ask` endpoint            | ☐    |

---

## 📅 Weeks 9–12 — Evaluation, Security & Observability

| Week | Focus                                     | Deliverable                                    | Done |
| ---- | ----------------------------------------- | ---------------------------------------------- | ---- |
| 9    | Classical evals refresher                 | Error analysis on small dataset                | ☐    |
| 10   | LLM/RAG evaluation                        | Add Ragas/TruLens evals to API                 | ☐    |
| 11   | Security & abuse prevention               | Guardrails + prompt injection mitigations      | ☐    |
| 12   | Prod readiness (cost/latency/reliability) | Policies applied (streaming, retries, caching) | ☐    |

---

## 📅 Weeks 13–16 — Orchestration, Data & Governance

| Week | Focus                       | Deliverable                                  | Done |
| ---- | --------------------------- | -------------------------------------------- | ---- |
| 13   | Orchestration options       | Thin façade with provider swap               | ☐    |
| 14   | Data pipelines for RAG      | Ingestion pipeline (OCR/cleanup/PII removal) | ☐    |
| 15   | MLOps mindset               | CI/CD + monitoring sketch for AI feature     | ☐    |
| 16   | Governance & responsible AI | Checklist (runbooks, DR, cost, PII policies) | ☐    |

---

## 📅 Weeks 17–20 — Capstone

| Week | Focus                  | Deliverable                         | Done |
| ---- | ---------------------- | ----------------------------------- | ---- |
| 17   | Capstone design doc    | Scenario choice + KPI definitions   | ☐    |
| 18   | Capstone build         | Core system implemented             | ☐    |
| 19   | Hardening & load tests | Red-team results + load test report | ☐    |
| 20   | Launch & docs          | User guide + on-call playbook       | ☐    |

---

## 📦 Capstone Options

* Enterprise RAG service (retrieval + evals)
* Internal AI assistant (summaries, updates)
* Multi-agent planner/worker system
* AI DevOps bot (CI/CD assistant)

---

> Keep each week’s output small but production-oriented — **architecture checklists, runnable demos, and logged metrics** are more valuable than lengthy notes.
