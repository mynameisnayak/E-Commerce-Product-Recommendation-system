E-commerce Product Recommendation System

The Product Recommendation System represents a machine learning-driven initiative that furnishes tailored product suggestions to users based on their historical browsing and purchase activities. Employing collaborative filtering and content-based filtering algorithms, the system analyzes user behavior, generating pertinent recommendations. The primary goal of this project is to enhance the overall user shopping experience and augment sales for e-commerce enterprises.
Dataset

The dataset utilized for this project pertains to Amazon, focusing on user ratings for electronic products. To mitigate biases, the dataset employs unique identifiers for products and users instead of names or potentially prejudiced information.

    Download the dataset here
    Explore similar datasets here.

Approach
1) Rank-Based Product Recommendation

Objective:

    Recommend products with the highest number of ratings.
    Target new customers with the most popular products.
    Address the Cold Start Problem.

Outputs:

    Recommend the top 5 products with a minimum of 50/100 ratings/interactions.

Approach:

    Calculate the average rating for each product.
    Determine the total number of ratings for each product.
    Construct a DataFrame using these values and sort it by average.
    Develop a function to retrieve the top 'n' products with a specified minimum number of interactions.

2) Similarity-based Collaborative Filtering

Objective:

    Provide personalized and relevant recommendations to users.

Outputs:

    Recommend the top 5 products based on interactions of similar users.

Approach:

    Convert user_id to an integer type for convenience.
    Implement a function to find similar users:
        Assess the similarity score between the target user and each user using cosine similarity.
        Extract and sort the similar users and their respective similarity scores.
        Remove the original user and its similarity score, returning the remaining similar users.
    Develop a function to recommend products:
        Utilize the previous function to obtain similar users for the target user_id.
        Identify products interacted with by the original user, defining them as observed_interactions.
        For each similar user, determine 'n' products they interacted with but the original user did not.
        Return the specified number of products.

3) Model-based Collaborative Filtering

Objective:

    Provide personalized recommendations based on user behavior, addressing sparsity and scalability challenges.

Outputs:

    Recommend the top 5 products for a specific user.

Approach:

    Convert the matrix of product ratings to a CSR matrix for efficiency.
    Conduct singular value decomposition (SVD) on the CSR matrix, reducing it to 50 latent features.
    Predict ratings for all users using the U, sigma, and Vt matrices.
    Store predicted ratings in a DataFrame and create a function to recommend products based on predictions.
    Evaluate the model by calculating the Root Mean Squared Error (RMSE) between actual and predicted ratings.

Note: The RMSE calculation involves taking the square root of the mean of squared errors between average actual and predicted ratings. The squared parameter in the mean_squared_error function determines whether to return MSE or RMSE. Setting squared to False yields the RMSE.
     

| ⚠️  This project is solely for learning how recommedation systems work. ⚠️ |
|-----------------------------------------------------------------------------|
