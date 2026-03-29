Movie Recommendation System
📌 Overview
This project implements a content-based movie recommendation system using Python and machine learning libraries. It analyzes movie metadata (genres, keywords, tagline, cast, director) and recommends similar movies based on textual feature similarity.

⚙️ Tools & Technologies
- Python
- Pandas, NumPy – data handling
- Scikit-learn – TF-IDF vectorization & cosine similarity
- difflib – fuzzy string matching for user input

📂 Dataset
- Source: movies.csv
- Size: 4803 rows × 24 columns
- Key features:
- Title
- Genres
- Keywords
- Tagline
- Cast
- Director
- Ratings
Example:
- Avatar → Budget: $237M, Genres: Action/Adventure/Fantasy/Sci-Fi, Rating: 7.2

🧹 Data Cleaning
- Removed duplicates (drop_duplicates())
- Filled missing values with empty strings
- Selected features: genres, keywords, tagline, cast, director

🛠️ Feature Engineering
- Combined selected features into one column: combined_features
- Applied TF-IDF Vectorizer → Sparse matrix of shape (4803, 17318)
- Captures term importance across movie descriptions

🤖 Model Building
- Cosine Similarity used on TF-IDF vectors
- Similarity matrix shape: (4803, 4803)
- Diagonal = 1.0 (self-similarity)
- Example: Avatar vs Pirates of the Caribbean → similarity ≈ 0.072

🎯 Recommendation Logic
- User inputs a movie title (e.g., Guardians of the Galaxy).
- Title matched using difflib.
- Retrieve similarity scores for that movie.
- Sort and return top N similar movies (excluding the input movie).

📊 Example Output
For Guardians of the Galaxy, recommendations include:
- Avatar
- The Chronicles of Riddick
- Star Trek Beyond
- Star Trek Into Darkness
- Moonraker

🚀 How to Run
- Clone repository & install dependencies:
pip install pandas numpy scikit-learn
- Place movies.csv in the project directory.
- Run the script:
python movie_recommender.py
- Enter a movie title when prompted.

🔮 Future Improvements
- Integrate collaborative filtering for user-based recommendations.
- Add web app interface using Flask/Streamlit.
- Expand dataset with more metadata (reviews, box office, etc.).

Would you like me to also create a sample movie_recommender.py script that matches this README so you can run the system directly?
# Movie_recommendation_-
This report clearly explains a movie recommendation system built with Python. It prepares and cleans data, merges features like genres, cast, and director, applies TF-IDF to convert text into vectors, and uses cosine similarity to suggest movies most similar to a user’s choice.
