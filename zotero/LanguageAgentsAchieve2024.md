---
category: literaturenote
tags: Computer Science - Computation and Language, Computer Science - Artificial Intelligence, Computer Science - Information Retrieval, Physics - Physics and Society
citekey: skarlinskiLanguageAgentsAchieve2024
status: unread
dateread:
---
# Notes


it uses three tools and gives llm the freedom to use them. 
1. search from google scholar, pubmed, arxiv, and any open source websites. This allows multiple search to be performed at llm's decision with different keywords. The documents are stored in vector database with text-embedding-ada-002 with 4000 token chunk.
2. gather_evidence is a search with llm agent generated queries that it thinks can helps answering the question. It performs a vector database search with the query and 1.search gathered documents. Then ask a summary_llm to summarize each returned document and rate it. Finally it takes the top-1 chunk to context library. 


# Key questions



---
> [!Cite]
> Skarlinski, M. D., Cox, S., Laurent, J. M., Braza, J. D., Hinks, M., Hammerling, M. J., Ponnapati, M., Rodriques, S. G., & White, A. D. (2024). _Language agents achieve superhuman synthesis of scientific knowledge_ (No. arXiv:2409.13740). arXiv. [https://doi.org/10.48550/arXiv.2409.13740](https://doi.org/10.48550/arXiv.2409.13740)

> [!Synth]
> **Contribution**::  
>   
> **Related**:: 

> [!Metadata]
> **Authors**::Skarlinski, Michael D., Cox, Sam, Laurent, Jon M., Braza, James D., Hinks, Michaela, Hammerling, Michael J., Ponnapati, Manvitha, Rodriques, Samuel G., White, Andrew D.
> **Title**:: Language agents achieve superhuman synthesis of scientific knowledge  
> **Year**:: 2024  
> **Citekey**:: skarlinskiLanguageAgentsAchieve2024> **Item Type**:: preprint> **DOI**:: 10.48550/arXiv.2409.13740

> [!Link]

> [!Abstract]
> Language models are known to hallucinate incorrect information, and it is unclear if they are sufficiently accurate and reliable for use in scientific research. We developed a rigorous human-AI comparison methodology to evaluate language model agents on real-world literature search tasks covering information retrieval, summarization, and contradiction detection tasks. We show that PaperQA2, a frontier language model agent optimized for improved factuality, matches or exceeds subject matter expert performance on three realistic literature research tasks without any restrictions on humans (i.e., full access to internet, search tools, and time). PaperQA2 writes cited, Wikipedia-style summaries of scientific topics that are significantly more accurate than existing, human-written Wikipedia articles. We also introduce a hard benchmark for scientific literature research called LitQA2 that guided design of PaperQA2, leading to it exceeding human performance. Finally, we apply PaperQA2 to identify contradictions within the scientific literature, an important scientific task that is challenging for humans. PaperQA2 identifies 2.34 +/- 1.99 contradictions per paper in a random subset of biology papers, of which 70% are validated by human experts. These results demonstrate that language model agents are now capable of exceeding domain experts across meaningful tasks on scientific literature.
---

# Annotations

### Imported: 2025-06-18 12:46 pm



