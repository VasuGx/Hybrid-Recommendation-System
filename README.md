# 🎧 Spotify Recommender System

A modular music recommender system that combines **Content-Based Filtering** and **Collaborative Filtering** to provide personalized track recommendations. The system is built using Python, DVC for pipeline management, and Streamlit for deployment. It is designed for scalability and reproducibility.

---

## 📌 Features

- ✅ **Data Cleaning & Preprocessing**
- 🎯 **Content-Based Filtering** using song metadata
- 👥 **Collaborative Filtering** using user listening history
- 🔀 **Hybrid Recommendations**
- 🧪 Modular and reproducible pipeline using **DVC**
- 🧱 Easy deployment with **Streamlit** and **Docker**
- 🧠 Uses encoders like `TFIDF`, `OneHotEncoder`, and `MinMaxScaler`

---

## 🗂️ Project Structure

```
spotify-recommender/
├── data/ # Raw and processed datasets
├── dvc.yaml # DVC pipeline stages
├── app.py # Streamlit frontend
├── content_based_filtering.py
├── collaborative_filtering.py
├── data_cleaning.py
├── hybrid_filtering.py
├── utils/ # Helper functions
│ └── encoders.py
├── models/ # Saved transformers/models
│ └── transformer.joblib
├── outputs/ # Final transformed data and matrices
├── requirements.txt
└── README.md
```


---

## ⚙️ Pipeline Overview

This project is managed using [DVC](https://dvc.org/) to ensure a reproducible and modular ML pipeline.

### 🔹 Stages in `dvc.yaml`:

1. **Data Cleaning**
   - Input: Raw Spotify datasets
   - Output: Cleaned CSVs and fitted encoders

2. **Content-Based Filtering**
   - Input: Cleaned features
   - Output: Transformed feature matrices (`.npz`), similarity data

3. **Collaborative Filtering**
   - Input: User listening history
   - Output: Sparse interaction matrix, song-user similarity matrix

4. **Hybrid Filtering**
   - Input: Outputs from both previous stages
   - Output: Final ranked recommendations

---

# 🧠 Recommender Logic
📌 Content-Based:
Vectorizes song metadata (genres, artists, lyrics)

Computes cosine similarity for ranking

📌 Collaborative:
Uses user play history to form a song-user matrix

Calculates item-item similarity via cosine distance

🔄 Hybrid:
Averages or weights both scores for better accuracy


🛠️ Setup & Installation

git clone https://github.com/VasuGx/Hybrid-Recommendation-System
cd spotify-recommender
pip install -r requirements.txt
dvc pull  # Pull data and models

📊 Sample Data
Song Metadata (songs.csv)

User Listening History (user_history.csv)

🧩 Tech Stack
Python

DVC

Scikit-Learn

Dask

Streamlit

Docker

GitHub Actions

Amazon ECR (optional)

✍️ Author
Vasu Gupta

Designed with modularity and reproducibility in mind.
