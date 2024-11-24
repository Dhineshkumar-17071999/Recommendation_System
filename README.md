# Recommendation_System

A recommendation system is a type of artificial intelligence or machine learning system designed to suggest items, products, or services to users based on their preferences, behavior, or historical data. It is widely used in e-commerce, streaming platforms, social media, and other applications to improve user engagement and satisfaction.

### Explicit Feedback vs. Implicit Feedback
In recommender systems, machine learning models are used to predict the rating of a user on an item. At inference time, we recommend to each user the items having highest predicted rating.

We therefore need to collect user feedback, so that we can have a ground truth for training and evaluating our models. An important distinction has to be made here between explicit feedback and implicit feedback.

![alt text](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*yPeDvQjUoFdLKb9CkxaFPA.png)

- **Explicit feedback:** Explicit feedback is a rating explicitly given by the user to express their satisfaction with an item. Examples are: number of stars on a scale from 1 to 5 given after buying a product, thumb up/down given after watching a video, etc. This feedback provides detailed information on how much a user liked an item, but it is hard to collect as most users typically don’t write reviews or give explicit ratings for each item they purchase.

- **Implicit feedback:** Implicit feedback, on the other hand, assume that user-item interactions are an indication of preferences. Examples are: purchases/browsing history of a user, list of songs played by a user, etc. This feedback is extremely abundant, but at the same time it is less detailed and more noisy (e.g. someone may buy a product as a present for someone else). However, this noise becomes negligible when compared to the sheer size of available data of this kind, and most modern Recommender Systems tend to rely on implicit feedback.

--------------------------------------------------------------------------------------------------------------------------------------------------------
### Methods of Recommendation Systems
1. Content-Based Filtering


   This approach uses the characteristics of items and user preferences to make recommendations. It relies on matching item attributes with the preferences or past behavior of a user.
   - **How it works:** If a user likes a movie tagged as "action" and "sci-fi," the system recommends other movies with similar tags.
   - **Real-life example:**
     - A book recommendation system suggesting books with similar genres, authors, or keywords on a platform like Goodreads.
     - Spotify suggesting songs based on the characteristics of the music a user listens to.
    
  - **Algorithms include:**
    - **TF-IDF (Term Frequency-Inverse Document Frequency):** Used to convert textual data (e.g., product descriptions) into numerical features for comparing item similarity.
      - **Example:** Recommending books based on similar plot keywords.

    - **Cosine Similarity:** Measures similarity between two items based on their feature vectors.
      - **Example:** Suggesting similar songs based on tempo, genre, and mood.
     
    - **k-Nearest Neighbors (k-NN):** Identifies the "k" most similar items to recommend to a user.
      - **Example:** Recommending articles similar to one recently read.
     
    - **Machine Learning Models (e.g., Logistic Regression, Decision Trees):** Predict user preferences based on item features and previous interactions.

---------------------------------------------------------------------------------------------------------------------------------------------------------

2. Collaborative Filtering




  This method relies on user interaction data, such as ratings, purchases, or likes, to recommend items. It identifies patterns and similarities between users or items. Collaborative filtering can be divided into two types:
  - **User-based Collaborative Filtering:** Recommends items based on the preferences of similar users.
Example: If User A and User B have similar tastes, items liked by User B will be recommended to User A.
  - **Item-based Collaborative Filtering:** Recommends items similar to the ones a user has interacted with.
Example: Amazon's "Customers who bought this also bought" feature.

  - **algorithms include:**
    - **User-Based Collaborative Filtering**
      - **Pearson Correlation Coefficient:** Measures the similarity between users based on their rating behavior. Example: Recommending movies liked by users with similar taste.
      - **Cosine Similarity:** Compares users’ preference vectors to find similar users.

    - **Item-Based Collaborative Filtering**
      - **Matrix Factorization Techniques (e.g., Singular Value Decomposition - SVD):** Reduces the user-item interaction matrix to uncover latent features shared between items.
        - **Example:** Used by Netflix for finding hidden patterns in movie ratings.
       
      - **Alternating Least Squares (ALS):** Optimizes recommendations by alternating between fixing user and item features.
     
    - **Advanced Techniques**
      - **Collaborative Deep Learning:** Combines collaborative filtering with deep learning models like neural networks for better accuracy.
        - **Example:** YouTube recommendations.

---------------------------------------------------------------------------------------------------------------------------------------------------------
        
