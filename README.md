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

## Quick Access

| Deliverable | File |
|---|---|
| Experimental Notebook | `Cross_Lingual.ipynb` |
| Generated Summaries | `generated_summaries.csv` |
| Automatic Evaluation | `automatic_eval_per_case.csv` |
| Manual Evaluation | `manual_evaluation.csv` |
| Error Analysis | `error_analysis.csv` |
| Metric vs Manual Comparison | `metric_vs_manual_comparison.xlsx` |
| Final Presentation | `Cross_Lingual_Legal_Summarization_Final.pptx` |

## Key Results

The experiment produced different rankings depending on the evaluation method.

### Automatic Evaluation

- **Few-shot** achieved the highest ROUGE-1, ROUGE-2, and ROUGE-L scores.
- **Zero-shot** achieved the highest BERTScore-F1.
- Therefore, ROUGE and BERTScore did not identify the same best-performing method.

### Manual Evaluation

| Method | Overall Manual Score |
|---|---:|
| Structured CoT | **2.24 / 5** |
| Zero-shot | **2.18 / 5** |
| Few-shot | **1.98 / 5** |

Structured CoT obtained the highest mean manual score, but the difference from Zero-shot was only 0.06 points.

### Main Finding

The experiment does not show a universal winner among the three prompting strategies. More importantly, case-level analysis revealed factual, legal, terminology, and omission errors that were not fully captured by automatic similarity metrics.

Therefore, automatic metrics should be treated as complementary evidence rather than as the sole measure of legal summarization quality.

## Generation Failure

Few-shot generation was attempted for all 10 MILDSum cases.

However, the Few-shot output for `Sample_5` was invalid/empty and was therefore treated as a generation failure.

Consequently:

- Few-shot generation was attempted for 10 cases.
- 9 valid Few-shot outputs were available for manual evaluation.
- Sample_5 was marked as N/A rather than assigning an artificial quality score.
- The failed output was not counted as a hallucination, omission, or other content error.

Therefore, Few-shot manual/error-analysis results use `n = 9`, while Zero-shot and Structured CoT use `n = 10`.

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
