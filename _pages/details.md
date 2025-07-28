---
layout: archive
permalink: /details/
author_profile: true
---
{% capture my_about %}



## 1 · Root Cause Analysis (RCA)

This study investigates how Large Language Models (LLMs) like GPT-4o, Llama 3.1, and Gemini 1.5 Pro can automate Root Cause Analysis (RCA) in customer service complaints. Traditionally, RCA relies on manual methods like Ishikawa diagrams or machine learning—but these approaches need significant domain expertise and data.

Here we introduce a new dataset based on 420 real-world complaints from the U.S. Consumer Financial Protection Bureau. We evaluated 5 LLMs across:

Multiclass RCA: Predicting issues from 10 predefined categories.

Open-ended RCA: Predicting without category constraints.

| Task        | Best Model | Accuracy   | 
|---------------|--------|------|
|Multiclass RCA | OpenAI o1, Gemini  | 68% |
|Open-ended RCA |   Llama 3.1 | 55% |

{% endcapture %}
<div class="wow animate__animated animate__fadeInUp" data-wow-delay="0.3s" data-wow-duration="1s">
  {{ my_about | markdownify }}
</div>


---

{% capture my_star %}

## 2 · STAR Retrieval

STAR (Self-Knowledge and Targeted Augmented Retrieval) is a scalable and efficient two-phase framework that improves retrieval-augmented generation (RAG) for large language models (LLMs).

Unlike traditional RAG systems that rely on iterative multi-step reasoning and complex decomposition, STAR simplifies the process using two distinct branches:

The Self-Knowledge Branch determines if the LLM already knows the answer. If so, it avoids any retrieval, reducing latency and cost. The Targeted Retrieval Branch works if the LLM is unsure, only then are external passages retrieved, segmented into chunks, and scored for relevance. Only the top segments are used to generate the final answer.

📊 Performance Highlights:
Evaluated on Llama2-13B
<div style="overflow-x: auto; margin: 1rem 0;">
  <table style="border-collapse: collapse; min-width: 600px; margin: 0 auto; ">
    <thead>
      <tr>
        <th style="border: 1px solid #ccc; padding: 8px;">Method</th>
        <th style="border: 1px solid #ccc; padding: 8px;">Avg EM</th>
        <th style="border: 1px solid #ccc; padding: 8px;">NQ</th>
        <th style="border: 1px solid #ccc; padding: 8px;">TriviaQA</th>
        <th style="border: 1px solid #ccc; padding: 8px;">HotpotQA</th>
        <th style="border: 1px solid #ccc; padding: 8px;">StrategyQA</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="border: 1px solid #ccc; padding: 8px;">Vanilla LM</td>
        <td>30.53</td><td>17.4</td><td>38.5</td><td>14.0</td><td>52.2</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ccc; padding: 8px;">Least-to-Most</td>
        <td>36.08</td><td>22.8</td><td>45.2</td><td>15.8</td><td>60.5</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ccc; padding: 8px;">IRCoT</td>
        <td>36.97</td><td>23.4</td><td>48.3</td><td>17.1</td><td>59.1</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ccc; padding: 8px;">RAG</td>
        <td>36.75</td><td>21.6</td><td>47.0</td><td>17.6</td><td>60.8</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ccc; padding: 8px;">SKRknn</td>
        <td>39.17</td><td>20.8</td><td>55.4</td><td>18.9</td><td>61.6</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ccc; padding: 8px;">REPLUG</td>
        <td>41.77</td><td>23.8</td><td>58.6</td><td>21.8</td><td>62.9</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ccc; padding: 8px;">Self-RAG</td>
        <td>47.58</td><td>28.4</td><td>69.3</td><td>25.4</td><td>67.2</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ccc; padding: 8px;">RA-ISF</td>
        <td>49.58</td><td>31.3</td><td>71.4</td><td>28.9</td><td>66.7</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ccc; padding: 8px;"><strong>STAR (Ours)</strong></td>
        <td><strong>50.98</strong></td>
        <td><strong>31.0</strong></td>
        <td><strong>71.9</strong></td>
        <td><strong>30.0</strong></td>
        <td><strong>71.0</strong></td>
      </tr>
    </tbody>
  </table>
</div>



---
Evaluated on GPT-3.5

<style>
.table-scroll {
  overflow-x: auto;
  width: 100%;
}

.table-scroll table {
  width: max-content;
  min-width: 100%;
  border-collapse: collapse;
}
</style>

