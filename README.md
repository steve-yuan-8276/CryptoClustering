# CryptoClustering

In this project, we leverage Python and unsupervised learning techniques to explore how cryptocurrencies are affected by 24-hour and 7-day price changes. Using clustering algorithms, such as K-means, we group cryptocurrencies based on their price changes and analyze the clusters with Principal Component Analysis (PCA) to optimize feature reduction.

* * *

## Python Libearies

- Python 3.12
- Jupyter Notebook
- Libraries: Pandas, scikit-learn, hvPlot, Plotly

## File Structure
    
    
    CryptoClustering/
    │
    ├── /Resource/crypto_market_data.csv
    ├── Crypto_Clustering.ipynb
    └── README.md
    
* * *

## Project Overview

The goal of this challenge is to predict if cryptocurrencies are impacted by 24-hour or 7-day price changes. We'll use the following techniques and tools to achieve this:

- **Unsupervised Learning (K-means Clustering)**
- **Principal Component Analysis (PCA)**
- **Data Normalization with `StandardScaler()`**
* * *

## Instructions

### 1. Data Preparation

- **Load the Data**: Load the `crypto_market_data.csv` file into a Pandas DataFrame.
- **Explore the Data**: Generate summary statistics and plot the data to visualize any preliminary insights.
- **Standardize the Data**: Normalize the data using the `StandardScaler()` module from scikit-learn to ensure that each feature contributes equally to the analysis.

### 2. Elbow Method to Determine Optimal k

- **Inertia Calculation**: Use the elbow method to calculate the inertia for k-values ranging from 1 to 11.
- **Plot the Elbow Curve**: Plot the inertia values to visually determine the best value for k.
- **Best k Value**: Record and discuss the optimal value for k based on the elbow curve.

### 3. K-Means Clustering with the Scaled Data

- **Initialize K-Means**: Fit the K-means model with the best k value.
- **Predict Clusters**: Use the scaled data to predict cluster groupings.
- **Scatter Plot Visualization**: Create a scatter plot with `hvPlot`, setting the x-axis as `"price_change_percentage_24h"` and the y-axis as `"price_change_percentage_7d"`. Add the cryptocurrency name to the `hover_cols` parameter to enhance identification.

### 4. Feature Optimization with PCA

- **PCA with 3 Components**: Use PCA to reduce the features to 3 principal components.
- **Explained Variance**: Retrieve the explained variance to determine how much information each principal component holds.
- **New PCA DataFrame**: Create a new DataFrame with the reduced PCA data and set the index to `coin_id`.
- **Best k Using PCA Data**: Apply the elbow method again to find the best k value for the reduced data.

### 5. K-Means Clustering with the PCA Data

- **K-Means with PCA**: Fit and predict the clusters using the PCA DataFrame.
- **Scatter Plot with PCA**: Visualize the clusters by creating a scatter plot with the principal components (`PC1`, `PC2`) and compare the cluster labels.

### 6. Visualize and Compare Results

- **Composite Plot for Elbow Curves**: Use `hvPlot` to compare the elbow curves generated with the original scaled data and PCA data.
- **Composite Plot for Clusters**: Compare the cryptocurrency clusters generated from both the original scaled data and the PCA-transformed data.
- **Analysis**: Discuss the impact of reducing features on the cluster analysis.
* * *

## Results

### Best Value for k

- After applying the elbow method, the optimal value for k was determined to be **4** using the scaled DataFrame and **4** using the PCA DataFrame.

### Impact of Feature Reduction

- By using PCA, we reduced the dimensionality of the dataset while retaining **89.5%** of the total variance. The clustering results, however, showed **minimal/significant** differences when using fewer features, indicating that feature reduction through PCA can **simplify/improve** the clustering process without **much loss/any loss** of valuable information.
* * *

## Conclusion

This project highlights the power of unsupervised learning methods like K-means clustering and dimensionality reduction techniques like PCA in identifying patterns and groupings within large datasets, such as cryptocurrency price changes. Through this approach, we can make informed predictions about the behavior of cryptocurrencies in different time windows.

Thanks for your time.