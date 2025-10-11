##  2. Solution Overview

For this project, I designed a hybrid AI-powered moderation pipeline to help detect, summarize, and flag suspicious product reviews for human oversight. The goal is to support eCommerce platforms in maintaining trust, improving rating accuracy, and streamlining the review moderation process.

###  How I Built It

I started by analyzing real-world review data, looking for inconsistencies between star ratings and the actual sentiment expressed in the text. From there, I engineered features to capture patterns like repetition, sentiment polarity, product name overlap, and promotional language.

Once the data was structured, I trained and fine-tuned multiple models:

- A BERT-based classifier to detect spam and fake reviews  
- A regression model to predict star ratings directly from review text  
- Extractive summarization using BERT embeddings  
- Abstractive summarization using GPT-3.5 and GPT-4

These models work together to evaluate reviews from multiple angles: semantic quality, sentiment alignment, and structural anomalies.

###  Architecture Overview

**Input Sources**  
- Manual review entry  
- CSV uploads from product databases  
- API integration with eCommerce platforms

**AI Modules**  
- BERT-based extractive summarization  
- GPT-3.5/GPT-4 abstractive summarization  
- Spam detection via anomaly flags (e.g., repetition, sentiment mismatch, product overlap)  
- Star rating prediction from review text

**Review Scoring & Flagging**  
- Compare predicted star rating vs. actual rating  
- Heuristic flags: short/extreme sentiment, promotional language, unrelated keywords  
- Anomaly detection using Isolation Forest and One-Class SVM

**Moderation Queue**  
- Reviews flagged as suspicious are routed to a dashboard  
- Moderators can approve, reject, or reclassify  
- Option to adjust product rating based on verified reviews

**Outputs**  
- Summary reports  
- Review classification (Genuine vs. Fake)  
- Updated product rating suggestions  
- Moderation logs for auditability

![Architecture Overview](./output/architecture.png)

---

