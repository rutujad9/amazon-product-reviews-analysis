# Amazon Product Reviews Analysis

A **data mining and natural language processing (NLP)** project that analyzes Amazon product reviews to:

- predict sentiment from review text
- discover underlying customer review topics
- identify mismatches between written sentiment and star ratings

---

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![NLP](https://img.shields.io/badge/NLP-Text%20Mining-green.svg)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange.svg)
![Project](https://img.shields.io/badge/Project-Academic-important.svg)

---

## Project Overview

Customer reviews contain valuable insights about products.  
This project applies **machine learning and NLP techniques** to extract meaningful information from Amazon product reviews.

The analysis focuses on:

- **Sentiment prediction** from review text
- **Topic discovery** in customer feedback
- **Rating–sentiment discrepancy detection**

These insights help identify patterns in customer feedback and highlight products with inconsistent ratings.

---

## Research Questions

The project investigates three key questions:

### 1️⃣ Can sentiment be predicted from review text?

Using **TF-IDF features** and a **Logistic Regression classifier**, the project evaluates whether textual reviews can accurately predict review sentiment.

### 2️⃣ What topics emerge in customer reviews?

Two topic discovery approaches are used:

- **Latent Dirichlet Allocation (LDA)**
- **Word2Vec embeddings + KMeans clustering**

These methods uncover common themes such as product categories and usage contexts.

### 3️⃣ Which products show mismatch between rating and sentiment?

Using **VADER sentiment analysis**, the project compares

```
written sentiment vs star rating
```

to identify products with **inconsistent feedback**.

---

## Dataset

Dataset: **Amazon Product Reviews dataset (Kaggle)**

https://www.kaggle.com/datasets/jillanisofttech/amazon-product-reviews

Main fields used:

- `ProductId`
- `Summary`
- `Score`

The dataset contains **customer reviews, product IDs, and rating scores**.

---

## Tech Stack

- Python
- pandas
- numpy
- scikit-learn
- nltk
- gensim
- matplotlib
- seaborn

---

## Project Structure

```
amazon-product-reviews/
│
├── notebooks/
│   └── data-mining.ipynb
├── images/
├── data/
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Methods Used

The following machine learning and NLP techniques were applied:

- **TF-IDF vectorization**
- **Logistic Regression sentiment classification**
- **Latent Dirichlet Allocation (LDA)**
- **Word2Vec embeddings**
- **KMeans clustering**
- **VADER sentiment analysis**
- **t-SNE visualization**
- **PCA visualization**

---

## Analysis Workflow

### Data Preprocessing

- removed missing summaries
- handled duplicate reviews
- cleaned text (HTML removal, punctuation removal)
- applied stopword filtering

### Sentiment Prediction

- converted ratings into **sentiment labels**
- extracted features using **TF-IDF**
- trained **Logistic Regression classifier**
- evaluated predictions using **classification metrics**

### Topic Discovery

Two complementary approaches were used:

**LDA Topic Modeling**

- identifies groups of words frequently appearing together

**Word2Vec + KMeans**

- clusters reviews based on semantic similarity

### Rating–Sentiment Discrepancy

Using **VADER sentiment scores**, the project calculates:

```
discrepancy = |sentiment_score - rating_score|
```

This highlights products where **text sentiment does not match the star rating**.

---

## Key Findings

- Logistic Regression trained on TF-IDF features achieved **84.68% accuracy** on the test dataset, demonstrating that review text can reliably predict sentiment.

- Customer reviews reveal **clear topic clusters** related to product categories using LDA and Word2Vec clustering.

- Some products exhibit **large sentiment–rating discrepancies**, indicating inconsistent feedback between review text and star ratings.

- **t-SNE and PCA visualizations** help reveal structure in customer review topics.

---

## How to Run

Clone the repository:

```bash
git clone https://github.com/rutujad9/amazon-product-reviews-analysis.git
cd amazon-product-reviews-analysis
```

Create a virtual environment:

```bash
python -m venv venv
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Download the dataset from Kaggle and place:

```
Reviews.csv
```

inside the **data/** folder.

Open the notebook:

```bash
jupyter notebook
```

Run:

```
notebooks/data-mining.ipynb
```

---

## Results Preview

### Rating Distribution
![Rating Distribution](images/rating-distribution.png)

### Topic Clusters using t-SNE
![t-SNE Topic Clusters](images/tsne-topics.png)

### Rating–Sentiment Discrepancy
![Rating–Sentiment Discrepancy](images/discrepancy-boxplot.png)

---

## Future Improvements

- apply **transformer-based sentiment models (BERT)**
- experiment with additional clustering algorithms
- analyze **full review text instead of summary only**
- build an **interactive dashboard** for product insights

---

## Author

Rutuja Deshmukh  
MSc Informatik — Germany

---

## License

This project is provided for **educational and portfolio purposes**.

The dataset belongs to the original **Kaggle source**.

