---
name: lingo-grep
description: >
  Parse raw English text from sci-fi/literature, filter out domain-specific noise, 
  and extract high-value vocabulary mapped to AI Infrastructure and Cloud Native scenarios.
  Triggers on /lingo-grep <payload>. The model processes the text and outputs a strict 
  Markdown analysis report tailored to modern distributed systems engineering.
---

This skill is an LLM-driven linguistic parser and context translator. Unlike a pure code hook, the model itself must execute the noise filtering, feature extraction, and re-contextualization logic. When triggered via `/lingo-grep`, the model applies the defined AI Infra persona, maps extracted vocabulary to specific technical scenarios (e.g., GPU scheduling, NCCL timeouts), and returns a formatted Markdown table. No conversational filler or preamble is generated.

### TARGET AUDIENCE CONTEXT
- **Domain:** AI Infrastructure, LLM Inference, Cloud Native, Kubernetes.
- **Tech Stack:** K8s, vLLM, SGLang, Ray, Triton Inference Server, CUDA/NCCL, containerd, LeaderWorkerSet.
- **Daily Scenarios:** Optimizing inference latency (KV cache management, Radix Attention), troubleshooting distributed systems (GPU OOM, NCCL timeouts, resource conflicts), scheduling AI workloads, and PR reviews.

### INSTRUCTIONS
When triggered, execute these steps strictly on the provided payload:
1. **Noise Filtering:** IGNORE hard sci-fi, fantasy, or irrelevant domain jargon (e.g., *Astrophage*, theoretical physics, alien biology). Treat them as opaque variables.
2. **Feature Extraction:** Extract exactly **3 to 5** high-utility language components (phrasal verbs, idioms, transition phrases) conveying problem-solving, state reporting, or logical deduction.
3. **Re-contextualization:** Map each extracted component to the `TARGET AUDIENCE CONTEXT`. Do NOT use generic IT examples. Use hyper-specific AI Infra/K8s scenarios.
4. **Translation Accuracy:** The final column MUST provide the full Chinese translation of the generated English example sentence, NOT just the Chinese meaning of the component.

### OUTPUT FORMAT
Return strictly in the following Markdown structure WITHOUT any preamble:

### 📦 LingoGrep Analysis Report
* **Context Summary:** [1-sentence concise summary of the narrative payload]

| Component | Chinese Meaning | AI Infra / Cloud Native Example (English) | Example Translation |
| :--- | :--- | :--- | :--- |
| `[Word/Phrase]` | [Meaning] | `[Hyper-specific tech scenario example]` | [Full Chinese translation of the ENTIRE example sentence] |
