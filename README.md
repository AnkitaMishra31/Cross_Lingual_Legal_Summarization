# Cross-Lingual Legal Summarization: English → Hindi

## Evaluating Zero-Shot, Few-Shot and Structured Chain-of-Thought Prompting on MILDSum

This repository contains the code, generated summaries, evaluation results, and presentation for an exploratory study of **English-to-Hindi legal summarization** using the **MILDSum** dataset.

The study compares three prompting strategies:

1. **Zero-Shot Prompting**
2. **Few-Shot Prompting**
3. **Structured Chain-of-Thought (CoT) Prompting**

The main objective is not simply to determine which method obtains the highest automatic metric score, but to understand:

> **What did we learn about English-to-Hindi legal summarization from this experiment, and what evidence supports the conclusion?**

---

## 1. Research Objective

Legal summarization is a high-stakes generation task where a summary may appear fluent and semantically relevant while still containing a legally consequential error.

For example, changing:

- a court or government entity,
- a monetary amount,
- a quantity,
- a legal provision,
- the court's reasoning, or
- the final legal decision

can substantially change the meaning of a case.

Therefore, this study evaluates both:

- **Automatic similarity metrics**, and
- **Human/manual legal-quality assessment**.

The experiment investigates whether the prompting strategy that performs well according to ROUGE/BERTScore also produces better summaries when evaluated for factuality, legal correctness, faithfulness, coverage, and Hindi quality.

---

# 2. Dataset

The experiment uses the **MILDSum** dataset.

Dataset:
[Law-AI/MILDSum](https://github.com/Law-AI/MILDSum)

The assignment specifies the 10 samples available in:

```text
MILDSum/Data/MILDSum_Samples
