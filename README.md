#  Final Project: Review Intelligence Pipeline

**Author:** Carllos Watts-Nogueira  
**Location:** Middletown, NY, USA  
**GitHub:** [github.com/carlloswatts](https://github.com/carlloswatts)  
**LinkedIn:** [linkedin.com/in/carlloswatts](https://linkedin.com/in/carlloswatts)

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
- [02 - Exploratory Data Analysis (EDA)](./02-eda/)
- [03 - Category Cleaning](./03-category-cleaning/)
- [04 - Text Cleaning & Vectorization](./04-text-cleaning-vectorization/)
- [05 - Feature Engineering](./05-feature-engineering/)
- [05-01 - Text Embeddings with SVD & GloVe](./05-01-text-embeddings-svd-glove/)
- [06 - EDA on Engineered Features](./06-eda-features/)
- [07 - Sentiment Analysis by Category](./07-sentiment-by-category/)

###  Supervised Modeling
- [08 - Rating Prediction](./08-rating-prediction/)
- [08 - Fine-Tuning BERT Models](./08-fine-tuning-berts/)
  - [BERT 5-Class Rating Model](./08-fine-tuning-berts/bert-5class-rating-model/)
  - [Hybrid Rating Pipeline](./08-fine-tuning-berts/hybrid-rating-pipeline/)
- [10 - Fake Review Modeling (Upsampled)](./10-fake-review-modeling-upsampled/)
- [10-01 - Fake Review Modeling (SMOTE)](./10-01-fake-review-modeling-smote/)
- [13 - Deep Learning Modeling](./13-dl-modeling/)
- [13-01 - RNN/LSTM with Embeddings & SMOTE](./13-01-rnnlstm-embeddings-smote/)
- [BERT - Fake Review Detection](./bert-fake-review/fine-tuning-bert-oversampling/)

###  Unsupervised Modeling
- [08 - Unsupervised Workflows](./08-unsupervised-workflows/)
  - [Clustering with KMeans](./08-unsupervised-workflows/clustering-kmeans-elbow/)
  - [Outlier Detection with Isolation Forest](./08-unsupervised-workflows/outlier-detection-isolation-forest/)
- [12 - Anomaly Detection](./12-anomaly-detection/)

###  Applications & Interfaces
- [09 - App: Rating Review Assistant](./09-app-rating-review/)
- [App - Fake Review Moderation](./app-fake-review/)
- [Review Summarization App](./review-summarization-app/)
- [Review Summarization - T5 Small](./review-summarization-t5-small/)
- [Review Summarization - BERT Base](./review-summarization-bert-base/)
- [Review Summarization - GPT-3](./review-summarization-gpt3/)
- [Review Summarization - GPT-4](./review-summarization-gpt4/)

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
