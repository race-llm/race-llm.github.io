---
title: "A Scalable Two-Phase Method for Low-Overhead Retrieval-Augmented Language Models "
collection: publications
category: manuscripts
# permalink: /assets/papers/2025136575.pdf
excerpt: 'STAR decides whether the LLM already knows the answer; if not, it retrieves and re‑ranks 100‑token chunks, yielding accuracy on NQ, TriviaQA and HotpotQA equal to or better than multi‑hop systems but at a fraction of cost'
# date: 2010-10-01
# venue: 'Journal 1'
# slidesurl: 'http://academicpages.github.io/files/slides2.pdf'
# paperurl: '{{ site.baseurl }}/assets/papers/2025136575.pdf'
paperurl: "/assets/papers/2025136575.pdf"
# citation: 'Your Name, You. (2010). &quot;Paper Title Number 2.&quot; <i>Journal 1</i>. 1(2).'
---

Recent advances in Retrieval-Augmented Generation (RAG) have allowed large language models (LLMs) to consult external knowledge bases to overcome their parameterized knowledge limitations. However, many RAG-based systems depend on iterative procedures like multi-step question decomposition, which can become unnecessarily time-consuming when questions are straightforward. 

To address this issue, we propose STAR (Self-Knowledge and Targeted Augmented Retrieval), a simplified two-branch retrieval-augmented questionanswering framework composed of two main components: a SelfKnowledge Branch and an optimized Passage Retrieval Branch. 

In our design, the system first checks whether the question can be answered using the LLM’s existing knowledge. If not, it retrieves passages and then ranks smaller segments of those passages based on their relevance. This approach reduces the query’s reliance on extraneous content, lowers computational costs, and offers a more direct route to accurate solutions. Empirical results on benchmarks such as Natural Questions and TriviaQA show that our simplified approach matches or exceeds the accuracy of multimodule counterparts while operating at a fraction of the complexity.