3. Hybrid Recommendation Systems




     Combines multiple methods, such as content-based and collaborative filtering, to overcome the limitations of each approach and improve accuracy.
  - **How it works:** Netflix uses hybrid systems to recommend shows and movies, combining viewing history, user ratings, and similarities between users and content.

  - **Algorithms from multiple approaches**
    - **Weighted Hybrid:** Combines scores from content-based and collaborative filtering algorithms.
      - **Algorithm Example:** Weighted Average.
    - **Model-Based Hybrid:** Uses machine learning or ensemble methods to merge predictions from different models.
      - **Example:** Random Forest or Gradient Boosting for combining recommendations.
    - **Switching Hybrid:** Chooses an algorithm dynamically based on the situation.
      - **Example:** Use collaborative filtering when user data is available; otherwise, switch to content-based filtering.

---------------------------------------------------------------------------------------------------------------------------------------------------------

4. Knowledge-Based Recommendation Systems





     These systems recommend items based on specific user requirements, preferences, or constraints without relying on historical data.
  - **Real-life example:** A travel agency platform recommending vacation packages based on budget, preferred destination type (beach/mountain), and activities.
  - **Algorithms:**
    - **Constraint-Based Filtering:** Recommends items by satisfying user-defined rules or preferences.
      - **Example:** A car recommendation system suggesting vehicles within a specific budget and mileage range.
    - **Case-Based Reasoning (CBR):** Finds solutions to new problems (recommendations) by adapting solutions from similar past cases.
    - **Bayesian Networks:** Models dependencies between user preferences and item features to recommend items.

---------------------------------------------------------------------------------------------------------------------------------------------------------

5. Deep Learning-Based Recommendation Systems





     Uses advanced techniques like neural networks to capture complex patterns in user behavior and item features.
  - **Real-life example:** YouTube suggesting videos based on your watch history, engagement patterns, and deep learning models.
  - **Algorithms**
    - **Autoencoders:** Neural networks used for dimensionality reduction and capturing latent features in sparse data.
      - **Example:** Recommending items in large catalogs.
    - **Recurrent Neural Networks (RNNs):** Used for sequential recommendations (e.g., predicting the next video or song).
      - **Example:** Spotify's "Next Up" suggestions.
    - **Convolutional Neural Networks (CNNs):** Extracts features from images (e.g., for fashion recommendations).
    - **Neural Collaborative Filtering (NCF):** A deep learning extension of traditional collaborative filtering, integrating user and item embeddings.
      - **Example:** Amazon's product suggestions.
    - **Transformers:** Models user behavior sequences for accurate next-item predictions.
      - **Example:** YouTube’s "watch next" feature.
     
---------------------------------------------------------------------------------------------------------------------------------------------------------

### Applications in Real Life
1. **E-commerce:** Amazon recommending products based on browsing history.
2. **Streaming Services:** Netflix suggesting shows or movies based on your watch history and ratings.
3. **Social Media:** Facebook recommending friends or pages based on your interactions.
4. **Food Delivery:** Apps like Zomato suggesting restaurants based on your previous orders.
5. **Education:** Platforms like Coursera recommending courses based on completed courses or search behavior.

---------------------------------------------------------------------------------------------------------------------------------------------------------

| Method/Algorithm | Explicit Feedback | Implicit Feedback |
| ---------------- | ----------------- | ----------------- |
| User-Based Collaborative Filtering | Ratings | Browsing history, purchase data |
| Item-Based Collaborative Filtering | Ratings | Co-occurrence data (e.g., items viewed or bought together) |
| Matrix Factorization (SVD, ALS) | Ratings | Implicit ALS variants using interaction confidence |
| Content-Based Filtering | Ratings, explicitly defined preferences | Browsing behavior, clicks |
| Knowledge-Based Systems | Explicit preferences (e.g., constraints, filters) | Not commonly used for implicit feedback |
| Deep Learning (e.g., Autoencoders, NCF) | Can work with ratings, reviews | Clicks, views, time spent, purchase data |
| Hybrid Systems | Combines both (e.g., ratings + interaction data) | Combines both |

----------------------------------------------------------------------------------------------------------------------------------------------------------

#### Key Insights:
- **Explicit Feedback** works best with algorithms like matrix factorization and user/item-based collaborative filtering, as they rely on user input to gauge preferences.
- **Implicit Feedback** is more common in real-world applications because explicit feedback is often sparse. Algorithms like ALS (for implicit data) and deep learning models are tailored for such scenarios.


**Example Applications:**
   - **Explicit Feedback:** Netflix ratings for movies or Goodreads star ratings for books.
   - **Implicit Feedback:** YouTube's "watch next" feature based on viewing history or Spotify's music suggestions from play history.
