
# Crypto Market Analysis

**Description**

This project performs an analysis of the cryptocurrency market data using clustering techniques. It aims to identify patterns and group similar cryptocurrencies based on their price change percentage over different time periods. Two approaches are taken: one using the original data and another using Principal Component Analysis (PCA) to reduce the dimensionality of the data.

**Installation**

Clone the repository:
  - git clone https://github.com/bauzaj/Crypto-Clustering.git

  - Navigate to the project directory: cd Crypto-Clustering

 
**Usage**

Import the required libraries and dependencies:

  - import pandas as pd
  - import hvplot.pandas
  - from sklearn.cluster import KMeans
  - from sklearn.decomposition import PCA
  - from sklearn.preprocessing import StandardScaler



**Visualize the data using line plots**

![image](https://github.com/bauzaj/Crypto-Clustering/assets/119364045/6514acc4-0fd8-4640-83d4-b5d11c3d6f59)

**Prepare the data for clustering**

df_market_data_scaled = StandardScaler().fit_transform(df_market_data[['price_change_percentage_24h', 'price_change_percentage_7d', 'price_change_percentage_14d',
                                                                       'price_change_percentage_30d', 'price_change_percentage_60d', 'price_change_percentage_200d',
                                                                       'price_change_percentage_1y']])

**Perform clustering using the original data**

  - model = KMeans(n_clusters=4, random_state=1)
  - predicted_clusters = model.fit_predict(df_market_data_scaled)
  - df_market_data_predicted = df_market_data_transformed.copy()
  - df_market_data_predicted['coin_clusters'] = predicted_clusters


**Visualize the clusters using scatter plots**

![image](https://github.com/bauzaj/Crypto-Clustering/assets/119364045/cd2f78ae-cd77-47ba-affe-8046323fc836)


**Perform clustering using PCA data**

  - pca = PCA(n_components=3)
  - mrkt_data_pca = pca.fit_transform(df_market_data)
  - k_pca = KMeans(n_clusters=2)
  - k_pca = model.fit_predict(mrkt_data_pca)
  - mrkt_data_pca_prediction = mrkt_data_pca.copy()
  - mrkt_data_pca_prediction['coin_clusters'] = k_pca



**Visualize the PCA clusters using scatter plots**

![image](https://github.com/bauzaj/Crypto-Clustering/assets/119364045/c2886012-fb46-4cd7-89d0-1b475ee6e601)



**Results**

The project identifies clusters of cryptocurrencies based on their price change percentage over various time periods. The analysis is performed using both the original data and PCA-transformed data. Visualizations, such as line plots and scatter plots, are used to display the data and clusters
