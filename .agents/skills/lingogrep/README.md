# lingo-grep

Extract AI Infra vocab from sci-fi text. Drop noise. Map to real engineering context.

## What it does

Generates a vocabulary report in a strict Markdown table. Drops hard sci-fi jargon (e.g., *Astrophage*). Extracts 3-5 high-value idiomatic phrases. Maps them directly to AI inference and K8s scenarios (vLLM, NCCL, etc.). Includes exact English tech examples and full Chinese translations.

Output only — no preamble, no conversational filler, no generic IT examples.

## How to invoke

```
/lingo-grep <payload>
```

Also triggers on "parse this", "extract vocab", "analyze snippet".

## Example output

```markdown
### 📦 LingoGrep Analysis Report
* **Context Summary:** Narrator wakes up and tests system logic.

| Component | Chinese Meaning | AI Infra / Cloud Native Example (English) | Example Translation |
| :--- | :--- | :--- | :--- |
| `I'm guessing` | 我猜想 / 推测 | `I'm guessing the NCCL timeout is caused by a bad node.` | 我猜想 NCCL 超时是由故障节点引起的。 |
| `drift off` | 进入休眠 | `When traffic drops, the pod can drift off under KEDA.` | 当流量下降时，Pod 可以在 KEDA 控制下进入休眠。 |
