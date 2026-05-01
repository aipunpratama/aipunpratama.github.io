---
layout: post
title: "KomDetek: Cyberbullying Detection in TikTok Comments"
date: 2025-06-19 14:00:00 +0700
categories: [projects, machine-learning]
tags: [python, nlp, sentiment-analysis, machine-learning, cyberbullying, google-colab]
author: aipunpratama
image: /assets/komdetek-banner.jpg
description: "A Natural Language Processing (NLP) project built with Python to analyze sentiment and automatically detect cyberbullying behavior within TikTok comments."
---

<div align="center">

<a href="https://colab.research.google.com/drive/1QQB4o4Eqn4RObcmGNNvLlhokYGYVf7TS?usp=sharing" target="_blank">
  <img src="https://img.shields.io/badge/Open_in_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Open in Colab">
</a>
<a href="https://github.com/aipunpratama/KomDetek" target="_blank">
  <img src="https://img.shields.io/badge/GitHub_Repo-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub Repo">
</a>

<br><br>

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
<img src="https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn">
<img src="https://img.shields.io/badge/NLTK-150458?style=for-the-badge&logo=python&logoColor=white" alt="NLTK">
<img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">

</div>

---

## 📖 Project Overview

**KomDetek** (Komentar Deteksi) is a Machine Learning and Natural Language Processing (NLP) project designed to tackle a growing issue in the digital age: online toxicity. Specifically focusing on the popular short-video platform **TikTok**, this project analyzes user comments to identify and classify cyberbullying and negative sentiment in the Indonesian language.

> *"Leveraging Machine Learning to foster safer and more positive digital communities on social media."*

### 🎯 **Mission**
To build a robust sentiment analysis classification model capable of understanding Indonesian internet slang, effectively distinguishing between normal commentary and harmful cyberbullying.

---

## ✨ Key Features & Methodology

### 🧠 **Natural Language Processing (NLP)**
- 🧹 **Text Preprocessing** - Advanced cleaning of raw TikTok comments (removing emojis, special characters, URLs, and transforming text to lowercase).
- 📖 **Stopword Removal & Stemming** - Utilizing NLP libraries to extract the root words and remove non-essential vocabulary.
- 🔠 **Slang Normalization** - Processing Indonesian internet slang into structured formats for better model understanding.

### 🤖 **Machine Learning Pipeline**
- 🔢 **Feature Extraction** - Transforming text data into numerical vectors using techniques like **TF-IDF** (Term Frequency-Inverse Document Frequency) or Count Vectorizer.
- 📈 **Model Training** - Training classification models to accurately categorize comments into specific sentiment classes.
- 📊 **Performance Evaluation** - Assessing model reliability using metrics like Accuracy, Precision, Recall, and F1-Score, complete with visual confusion matrices.

---

## 🛠️ Technology Stack

| Category               | Technology          | Purpose                                    |
| ---------------------- | ------------------- | ------------------------------------------ |
| **Language**           | Python 3            | 100% Core development language             |
| **Environment**        | Google Colab        | Cloud-based Jupyter environment for ML     |
| **Data Manipulation**  | Pandas, NumPy       | Data structuring and numerical computation |
| **NLP Processing**     | NLTK, Sastrawi      | Text processing for Bahasa Indonesia       |
| **Machine Learning**   | Scikit-Learn        | Model building, training, and evaluation   |
| **Data Visualization** | Matplotlib, Seaborn | Visualizing distributions and metrics      |

---

## 🏗️ The Machine Learning Architecture

### **NLP Data Pipeline**
```
🛡️ KomDetek Workflow
├── 📥 1. Data Collection (Raw TikTok comments dataset)
├── 🧹 2. Text Preprocessing 
│   ├── Case Folding & Cleansing
│   ├── Tokenization
│   └── Stopword Removal & Stemming
├── 🧮 3. Feature Extraction (Text to Vector)
├── 🤖 4. Model Training (Classification Algorithms)
└── 📈 5. Evaluation (Confusion Matrix & Accuracy Scores)
```

---

## 🚀 How to Run the Project

Since this project is fully developed in **Google Colaboratory**, you can easily run and interact with the code without installing anything locally!

1. **Open the Notebook:** Click the **[Open in Colab](https://colab.research.google.com/drive/1QQB4o4Eqn4RObcmGNNvLlhokYGYVf7TS?usp=sharing)** button at the top of this page.
2. **Copy to Drive:** Go to `File > Save a copy in Drive` so you can make your own edits.
3. **Run the Cells:** Click `Runtime > Run all` to execute the data pipeline from preprocessing to model evaluation.

*(Alternatively, you can clone the [GitHub Repository](https://github.com/aipunpratama/KomDetek) and run the `.ipynb` file locally using Jupyter Notebook).*

---

## 🌟 Future Development Plans

| Phase       | Feature                                    | Timeline  | Status     |
| ----------- | ------------------------------------------ | --------- | ---------- |
| **Phase 1** | 📊 Data Collection & Preprocessing Pipeline | Completed | ✅ Finished |
| **Phase 2** | 🤖 Machine Learning Model Training          | Completed | ✅ Finished |
| **Phase 3** | 🕸️ Web Interface / Dashboard Deployment     | Planned   | 📋 Planned  |
| **Phase 4** | 🧠 Deep Learning Integration (LSTM / BERT)  | Planned   | 💭 Concept  |

---

## 📊 Project Highlights

<div align="center">

<img src="https://img.shields.io/badge/Status-Completed-success?style=flat-square" alt="Status">
<img src="https://img.shields.io/badge/Language-Python_100%25-blue?style=flat-square" alt="Python">
<img src="https://img.shields.io/badge/Domain-NLP_%26_Sentiment_Analysis-purple?style=flat-square" alt="NLP">

</div>

### **Key Achievements**
- ✅ **Cloud-Native Development** - Successfully utilized Google Colab for seamless model training and experimentation.
- ✅ **High-Quality Preprocessing** - Handled the complex, unstructured nature of social media text (TikTok comments) using robust normalization techniques.
- ✅ **Accurate Classification** - Built a model capable of distinguishing toxic behavior with high reliability.

---

## 💡 Conclusion

**KomDetek** proves that Machine Learning can be a powerful ally in the fight against online toxicity. By accurately detecting cyberbullying in TikTok comments, this project demonstrates a complete end-to-end Natural Language Processing pipeline. 

By leveraging cloud environments like Google Colab, the barrier to reproducing this research is eliminated, allowing anyone to explore the model's logic step-by-step. This project lays the groundwork for automated moderation tools that can help creators and platforms maintain a healthy, positive environment for their users.

---

### 🌐 Links & Resources

**Developed with ❤️ by [aipunpratama](https://github.com/aipunpratama)**

<div align="center">

<a href="https://colab.research.google.com/drive/1QQB4o4Eqn4RObcmGNNvLlhokYGYVf7TS?usp=sharing" target="_blank">
  <img src="https://img.shields.io/badge/View_in_Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Colab">
</a>
&nbsp;&nbsp;
<a href="https://github.com/aipunpratama/KomDetek" target="_blank">
  <img src="https://img.shields.io/badge/View_on_GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
</a>

</div>

---

<div align="center">
<sub>🛡️ Supporting safer internet spaces. Give the repository a star if you support this cause! ⭐</sub>
</div>