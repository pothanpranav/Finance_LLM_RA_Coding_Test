# Finance_LLM_RA_Coding_Test

## Beyond the Answer — Probing Numerical Reasoning in Financial LLMs

This repository contains my submission for the Finance RA Coding Test based on the FinQA dataset.

The project investigates numerical reasoning failures in small language models for financial question answering using Qwen2.5-0.5B-Instruct.

---

# Objective

The goal of this project is not simply to maximize accuracy, but to analyze:

- why financial reasoning models fail,
- what types of reasoning errors occur,
- how retrieval affects reasoning quality,
- and whether evidence grounding can improve reliability.

The project studies:
- symbolic financial reasoning,
- retrieval grounding,
- context sensitivity,
- and reasoning-program fidelity.

---

# Dataset

Dataset used:
- FinQA
- 8,281 financial QA examples
- S&P 500 earnings reports
- Numerical reasoning over tables and text

Dataset link:
https://github.com/czyssrs/FinQA

---

# Model Used

- Qwen2.5-0.5B-Instruct
- HuggingFace Transformers
- Evaluated on 100 FinQA test examples

Model link:
https://huggingface.co/Qwen

---

# Repository Structure

| File | Description |
|---|---|
| `finance_llm_assignment.ipynb` | Main notebook containing all experiments and analysis |
| `full_context.json` | Full-context dataset |
| `table_only_context.json` | Table-only dataset |
| `text_only_context.json` | Text-only dataset |
| `full_context_outputs.json` | Outputs using full context |
| `table_only_outputs.json` | Outputs using table-only context |
| `text_only_outputs.json` | Outputs using text-only context |
| `no_evidence_grounded_outputs.json` | Outputs without evidence-grounded retrieval |
| `evidence_grounded_outputs.json` | Outputs using evidence-grounded retrieval |

---

# Key Experiments

## Layer 1 — Dataset and Reasoning Analysis

Studied:
- FinQA program structures,
- evidence-source distribution,
- percentage reasoning patterns,
- symbolic execution,
- and execution vs program accuracy.

---

## Layer 2 — Qwen Financial Reasoning Pipeline

Built a reasoning pipeline that:
1. formats financial tables and text,
2. prompts Qwen2.5-0.5B-Instruct,
3. generates reasoning programs,
4. extracts final answers,
5. evaluates execution accuracy.

Conducted:
- error taxonomy analysis,
- context sensitivity experiments,
- and program-vs-answer evaluation.

---

## Layer 3 — Evidence-Grounded Retrieval

Implemented an evidence-grounded retrieval strategy that:
- filters irrelevant context,
- prioritizes gold evidence,
- reduces retrieval ambiguity,
- and improves reasoning stability.

Key insight:
> Small financial language models fail more from evidence misalignment than from arithmetic inability.

---

# Error Taxonomy

Model failures were categorized into:
- Retrieval Errors
- Operation Errors
- Order Errors
- Hallucination Errors
- Rounding / Formatting Errors

Retrieval failures were found to be the dominant failure mode.

---

# Main Findings

- Financial reasoning failures often originate before arithmetic execution.
- Tables are more important than text for numerical grounding.
- Mixed-evidence questions remain challenging.
- Execution accuracy can exceed program accuracy.
- Evidence-grounded retrieval improves reasoning reliability without fine-tuning.

---

## AI Usage Disclosure

The following ChatGPT transcript(s) were used during the development of this assignment:

- https://chatgpt.com/share/6a0308a9-02b0-8324-866a-b54a56c6ae2f
---
# References

1. FinQA Dataset  
   https://github.com/czyssrs/FinQA

2. FinQANet Paper  
   https://arxiv.org/abs/2109.00122

3. Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks  
   https://arxiv.org/abs/2005.11401

4. Hierarchical Retrieval with Evidence Curation for Open-Domain Financial Question Answering  
   https://arxiv.org/abs/2505.20368

---

# Author

Pranav Pothan
