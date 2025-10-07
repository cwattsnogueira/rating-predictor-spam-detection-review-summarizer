#  Text Cleaning and Vectorization

[![Status](https://img.shields.io/badge/status-active-brightgreen)](https://github.com/cwattsnogueira/rating-predictor-spam-detection-review-summarizer)
![License](https://img.shields.io/badge/license-MIT-blue)
![Python](https://img.shields.io/badge/python-3.10%2B-yellow)
![NLP](https://img.shields.io/badge/NLP-preprocessing%20%7C%20vectorization-purple)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-CountVectorizer%20%7C%20TFIDF-orange)
![Ethical AI](https://img.shields.io/badge/ethics-clean%20%26%20transparent-green)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cwattsnogueira/rating-predictor-spam-detection-review-summarizer/blob/main/04_text_cleaning_and_vectorization.ipynb)

---

##  Purpose

This notebook prepares the `reviews.text` field for NLP modeling. It performs deep text cleaning, analyzes review length, and vectorizes the cleaned text using both CountVectorizer and TF-IDF. Each artifact is saved separately for downstream ML, DL, and fine-tuning workflows.

---

##  Folder Structure

```
├── 04-text-cleaning-vectorization/
│   ├── input/        # Contains cleaned_reviews_with_categories.parquet
│   ├── notebook/     # This notebook
│   ├── output/       # Saved vectorized matrices and models
│   └── README.md     # This documentation
```

---

##  Input File

| File Name                          | Description                                 | Link |
|-----------------------------------|---------------------------------------------|------|
| `cleaned_reviews_with_categories.parquet` | Dataset with cleaned categories and review text | [ View file](../03-category-cleaning/output/cleaned_reviews_with_categories.parquet) |

---

##  Output Artifacts

Each file below is saved in the `output/` folder and ready for download:

| File Name                          | Description                              | Download Link |
|-----------------------------------|------------------------------------------|----------------|
| `cleaned_reviews_with_text.parquet` | Full dataset with cleaned text           | [ Download](./output/cleaned_reviews_with_text.parquet) |
| `X_count_vectorized.pkl`          | CountVectorizer matrix                   | [ Download](./output/X_count_vectorized.pkl) |
| `count_vectorizer.pkl`            | Fitted CountVectorizer model             | [ Download](./output/count_vectorizer.pkl) |
| `X_tfidf_vectorized.pkl`          | TF-IDF matrix                            | [ Download](./output/X_tfidf_vectorized.pkl) |
| `tfidf_vectorizer.pkl`            | Fitted TF-IDF model                      | [ Download](./output/tfidf_vectorizer.pkl) |

---

##  What the Code Does

- Loads the enhanced dataset with category information
- Cleans the `reviews.text` field:
  - Removes HTML, punctuation, digits, URLs
  - Lowercases, tokenizes, removes stopwords
  - Applies lemmatization
- Analyzes review length and flags short entries
- Vectorizes the cleaned text using:
  - `CountVectorizer` (bag-of-words)
  - `TfidfVectorizer` (term frequency–inverse document frequency)
- Saves all artifacts for reuse in modeling pipelines

---

##  Budget Justification

| Task                          | Skill Area               | Budget Rationale |
|-------------------------------|--------------------------|------------------|
| Text cleaning pipeline        | NLP preprocessing        | High — ensures clean, consistent input |
| Stopword removal & lemmatization | Linguistic normalization | Medium — improves semantic clarity |
| Review length analysis        | Feature engineering       | Medium — flags sparse or noisy entries |
| CountVectorizer & TF-IDF      | Vectorization             | High — foundational for ML/NLP modeling |
| Artifact saving               | Workflow modularity       | High — supports reproducibility and reuse |

---

