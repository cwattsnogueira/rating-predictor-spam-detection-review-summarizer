#  Review Data Loader & Cleaning Pipeline

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cwattsnogueira/rating-predictor-spam-detection-review-summarizer/blob/main/01_data_loader_review_clean.ipynb)
![Status](https://img.shields.io/badge/status-active-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Python](https://img.shields.io/badge/python-3.10%2B-yellow)
![Pandas](https://img.shields.io/badge/pandas-2.0.3-orange)
![Data Cleaning](https://img.shields.io/badge/data--cleaning-✓-lightgrey)
![Notebook](https://img.shields.io/badge/notebook-Jupyter-informational)
![Last Updated](https://img.shields.io/badge/last--updated-October_2025-blueviolet)

##  Project Context & Objective

This notebook is the first stage of a larger AI/ML bootcamp final project. It focuses on loading, inspecting, and cleaning a raw product review dataset to prepare it for downstream modeling and analysis. The goal is to preserve informative features, handle missingness and duplication ethically, and document every decision transparently.

##  Folder Structure

```
├── open colab [Add link here]
├── 01-data-loader-review-clean/
│   ├── input/        # Place raw input files here (see below)
│   ├── notebook/     # Contains the Jupyter notebook for this pipeline
│   ├── output/       # Cleaned dataset and intermediate files
│   └── README.md     # This documentation
```

##  Required Files

Please place the following files in the `input/` folder before running the notebook:

| File Name              | Description                                      | Link Placeholder |
|------------------------|--------------------------------------------------|------------------|
| `raw_reviews.csv`      | Raw review dataset with product and user fields  | [raw_reviews.csv](./01-data-loader-review-clean/input/)  |

##  Generated Files

After running the notebook, the following file will be saved in the `output/` folder:

| File Name                   | Description                                      | Format |
|----------------------------|--------------------------------------------------|--------|
| `cleaned_reviews.parquet`  | Cleaned and deduplicated review dataset [cleaned_reviews.parquet](./01-data-loader-review-clean/output/) | Parquet |

##  Summary of What the Code Does

- Loads raw review data and previews structure
- Identifies and removes columns with excessive missingness or low modeling value
- Drops rows missing critical fields (e.g., review text, date, title, username)
- Converts date fields to UTC datetime format
- Flags and encodes missing values for behavioral fields (`didPurchase`, `doRecommend`)
- Normalizes helpful vote counts and creates engagement flags
- Deduplicates reviews using multiple strategies (text, title, user-date combinations)
- Documents column-level decisions in a final cleaning report

##  What We Generate

The final output is a cleaned, structured dataset suitable for:

- NLP modeling (e.g., sentiment analysis, topic modeling)
- Behavioral segmentation (e.g., purchase likelihood, recommendation patterns)
- Product-level aggregation and trend analysis
- Ethical modeling with clear handling of missing and ambiguous data

##  Technical Budget Summary

Here’s a breakdown of the key technical operations and their modeling value:

| Task                            | Skill Area                        | Budget Justification |
|---------------------------------|-----------------------------------|----------------------|
| Missing value analysis          | Data wrangling, pandas            | High — preserves modeling integrity |
| Date parsing and conversion     | Temporal feature engineering      | Medium — enables time-based modeling |
| Ordinal encoding of behaviors   | Feature engineering, ethics       | High — captures user intent and silence |
| Log-normalization of helpfulness| Statistical transformation        | Medium — balances skewed distributions |
| Deduplication strategies        | NLP, user-level analysis          | High — prevents data leakage and bias |
| Column-level documentation      | Technical writing, transparency   | High — supports reproducibility and auditability |

##  Column Cleaning Decisions

A detailed column-by-column review is included in the notebook. Here's a preview:

-  Kept: `reviews.text`, `reviews.rating`, `reviews.username`, `upc`, `manufacturer`, `brand`
-  Dropped: `reviews.userCity`, `reviews.userProvince`, `ean`, `reviews.id`
-  Encoded: `reviews.didPurchase`, `reviews.doRecommend` → mapped to ordinal values with missing flags
-  Transformed: `reviews.numHelpful` → filled, flagged, log-normalized




