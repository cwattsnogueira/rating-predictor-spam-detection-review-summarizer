#  Final Project: Review Intelligence Pipeline

**Author:** Carllos Watts-Nogueira  
**Location:** NY, USA  
**GitHub:** [github.com/carlloswatts-nogueira](https://github.com/cwattsnogueira)  
**LinkedIn:** [linkedin.com/in/carlloswatts-nogueira](https://linkedin.com/in/carlloswattsnogueira)

---

##  Business Overview

This repository presents a full pipeline for analyzing and moderating product reviews using machine learning, NLP, and deep learning techniques. It is designed to support both technical exploration and business decision-making.

 Business Documentation:
- [Problem Statement](./docs-business/01_problem.md)
- [Solution Overview](./docs-business/02_solution.md)
- [Results & Insights](./docs-business/03_results.md)

---

##  Project Structure

###  Preprocessing & Initial Analysis
- [01 - Data Loader & Review Cleaning](./01-data-loader-review-clean/)
- [02 - Exploratory Data Analysis (EDA)](./02-eda-initial)
- [03 - Category Cleaning](./03-category-cleaning/)
- [04 - Text Cleaning & Vectorization](./04-text-cleaning-vectorization/)
- [05 - Feature Engineering](./05-feature-engineering/)
- [05-01 - Text Embeddings with SVD & GloVe](./05-01-text-embeddings-svd-glove/)
- [05-02 - Data Profiling with YData](./05-02-data-profiling/)
- [06 - EDA on Engineered Features](./06-eda-features/)
- [07 - Sentiment Analysis by Category](./07-sentiment-by-category/)

###  Supervised Modeling
- [08 - Rating Prediction](./08-rating-prediction/)
- [08-01 - Fine-Tuning BERT Models](./08-01-fine-tuning-berts/)
  - [08-01-01-BERT 5-Class Rating Model](./08-01-fine-tuning-berts/bert-5class-rating-model/)
  - [08-01-02-Hybrid Rating Pipeline](./08-01-fine-tuning-berts/hybrid-rating-pipeline/)
- [10 - Fake Review Modeling (Upsampled)](./10-fake-review-modeling-upsampled/)
- [10-01 - Fake Review Modeling (SMOTE)](./10-01-fake-review-modeling-smote/)
- [12 - Deep Learning Modeling](./12-dl-modeling/)
- [12-01 - RNN/LSTM with Embeddings & SMOTE](./12-01-rnnlstm-embeddings-smote/)
- [13-BERT - Fake Review Detection](./13-fine-tuning-bert-oversampling/)

###  Unsupervised Modeling
- [08-02 - Unsupervised Workflows](./08-02-unsupervised-workflows/)
  - [08-02-01-Clustering with KMeans](./08-02-unsupervised-workflows/clustering-kmeans-elbow/)
  - [08-02-02-Outlier Detection with Isolation Forest](./08-02-unsupervised-workflows/outlier-detection-isolation-forest/)
- [11 - Anomaly Detection](./11-anomaly-detection/)

###  Applications & Interfaces
- [09 - App: Rating Review Assistant](./09-app-rating-review/)
- [14 - App - Spam Review Moderation](./14-app-fake-review/)
- [15 - Review Summarization App](./15-review-summarization-app/)
- [15-01 - Review Summarization - T5 Small](./15-review-summarization-app/15-01-review-summarization-t5-small/)
- [15-02 - Review Summarization - BERT Base](./15-review-summarization-app/15-02-review-summarization-bert-base/)
- [15-03 - Review Summarization - GPT-3](./15-review-summarization-app/15-03-review-summarization-gpt3/)
- [15-04 - Review Summarization - GPT-4](./15-review-summarization-app/15-04-review-summarization-gpt4/)

---

##  Navigation & Dependencies

Each module includes:
-  A technical `README.md`
-  Jupyter/Colab notebooks in `notebook/`
-  Outputs in `output/`
-  Colab links and reusable artifacts

Modules are designed to run sequentially, with outputs from one step feeding into the next.

---

##  Getting Started

1. Begin with [01 - Data Loader](./01-data-loader-review-clean/) to load and clean raw review data.
2. Follow the numbered folders to explore the full pipeline.
3. Refer to each module’s README for technical details and Colab links.
4. For business context, explore the [docs-business](./docs-business/) folder.

---

##  Contributions

This project is under active development. Suggestions, improvements, and collaborations are welcome!
