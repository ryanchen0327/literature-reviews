---
category: literaturenote
tags: Computer Science - Computation and Language, Computer Science - Artificial Intelligence, Computer Science - Information Retrieval
citekey: izacardUnsupervisedDenseInformation2022a
status: unread
dateread:
---
# Notes

Cross encoder/bi encoder

Unsupervised training for contrastive learning:
Training set generation: 
	Positive pairs:
		Inverse Cloze Task: aba -> q: a...a, k: b
		Independent cropping: Symmetric: both q and k are same length, overlaps: encourages exact matching, Shorter queries may make the task **more difficult**, forcing the model to learn better representations.
	Negative pairs:
		In batch: it requires extremely large batch sizes to work well
		across batch: last batch contains outdated representation since current batch runs on an updated θ. Fix by slowing down key encoder by θk ← mθk + (1 − m)θq. (MoCo)
Unsupervised training:
	s(q, d) = 〈fθ(q), fθ(d)〉.
	L(q, k+) = − exp(s(q, k+)/τ )   /    ( exp(s(q, k+)/τ ) + ∑K  i=1 exp(s(q, ki)/τ) ) ,
Ablation: 
	MOCO and in-batch negatives have similar results. So, MoCo is better with less memory use for more negative pairs.
	More negative samples leads to better results.
	random cropping strategy outperforms the inverse cloze task in this setting
		


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



