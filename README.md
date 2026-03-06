# Amazon Product Reviews Analysis

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![NLP](https://img.shields.io/badge/NLP-Text%20Mining-green.svg)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange.svg)
![Academic Project](https://img.shields.io/badge/Project-Academic-important.svg)
![License](https://img.shields.io/badge/License-Academic-lightgrey.svg)


## Project Overview
This project analyzes Amazon product reviews using advanced data mining and natural language processing techniques. The goal is to extract meaningful insights from customer review text by predicting sentiment, discovering hidden topics, and identifying inconsistencies between star ratings and textual sentiment.

The project was developed as part of the **Advanced Data Mining** course under the supervision of **Prof. Dennis Mendoza**.

---

## Research Questions
1. Can sentiment be predicted from review text?
2. What topics emerge in customer reviews?
3. Which products have the highest discrepancy between star ratings and review sentiment?

---

## Dataset
- **Source:** Kaggle – Amazon Product Reviews Dataset
- **Main Fields Used:**
  - `ProductId`
  - `Summary`
  - `Score`
- Reviews with missing summaries were removed.
- Duplicate entries were filtered out.

---

## Project Structure
```
├── data-mining.ipynb   # Main notebook with full analysis
├── README.md           # Project documentation
```

---

## Methodology

### 1. Data Preprocessing
- Text cleaning: lowercasing, removing HTML tags, punctuation, and non-alphabetic characters
- Removal of English and domain-specific stopwords
- Creation of a cleaned text column (`clean_summary`)

### 2. Sentiment Labeling
Star ratings were mapped to sentiment labels:
- Rating ≥ 4 → Positive
- Rating = 3 → Neutral
- Rating ≤ 2 → Negative

---

## Sentiment Prediction (Research Question 1)
- **Feature Extraction:** TF-IDF vectorization
- **Model:** Logistic Regression
- **Train-Test Split:** 80% training, 20% testing
- **Evaluation Metrics:** Precision, Recall, F1-score

Result: The model achieved good performance, showing that review text can effectively predict sentiment.

---

## Topic Modeling (Research Question 2)
Two different approaches were used:

### Approach 1: Latent Dirichlet Allocation (LDA)
- Applied on a document-term matrix using CountVectorizer
- Extracted 4 latent topics based on word co-occurrence
- Topics interpreted using top keywords

### Approach 2: Word2Vec + KMeans
- Word2Vec embeddings trained on review summaries
- Review-level vectors created by averaging word embeddings
- KMeans clustering (4 clusters)
- Topics identified and labeled manually
- Visualized using t-SNE and PCA

---

## Rating–Sentiment Discrepancy Analysis (Research Question 3)
- Sentiment scores computed using VADER sentiment analysis
- Ratings mapped to numerical sentiment values
- Discrepancy calculated as the absolute difference between rating score and sentiment score
- Average discrepancy computed per product

This analysis highlights products with inconsistent customer feedback.

---

## Visualization
- Rating distribution (bar chart & pie chart)
- Top words in positive vs negative reviews
- Topic visualizations using t-SNE and PCA
- Boxplots for rating–sentiment discrepancy

---

## Tools & Technologies
- **Programming Language:** Python
- **Libraries:**
  - pandas, numpy
  - scikit-learn
  - matplotlib, seaborn
  - nltk, gensim

---

## How to Run
1. Clone the repository:
   ```bash
   git clone https://gitlab.rlp.net/adam_ws_2526/amazonreviews_rutuja.git
   ```
2. Open the project in any IDE.

3. Run `data-mining.ipynb` cell by cell.

---

## Results Summary
- Sentiment can be reliably predicted from review text
- Clear and interpretable topics emerge from customer reviews
- Certain products show strong mismatches between ratings and textual sentiment

---

## Future Work
- Apply transformer-based models (BERT, RoBERTa) for sentiment analysis
- Analyze temporal trends in reviews
- Extend topic modeling to include neutral and negative reviews

---

## Author
**Rutuja Deshmukh**  
MSc Informatik  
Advanced Data Mining  
TH Bingen

---

## License
This project is intended for academic use only.

