<p align="center">
  <img src="https://img.shields.io/badge/Language-English-blue?style=for-the-badge&logo=googletranslate&logoColor=white" alt="English">
  <a href="README_TR.md"><img src="https://img.shields.io/badge/Dil-Türkçe-red?style=for-the-badge&logo=googletranslate&logoColor=white" alt="Türkçe"></a>
</p>

---

# 🎬 CosineCast — Movie Recommender System

[![Live Demo](https://img.shields.io/badge/Live_Demo-CosineCast_App-E50914?style=for-the-badge&logo=google&logoColor=white)](https://cosinecast.ai.studio/)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1_gwoZcq9GkjQnLejZ5dtYFn62_auoNNT?usp=sharing)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Dataset](https://img.shields.io/badge/Dataset-MovieLens_100K-F37021?style=flat)](https://grouplens.org/datasets/movielens/100k/)

An end-to-end, mathematically grounded Movie Recommendation System built on the benchmark **MovieLens 100K** dataset. 

This repository hosts the original **Google Colab notebook**, algorithms, and exploratory data analysis built completely from scratch. An interactive, production-ready web application demo was built and deployed using **Google AI Studio** to showcase the model in real time.

🔗 **Explore the Live Web App:** [CosineCast Interactive Demo](https://cosinecast.ai.studio/)

---

## 📌 Project Architecture & Attribution

- **Core Machine Learning & Algorithms (Google Colab):**  
  Designed, formulated, and implemented **from scratch** in Google Colab. Covers data ingestion, exploratory data analysis (EDA), matrix vectorization, and recommendation math (Content-Based and Collaborative Filtering).
  
- **Interactive Web Demo (Google AI Studio):**  
  To bring the static notebook to life, **Google AI Studio** was utilized to convert the Colab engine into an interactive, reactive web user interface.

---

## 🚀 Key Recommendation Algorithms

### 1. Content-Based Filtering (Genre Cosine Similarity)
- Encodes film genres into binary feature vectors.
- Calculates high-dimensional cosine similarity between item representations:
  $$\text{Cosine Similarity}(\mathbf{u}, \mathbf{v}) = \frac{\mathbf{u} \cdot \mathbf{v}}{\|\mathbf{u}\|_2 \|\mathbf{v}\|_2}$$
- Recommends the top $N$ closest cinematic matches for any selected film.

### 2. User-Based Collaborative Filtering (User-Item Matrix)
- Constructs a sparse pivot matrix ($610 \text{ users} \times 9{,}700+ \text{ movies}$).
- Identifies the most correlated peer users with shared taste profiles.
- Predicts missing movie ratings through similarity-weighted voting and delivers targeted recommendations.

### 3. Cold-Start Solution for New Users
- Addresses the cold-start problem by presenting an onboarding taste profile builder.
- Dynamically blends initial rating inputs with genre preferences to deliver real-time personalized suggestions without requiring a prior user history.

### 4. Exploratory Data Analysis (EDA)
- Rating distributions, user activity histograms, sparsity analysis, and genre heatmaps.

---

## 📊 Dataset: GroupLens MovieLens 100K

- **100,836** ratings across **9,742** movies.
- **610** unique anonymous users.
- Rating scale: $0.5$ to $5.0$ stars.

---

## 🛠️ Tech Stack & Libraries

- **Data Processing & Math:** Python, `pandas`, `numpy`, `scipy`
- **Machine Learning & Similarity:** `scikit-learn` (`cosine_similarity`)
- **Development Environment:** Google Colab
- **Live Demo Platform:** Google AI Studio / Cloud Run (React, TypeScript, Tailwind CSS)
