# CryptoClustering
Using Python and unsupervised machine learning techniques, the purpose of this project was to predict whether various cryptocurrencies are affected by 24 hour or 7 day price changes. Two models were created: one using  the full dataset and another using the results of Principal Component Analysis (PCA). PCA identifies what factors contribute the most to the data's variability and assigns them a higher weight when forming the final clusters. SciKit Learn and Pandas are the main Python libraries used in this module.

The most optimal value of k, the number of clusters that best represents the data, was determined to be four. Comparing the two models, PCA resulted in tighter clusters, highlighting its ability to remove noise from the visualizations by reducing the number of incorporated variables to the ones that have the most impact on the changes seen within the data.

The clusters formed from the full dataset appear to show that the majority of cryptocurrencies are less affected by price changes occurring within 24 hours and are mostly affected by changes that occur around a week. A crypto called Ethlend is one crypto that appears in its own cluster and is affected negatively by 24 hour changes. Another crypto, celsius-degree-token, on the other hand, also belongs to a cluster of its own and is affected by 24 hour price changes, although more positively.

## Data Preparation
To prepare the data, the price change percentages within the dataset were normalized using StandardScaler from SciKit Learn. A new Pandas DataFrame was created with the scaled values, reassigning their respective cryptocurrencies.

## Finding k using original data and clusters
An elbow curve was created by finding the inertia resulting from models with k clusters, ranging between 1 to 10. Those values were charted against the number of clusters that formed them. The optimal value of k was determined by choosing the point around the chart's steepest negative change and before the chart begins to gradually continue toward zero. k was chosen to be 4.

<p align="center">
<img src="imgs/original_k.png" width=50% height=50%/>
</p>

A model was then fit to the data resulting in four clusters and can be seen below.

<p align="center">
<img src="imgs/original_clusters.png" width=50% height=50% image-align="center">
</p>

Most of the crytocurrencies belong to clusters that are more affected by seven day price changes. However, there are two clusters that seem to be a bit more volatile, with prices changing within 24 hours.

## Finding k using Principal Component Analysis (PCA) and clusters

The same process was applied using PCA, available in SciKit Learn. An elbow curve was created to determine the best k, which was also four.

<p align="center">
<img src="imgs/pca_k.png" width=50% height=50%>
</p>

Clusters using the PCA results are formed, grouping the fields that affect the data's variability into four components. These clusters appear to be more closely grouped than those formed using the full dataset. This is likely because fields that have less effect on the data's variability are not included in the clusters.

<p align="center">
<img src="imgs/pca_clusters.png" width=50% height=50%>
</p>

## Comparing elbow curves & clusters

Below are the curves and models for side by side comparison.
<img src="imgs/elbow_curve_comp.png">


<img src="imgs/cluster_comp.png">
