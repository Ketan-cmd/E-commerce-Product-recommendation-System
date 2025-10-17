# Ecommerce Product Recommendation System

The **Ecommerce Product Recommendation System** is a machine learning-based project designed to provide personalized product recommendations to users. By analyzing user browsing and purchase history, the system employs collaborative filtering and content-based filtering algorithms to enhance the shopping experience and boost sales for e-commerce businesses.

---

## 📂 Dataset

This project utilizes an Amazon dataset containing user ratings for electronic products. To ensure unbiased analysis, each product and user is assigned a unique identifier. The dataset can be accessed via the following links:

- [Amazon Electronics Rating Dataset](https://www.kaggle.com/datasets/vibivij/amazon-electronics-rating-datasetrecommendation/download?datasetVersionNumber=1)
- [Additional Datasets](https://jmcauley.ucsd.edu/data/amazon/)

---

## 🛠️ Approach

### 1️⃣ Rank-Based Product Recommendation

**Objective:**
- Recommend products with the highest number of ratings.
- Target new customers with the most popular products.
- Address the [Cold Start Problem](https://github.com/Ketan-cmd/E-commerce-Product-recommendation-System/blob/main/ColdStartProblem.md).
**Outputs:**
- Recommend the top 5 products with at least 50/100 ratings.

**Methodology:**
- Calculate the average rating for each product.
- Compute the total number of ratings for each product.
- Sort products by average rating and filter based on the minimum number of interactions.
- Provide a function to retrieve the top `n` products.

---

### 2️⃣ Similarity-Based Collaborative Filtering

**Objective:**
- Deliver personalized and relevant recommendations to users.

**Outputs:**
- Recommend the top 5 products based on interactions of similar users.

**Methodology:**
- Convert `user_id` to integer values for convenience.
- Implement a function to find similar users using cosine similarity:
  1. Compute similarity scores between the target user and others.
  2. Sort and extract the most similar users.
  3. Exclude the original user from the results.
- Develop a recommendation function:
  1. Identify products interacted with by similar users but not the target user.
  2. Return the top `n` recommended products.

---

### 3️⃣ Model-Based Collaborative Filtering

**Objective:**
- Provide personalized recommendations while addressing sparsity and scalability challenges.

**Outputs:**
- Recommend the top 5 products for a specific user.

**Methodology:**
- Convert the product ratings matrix into a Compressed Sparse Row (CSR) format to optimize memory and computation.
- Perform Singular Value Decomposition (SVD) to reduce matrix dimensionality to 50 latent features.
- Predict ratings for all users by multiplying the decomposed matrices.
- Store predicted ratings in a DataFrame and filter out products already rated by the user.
- Sort and recommend products based on predicted ratings.

**Evaluation:**
- Calculate the Root Mean Squared Error (RMSE) to assess model performance.
- Compare actual and predicted ratings to measure accuracy.

---

## 👤 Author

- **GitHub:** [Ketan-cmd](https://github.com/Ketan-cmd)

---

> ⚠️ **Disclaimer:** This project is intended solely for educational purposes to understand how recommendation systems work.

---
