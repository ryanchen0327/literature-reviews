---
dg-publish: true
category: literaturenote
tags: Computer Science - Computation and Language
citekey: honovichTRUEReevaluatingFactual2022
status: unread
dateread:
---
# Notes

# 📊 Survey on Factual Consistency Evaluation

### 📚 Overview
- **Databases reviewed**: 11 factual consistency datasets
- **Metrics surveyed**: 10 evaluation methods

---

## 🧮 Evaluation Metrics

### 🔹 N-gram Based (Weak Correlation with Factual Consistency)
- BLEU
- ROUGE
- Token F1

### 🔹 Model-Based
- **BERTScore**
- **BLEURT**
- **FactCC**
- **BARTScore**
- **CTC**

### 🔹 NLI-Based
- **ANLI** (T5-11B fine-tuned on ANLI)
- **SUMMAC**

### 🔹 QG-QA Based
- **Q²**
- **QuestEval**

---

### 🔍 Key Observations

- **NLI-based methods** (ANLI, SCZS17, Q²) **outperform** other categories.
- All methods show **performance degradation** on **longer contexts**.
- **Metric combinations** yield **better results** than using individual metrics.
- **Larger models** lead to improved **ROC AUC**.

---

## 🧪 Evaluation of Metric Failures

### A. ❗️“Hard” Examples: All Metrics Failed
- Reviewed **80 examples** with **complete metric-human disagreement**
- Found **35/80 (44%)** had **annotation errors** (human label likely incorrect)

### B. ⚠️ Moderately Hard Examples: 1–2 Metrics Failed
- Reviewed **100 examples**
- Found **27/100 (27%)** annotation errors

### C. ✅ Random Baseline
- Randomly sampled **100 examples**
- Found only **10/100 (10%)** annotation errors

---

### 🧠 Insight
> **Automatic metrics can outperform human annotators** in reliability for ambiguous or complex cases.

📌 Use **high-confidence metric disagreements** as a signal to **clean or audit human labels**.

# Key questions

How to address degradation on long input. 
Do we need a more consistent annotation scheme for metric comparison?

---
> [!Cite]
> Honovich, O., Aharoni, R., Herzig, J., Taitelbaum, H., Kukliansy, D., Cohen, V., Scialom, T., Szpektor, I., Hassidim, A., & Matias, Y. (2022). _TRUE: Re-evaluating Factual Consistency Evaluation_ (No. arXiv:2204.04991). arXiv. [https://doi.org/10.48550/arXiv.2204.04991](https://doi.org/10.48550/arXiv.2204.04991)

> [!Synth]
> **Contribution**::  
>   
> **Related**:: 

> [!Metadata]
> **Authors**::Honovich, Or, Aharoni, Roee, Herzig, Jonathan, Taitelbaum, Hagai, Kukliansy, Doron, Cohen, Vered, Scialom, Thomas, Szpektor, Idan, Hassidim, Avinatan, Matias, Yossi
> **Title**:: TRUE: Re-evaluating Factual Consistency Evaluation  
> **Year**:: 2022  
> **Citekey**:: honovichTRUEReevaluatingFactual2022> **Item Type**:: preprint> **DOI**:: 10.48550/arXiv.2204.04991

> [!Link]
> [Preprint PDF](file:///Users/ryanchen/Zotero/storage/CG7N7EGZ/Honovich%20et%20al.%20-%202022%20-%20TRUE%20Re-evaluating%20Factual%20Consistency%20Evaluation.pdf)

> [!Abstract]
> Grounded text generation systems often generate text that contains factual inconsistencies, hindering their real-world applicability. Automatic factual consistency evaluation may help alleviate this limitation by accelerating evaluation cycles, filtering inconsistent outputs and augmenting training data. While attracting increasing attention, such evaluation metrics are usually developed and evaluated in silo for a single task or dataset, slowing their adoption. Moreover, previous meta-evaluation protocols focused on system-level correlations with human annotations, which leave the example-level accuracy of such metrics unclear. In this work, we introduce TRUE: a comprehensive survey and assessment of factual consistency metrics on a standardized collection of existing texts from diverse tasks, manually annotated for factual consistency. Our standardization enables an example-level meta-evaluation protocol that is more actionable and interpretable than previously reported correlations, yielding clearer quality measures. Across diverse state-of-the-art metrics and 11 datasets we find that large-scale NLI and question generation-and-answering-based approaches achieve strong and complementary results. We recommend those methods as a starting point for model and metric developers, and hope TRUE will foster progress towards even better evaluation methods.
---

# Annotations

### Imported: 2025-06-03 2:56 pm



