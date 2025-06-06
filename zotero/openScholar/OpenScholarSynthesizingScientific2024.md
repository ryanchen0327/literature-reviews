---
dg-publish: true
category: literaturenote
tags:
  - Retrieval
citekey: asaiOpenScholarSynthesizingScientific2024
status: read
dateread: 06/03/2025
---
# 📝 Notes

### 📚 Data Sources
1. **Google Search** – General-purpose web search.
2. **Semantic Scholar API** – Continuously updated; built on the **S2ORC** corpus.
3. [**peS2o Dataset** ](obsidian://open?vault=litrev&file=zotero%2FRAG%20Benchmark%2FS2ORCSemanticScholar2020)– Also based on **S2ORC**; used for retrieval model training.

> 🔁 **Note**: Both Semantic Scholar and peS2o are derived from the same underlying corpus: **S2ORC (Semantic Scholar Open Research Corpus)**.

---

### 🧠 System Overview

- **Retrieval (peS2o)**, **Reranking**, and **Feedback Loops** are powered by **trained models**.
- **Google Search** and other components are **algorithmic** (non-learning based).
- A **[bi-encoder](obsidian://open?vault=litrev&file=zotero%2FRAG%20Benchmark%2FUnsupervisedDenseInformation2022a) trained on the peS2o corpus** is expected to outperform general-purpose embeddings (e.g., Weaviate).

---

# ❓ Questions

### Why is the system using a **[cross-encoder trained on Chinese embeddings](obsidian://open?vault=litrev&file=zotero%2FopenScholar%2FCPackPackedResources2024)**?
- Is **fine-tuning** this model producing **better results** than using:
  - an **English-only** cross-encoder?
  - or a **multilingual** cross-encoder?


---

> [!Cite]
> Asai, A., He, J., Shao, R., Shi, W., Singh, A., Chang, J. C., Lo, K., Soldaini, L., Feldman, S., D’arcy, M., Wadden, D., Latzke, M., Tian, M., Ji, P., Liu, S., Tong, H., Wu, B., Xiong, Y., Zettlemoyer, L., … Hajishirzi, H. (2024, November 21). _OpenScholar: Synthesizing Scientific Literature with Retrieval-augmented LMs_. arXiv.Org. [https://arxiv.org/abs/2411.14199v1](https://arxiv.org/abs/2411.14199v1)

> [!Synth]
> **Contribution**::  
>   
> **Related**:: 

> [!Metadata]
> **Authors**::Asai, Akari, He, Jacqueline, Shao, Rulin, Shi, Weijia, Singh, Amanpreet, Chang, Joseph Chee, Lo, Kyle, Soldaini, Luca, Feldman, Sergey, D'arcy, Mike, Wadden, David, Latzke, Matt, Tian, Minyang, Ji, Pan, Liu, Shengyan, Tong, Hao, Wu, Bohao, Xiong, Yanyu, Zettlemoyer, Luke, Neubig, Graham, Weld, Dan, Downey, Doug, Yih, Wen-tau, Koh, Pang Wei, Hajishirzi, Hannaneh
> **Title**:: OpenScholar: Synthesizing Scientific Literature with Retrieval-augmented LMs  
> **Year**:: 2024  
> **Citekey**:: asaiOpenScholarSynthesizingScientific2024> **Item Type**:: webpage

> [!Link]
> [Full Text PDF](file:///Users/ryanchen/Zotero/storage/IFH249GP/Asai%20等%20-%202024%20-%20OpenScholar%20Synthesizing%20Scientific%20Literature%20with%20Retrieval-augmented%20LMs.pdf)

> [!Abstract]
> Scientific progress depends on researchers' ability to synthesize the growing body of literature. Can large language models (LMs) assist scientists in this task? We introduce OpenScholar, a specialized retrieval-augmented LM that answers scientific queries by identifying relevant passages from 45 million open-access papers and synthesizing citation-backed responses. To evaluate OpenScholar, we develop ScholarQABench, the first large-scale multi-domain benchmark for literature search, comprising 2,967 expert-written queries and 208 long-form answers across computer science, physics, neuroscience, and biomedicine. On ScholarQABench, OpenScholar-8B outperforms GPT-4o by 5% and PaperQA2 by 7% in correctness, despite being a smaller, open model. While GPT4o hallucinates citations 78 to 90% of the time, OpenScholar achieves citation accuracy on par with human experts. OpenScholar's datastore, retriever, and self-feedback inference loop also improves off-the-shelf LMs: for instance, OpenScholar-GPT4o improves GPT-4o's correctness by 12%. In human evaluations, experts preferred OpenScholar-8B and OpenScholar-GPT4o responses over expert-written ones 51% and 70% of the time, respectively, compared to GPT4o's 32%. We open-source all of our code, models, datastore, data and a public demo.

---

# Annotations

### Imported: 2025-06-03 2:06 pm


<mark style="background-color: #ff6666">Quote</mark>  
> y, C = G(x, R(x, D)),


<mark style="background-color: #ff6666">Quote</mark>  
> iteratively enhances its output through retrieval-augmented self-feedback (Section 2.2)


<mark style="background-color: #ff6666">Quote</mark>  
> We built our datastore using peS2o v3,


<mark style="background-color: #ff6666">Quote</mark>  
> Following prior work (Shao et al., 2024), we split the main text of each paper into discrete, 250-word text blocks (as determined by white space) and concatenate the paper title to each block to formulate passages in D.


<mark style="background-color: #ff6666">Quote</mark>  
> develop θbi by continually pre-training Contriever (Izacard et al., 2022) on the peS2o datastore in an unsupervised fashion to improve domain-specific retrieval performance


<mark style="background-color: #ff6666">Quote</mark>  
> These keywords are then used to retrieve the top 10 papers for each, as ranked by citation count, via the Semantic Scholar Search API


<mark style="background-color: #ff6666">Quote</mark>  
> we obtain the top 10 search results using the You.com retrieval API,3 restricting the search to academic platforms such as ArXiv and PubMed. If the papers are open-access, we extract and add their full texts to the candidate pool; otherwise, we include only their abstracts.


<mark style="background-color: #ff6666">Quote</mark>  
> cross-encoder reranker


<mark style="background-color: #ff6666">Quote</mark>  
> cross-encoder reranker jointly encodes and computes the relevance score between the input query and each of the passages.


<mark style="background-color: #ff6666">Quote</mark>  
> we fine-tune a BGE-reranker (Xiao et al., 2023) using synthetic data generated by Llama 3 70B Instruct


<mark style="background-color: #ff6666">Quote</mark>  
> (1) initial response and feedback generation to output the initial draft y0 and a set of feedback on y0; (2) iterative refinement with additional retrieval to improve y0 using the feedback, and (3) citation verification. Full details are in the Appendix.


<mark style="background-color: #ff6666">Quote</mark>  
> each feedback ft is a natural language sentence that describes potential improvements.


<mark style="background-color: #5fb236">Quote</mark>  
> allows the LM to generate flexible natural language feedback


<mark style="background-color: #5fb236">Quote</mark>  
> If the feedback sequence identifies missing content (e.g., “The answer only includes empirical results on QA tasks. Add results from other task types.”), the LM also generates a retrieval query for additional retrieval using the pipeline in Section 2.1.


<mark style="background-color: #ff6666">Quote</mark>  
> pairwise-filtering and rubric-filtering,


<mark style="background-color: #ff6666">Quote</mark>  
> In pair-wise filtering, we compare the quality of model outputs yT (output at the final step) and y0 (initial output), and retain the output that is judged to be higher quality.


<mark style="background-color: #2ea8e5">Quote</mark>  
> y0 is preferred over yT around 20%


<mark style="background-color: #ff6666">Quote</mark>  
> answer generation (x → y), feedback generation (y0 → F), and feedback incorporation (yt−1, ft → yt).


<mark style="background-color: #2ea8e5">Quote</mark>  
> incorporating both final and intermediate outputs during training helps smaller LMs learn to generate more effective feedback.


<mark style="background-color: #ff6666">Quote</mark>  
> CHOLARQABENCH, a benchmark that supports diverse formats of scientific literature synthesis tasks, including closed-form classification, multiple-choice, and longform generation,






