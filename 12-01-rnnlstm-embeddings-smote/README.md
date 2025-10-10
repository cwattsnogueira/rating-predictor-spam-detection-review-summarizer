#  Binary Review Classification with PyTorch LSTM + SMOTE

[![Status](https://img.shields.io/badge/status-active-brightgreen)](https://github.com/cwattsnogueira/rating-predictor-spam-detection-review-summarizer)
![License](https://img.shields.io/badge/license-MIT-blue)
![Python](https://img.shields.io/badge/python-3.10%2B-yellow)
![PyTorch](https://img.shields.io/badge/pytorch-LSTM--based--model-orange)
![Modeling](https://img.shields.io/badge/modeling-text--only--classification-purple)
![Bias Mitigation](https://img.shields.io/badge/SMOTE-balanced--training-green)

<a href="https://colab.research.google.com/github/cwattsnogueira/rating-predictor-spam-detection-review-summarizer/blob/main/12_01_RNNLSTM_embeddings_SMOTE.ipynb" target="_parent">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

---

##  Purpose

This notebook trains a binary classifier using a **custom PyTorch LSTM model** to detect fake reviews. It includes SMOTE-based class balancing, token-level preprocessing, optional GloVe embeddings, and full evaluation across train/val/test splits.

---

##  Folder Structure

```
├── 12-01-pytorch-lstm-smote/
│   ├── notebook/     # Contains this PyTorch LSTM notebook
│   ├── output/       # Saved model, vocab, and plots
│   └── README.md     # This documentation
```

---

##  Input Files

| File Name                      | Description                                 | Link |
|-------------------------------|---------------------------------------------|------|
| `engineered_features.parquet` | Dataset with cleaned text and binary label  | [View file](../05-feature-engineering/output/engineered_features.parquet) |
| `glove.6B.100d.txt`           | Optional GloVe embeddings (if available)     | [Upload manually] |

---

##  Output Files

| File Name             | Description                                 | Link |
|----------------------|---------------------------------------------|------|
| `best_rnn_model.pt`  | Best model weights (based on val F1)        | [Download](./output/best_rnn_model.pt) |
| `rnn_vocab.pkl`       | Vocabulary mapping (`itos`, `stoi`)         | [Download](./output/rnn_vocab.pkl) |

---

##  What the Code Does

###  Data Preparation

- Loads text and binary label column (auto-detected)
- Splits into train/val/test (70/15/15)
- Applies SMOTE using TF-IDF to balance training set
- Reconstructs balanced text samples for token-based modeling

###  Tokenization & Vocabulary

- Tokenizes text using whitespace split
- Builds vocabulary from training set (max 30k tokens)
- Converts text to padded sequences for PyTorch

###  Embedding Initialization

- Optionally loads GloVe vectors (`glove.6B.100d.txt`)
- Builds embedding matrix for known tokens

###  Model Architecture

- Custom `LSTMClassifier` with:
  - Embedding layer (trainable)
  - Bidirectional LSTM
  - Mean pooling
  - Dropout + Dense output (2 classes)

###  Training & Evaluation

- Trains for 6 epochs with early saving based on validation F1
- Evaluates on test set with:
  - Accuracy
  - Precision
  - Recall
  - F1 Score

---

##  Final Test Performance

| Metric     | Value |
|------------|-------|
| Accuracy   | 0.89  |
| Precision  | 0.91  |
| Recall     | 0.87  |
| F1 Score   | 0.89  |

---

##  Budget Justification

| Task                              | Skill Area               | Budget Rationale |
|-----------------------------------|--------------------------|------------------|
| SMOTE balancing                   | Bias mitigation          | High — ensures fair training |
| Custom LSTM architecture          | Deep learning            | High — captures sequential patterns |
| GloVe integration (optional)      | Semantic enrichment      | Medium — improves embedding quality |
| Token-level preprocessing         | NLP pipeline             | Medium — supports reproducibility |
| Evaluation + export               | Interpretability         | High — enables deployment and auditability |

---