<div style="overflow-x: auto; margin: 1rem 0;">
  <table style="border-collapse: collapse; min-width: 600px; margin: 0 auto; ">
    <thead>
      <tr>
        <th style="border: 1px solid #ddd; padding: 8px;">Method</th>
        <th style="border: 1px solid #ddd; padding: 8px;">Avg EM</th>
        <th style="border: 1px solid #ddd; padding: 8px;">NQ</th>
        <th style="border: 1px solid #ddd; padding: 8px;">TriviaQA</th>
        <th style="border: 1px solid #ddd; padding: 8px;">HotpotQA</th>
        <th style="border: 1px solid #ddd; padding: 8px;">StrategyQA</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="border: 1px solid #ddd; padding: 8px;">Direct Prompt</td>
        <td>45.95</td><td>29.2</td><td>67.3</td><td>22.1</td><td>65.2</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ddd; padding: 8px;">Least-to-Most</td>
        <td>50.00</td><td>32.5</td><td>68.8</td><td>30.2</td><td>68.5</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ddd; padding: 8px;">IRCoT</td>
        <td>50.32</td><td>32.9</td><td>66.8</td><td>33.7</td><td>67.9</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ddd; padding: 8px;">RAG</td>
        <td>48.20</td><td>31.7</td><td>64.2</td><td>32.2</td><td>64.7</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ddd; padding: 8px;">SKRknn</td>
        <td>51.40</td><td>33.8</td><td>67.5</td><td>34.2</td><td>70.1</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ddd; padding: 8px;">RA-ISF</td>
        <td><b>59.68</b></td><td>40.2</td><td>76.1</td><td>46.5</td><td>75.9</td>
      </tr>
      <tr>
        <td style="border: 1px solid #ddd; padding: 8px;"><b>STAR (Ours)</b></td>
        <td><b>58.63</b></td><td><b>42.9</b></td><td><b>76.2</b></td><td><b>39.5</b></td><td><b>75.9</b></td>
      </tr>
    </tbody>
  </table>
</div>


{% endcapture %}
<div class="wow animate__animated animate__fadeInUp" data-wow-delay="0.3s" data-wow-duration="1s">
  {{ my_star | markdownify }}
</div>
---

## 3 · Care by Design (CbD)

**CbD** embeds:
- An *empathy embedding*
- Dynamic personalisation
- Human in the loop fine tuning
The Care-by-Design (CbD) framework  enhances AI-driven customer service chatbots by embedding empathy, contextual understanding, and personalization into large language models. The traditional AI lacks emotional intelligence, and human agents face burnout and bias, leading to inconsistent service quality.

The CbD approach integrates:
Empathy theory
Service-dominant logic
Contextual learning
Dynamic personalization
Empathy-driven dialogue
Fine-tuning + prompt engineering

A case study comparing standard GPT-4 to a CbD-enhanced model showed that the CbD model significantly improved customer satisfaction, emotional responsiveness, and perceived care.

The study highlights how empathetic LLMs can offer emotionally intelligent, consistent, and personalized service at scale — shaping the future of customer experience in a post-human-agent era.
<!-- Together, these significantly boost customer satisfaction, as demonstrated in a **20-user study**. -->

![CBD]({{ site.baseurl }}/images/cbd_screenshot.png)


<style>
.design-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  /* background-color: #1f1f1f; */
  /* min-height: 100vh; */
  /* padding: 10px 0; */
  font-family: Jost;
}

.design {
  display: flex;
  align-items: center;
  justify-content: center;
}

.timeline {
  width: 80%;
  height: auto;
  max-width: 800px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
}

.timeline-content {
  padding: 10px;
  /* background: #1f1f1f; */
  -webkit-box-shadow: 5px 5px 10px #1a1a1a, -5px -5px 10px #242424;
          box-shadow: 5px 5px 10px #1a1a1a, -5px -5px 10px #242424;
  border-radius: 5px;
  color: teal;
  /* padding: 1.75rem; */
  transition: 0.4s ease;
  overflow-wrap: break-word !important;
  margin: 1rem;
  /* margin-bottom: 20px; */
  border-radius: 6px;
}

/* .timeline-component {
  margin: 0px 20px 20px 20px;
} */

@media screen and (min-width: 768px) {
  .timeline {
    display: grid;
    grid-template-columns: 1fr 3px 1fr;
  }
  .timeline-middle {
    position: relative;
    background-image: linear-gradient(45deg, #6d8196, #6d8196, #6d8196);
    /* background-image: linear-gradient(45deg, #F27121, #E94057, #8A2387); */
    width: 3px;
    height: 100%;
  }
  .main-middle {
    opacity: 0;
  }
  .timeline-circle {
    position: absolute;
    top: 0;
    left: 50%;
    width: 15px;
    height: 15px;
    border-radius: 50%;
    background-image: linear-gradient(45deg, #6d8196, #6d8196, #6d8196);
    -webkit-transform: translateX(-50%);
            transform: translateX(-50%);
  }
}
</style>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Jost:wght@200;300;400&display=swap');
</style>

## 🔭 Roadmap
<!-- Timeline container -->
<section class="design-section">
  <div class="timeline">
    <div class="timeline-empty"></div>
    <!-- First timeline block -->
    <div class="timeline-middle">
      <div class="timeline-circle"></div>
    </div>
    <div class="timeline-component timeline-content">
      <h3 style="margin-bottom:2rem">Few‑shot RCA + expansion of the complaint corpus</h3>
    </div>
    <!-- Second timeline block -->
    <div class="timeline-component timeline-content">
      <h3 style="margin-bottom:2rem">Open‑sourcing STAR API and benchmark harness</h3>
    </div>
    <div class="timeline-middle">
      <div class="timeline-circle"></div>
    </div>
    <div class="timeline-empty"></div>
    <!-- Third timeline block -->
    <div class="timeline-empty"></div>
    <div class="timeline-middle">
      <div class="timeline-circle"></div>
    </div>
    <div class="timeline-component timeline-content">
      <h3 style="margin-bottom:2rem">Full CbD evaluation on multi-modal chat</h3>
    </div>

  </div>
</section>
