# 🎬 CineMatch – Hybrid Movie Recommendation System

CineMatch is a hybrid movie recommendation system that combines Content-Based Filtering and Collaborative Filtering to provide personalized movie recommendations based on movie characteristics and user preferences.

Developed as part of the Digital Egypt Pioneers Initiative (DEPI) – AI & Data Science Track.

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Project Objectives](#-project-objectives)
- [Key Features](#-key-features)
- [Recommendation Methodology](#-recommendation-methodology)
- [Dataset](#-dataset)
- [Technologies Used](#-technologies-used)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Running the Application](#-running-the-application)
- [Team Members](#-team-members)
- [Future Improvements](#-future-improvements)
- [References](#-references)

---

## 🎯 Project Overview

Movie streaming platforms provide users with thousands of movies, making it difficult to discover content that matches their interests.

CineMatch addresses this challenge by implementing a hybrid recommendation approach that combines two recommendation techniques:

1. **Content-Based Filtering:** Recommends movies based on their characteristics and similarity to movies the user likes.
2. **Collaborative Filtering:** Recommends movies based on the preferences and ratings of users with similar interests.

By combining both approaches, CineMatch aims to provide personalized and relevant movie recommendations.

---

## 🎯 Project Objectives

- Develop a personalized movie recommendation system.
- Combine Content-Based and Collaborative Filtering techniques.
- Analyze movie metadata and user ratings.
- Address the cold-start problem through a content-based fallback mechanism.
- Build an interactive web application using Streamlit.
- Evaluate recommendation quality and system performance.

---

## ✨ Key Features

- Movie data collection and integration.
- Movie metadata cleaning and preprocessing.
- Exploratory Data Analysis (EDA).
- Content-Based Filtering using TF-IDF.
- Movie similarity calculation using Cosine Similarity.
- Collaborative Filtering based on user ratings.
- User similarity calculations.
- Hybrid recommendation scoring.
- Movie rating functionality.
- Top-10 movie recommendations.
- Content-Based fallback when collaborative information is unavailable.
- Interactive Streamlit application.

---

## 🧠 Recommendation Methodology

CineMatch uses a hybrid recommendation architecture consisting of three main components.

### 1. Content-Based Filtering

Content-Based Filtering recommends movies based on their features and similarity to movies previously liked by the user.

The system analyzes movie metadata, including:

- Movie genres.
- Movie overview and description.
- Keywords.
- Directors.
- Cast members.

**Techniques Used:**

- Text Preprocessing.
- Feature Engineering.
- TF-IDF Vectorization.
- Cosine Similarity.
- VADER Sentiment Analysis.

TF-IDF converts textual movie information into numerical feature vectors, while Cosine Similarity measures the similarity between movies.

### 2. Collaborative Filtering

Collaborative Filtering analyzes user ratings to identify users with similar preferences and generate recommendations based on their behavior.

**Main Steps:**

- Build a User-Item Interaction Matrix.
- Apply mean-centering to user ratings.
- Calculate user similarity using Cosine Similarity.
- Identify similar users.
- Predict movie ratings based on similar users' preferences.
- Generate personalized recommendations.

### 3. Hybrid Recommendation System

The Hybrid Recommendation System combines the results of Content-Based Filtering and Collaborative Filtering into a single recommendation score.

**Hybrid Score Formula:**

```python
hybrid_score = (
    0.5 * content_score +
    0.5 * collaborative_score
)
```

Both scores should be normalized or placed on compatible scales before combining them.

**Cold-Start Handling**

When collaborative information is unavailable, the system uses Content-Based Filtering as a fallback:

```python
hybrid_score = content_score
```

This allows CineMatch to continue generating recommendations when sufficient collaborative information is not available.

---

## 📊 Dataset

CineMatch uses multiple data sources to combine movie information with user preferences.

| Dataset | Purpose |
|---|---|
| MovieLens Small | User ratings and movie information |
| TMDB | Movie descriptions, keywords, cast, and directors |
| IMDb | Additional movie ratings and information |

### MovieLens Small Dataset

The MovieLens Small dataset contains:

- 100,836 ratings.
- 610 users.
- 9,742 movies.

MovieLens ratings are used as the primary source for Collaborative Filtering.

Additional metadata from TMDB and IMDb enriches the Content-Based Filtering component.

---

## 🛠 Technologies Used

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical operations |
| Scikit-learn | Machine learning and TF-IDF |
| NLTK / VADER | Sentiment analysis |
| Matplotlib | Data visualization |
| Seaborn | Exploratory data analysis |
| Streamlit | Web application |
| Git & GitHub | Version control and collaboration |

---

## 📁 Project Structure

The following is a suggested project structure. Actual filenames may vary depending on the implementation.

```text
CineMatch/
│
├── app.py
├── functions.py
├── requirements.txt
├── README.md
│
├── data/
│   ├── movies.csv
│   ├── ratings.csv
│   └── clean_content.csv
│
├── models/
│   ├── movie_similarity_matrix.pkl
│   └── collaborative_model.pkl
│
├── notebooks/
│   ├── data_collection.ipynb
│   ├── data_preprocessing.ipynb
│   ├── eda.ipynb
│   ├── content_based_filtering.ipynb
│   ├── collaborative_filtering.ipynb
│   └── hybrid_recommendation.ipynb
│
└── assets/
    └── images/
```

---

## ⚙️ Installation

### Prerequisites

Make sure you have installed:

- Python 3.10 or higher.
- Git.
- pip.

### 1. Clone the Repository

```bash
git clone <REPOSITORY_URL>
```

### 2. Navigate to the Project Directory

```bash
cd CineMatch
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

**Windows:**

```bash
venv\Scripts\activate
```

**macOS / Linux:**

```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

Make sure the requirements file contains the actual dependencies used by the project.

---

## 🚀 Running the Application

After installing dependencies and preparing the required datasets and model files, run:

```bash
streamlit run app.py
```

The application should open in your default browser.

---

## 👥 Team Members

This project is developed by a team of five members as part of the Digital Egypt Pioneers Initiative (DEPI) – AI & Data Science Track.

### 1. Mohamed Salah Abozaid

**Role:** Data Engineering & Analysis

**Responsibilities:**
- Data Collection and Integration.
- Data Cleaning and Preprocessing.
- Exploratory Data Analysis (EDA).
- Preparing clean datasets for model development.

**Main Deliverables:**
- Cleaned movie dataset.
- Integrated ratings and movie metadata.
- Data analysis notebook and visualizations.

### 2. Ahmed Reda Fathy Salim

**Role:** Content-Based Filtering & NLP

**Responsibilities:**
- Content-Based Filtering.
- Text preprocessing and feature engineering.
- TF-IDF Vectorization.
- Cosine Similarity calculations.
- VADER Sentiment Analysis.

**Main Deliverables:**
- Content-Based Recommendation Model.
- Movie similarity matrix.
- Content-Based Filtering notebook.

### 3. Mohamed Mahmmud Ibrahim Hamed Sakr

**Role:** Collaborative Filtering

**Responsibilities:**
- Collaborative Filtering.
- User-Item Interaction Matrix.
- User similarity calculations.
- Rating prediction and recommendation logic.

**Main Deliverables:**
- Collaborative Filtering Model.
- User similarity matrix.
- Collaborative Filtering notebook.

### 4. Abdelrhman Abdelsamad Elessawy Abdelsamad

**Role:** Hybrid System & Evaluation

**Responsibilities:**
- Hybrid Recommendation System.
- Combining Content-Based and Collaborative Filtering.
- Recommendation score calculation.
- Model evaluation and performance testing.

**Main Deliverables:**
- Hybrid Recommendation Engine.
- Top-N recommendation results.
- Model evaluation report.

### 5. Mohamed Sayed Mahmoud Mohamed

**Role:** Streamlit Application & UI/UX

**Responsibilities:**
- Streamlit Web Application.
- User Interface and User Experience (UI/UX).
- Movie search and rating functionality.
- Displaying recommended movies and movie information.
- Application integration and deployment.

**Main Deliverables:**
- Interactive Streamlit Application.
- Application interface and functionality.
- Deployment and final application demo.

---

## 🔮 Future Improvements

- Improve recommendation accuracy through parameter tuning.
- Explore additional hybrid recommendation strategies.
- Improve recommendation diversity.
- Integrate additional movie metadata sources.
- Enhance the user interface and user experience.
- Evaluate the system using additional recommendation metrics.
- Explore more advanced recommendation algorithms.

---

## 📚 References

1. Salton, G., & Buckley, C. (1988). Term-weighting approaches in automatic text retrieval. *Information Processing & Management, 24*(5), 513–523. https://doi.org/10.1016/0306-4573(88)90021-0

2. Sarwar, B., Karypis, G., Konstan, J., & Riedl, J. (2001). Item-based collaborative filtering recommendation algorithms. *Proceedings of the 10th International Conference on World Wide Web*. https://doi.org/10.1145/371920.372071

3. Burke, R. (2002). Hybrid recommender systems: Survey and experiments. *User Modeling and User-Adapted Interaction, 12*, 331–370. https://doi.org/10.1023/A:1021240730564

4. Hutto, C. J., & Gilbert, E. (2014). VADER: A parsimonious rule-based model for sentiment analysis of social media text. *Proceedings of the International AAAI Conference on Web and Social Media, 8*(1), 216–225. https://doi.org/10.1609/icwsm.v8i1.14550

5. GroupLens Research. MovieLens Datasets. https://grouplens.org/datasets/movielens/

---

## 📄 License

This project is developed for educational purposes as part of the DEPI AI & Data Science Track.