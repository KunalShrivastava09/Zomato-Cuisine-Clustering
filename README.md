# Zomato-Cuisine-Clustering
This project utilizes unsupervised machine learning to segment Zomato restaurants based on their key attributes, such as rating, votes, cost, and cuisine type. The goal is to identify distinct restaurant clusters and build a simple recommendation engine that suggests similar or highly-rated restaurants within the same cluster.
The project addresses the challenge of providing personalized recommendations to users in a crowded market. By clustering restaurants with similar characteristics, a user looking for a specific type of dining experience (e.g., high-end buffet, budget-friendly cafe) can be easily matched with a group of comparable options, enhancing their discovery process.

Data Source
The dataset used in this project is sourced from Zomato, an online restaurant aggregator and food delivery service. The Zomato_data.csv file contains the following features for 148 restaurants:

name: The name of the restaurant.

online_order: Indicates if the restaurant offers online ordering.

book_table: Indicates if table booking is available.

rate: The average user rating of the restaurant.

votes: The total number of user votes.

approx_cost(for two people): The estimated cost for two people.

listed_in(type): The cuisine or restaurant type (e.g., 'Buffet', 'Cafes', 'Dining').

Methodology
The project follows a standard data science pipeline:

Data Preprocessing: The raw data was cleaned to prepare it for machine learning. This involved converting the rate column from a string (e.g., "4.1/5") to a numeric format, dropping rows with missing values, and converting categorical features like online_order and book_table into binary (1 or 0) numerical representations. The listed_in(type) column was one-hot encoded to create separate binary columns for each cuisine type.

Feature Scaling: Numerical features such as rate, votes, and approx_cost were normalized using StandardScaler to ensure they contribute equally to the clustering process.

Clustering with K-Means: The K-Means algorithm was used to group restaurants. The optimal number of clusters (k) was determined using the Elbow Method. A value of k=5 was selected based on the resulting plot, indicating a good balance between a low number of clusters and low inertia.

Dimensionality Reduction: Principal Component Analysis (PCA) was applied to the clustered data to reduce its dimensionality to two components for easy visualization. This allowed for a clear, two-dimensional scatter plot to show the separation of the restaurant clusters.

Recommendation System: A simple content-based recommendation system was built. Given a restaurant name, it finds the cluster it belongs to and recommends other restaurants from the same cluster. This can be extended to recommend the highest-rated restaurants within that cluster.

Results and Insights
Cluster Analysis: The K-Means algorithm successfully grouped the restaurants into 5 distinct clusters based on their attributes. The visualization using PCA confirmed the separation of these clusters.

Performance Metrics: The Silhouette Score was used to evaluate the quality of the clustering. Your project achieved a Silhouette Score of 0.30, which indicates that the clusters are reasonably well-defined.

Recommendation Engine: The recommendation functions recommend_similar and recommend_highly_rated provide tailored suggestions by identifying restaurants in the same cluster. For example, the project can suggest highly-rated alternatives to a given restaurant, helping users discover new places that fit their preferences.

Technologies Used
Python

Pandas

NumPy

Scikit-learn

Matplotlib

Seaborn
