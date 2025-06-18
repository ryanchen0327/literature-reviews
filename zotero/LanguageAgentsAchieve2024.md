---
category: literaturenote
tags: Computer Science - Computation and Language, Computer Science - Artificial Intelligence, Computer Science - Information Retrieval, Physics - Physics and Society
citekey: skarlinskiLanguageAgentsAchieve2024
status: unread
dateread:
---
# Notes

## System Overview: LLM Agent with Three Tools

This system equips a language model (LLM) with three key tools, allowing autonomous decision-making for evidence gathering and answering.  
**Keywords:** `summary_llm`, `ask_llm`, `answer_llm`, `context library`, `different prompts`

---

### 1. `search`

- Searches sources like **Google Scholar**, **PubMed**, **arXiv**, and other open-access websites.
- Multiple search queries can be issued at the LLM's discretion, using different keywords.
- Retrieved documents are chunked into **4000-token segments**.
- Chunks are stored in a **vector database** using the `text-embedding-ada-002` model.

---

### 2. `gather_evidence`

- Uses LLM-generated queries to find relevant information.
- Executes a vector database search over both:
  - Previously searched documents (from Tool 1)
  - The new query
- For each matching document:
  - Applies `summary_llm` prompt to summarize and **rate** the result.
- The **top-1 rated chunk** is added to the **context library**.

---

### 3. `answer_question`

- First, applies `ask_llm` to extract relevant internal knowledge into the **context library**.
- Then, invokes `answer_llm` to generate an answer using:
  - The **user's original question**
  - The accumulated **context library**

---

### Agent Initialization Prompt

All tools are driven by an LLM agent initialized with the following instruction:

> **"Answer question: <question>. Search for papers, gather evidence, and answer. If you do not have enough evidence, you can search for more papers (preferred) or gather more evidence with a different phrase. You may rephrase or break-up the question in those steps. Once you have five or more pieces of evidence from multiple sources, or you have tried many times, call answer_question tool. You may reject the answer and try again if it is incomplete."**

# key improve


# Key questions

Cannot verify paper's faithfulness.


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



