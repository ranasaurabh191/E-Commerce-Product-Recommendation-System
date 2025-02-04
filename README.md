
E-Commerce Product Recommendation System
The E-Commerce Product Recommendation System is a machine learning-based project designed to provide personalized product recommendations to users based on their browsing and purchase histories. It utilizes collaborative filtering and content-based filtering algorithms to analyze user behavior and generate relevant product suggestions. The goal is to enhance the user shopping experience and drive sales for e-commerce platforms.

Dataset
For this project, I used the Amazon Electronics Ratings dataset, which contains user ratings for various electronic products. 
To avoid biases, each product and user is assigned a unique identifier, instead of using names or other potentially biased information.

Approach
1. Rank-Based Product Recommendation

Objective:
Recommend products with the highest number of ratings.
Target new customers with the most popular products.
Address the cold start problem.

Outputs:
Recommend the top 5 products with a minimum of 50/100 ratings/interactions.

Approach:
Compute the average rating and total number of ratings for each product.
Create a DataFrame and sort it by the average rating.
Implement a function to get the top 'n' products based on a minimum number of interactions.

2. Similarity-Based Collaborative Filtering

Objective:
Provide personalized and relevant recommendations to users.

Outputs:
Recommend the top 5 products based on the interactions of similar users.

Approach:
Convert user_id to integer values for simplicity (0 to 1539).
Calculate similarity scores between users using cosine similarity.
Extract similar users and their scores, excluding the original user.
Recommend products by considering the interactions of similar users.

3. Model-Based Collaborative Filtering
Objective:
Provide personalized product recommendations by leveraging user preferences and addressing challenges of sparsity and scalability.

Outputs:
Recommend the top 5 products for a specific user.

Approach:
Convert the product ratings matrix into a CSR (Compressed Sparse Row) matrix for efficient memory use.
Apply Singular Value Decomposition (SVD) to reduce dimensionality and extract latent features (50 in this case).
Compute predicted ratings for all users using SVD.
Store predicted ratings in a DataFrame with users as rows and products as columns.
Implement a function to recommend products based on predicted ratings, excluding already rated products.

Evaluation:
Calculate the average actual ratings and predicted ratings.
Compute the Root Mean Square Error (RMSE) between actual and predicted ratings to evaluate the accuracy of the model.
