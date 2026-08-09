<h1 align="center">Marco Simoni</h1>

<p align="center">
  <b>Ph.D. in Artificial Intelligence — Sapienza University of Rome</b><br>
  Reinforcement Learning for LLM post-training · Foundation Models · AI for Cybersecurity
</p>

<p align="center">
  <a href="https://winstonsmith1897.github.io/"><img src="https://img.shields.io/badge/Website-000000?style=flat-square&logo=githubpages&logoColor=white" alt="Website"></a>
  <a href="https://scholar.google.com/citations?user=hhNQwfkAAAAJ"><img src="https://img.shields.io/badge/Google_Scholar-4285F4?style=flat-square&logo=googlescholar&logoColor=white" alt="Google Scholar"></a>
  <a href="https://www.linkedin.com/in/marcosimoniai/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="https://x.com/MarcoSimon21078"><img src="https://img.shields.io/badge/X-000000?style=flat-square&logo=x&logoColor=white" alt="X"></a>
  <a href="https://medium.com/@marco.simoni0711"><img src="https://img.shields.io/badge/Medium-000000?style=flat-square&logo=medium&logoColor=white" alt="Medium"></a>
  <a href="mailto:marco.simoni0711@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a>
</p>

---

## About

I work on **making language models reason reliably** — from the optimization algorithms that train them to the architectures that run them.

My Ph.D. research (Sapienza University of Rome, in collaboration with **CNR-IIT**) focused on reinforcement learning for LLM post-training and on adapting foundation models to high-stakes domains, primarily cybersecurity. I design policy optimization methods that remain stable without a reference model, build LLM architectures from scratch, and ship retrieval and graph-reasoning systems that outperform frontier models on domain-specific tasks.

I care about results that hold up under scrutiny: reproducible code, honest baselines, and benchmarks that measure what they claim to measure.

**Currently working on:** objective bias in group-based RL, KL-free policy optimization, and efficient inference for reasoning models.

---

## Research Focus

**RL for LLM Alignment** — Policy optimization (PPO, GRPO, GTPO) for reasoning. Diagnosing and fixing gradient conflict, entropy collapse, and hidden objective biases in group-relative methods.

**LLM Architecture & Efficiency** — Transformer design from first principles: Sparse MoE, RoPE, GQA, sliding-window attention, static KV caching. Throughput and memory as first-class design constraints.

**Retrieval & Graph Reasoning** — Multi-retriever RAG systems and executable reasoning over knowledge graphs for domains where hallucination is unacceptable.

**AI for Cybersecurity** — Foundation models for attack prediction, LLM-driven vulnerability detection, and knowledge-graph modeling of Cyber Threat Intelligence (MITRE ATT&CK, CAPEC, MBC, CVE).

---

## Selected Projects

### [GTPO — Group-relative Trajectory-based Policy Optimization](https://github.com/winstonsmith1897/GTPO) &nbsp;<img src="https://img.shields.io/badge/TACL-accepted-2ea44f?style=flat-square" alt="Accepted at TACL">

A KL-free policy optimization algorithm for LLM post-training. GTPO identifies **conflict tokens** — tokens appearing at the same position across completions with opposite rewards — and protects them by skipping negative updates while amplifying positive ones. It additionally filters completions whose entropy exceeds a provable threshold, preventing policy collapse without a reference model.

| Property | GRPO | GTPO |
|---|---|---|
| Reference model required | Yes (KL term) | **No** |
| Gradient conflict handling | None | Conflict masking |
| Entropy control | Implicit via KL | Provable threshold filter |
| Reasoning gain (OOD: AIME'24/'25, AMC) | baseline | **up to +15%** |

