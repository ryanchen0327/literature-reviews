---
dg-publish: true
category: literaturenote
tags:
  - Computer
  - Science
  - "-"
  - Computation
  - and
  - Language
  - Computer
  - Science
  - "-"
  - Artificial
  - Intelligence
  - Computer
  - Science
  - "-"
  - Information
  - Retrieval
citekey: izacardUnsupervisedDenseInformation2022a
status: read
dateread:
---
# Notes

## Cross-Encoder vs Bi-Encoder: Unsupervised Contrastive Learning

### 🔧 Unsupervised Training Setup

#### 🟢 Positive Pair Generation
- **Inverse Cloze Task**:  
  Format: `aba`  
  - Query `q`: `a...a`  
  - Key `k+`: `b`

- **Independent Cropping (Symmetric Strategy)**:  
  - Both `q` and `k+` are of the same length  
  - Overlapping spans encourage exact matching  
  - **Shorter queries** make the task *more difficult*, encouraging the model to learn better representations

#### 🔴 Negative Pair Generation
- **In-Batch Negatives**:  
  - Requires **extremely large batch sizes** to be effective

- **Cross-Batch Negatives (Momentum Encoder)**:
  - Problem: Last batch contains outdated representations  
  - Solution (MoCo): Use a momentum update for key encoder:  
    \[
    \theta_k \leftarrow m \cdot \theta_k + (1 - m) \cdot \theta_q
    \]

---

### 🧪 Contrastive Loss
Score function:
\[
s(q, d) = \langle f_{\theta}(q), f_{\theta}(d) \rangle
\]

Contrastive loss:
\[
\mathcal{L}(q, k^+) = - \frac{\exp(s(q, k^+)/\tau)}{\exp(s(q, k^+)/\tau) + \sum_{i=1}^K \exp(s(q, k_i^-)/\tau)}
\]

---

### 🔍 Ablation Study

- **MoCo vs. In-Batch Negatives**:  
  → Perform similarly  
  → MoCo is **more memory efficient** with a **larger pool of negatives**

- **Number of Negatives**:  
  → More negatives → **Better performance**

- **Positive Pair Strategy**:  
  → **Random cropping** outperforms **Inverse Cloze Task**

# Key questions



---
> [!Cite]
> Izacard, G., Caron, M., Hosseini, L., Riedel, S., Bojanowski, P., Joulin, A., & Grave, E. (2022). _Unsupervised Dense Information Retrieval with Contrastive Learning_ (No. arXiv:2112.09118). arXiv. [https://doi.org/10.48550/arXiv.2112.09118](https://doi.org/10.48550/arXiv.2112.09118)

> [!Synth]
> **Contribution**::  
>   
> **Related**:: 

> [!Metadata]
> **Authors**::Izacard, Gautier, Caron, Mathilde, Hosseini, Lucas, Riedel, Sebastian, Bojanowski, Piotr, Joulin, Armand, Grave, Edouard
> **Title**:: Unsupervised Dense Information Retrieval with Contrastive Learning  
> **Year**:: 2022  
> **Citekey**:: izacardUnsupervisedDenseInformation2022a> **Item Type**:: preprint> **DOI**:: 10.48550/arXiv.2112.09118

> [!Link]
> [Preprint PDF](file:///Users/ryanchen/Zotero/storage/YZ6FQNAY/Izacard%20et%20al.%20-%202022%20-%20Unsupervised%20Dense%20Information%20Retrieval%20with%20Contrastive%20Learning.pdf)

> [!Abstract]
> Recently, information retrieval has seen the emergence of dense retrievers, using neural networks, as an alternative to classical sparse methods based on term-frequency. These models have obtained state-of-the-art results on datasets and tasks where large training sets are available. However, they do not transfer well to new applications with no training data, and are outperformed by unsupervised term-frequency methods such as BM25. In this work, we explore the limits of contrastive learning as a way to train unsupervised dense retrievers and show that it leads to strong performance in various retrieval settings. On the BEIR benchmark our unsupervised model outperforms BM25 on 11 out of 15 datasets for the Recall@100. When used as pre-training before fine-tuning, either on a few thousands in-domain examples or on the large MS~MARCO dataset, our contrastive model leads to improvements on the BEIR benchmark. Finally, we evaluate our approach for multi-lingual retrieval, where training data is even scarcer than for English, and show that our approach leads to strong unsupervised performance. Our model also exhibits strong cross-lingual transfer when fine-tuned on supervised English data only and evaluated on low resources language such as Swahili. We show that our unsupervised models can perform cross-lingual retrieval between different scripts, such as retrieving English documents from Arabic queries, which would not be possible with term matching methods.
---

# Annotations

### Imported: 2025-06-04 11:54 am


<mark style="background-color: #ff6666">Quote</mark>  
> The relevance score between a query and a document is given by the dot product between their representations after applying the encoder.


<mark style="background-color: #ff6666">Quote</mark>  
> Empirically, we observed that using the same encoder, such as in Xiong et al. (2020) and Reimers & Gurevych (2019), generally improves robustness in the context of zero-shot transfer or few-shot learning, while having no impact on other settings.



