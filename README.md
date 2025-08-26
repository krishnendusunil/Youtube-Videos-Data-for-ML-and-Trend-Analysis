# YouTube Video Views Prediction and Analysis

This project explores a dataset of YouTube video metadata to understand factors influencing video views and to build a predictive model for video popularity.

## Dataset

The analysis utilizes a dataset containing metadata for a random selection of YouTube videos. Key information includes:
- Video characteristics (duration, resolution, bitrate, frame rate, codec)
- Categorical data (category, hashtags)
- Engagement metrics (views, likes, comments)
- Textual data (title, description)

## Analysis and Methodology

The project followed a structured approach:

1.  **Data Loading and Cleaning:** Loaded the dataset and handled missing values in the 'description' and 'hashtags' columns.
2.  **Exploratory Data Analysis (EDA):** Conducted a detailed analysis of feature distributions, categorical data (categories, codecs), and correlations between features, including engagement metrics. Visualizations such as histograms, heatmaps, and a word cloud of hashtags were generated.
3.  **Feature Engineering:** Created new features from existing data, including:
    -   Sentiment scores for video titles and descriptions using the VADER lexicon.
    -   Length of video titles and descriptions.
4.  **Data Preparation for Modeling:** Selected 'views' as the target variable, prepared the feature set (numerical, engineered, and one-hot encoded categorical features), and split the data into training and testing sets.
5.  **Model Building and Evaluation:**
    -   Trained and evaluated a **Random Forest Regressor** model.
    -   Trained and evaluated a **Gradient Boosting Regressor** model.
    -   Compared the performance of both models using regression metrics (MSE, RMSE, R2).
    -   Analyzed feature importance for both models to understand key predictors of views.
    -   Compared actual versus predicted views on the test set.

## Key Findings

-   Engagement metrics (views, likes, comments) are highly correlated with each other.
-   Video category is a significant factor influencing average engagement.
-   Basic video quality metrics (bitrate, resolution) and the overall sentiment/length of titles and descriptions showed weaker linear correlations with views compared to engagement metrics and category.
-   Feature importance analysis revealed that `likes` and `comments`, along with description-related features and certain categories, were most influential in predicting views.
-   The **Gradient Boosting Regressor** model significantly outperformed the Random Forest Regressor, achieving a higher R-squared score (0.94) and lower RMSE, indicating better predictive power on this dataset.

## Conclusion

The analysis provided valuable insights into the factors associated with YouTube video popularity. The trained Gradient Boosting Regressor model demonstrates a strong ability to predict video views based on the available features, highlighting the importance of engagement metrics, video category, and description characteristics.

This project serves as a foundation for further exploration, such as hyperparameter tuning, investigating non-linear relationships, or deploying the model for predictions.
