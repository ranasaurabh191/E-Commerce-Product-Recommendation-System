# 💡 E-Commerce Product Recommendation System

An intelligent machine learning-based recommendation system that suggests relevant products to users based on their interaction history. This project utilizes collaborative filtering and ranking methods to provide personalized suggestions, especially for new users and returning shoppers.

---

## 📦 Dataset

We used the **Amazon Electronics Ratings** dataset, which contains:
- **User Ratings** of various electronic items.
- **Anonymized IDs** for both users and products to prevent any bias from personal identifiers.

---

## 🚀 Objectives

1. Address the **cold start problem** for new users.
2. Provide **relevant recommendations** using multiple approaches.
3. Handle **sparsity** and **scalability** efficiently.
4. Ensure that suggestions are **accurate, scalable, and memory-efficient**.

---

## 🧠 Approaches Used

### 🔹 1. Rank-Based Product Recommendation

**Goal:** Recommend popular products to all users — especially new ones.

- ✅ Ideal for cold start scenarios.
- ✅ Recommends products with high popularity and good average ratings.

**Steps:**
- Compute the average rating and the number of ratings for each product.
- Filter products with a minimum number of interactions (e.g., 50 or 100).
- Sort by average rating and recommend the top N products.

**Output:**  
Top 5 most popular products based on number of ratings and average score.

---

### 🔹 2. Similarity-Based Collaborative Filtering (User-User)

**Goal:** Recommend items based on preferences of users with similar tastes.

- ✅ Personalized recommendations.
- ✅ Great for users with sufficient interaction history.

**Steps:**
- Map `user_id` to integer values for simplicity.
- Construct a user-item interaction matrix.
- Compute **cosine similarity** between users.
- Identify the most similar users.
- Recommend products liked by similar users but not yet interacted with by the target user.

**Output:**  
Top 5 personalized product suggestions for a given user.

---

### 🔹 3. Model-Based Collaborative Filtering (Matrix Factorization)

**Goal:** Use latent features to model user-product interactions.

- ✅ Handles data sparsity well.
- ✅ Scalable for large datasets.

**Steps:**
- Convert the user-item matrix to a **Compressed Sparse Row (CSR)** format for memory efficiency.
- Apply **Singular Value Decomposition (SVD)** with 50 latent features.
- Predict ratings for all users across all products.
- Store predicted ratings in a DataFrame with users as rows and products as columns.
- Recommend top N products with highest predicted ratings (excluding already rated ones).

**Output:**  
Top 5 predicted items for each user based on their latent preferences.

---

## 📊 Model Evaluation

To evaluate the accuracy and effectiveness of the model:

- 📉 **Root Mean Square Error (RMSE)** is calculated between actual and predicted ratings.
- 📈 Comparison of **average actual vs. predicted ratings**.
- 🧪 Cross-validation and performance testing to ensure generalizability.

---

## 🛠️ Tools & Technologies Used

- **Python**
- **Pandas**, **NumPy**, **scikit-learn**
- **SciPy** for sparse matrices
- **Matplotlib**, **Seaborn** for visualization

---

## 📌 Key Takeaways

- Handled **cold start**, **scalability**, and **sparsity** problems using different techniques.
- Designed modular code and notebooks for **experimentation** and **reproducibility**.
- Achieved **interpretable**, **efficient**, and **realistic** recommendations using real-world data.

---

> *“Recommender systems are not just about suggesting products — they're about understanding users.”*
