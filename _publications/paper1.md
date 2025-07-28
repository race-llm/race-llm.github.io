---
title: "Dear LLM, Why Are They Complaining? On Root‑Cause Analysis in Customer Service"
collection: publications
category: manuscripts
# permalink: /publication/2009-10-01-paper-title-number-1
excerpt: 'We curate 420 real financial‑service complaints across 44 issues and benchmark five frontier models, showing zero‑shot RCA is already viable yet leaves head‑room for few‑shot tuning'
# date: 2009-10-01
# venue: 'Journal 1'
# slidesurl: 'http://academicpages.github.io/files/slides1.pdf'
# paperurl: '{{ site.baseurl }}/assets/papers/2025103092.pdf'
paperurl: "/assets/papers/2025103092.pdf"

# bibtexurl: 'http://academicpages.github.io/files/bibtex1.bib'
# citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
---
The goal of Root Cause Analysis (RCA) is to determine the underlying concern from a host of concerns. In customer service, RCA can help organizations identify fundamental issues in customer complaints and dissatisfaction.

Traditional RCA methods relied on human analysis, often prone to subjectivity and bias. Moreover, processing a large volume of complaint narratives demands significant resources. With data-driven approaches like machine learning, the efficiency of RCA has improved. However, these approaches require domain expertise and training data for accurate performance.

Large Language Models (LLMs) can mitigate this challenge by learning from limited examples through few-shot learning or without any examples through zero-shot learning.

This research introduces a dataset for RCA detection collected from real-world customer complaint narratives across diverse issues. Six state-of-the-art LLMs, including OpenAI's o1, GPT-4o, Sonnet, and Gemini, were evaluated on their performance in detecting RCA. Llama performed the best in open-ended RCA (55%) whereas o1 performed the best in multiclass RCA (68%).

Our findings highlight the potential of LLMs in automating RCA. The limitations of current approaches, like model interpretability and domain-specific generalization, were discussed along with future research directions to enhance RCA capabilities further using LLMs.