Evaluated on GSM8K, MATH and AIME2024, GTPO consistently outperforms both GRPO and SFT across settings. **Accepted at TACL.**
📄 [arXiv:2508.03772](https://arxiv.org/abs/2508.03772) · ✍️ [Blog post](https://medium.com/@marco.simoni0711/gtpo-vs-grpo-a-smarter-path-to-stable-reasoning-llms-3f51bc0b58c1)

---

### [MoRSE — Mixture of RAG Security Experts](https://github.com/Mixture-of-RAGs-Security-Experts/MoRSE)

The first specialized RAG assistant for cybersecurity: a dual-cascaded framework with **7 parallel retrievers**, each specialized on a distinct knowledge source (MITRE, CVE, Metasploit, ExploitDB). Knowledge bases update in real time — no retraining required.

**Result:** +15% response accuracy over GPT-4 on general and multi-hop cybersecurity questions.
📄 [ACM SAC 2025](https://dl.acm.org/doi/10.1145/3672608.3707898) · [arXiv:2407.15748](https://arxiv.org/abs/2407.15748)

---

### [TITAN — Graph-Executable Reasoning for Cyber Threat Intelligence](https://github.com/cti-graph-reasoner/TITAN)

Bridges natural-language threat queries and executable reasoning over a structured knowledge graph. An LLM **path planner** predicts relational paths and starting entities; a **graph executor** traverses them over a modified MITRE knowledge graph to retrieve the answer set. Released with the **TITAN Dataset**: 88,209 examples (74,258 train / 13,951 test) pairing questions with executable reasoning paths and step-by-step Chain-of-Thought explanations.

📄 [arXiv:2510.14670](https://arxiv.org/abs/2510.14670)

---

### [DantinoX — LLM from Scratch in JAX/Flax](https://github.com/winstonsmith1897/DantinoX)

A full LLM architecture implemented from first principles: **Sparse Mixture-of-Experts, RoPE, attention gating, GQA**. Hardware throughput maximized via sliding-window attention, static KV caching and gradient checkpointing. Built to make every architectural trade-off explicit and measurable.

---

## Publications

Metrics: **215 citations · h-index 6 · i10-index 4** ([Google Scholar](https://scholar.google.com/citations?user=hhNQwfkAAAAJ))

### 2026

- **GTPO: Stabilizing Group Relative Policy Optimization via Gradient and Entropy Control** — **M. Simoni**, A. Fontana, G. Rossolini, A. Saracino, P. Mori. *Transactions of the Association for Computational Linguistics (TACL)*. [arXiv:2508.03772](https://arxiv.org/abs/2508.03772) · [code](https://github.com/winstonsmith1897/GTPO)
- **On the Hidden Objective Biases of Group-based Reinforcement Learning** — A. Fontana, **M. Simoni**, G. Rossolini, P. Mori, A. Saracino. *ACL 2026*.
- **Concise Thoughts: Impact of Output Length on LLM Reasoning and Cost** — S. Nayab, G. Rossolini, **M. Simoni**, A. Saracino, G. Buttazzo, et al. *Information Sciences*. `123 citations`
- **Toward Reliable and Adaptive Large Language Models in the Cybersecurity Domain** — **M. Simoni**. *Ph.D. Thesis, Sapienza University of Rome*.

### 2025

- **TITAN: Graph-Executable Reasoning for Cyber Threat Intelligence** — **M. Simoni**, A. Fontana, A. Saracino, P. Mori. [arXiv:2510.14670](https://arxiv.org/abs/2510.14670)
- **Improving LLM Reasoning for Vulnerability Detection via Group Relative Policy Optimization** — **M. Simoni**\*, A. Fontana\*, G. Rossolini, A. Saracino. [arXiv:2507.03051](https://arxiv.org/abs/2507.03051)
- **KGQuest: Template-Driven QA Generation from Knowledge Graphs with LLM-Based Refinement** — S. Nayab, **M. Simoni**, G. Rossolini, A. Saracino. [arXiv:2511.11258](https://arxiv.org/abs/2511.11258)
- **MoRSE: Bridging the Gap in Cybersecurity Expertise with Retrieval Augmented Generation** — **M. Simoni**, A. Saracino, V. P., M. Conti. *ACM/SIGAPP SAC 2025*, 1213–1222. `33 citations`
- **On-Device Derivation of IoT Usage Control Policies: Automating U-XACML Policy Generation from Natural Language with LLMs** — L. Alajramy, **M. Simoni**, M. Rasori, A. Saracino, P. Mori. *Future Generation Computer Systems*.
- **Leveraging Knowledge Graphs and LLMs for Structured Generation of Misinformation** — S. Nayab, **M. Simoni**, G. Rossolini. *ARES 2025*, 334–350.
- **Unmasking Model Behavior: How LLMs Reason on Vulnerability Detection** — A. Fontana, **M. Simoni**. *ARES 2025*, 316–333.
- **MATRIX: A Comprehensive Graph-Based Framework for Malware Analysis and Threat Research** — **M. Simoni**, A. Saracino. *SECRYPT 2025*.

### 2024 and earlier

- **Cybersecurity with LLMs and RAGs: Challenges and Innovations** — **M. Simoni**, A. Saracino. *SecureComm 2024*.
- **Graph-Based Android Malware Detection and Categorization through BERT Transformer** — **M. Simoni**, A. Saracino. *ARES 2023*. `19 citations`

<sub>\* Equal contribution.</sub>

---

## Research Experience

**CNR-IIT & NetGroup** — *AI Researcher*
Engineered an LLM-driven framework automating the translation of natural-language requirements into structured XACML / U-XACML access control policies, deployable on-device for IoT and smart-home environments.

**Horus Project** — *AI Researcher*
Architected and trained a Transformer-based foundation model from scratch for proactive cyber-attack prediction.

---

## Technical Writing

- [**GTPO vs GRPO: A Smarter Path to Stable Reasoning LLMs**](https://medium.com/@marco.simoni0711/gtpo-vs-grpo-a-smarter-path-to-stable-reasoning-llms-3f51bc0b58c1) — How conflict masks and entropy regularization address GRPO's gradient conflicts and policy collapse.
- [**REINFORCE vs. Posterior Token Targets: Two Paths to Steering Language Models**](https://medium.com/@marco.simoni0711/reinforce-vs-posterior-token-targets-two-paths-to-steering-language-models-42892f15cd70) — The core mechanics of reshaping per-step token probabilities to steer model behavior.

---

## Stack

**Training & Serving** &nbsp;`PyTorch` `JAX/Flax` `TensorFlow` `HuggingFace` `TRL` `Unsloth` `vLLM` `LangChain`

**Security & Data** &nbsp;`MITRE ATT&CK` `CAPEC` `MBC` `NetworkX` `Neo4j` `MongoDB` `SQL` `Metasploit` `pwndbg`

**Infrastructure** &nbsp;`Python` `Docker` `Linux` `Git`

---

<p align="center">
  <sub>Open to research collaborations on RL for post-training, reasoning, and trustworthy LLMs.</sub><br>
  <sub><a href="mailto:marco.simoni0711@gmail.com">marco.simoni0711@gmail.com</a></sub>
</p>
