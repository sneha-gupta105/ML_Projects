Link to Jupyter Source File: 
https://colab.research.google.com/drive/1NegQWyAAAqNf77P7xJV4eAyZL_c5756I?usp=sharing
---

# 🎬 Movie Recommender System

This project is a **Content-Based Movie Recommender System** that suggests movies based on the similarity of content features such as genres, cast, crew, and plot overviews.

---

## 📌 Project Overview

**Objective**: Recommend top 5 similar movies to a given movie using a content-based filtering approach.

**Workflow**:

```
Dataset → Preprocessing → Feature Engineering → Vectorization → Similarity Computation → Recommendation
```

---

## 🧠 Recommender System Types

1. **Content-Based Filtering** – Focuses on movie features (used in this project).
2. **Collaborative Filtering** – Based on user similarity.
3. **Hybrid Systems** – Combine both approaches.

---

## 📂 Dataset Used

**Source**: [TMDB 5000 Movie Dataset](https://www.kaggle.com/tmdb/tmdb-movie-metadata)

* `tmdb_5000_credits.csv`: Contains cast and crew info.
* `tmdb_5000_movies.csv`: Contains movie metadata like genres, keywords, overviews, etc.

---

## 🧹 Data Preprocessing

Selected columns:

* `movie_id`, `title`, `overview`, `genres`, `keywords`, `cast`, `crew`

Transformations:

* Extract top 3 cast members.
* Extract director from crew.
* Convert lists from string to actual Python lists.
* Merge all features into a single `tags` column.
* Apply **stemming** to normalize words.

---

## 🧮 Vectorization & Similarity

* Used **Bag of Words** model via `CountVectorizer` (top 5000 frequent words).
* Removed stop words (e.g., "the", "and").
* Computed **Cosine Similarity** to find top 5 closest movies.

---

## 🛠 Technologies Used

* Python (Pandas, NumPy, Scikit-learn, NLTK)
* Jupyter Notebook / Google Colab
* Dataset from Kaggle

---

## 🚀 How to Use

1. Clone the repository or copy the code into your Jupyter Notebook / Colab.
2. Download the dataset from Kaggle and upload it to the appropriate path.
3. Run all cells to process the data and build the recommendation system.
4. Call `recommend('Movie Name')` to get top 5 similar movies.

---

## 📈 Sample Output

```python
recommend('Life of Pi')
```

**Output**:

```
Cast Away  
The Beach  
The Thin Red Line  
The Book Thief  
Seven Years in Tibet  
```

---

## 📦 Future Improvements

* Deploy as a web application using Flask or Streamlit.
* Add a user-based collaborative filtering module.
* Integrate movie posters and trailers using TMDB API.
* Improve performance using TF-IDF or deep learning embeddings.

