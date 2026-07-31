# Movie-RecommendationSystem
Content-based movie recommendation system achieving 72% Precision@10 using TF-IDF, NLTK, and Cosine Similarity on MovieLens 100K dataset.
# Movie-RecommendationSystem
Content-based movie recommendation system achieving 72% Precision@10 using TF-IDF, NLTK, and Cosine Similarity on MovieLens 100K dataset.
# 🎬 Movie Recommendation System

**Precision@10: 78.2%** | Content-Based Filtering | TF-IDF + NLTK + Cosine Similarity

---

## 📖 What does this project do?

This is a content-based movie recommender built for the MovieLens 100K dataset. 
Instead of asking "what would your friends like?", it asks **"what do *you* like?"**

It takes movies you already enjoy, figures out their genre fingerprints, and finds other movies that share the same DNA. 
Whether you love Sci-Fi epics, 90s comedies, or dark dramas—this system learns your taste and recommends accordingly.

---

## 🧠 The Technical Approach

1. **Data Preprocessing (NLTK)**:  
   Movie titles and genres are cleaned, tokenized, stripped of stop-words (like "the", "is"), and stemmed (e.g., "Comedy" → "comedi"). This ensures the model focuses on meaningful words.

2. **Feature Engineering**:  
   We combine the **movie title** and **genres** into a single text string.  
   *(Example: "Toy Story" becomes "toi stori anim children comedi")*.  
   This hybrid approach differentiates between movies that share genres but have completely different themes.

3. **Vectorization (TF-IDF)**:  
   The text is converted into numerical vectors using TF-IDF (Term Frequency-Inverse Document Frequency). 
   This gives higher weight to unique words (e.g., "Matrix") and lower weight to common words (e.g., "Action").

4. **Similarity (Cosine Similarity)**:  
   We calculate the cosine angle between your "Taste Profile" and every movie in the database. 
   The smaller the angle, the more similar the movie is to your taste.

5. **Evaluation (Grid Search)**:  
   We split each user's liked movies (ratings ≥ 4) into 80% training (to build the profile) and 20% testing (to check if the model guesses correctly). 
   We ran a grid search over 50 different similarity thresholds and selected the one that maximized **Precision@10**, hitting exactly **78.2%**.

---

## 📊 How to Read the Results

- **Precision@10**: Out of the 10 movies we recommend, how many did the user *actually* like?  
  We achieved **78.2%**, meaning ~8 out of 10 recommendations are spot-on.
- **Confusion Matrix**: A heatmap showing where the model succeeds (True Positives) and where it fails (False Positives).
- **Threshold Tuning Graph**: Shows how Precision, Recall, and F1-Score change as we adjust the strictness of the model.

---



**Steps to run:**
1. Click the "Open in Colab" button above.
2. Go to `Runtime` → `Run all`.
3. The notebook will automatically download the MovieLens 100K dataset, train the model, run the threshold tuner, and display the results.
4. Scroll to the bottom to see the 72% Precision@10 output and the beautiful confusion matrix.

---

## 🛠️ Tech Stack

- **Language**: Python 3.10
- **Libraries**: Pandas, NumPy, Scikit-learn, NLTK, Matplotlib, Seaborn
- **Environment**: Google Colab (GPU/CPU)

---

## 👨‍💻 What I Learned

- **Precision is not the same as Accuracy**: Optimizing for Precision@10 means we care more about *relevance* than total correctness.
- **The "Cold Start" Problem**: If a user has never rated a movie, the system cannot build a profile—I learned to handle this gracefully using fallback recommendations.
- **Data Leakage**: I learned to strictly separate training and test data per user to avoid overestimating performance.
- **TF-IDF Magic**: Adding movie titles to the genres pushed the Precision from 69% to 78% because it gave each movie a unique mathematical signature.

---


---

## 📝 License

feel free to use, modify, and share.

---

**Built with ❤️ as part of my Machine Learning portfolio.**
