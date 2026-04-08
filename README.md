# 🐦 Twitter Sentiment Analysis & Topic Modeling

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![NLTK](https://img.shields.io/badge/NLTK-3.8-green)
![Gensim](https://img.shields.io/badge/Gensim-4.4.0-orange)
![Dataset](https://img.shields.io/badge/Dataset-Sentiment140-yellow)

## 📌 Project Overview

An end-to-end NLP project analyzing **1.6 million tweets** from the Sentiment140 dataset. The project covers the full data science pipeline — from raw text cleaning to sentiment analysis and topic modeling — uncovering hidden patterns in Twitter user behavior from 2009.

---

## 🎯 Business Problem

How do people express emotions on social media, and what topics dominate public discourse? This project answers:
- What is the overall sentiment distribution on Twitter?
- Which topics do users tweet about most?
- When are users most positive/negative throughout the day?
- How accurately can rule-based NLP detect tweet sentiment?

---

## 📂 Project Structure
twitter-sentiment-tracker/
├── notebooks/
│   ├── analysis.ipynb
├── outputs/
│   └── dashboard.png
├── README.md
└── LICENSE
---

## 📊 Dataset

- **Source:** [Sentiment140 — Kaggle](https://www.kaggle.com/datasets/kazanova/sentiment140)
- **Size:** 1.6 million tweets
- **Period:** April — June 2009
- **Features:** target, date, user, text
- **Labels:** 0 = Negative, 4 = Positive (converted to 0/1)

---

## 🔧 Tech Stack

| Category | Tools |
|---|---|
| Data Processing | Pandas, NumPy |
| Text Cleaning | NLTK, Regex |
| Sentiment Analysis | VADER (SentimentIntensityAnalyzer) |
| Topic Modeling | Gensim (LDA) |
| Visualization | Matplotlib, Seaborn, WordCloud |
| Environment | Jupyter Notebook |

---

## 🚀 Project Pipeline

### Phase 1 — Data Loading & Setup
- Loaded 1.6M tweets with custom column names
- Checked for null values and duplicates
- Converted target labels (4 → 1)
- Parsed datetime column

### Phase 2 — Text Cleaning & EDA
- Lowercasing, URL removal, @mention removal
- Extracted hashtags into separate column before removal
- Removed special characters, stopwords, custom noise words
- Lemmatization using WordNetLemmatizer
- EDA: Tweet length distribution, word frequency, WordCloud, hashtag analysis, time trends

### Phase 3 — Sentiment Analysis (VADER)
- Applied VADER to all 1.6M tweets
- Generated compound scores (-1 to +1)
- Classified tweets into Positive / Neutral / Negative
- Compared VADER predictions vs original labels — **71.56% accuracy**
- Confusion matrix analysis

### Phase 4 — Topic Modeling (LDA)
- Sampled 100k tweets for LDA
- Built Gensim Dictionary + Corpus
- Trained LDA with 10 topics
- Identified and labeled topics manually

### Phase 5 — Visualization & Insights
- Built 6-panel master dashboard
- Generated business recommendations

---

## 📈 Key Findings

| Finding | Insight |
|---|---|
| Sentiment Split | 46.3% Positive, 27.7% Neutral, 25.9% Negative |
| VADER Accuracy | 71.56% — good for rule-based, no training required |
| Top Topic | Work & Daily Life dominates Twitter discourse |
| Peak Positivity | UTC 0-7 hours (US evening time) |
| Top Hashtag | #followfriday — 2600+ mentions |
| Neutral Spike | 443k tweets scored 0.00 — insufficient sentiment signals |

---

## 💡 Business Recommendations

1. **Brand Engagement** — Schedule posts during UTC 0-7 (US evening) for maximum positive sentiment reach
2. **Content Strategy** — Work-life balance and morning wellbeing content resonates most with Twitter audience
3. **Hashtag Strategy** — Community-driven hashtags like #followfriday drive highest organic engagement
4. **Sentiment Monitoring** — VADER sufficient for trend-level analysis; ML model recommended for production-level accuracy
5. **Crisis Detection** — Negative sentiment spikes (like June 17, 2009) can signal real-world events early

---

## ⚠️ Limitations

- Dataset is from 2009 — Twitter behavior has changed significantly
- VADER struggles with sarcasm and informal negative language
- Non-English tweets (~small %) may affect sentiment scores
- LDA trained on 100k sample, not full 1.6M tweets

---

## 🛠️ Setup & Installation

```bash
# Clone the repo
git clone https://github.com/byteephantom/twitter-sentiment-tracker.git
cd twitter-sentiment-tracker

# Install dependencies
pip install -r requirements.txt

# Download NLTK data
python -c "import nltk; nltk.download('stopwords'); nltk.download('wordnet'); nltk.download('vader_lexicon')"

# Run notebook
jupyter notebook notebooks/analysis.ipynb
```

---

## 📦 Requirements
```bash
  pandas
  numpy
  matplotlib
  seaborn
  nltk
  gensim
  wordcloud
  tqdm
  scikit-learn
  jupyter 
```
---

## 👤 Author

**Quantum Nomad**
- GitHub: [@byteephantom](https://github.com/byteephantom)
- LinkedIn: [Ayush Kumar]([https://linkedin.com/in/ayushk24)

---

## 📜 License

MIT License — feel free to use and modify.
