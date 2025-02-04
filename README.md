#E-Commerce Product Recommendation System
The Product Recommendation System is a machine learning-driven project designed to provide personalized product suggestions to users based on their browsing and purchase histories. It leverages collaborative filtering and content-based filtering algorithms to analyze user behavior and generate relevant recommendations. The goal of this project is to enhance the overall shopping experience for users and help e-commerce businesses increase sales.

Dataset
For this project, I used the Amazon Electronics Ratings dataset, which contains user ratings for various electronic products. The dataset doesn't include any headers, so to eliminate potential biases, each product and user is assigned a unique identifier instead of using names or other potentially biased data.


Approach
Rank-Based Product Recommendation

Objective:
Recommend products with the highest number of ratings.
Target new customers with the most popular products.
Address the cold start problem.
Outputs:
Recommend the top 5 products with a minimum of 50/100 ratings/interactions.
Approach:
Compute the average rating and total number of ratings for each product.
Create a DataFrame with these values and sort it by the average rating.
Implement a function to get the top 'n' products based on a minimum number of interactions.
Similarity-Based Collaborative Filtering

Objective:
Provide personalized and relevant recommendations to users.
Outputs:
Recommend the top 5 products based on the interactions of similar users.
Approach:
Convert user_id to integer values for ease of calculation (0 to 1539).
Write a function to find similar users by calculating similarity scores using cosine similarity.
Extract similar users and their scores from the sorted list, excluding the original user.
Implement a function to recommend products by considering the observed interactions of the user and the interactions of similar users.
Model-Based Collaborative Filtering

Objective:
Offer personalized product recommendations based on past user behavior and preferences, while tackling the challenges of sparsity and scalability in other collaborative filtering techniques.
Outputs:
Recommend the top 5 products for a particular user.
Approach:
Convert the product ratings matrix into a CSR (Compressed Sparse Row) matrix to save memory and reduce computational time.
Apply Singular Value Decomposition (SVD) to the CSR matrix to reduce dimensionality and extract 50 latent features.
Compute predicted ratings for all users using the SVD technique (multiplying the U, sigma, and Vt matrices).
Store the predicted ratings in a DataFrame with users as rows and products as columns.
Write a function to recommend products based on the predicted ratings, filtering out already rated products and sorting by predicted ratings.
Evaluation:
Calculate the average actual ratings and average predicted ratings.
Create a DataFrame (rmse_df) containing the average ratings and compute the Root Mean Square Error (RMSE) between actual and predicted ratings using the mean_squared_error function.
