#  Review Summarization App (GPT-3.5 + Gradio)

[![Status](https://img.shields.io/badge/status-live-green)](https://github.com/cwattsnogueira/rating-predictor-spam-detection-review-summarizer)
![License](https://img.shields.io/badge/license-MIT-blue)
![Python](https://img.shields.io/badge/python-3.10%2B-yellow)
![OpenAI](https://img.shields.io/badge/model-GPT--3.5--turbo-lightblue)
![Gradio](https://img.shields.io/badge/UI-gradio%20interactive-orange)
![Modeling](https://img.shields.io/badge/modeling-review--summarization-purple)

<a href="https://colab.research.google.com/github/cwattsnogueira/rating-predictor-spam-detection-review-summarizer/blob/main/13_03_review_summarization_gpt3.ipynb" target="_parent">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

---

##  Purpose

This notebook launches a **Gradio app** that uses **GPT-3.5-turbo** to generate concise summaries of product reviews. It supports both manual text input and CSV uploads, and personalizes the output using the product name.

---

##  What the Code Does

- Loads GPT-3.5 API key securely via `userdata.get("OPENAI_API_KEY")`
- Cleans and joins reviews into a single prompt
- Sends prompt to GPT-3.5 with temperature control
- Returns a 3-sentence summary tailored to the product
- Supports both manual and CSV-based review summarization

---

##  App Interface Overview

###  Manual Input Tab

Users can paste multiple reviews and specify a product name to generate a personalized summary.

####  Example: Summarizing Nutricost Reviews

![Manual Review Summary](./output/sum_revi.png)

---

###  CSV Upload Tab

Users can upload a CSV file containing reviews and specify the column name to summarize them collectively.

####  Example: Summarizing Headphone Reviews from CSV

![CSV Review Summary](./output/csvrevi.png)

---

##  Inputs Supported

| Input Type     | Description |
|----------------|-------------|
| Manual Reviews | Paste multiple reviews directly |
| CSV File       | Upload a CSV with a column containing reviews |

---

##  Output Format

```markdown
**Product:** Wireless Headset

**Summary:**
Customers appreciate the headset’s sound quality and battery life. Many mention its comfort during long use and effective noise cancellation. A few users noted minor pairing issues but overall satisfaction is high.
```

---

##  Budget Justification

| Task                              | Skill Area               | Budget Rationale |
|-----------------------------------|--------------------------|------------------|
| GPT-3.5 prompt engineering        | NLP + summarization      | High — enables semantic compression |
| Gradio interface design           | UX + interactivity       | High — improves user engagement |
| CSV ingestion                     | Workflow flexibility     | Medium — supports batch summarization |
| Markdown output                   | Presentation clarity     | Medium — improves readability |
| Secure API key handling           | Deployment hygiene       | Medium — ensures safe access to OpenAI services |

---

