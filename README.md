# 📰 Text Mining on Korean News Discourse: PC, Topics & Sentiment

This repository contains all the source code and methodology used in the paper:

**"토픽모델링 및 감성분석 기법을 활용한 언론 기사의 핵심 이슈 및 논조 분석 – 정치적 올바름 키워드를 중심으로"**  
by Hyungjoo Kim (Ajou University, Department of Sociology & AI Convergence)

---

## 📌 Project Overview

This project explores how Korean media covered *Political Correctness (PC)* between 2010 and 2024.  
Using **LDA Topic Modeling** and **Lexicon-based Sentiment Analysis**, the research quantitatively identifies major topics, sentiment polarities, and ideological framings of conservative and progressive newspapers.

---

## 🛠 Methodology

### 🔹 Data Collection
- **Source**: Korean news articles including "정치적 올바름" keyword
- **Period**: 2010–2024
- **Collected via**: Selenium + BeautifulSoup crawling
- **Dataset Size**: ~4,100 articles

### 🔹 Preprocessing
- **NLP Tools**: KoNLPy (Okt tokenizer), R tidytext
- **Cleaning**: Remove non-Korean characters, combine title+body
- **Split**: 
  - Topic Modeling: nouns only  
  - Sentiment Analysis: nouns + adjectives + adverbs + verbs

---

## 📊 Analysis Pipeline

### 1. 📈 Keyword Frequency
- Extract TF and TF-IDF scores
- Visualize via Word Cloud

### 2. 🧠 LDA Topic Modeling
- Gensim LDA from `k=2` to `k=30`
- Evaluate with:
  - `Perplexity` (lower = better)
  - `Coherence (c_v)` (higher = better)
- Final model: `k=3` topics  
- Visualized using **pyLDAvis**

### 3. ❤️ Sentiment Analysis
- Dictionary: KNU Korean Sentiment Lexicon (Likert scale -2 to +2)
- Tool: KoNLPy + custom parser
- Output: tone distribution by topic & media ideology (liberal/conservative)

---

## 🧠 Topic Summary (k=3)

| Topic ID | Top Keywords | Interpretation |
|----------|--------------|----------------|
| 0 | 정치, 대통령, 정책, 보수, 진보 | Political Discourse & Party Conflict |
| 1 | 여성, 인종, 다양성, 차별 | Gender & Racial Diversity and Fairness |
| 2 | 트럼프, 대선, 표현의 자유 | Populist Politics & Free Speech Debates |

---

## 🔍 Key Findings

- Media frames differ **significantly by ideology** (liberal vs. conservative)
- PC is **not a single-topic discourse** but overlaps with **identity politics, speech regulation**, and **inter-party conflict**
- Emotional tones are **highly polarized**, often reflecting the outlet's bias
- Topic 1 (diversity-related) had the **highest affective polarity**

---

## 📁 Files

| File | Description |
|------|-------------|
| `lda_model.py` | Topic modeling pipeline (gensim + pyLDAvis) |
| `sentiment_analysis.py` | KNU lexicon-based tone analysis |
| `preprocessing.py` | Full text preprocessing steps |
| `data/` | Crawled and cleaned datasets |
| `visuals/` | Word clouds and pyLDAvis outputs |
| `thesis_summary.pdf` | Full research summary (in Korean) |

---

## 🧾 Citation

