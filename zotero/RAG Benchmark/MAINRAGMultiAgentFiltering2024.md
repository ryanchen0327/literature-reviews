---
dg-publish: true
category: literaturenote
tags: Computer Science - Computation and Language, Computer Science - Information Retrieval
citekey: changMAINRAGMultiAgentFiltering2024
status: unread
dateread:
---
# Notes

# 📄 Document Ordering and Reranking Notes

- **Document ordering** helps the LLM produce **more desirable results**.  
  → 📌 Consider **improving the reranker** to better leverage this effect.

---

### 📊 Relevance Distribution Insight

- In cases of a **skewed relevance distribution** (i.e., only a few documents are truly relevant), the **score threshold** for document selection should be **adjusted accordingly**.
- However, in **OpenScholar**, the current setup selects a fixed `top_n` number of papers, **regardless of distribution skew**.

---

### 🧪 Retrieval Improvements

- Added **filters** for:
  - The **initially retrieved** documents
  - The **reflection-retrieved** documents

- Added **more data sources** for **reflection retrieval**:
  - 🧠 This leads to **significantly more documents** being retrieved
  - ✅ Thus, a **stricter threshold** is now applied to maintain precision

---

### 🔗 Codebase

GitHub Repository:  
👉 [OpenScholarForSciFy](https://github.com/ryanchen0327/OpenScholarForSciFy)


# Key questions



---
> [!Cite]
> Chang, C.-Y., Jiang, Z., Rakesh, V., Pan, M., Yeh, C.-C. M., Wang, G., Hu, M., Xu, Z., Zheng, Y., Das, M., & Zou, N. (2024). _MAIN-RAG: Multi-Agent Filtering Retrieval-Augmented Generation_ (No. arXiv:2501.00332). arXiv. [https://doi.org/10.48550/arXiv.2501.00332](https://doi.org/10.48550/arXiv.2501.00332)

> [!Synth]
> **Contribution**::  
>   
> **Related**:: 

> [!Metadata]
> **Authors**::Chang, Chia-Yuan, Jiang, Zhimeng, Rakesh, Vineeth, Pan, Menghai, Yeh, Chin-Chia Michael, Wang, Guanchu, Hu, Mingzhi, Xu, Zhichao, Zheng, Yan, Das, Mahashweta, Zou, Na
> **Title**:: MAIN-RAG: Multi-Agent Filtering Retrieval-Augmented Generation  
> **Year**:: 2024  
> **Citekey**:: changMAINRAGMultiAgentFiltering2024> **Item Type**:: preprint> **DOI**:: 10.48550/arXiv.2501.00332

> [!Link]
> [Full Text PDF](file:///Users/ryanchen/Zotero/storage/7XSJL482/Chang%20等%20-%202024%20-%20MAIN-RAG%20Multi-Agent%20Filtering%20Retrieval-Augmented%20Generation.pdf)

> [!Abstract]
> Large Language Models (LLMs) are becoming essential tools for various natural language processing tasks but often suffer from generating outdated or incorrect information. Retrieval-Augmented Generation (RAG) addresses this issue by incorporating external, real-time information retrieval to ground LLM responses. However, the existing RAG systems frequently struggle with the quality of retrieval documents, as irrelevant or noisy documents degrade performance, increase computational overhead, and undermine response reliability. To tackle this problem, we propose Multi-Agent Filtering Retrieval-Augmented Generation (MAIN-RAG), a training-free RAG framework that leverages multiple LLM agents to collaboratively filter and score retrieved documents. Specifically, MAIN-RAG introduces an adaptive filtering mechanism that dynamically adjusts the relevance filtering threshold based on score distributions, effectively minimizing noise while maintaining high recall of relevant documents. The proposed approach leverages inter-agent consensus to ensure robust document selection without requiring additional training data or fine-tuning. Experimental results across four QA benchmarks demonstrate that MAIN-RAG consistently outperforms traditional RAG approaches, achieving a 2-11% improvement in answer accuracy while reducing the number of irrelevant retrieved documents. Quantitative analysis further reveals that our approach achieves superior response consistency and answer accuracy over baseline methods, offering a competitive and practical alternative to training-based solutions.
---

# Annotations

### Imported: 2025-06-03 3:14 pm


<mark style="background-color: #ff6666">Quote</mark>  
> MAIN-RAG introduces an adaptive filtering mechanism that dynamically adjusts the relevance filtering threshold based on score distributions, effectively minimizing noise while maintaining high recall of relevant documents.


<mark style="background-color: #ff6666">Quote</mark>  
> collaborative multi-agent approach where multiple LLM agents filter and score retrieved documents.





<mark style="background-color: #ffd400">Quote</mark>  
> first is Self-RAG (Asai et al., 2024b), a var




