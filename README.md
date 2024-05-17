# Recommendation System for E-Commerece Platform

This project demonstrates the implementation of a recommender system using collaborative filtering techniques on a dataset of electronics reviews from Amazon.

Table of Contents
- [Usage](#usage)
- [Introduction](#introduction)
- [Data Preparation](#data-preparation)
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)
- [Popularity-Based Recommendation](#Popularity-Based-Recommendation)

# Introduction
This project aims to build a recommendation system for electronics products using collaborative filtering. The dataset contains user reviews and ratings for various electronics products. The recommender system suggests products to users based on their ratings and the ratings of similar users.

# Usage
- Ensure all dependencies are installed and run the Jupyter notebook to see the results:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn scipy
```

- Use the recommend_items function to get item recommendations for a specific user.
```bash
userID = 4
num_recommendations = 5
recommend_items(userID, pivot_df, preds_df, num_recommendations)
```

# Data Preparation

- The dataset is loaded from the Electronics_5.json file.
- Only the first 5000 lines are read to keep the dataset manageable.
- A pandas DataFrame is created with relevant columns: reviewerID, asin, and overall.
- Users who have rated 5 or more items are retained for analysis.
- A pivot table is created where rows represent users and columns represent products, with ratings as values.

# Exploratory Data Analysis
- Summary statistics of the ratings, number of unique users and products, and density of the ratings matrix are calculated.
- The top 10 users based on the number of ratings are identified.

# Popularity-Based Recommendation
- Products are recommended based on the count of reviews in the training data.
- A function to recommend the top 5 products to any user based on popularity.
- The user-item ratings matrix is factorized using SVD to reduce dimensionality and make predictions.
- A function to recommend items to a user based on the predicted ratings.
