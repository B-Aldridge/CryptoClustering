# CryptoClustering

In this challenge, the aim is to cluster cryptocurrencies using the K-means algorithm and explore the impact of feature reduction using Principal Component Analysis (PCA). Unsupervised machine learning was used to predict whether cryptocurrencies are affected by 24-hour or 7-day price change. Starter code was provided by the Bootcamp.

## Prepare the Data
To start, data was normailized from the CSV file using the StandardScaler module from scikit-learn.

## Find the Best Value for k Using the Original Scaled DataFrame
The elbow method was used to determine the optimal value for k. By evaluating the inertia values for different k values, one can identify the point where additional clusters do not significantly improve the model's performance. Once that was completed, the following questions was asked:

### What is the best value for k?

#### Answer: Analyzing the elbow curve plot suggests that using the K value of 4 may be the best value to use as after this point, inertia seems to level off as shown on the curve. The K value of 3 could still be a valid option in addition.


## Cluster Cryptocurrencies with K-means Using the Original Scaled Data
With the best value for k obtained, the K-means model was intialized and was fit to the original scaled DataFrame. Cluster labels was assigned to each data point and a scatter plot was created using hvPlot to visualize the clusters. The x-axis represents "PC1," the first principal component, while the y-axis represents "PC2," the second principal component. The color of each point corresponds to the cluster it belongs to, and the hover feature includes the "coin_id" for easy identification.

## Optimize Clusters with Principal Component Analysis
Performing PCA on the original scaled DataFrame allows us to reduce the dimensionality of the data while retaining the most important information. By analyzing the explained variance of each principal component, one can assess how much of the data's variance is explained by the selected components. The following question was answered during this step:

### What is the total explained variance of the three principal components?

#### Answer: The total explained variance of the three prinipal components is 0.89503166 or approximately 89.5%. This is calulated by adding each individial explained variance.

## Find the Best Value for k Using the PCA Data
Similar to the previous step, the elbow method was used on the PCA data to determine the optimal value for k. This will help understand if the reduced feature space affects the choice of k. Then two questions were posed and anwered:

### What is the best value for k when using the PCA data? 

#### Answer: Analyzing the elbow curve plot from the PCA data suggests that using the K value of 4 may be still the best optimal value as after this point, inertia seems to level off. The K value of 3 could still be a valid option in addition similar original.

### Does it differ from the best k value found using the original data?

#### Answer: No

## Cluster Cryptocurrencies with K-means Using the PCA Data
Using the best value for k obtained from the previous step, the K-means model was initialized again, this time using the PCA-transformed data. Cluster labels was assigned to each data point and a scatter plot was created using hvPlot. The x-axis represents the "price_change_percentage_24h," while the y-axis represents the "price_change_percentage_7d." The color of each point corresponds to the assigned cluster, and the hover feature includes the "coin_id" for easy identification.

## Visualization
The cluster analysis results were placed together for a comparison to contrast the outcome for both techniques.

The following question was asked of the results:

### What is the impact of using fewer features to cluster the data using K-Means?

#### Answer: Upon visually analyzing the results, using fewer features through the PCA method produced clusters that tend to be appearing more close together in comparison to the results from the original. 
