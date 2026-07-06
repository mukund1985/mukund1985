<h2 align="left">Mukund Pandey</h2>

**Staff ML Engineer · Meta**

Building agentic AI systems, LLM eval infrastructure, and XAI pipelines at billion-user scale. Current focus: making AI systems that can explain themselves, fail safely, and be trusted in production.

---

### What I work on

- **Agentic AI** — multi-step agent architectures, tool-use, planning, 
  and safety guardrails at scale
- **LLM Eval Infrastructure** — consistency, hallucination detection, 
  factual grounding, response drift
- **LLM Inference Infrastructure** — high-throughput model serving, 
  torch.compile optimisation, KV cache efficiency, production latency SLAs
- **MLOps & Observability** — drift detection, model monitoring, 
  evaluation pipelines, contributor to evidentlyai/evidently
- **Explainable AI (XAI)** — decision explainability hooks, 
  counterfactual reasoning, causal attribution
- **Security ML** — real-time risk scoring, access intelligence, 
  anomaly detection at billion-event scale

---

### Research

**[Mechanistic Interpretability of Hybrid SSM-Attention Models: Induction, Factual Recall, and Weight-Tied Attention in Zamba2-1.2B](https://github.com/mukund1985/mech-interp-hybrid-ssm)** *(arXiv preprint, under review)*

First mechanistic analysis of weight-tied attention in hybrid SSM architectures. Introduces the SSM Induction Score (SSMI) and shows that Zamba2-1.2B's 6 shared-attention layers implement functionally distinct computations (induction heads at layers 5/11, induction completion at layer 23, factual recall at layer 35) despite identical QKV weights — driven entirely by residual stream context. Code: [mech-interp-hybrid-ssm](https://github.com/mukund1985/mech-interp-hybrid-ssm).

**[Evaluating Agentic AI in the Wild: Failure Modes, Drift Patterns, and a Production Evaluation Framework](https://arxiv.org/abs/2605.01604)**

[![arXiv](https://img.shields.io/badge/arXiv-2605.01604-b31b1b.svg)](https://arxiv.org/abs/2605.01604)
[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.19947138-blue.svg)](https://doi.org/10.5281/zenodo.19947138)

Identifies 7 failure modes in production agentic AI systems and introduces PAEF (Production Agentic Evaluation Framework) — validated on four controlled experiments. Reference implementation: [llm-eval-toolkit](https://github.com/mukund1985/llm-eval-toolkit).

---

### Open source

**My repos**
| Repo | Description |
|---|---|
| [mech-interp-hybrid-ssm](https://github.com/mukund1985/mech-interp-hybrid-ssm) | Mechanistic interpretability of Zamba2-1.2B — SSMI, copy scores, logit-lens factual recall across 38 layers |
| [llm-eval-toolkit](https://github.com/mukund1985/llm-eval-toolkit) | Production-grade framework for evaluating LLM agent outputs — consistency, grounding, hallucination, drift |
| [agentic-safety-patterns](https://github.com/mukund1985/agentic-safety-patterns) | Pattern library for safe agentic systems — circuit breakers, explainability hooks, rollback, audit logging |
| [retrieval-ranking-eval](https://github.com/mukund1985/retrieval-ranking-eval) | Dense retrieval + cross-encoder reranking pipeline benchmarked on BEIR datasets — NDCG@K, Recall@K, MRR |
| [QuantumAI-IntradayRiskDemo](https://github.com/mukund1985/QuantumAI-IntradayRiskDemo) | Intraday risk pipeline: LSTM volatility forecasting + quantum-inspired QUBO/D-Wave portfolio optimisation |

**Upstream contributions**
| Repo | What |
|---|---|
| [TransformerLensOrg/TransformerLens](https://github.com/TransformerLensOrg/TransformerLens) | PR #1486 open — Zamba2Bridge adapter for Zamba2-1.2B hybrid SSM; exposes hook_in/hook_out on all 38 layers + attention hooks on 6 hybrid layers; enables mechanistic interpretability on Mamba-2/attention hybrid models |
| [TransformerLensOrg/TransformerLens](https://github.com/TransformerLensOrg/TransformerLens) | PR #1434 **merged** ✅ — NemotronH hybrid Mamba2-Transformer adapter (nvidia/Nemotron-H-8B/47B); SSMBlockBridge + optional Mamba submodules handle 4 heterogeneous layer types; 52 unit tests |
| [TransformerLensOrg/TransformerLens](https://github.com/TransformerLensOrg/TransformerLens) | PR #1408 **merged** ✅ — DeepSeek-V2 / V2-Lite / Coder-V2 architecture adapter; handles complex-exponential RoPE, optional Q LoRA path (V2-Lite), and unhookable gate; 17 integration tests |
| [TransformerLensOrg/TransformerLens](https://github.com/TransformerLensOrg/TransformerLens) | PR #1396 **merged** ✅ — direct path patching implementation (`get_act_patch_direct_path`), closes issue #111 opened by Neel Nanda in 2022; supports HookedTransformer and TransformerBridge, full test suite |
| [TransformerLensOrg/TransformerLens](https://github.com/TransformerLensOrg/TransformerLens) | PR #1399 **merged** ✅ — adapter unit tests for Phi-3 and Granite/GraniteMoe (55 tests), part of issue #1302 |
| [evidentlyai/evidently](https://github.com/evidentlyai/evidently) | PR #1863 open — ROUGE score descriptor (rouge1/2/L, F/P/R variants, NaN-safe; 737 lines, 31 tests); closes issue #1318 |
| [evidentlyai/evidently](https://github.com/evidentlyai/evidently) | PR #1862 open — fixes silent data corruption in KL-divergence drift scoring; replaces hardcoded fill value with data-relative min_nonzero/10 |
| [huggingface/trl](https://github.com/huggingface/trl) | PR #6120 open — adds `save_value_model` flag to PPOConfig; persists critic checkpoint alongside policy, making PPO runs resumable |
| [huggingface/trl](https://github.com/huggingface/trl) | PR #6121 open — fixes mathematically-impossible negative entropy in PPO trainer; masks INVALID_LOGPROB padding tokens |
| [huggingface/trl](https://github.com/huggingface/trl) | PR #6122 open — fixes OnlineDPOTrainer crash on eval_strategy=steps; adds prediction_step override |
| [huggingface/trl](https://github.com/huggingface/trl) | PR #6123 open — implements Adaptive Beta-DPO (arXiv:2407.08639); per-batch beta scaling via preference margin EMA |
| [huggingface/swift-transformers](https://github.com/huggingface/swift-transformers) | PR #370 open — fixes offline-mode crash; path canonicalization bug with `..` components in downloadBase |
| [huggingface/swift-transformers](https://github.com/huggingface/swift-transformers) | PR #371 open — fixes fatal crash on Task cancellation; replaces `try!` with `async throws` across CoreML generation call chain |
| [huggingface/swift-transformers](https://github.com/huggingface/swift-transformers) | PR #372 open — adds `encodeWithOffsets()` returning character-span offsets per token, matching Python `return_offsets_mapping=True` |
| [vllm-project/vllm](https://github.com/vllm-project/vllm) | PR #46068 open — reject invalid negative values for `max_logprobs` and `long_prefill_token_threshold` via Pydantic field validators; closes issue #43985 |
| [vllm-project/vllm](https://github.com/vllm-project/vllm) | PR #41381 open — torch.compile config hash typing cleanups + cache_key_factors debug expansion |

---

### Stack

<!-- ML / AI -->
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)

<!-- Eval / Ops -->
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Ray](https://img.shields.io/badge/Ray-028CF0?style=flat-square&logo=ray&logoColor=white)

<!-- Infra / Cloud -->
![Apache Spark](https://img.shields.io/badge/Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![GCP](https://img.shields.io/badge/GCP-4285F4?style=flat-square&logo=googlecloud&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)

---

### Find me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/mukund-pandey/)
[![Medium](https://img.shields.io/badge/Medium-12100E?style=flat-square&logo=medium&logoColor=white)](https://mukund-pandey.medium.com/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/mukund1985)

---

### GitHub Stats

![GitHub Stats](https://github-readme-stats-swart-five-12.vercel.app/api?username=mukund1985&show_icons=true&theme=default&hide_border=true&count_private=true)
![Top Languages](https://github-readme-stats-swart-five-12.vercel.app/api/top-langs/?username=mukund1985&layout=compact&hide_border=true&langs_count=6&hide=jupyter%20notebook,batchfile,shell,c,hcl)
