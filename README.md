# Cross-Lingual Legal Summarization: Evaluating Zero-Shot, Few-Shot, and Structured CoT Prompting

## Overview

This project investigates **English-to-Hindi legal summarization** using the **MILDSum** dataset. The main objective is to evaluate how different prompting strategies affect the quality of Hindi legal summaries generated from English court judgments.

Three prompting strategies are compared using the same instruction-tuned language model:

1. **Zero-shot prompting**
2. **Few-shot prompting**
3. **Structured Chain-of-Thought (CoT) prompting**

The experiment evaluates the generated summaries using both:

- **Automatic metrics:** ROUGE-1, ROUGE-2, ROUGE-L, and BERTScore-F1
- **Manual evaluation:** Factuality, Coverage, Legal Correctness, Faithfulness, and Hindi Quality
- **Error analysis:** Hallucination, important omissions, wrong facts, wrong legal conclusions, translation/language errors, and incorrect legal terminology

The experiment uses **10 MILDSum samples** and is intended as a small exploratory evaluation rather than a statistically generalizable benchmark.

---

## Research Question

> **What did we learn about English-to-Hindi legal summarization from this experiment, and what evidence supports the conclusion?**

More specifically:

- Does few-shot prompting improve legal summarization compared with zero-shot prompting?
- Does structured reasoning improve factual and legal reliability?
- Do automatic metrics such as ROUGE and BERTScore agree with manual legal evaluation?
- What types of errors occur across the three prompting strategies?
- Can a summary obtain a good automatic score while still containing a legally important error?

---

## Objectives

The main objectives of this project are:

- To generate Hindi summaries of English legal judgments.
- To compare zero-shot, few-shot, and structured CoT prompting.
- To evaluate summaries using standard automatic summarization metrics.
- To perform manual evaluation specifically considering legal-domain requirements.
- To identify common factual, legal, linguistic, and terminology-related errors.
- To investigate disagreements between automatic metrics and human/manual evaluation.
- To analyze representative cases in detail.
- To understand why automatic similarity metrics alone may not be sufficient for legal summarization.

---

# Dataset

## MILDSum

The experiment uses the **MILDSum** dataset for multilingual legal document summarization.

Official repository:

https://github.com/Law-AI/MILDSum

For this assignment, the following directory was used:

https://github.com/Law-AI/MILDSum/tree/main/Data/MILDSum_Samples

Each sample contains:

- `EN_Judgment.txt` — English legal judgment
- `EN_Summary.txt` — English reference summary
- `HI_Summary.txt` — Hindi reference summary

### Experimental Input and Reference

For every case:

```text
Input:
English Judgment

Reference:
Hindi Summary
