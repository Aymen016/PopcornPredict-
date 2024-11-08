# 🎬 Movie Recommendation System

This project creates a movie recommendation system using a dataset of movies from TMDB (The Movie Database). The system suggests similar movies based on features like genres, keywords, cast, and crew.

## 🚀 Project Setup

1. **📥 Install Dependencies**:
   - Ensure you have Python and necessary packages installed.
   - Install packages from `requirements.txt`:
     ```bash
     pip install -r requirements.txt
     ```

2. **📂 Load Data**:
   - Place `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv` in the project directory.
   - Data is loaded using pandas.

## 🔧 Data Preprocessing

1. **🧹 Cleaning and Handling Missing Values**:
   - Missing values in numerical columns are handled with median values.
   - Text-based columns are filled with "Unknown."

2. **📜 Data Parsing**:
   - JSON columns (e.g., genres, keywords) are parsed using `ast.literal_eval`.

3. **🔍 Feature Engineering**:
   - Combine relevant features into a "tags" column.
   - Text is cleaned and stemmed using NLTK’s `PorterStemmer`.

## 🧠 Model Training and Evaluation

1. **📚 Text Vectorization**:
   - Vectorize the tags column using `CountVectorizer` with a max limit of 50,000 features and stop words removed.

2. **💡 Cosine Similarity**:
   - Compute cosine similarity between movies to find similar titles.

## 🎥 Movie Recommendation Function

The `recommend(movie_title)` function retrieves and displays the top 5 similar movies based on cosine similarity.

Example usage:
```bash
recommend(avatar)
 ```

## 🧪 Machine Learning Techniques

- 🟢 Used `GradientBoostingRegressor` for revenue and vote prediction.
- 🔵 Implemented a classification model with logistic regression to predict high/low ratings.

## 📋 Requirements

- 🐍 Python 3.x
- Libraries: `pandas`, `numpy`, `sklearn`, `nltk`, `matplotlib`, `seaborn`, `plotly`

## ▶️ Running the Code

Load the dataset and preprocess the data:

```python
import pandas as pd
movies_df = pd.read_csv('tmdb_5000_movies.csv')
