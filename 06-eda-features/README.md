#  EDA on Engineered Features

[![Status](https://img.shields.io/badge/status-active-brightgreen)](https://github.com/cwattsnogueira/rating-predictor-spam-detection-review-summarizer)
![License](https://img.shields.io/badge/license-MIT-blue)
![Python](https://img.shields.io/badge/python-3.10%2B-yellow)
![Pandas](https://img.shields.io/badge/pandas-2.0.3-orange)
![Seaborn](https://img.shields.io/badge/seaborn-0.12.2-lightblue)
![Matplotlib](https://img.shields.io/badge/matplotlib-3.8.0-purple)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-RandomForestClassifier-orange)
![Feature Engineering](https://img.shields.io/badge/feature--analysis-✓-informational)
![Ethical AI](https://img.shields.io/badge/ethics-bias--detection-green)

<a href="https://colab.research.google.com/github/cwattsnogueira/rating-predictor-spam-detection-review-summarizer/blob/main/06_eda_features.ipynb" target="_parent">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

---

##  Purpose

This notebook performs exploratory data analysis (EDA) on engineered features used for fake review detection and rating prediction. It validates assumptions, visualizes distributions, detects bias, and ranks feature importance using a Random Forest model.

---

##  Folder Structure

```
├── 06-eda-features/
│   ├── notebook/     # Contains this EDA notebook
│   ├── output/       # Saved plots and visualizations
│   └── README.md     # This documentation
```

---

##  Input File

| File Name                      | Description                                 | Link |
|-------------------------------|---------------------------------------------|------|
| `engineered_features.parquet` | Dataset with structured features            | [View file](../05-feature-engineering/output/engineered_features.parquet) |

---

##  What the Code Does

- Loads the engineered dataset and selects key features for analysis
- Plots distribution histograms for each feature
- Computes and visualizes a correlation matrix including the target label
- Uses boxplots to compare feature distributions across fake/genuine labels
- Displays label balance using a countplot
- Trains a `RandomForestClassifier` to assess feature importance
- Visualizes ranked importance scores to guide modeling decisions

---

##  Features Analyzed

```python
[
  'review_length',
  'sentiment_polarity',
  'username_dup_flag',
  'product_name_match_flag',
  'unrelated_product_flag',
  'semantic_mismatch_score'
]
```

These features capture linguistic, behavioral, and semantic signals relevant to fake review detection.

---

##  Visual Outputs

All plots are saved in the `output/` folder and rendered below:

###  Feature Distributions

- ![Review Length](./output/reviewlength.png)
- ![Sentiment Polarity](./output/sentimentpolarity.png)
- ![Username Duplication Flag](./output/distributionusernamedupflag.png)
- ![Product Name Match Flag](./output/distributionofproductname.png)
- ![Unrelated Product Flag](./output/distributionunrelatedproduct.png)
- ![Semantic Mismatch Score](./output/distributionofsemantic.png)

###  Label Comparison by Feature

- ![Review Length by Label](./output/distributionreview.png)
- ![Sentiment Polarity by Label](./output/distributionsentiment.png)
- ![Username Dup Flag by Label](./output/usernamedupflagfakereview.png)
- ![Product Name Match by Label](./output/productnamematchflag.png)
- ![Unrelated Product Flag by Label](./output/unrelatedproductflagfake.png)
- ![Semantic Mismatch by Label](./output/semanticmismatch.png)

###  Correlation & Label Distribution

- ![Correlation Matrix](./output/corre.png)
- ![Fake Review Label Distribution](./output/fakereviewlabeldist.png)

###  Feature Importance

- ![Feature Importance](./output/featureimportance.png)

---

##  Budget Justification

| Task                          | Skill Area               | Budget Rationale |
|-------------------------------|--------------------------|------------------|
| Distribution analysis         | EDA                      | High — reveals skew, outliers, and signal strength |
| Correlation matrix            | Feature selection         | Medium — identifies redundancy and relationships |
| Label comparison via boxplots | Bias detection            | High — supports ethical modeling |
| Random Forest importance      | ML interpretability       | High — guides feature prioritization |
| Visualization                 | Data storytelling         | Medium — improves stakeholder communication |

---

