#  Data Profiling with YData

[![Status](https://img.shields.io/badge/status-active-brightgreen)](https://github.com/cwattsnogueira/rating-predictor-spam-detection-review-summarizer)
![License](https://img.shields.io/badge/license-MIT-blue)
![Python](https://img.shields.io/badge/python-3.10%2B-yellow)
![YData Profiling](https://img.shields.io/badge/ydata--profiling-4.6.2-lightblue)
![Feature Engineering](https://img.shields.io/badge/feature--analysis-✓-purple)
![Ethical AI](https://img.shields.io/badge/ethics-transparent--audit-green)

<a href="https://colab.research.google.com/github/cwattsnogueira/rating-predictor-spam-detection-review-summarizer/blob/main/05_02_ydata_profiling.ipynb" target="_parent">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

---

##  Purpose

This notebook generates a full exploratory data profiling report using the `ydata-profiling` library. It analyzes the structured features of the engineered review dataset, excluding textual columns, and produces a rich HTML report for inspection, validation, and feature selection.

---

##  Folder Structure

```
├── 05-02-data-profiling/
│   ├── 05_02_ydata_profiling.ipynb # Notebook for generating the report
│   ├── 05_02_ydata_profiling.py    # Script version (optional)
│   ├── index.html                  # Generated HTML report
│   └── README.md                   # This documentation
```

---

##  Input File

| File Name                      | Description                                 | Link |
|-------------------------------|---------------------------------------------|------|
| `engineered_features.parquet` | Dataset with structured and textual features | [View file](../05-feature-engineering/output/engineered_features.parquet) |

---

##  Output File

| File Name               | Description                          | Link |
|------------------------|--------------------------------------|------|
| `profiling_report.html`| Full interactive profiling report    | [View report](https://guileless-pegasus-81a444.netlify.app/) |

---

##  What the Code Does

- Loads the engineered review dataset
- Drops textual and identifier columns to focus on structured features
- Generates a full profiling report using `ProfileReport` from `ydata-profiling`
- Saves the report as an HTML file for sharing and inspection
- Optionally renders the report inline in notebook environments

---

##  Columns Excluded from Profiling

The following columns are excluded to avoid noise and focus on numeric, categorical, and behavioral signals:

```python
[
  "reviews.text", "reviews.title", "reviews.username",
  "reviews.sourceURLs", "label_text", "clean_text",
  "purchase_status", "recommend_status", "sentiment_category",
  "brand", "categories", "manufacturer", "manufacturerNumber",
  "name", "main_category", "category_group", "keys", "upc"
]
```

---

##  Budget Justification

| Task                        | Skill Area             | Budget Rationale |
|-----------------------------|------------------------|------------------|
| Column filtering            | Data cleaning          | Medium — improves signal clarity |
| Automated profiling         | Feature analysis       | High — accelerates insight generation |
| HTML report generation      | Transparency & sharing | High — supports auditability and collaboration |
| Explorative mode            | Ethical design         | High — reveals hidden patterns and risks |

---

