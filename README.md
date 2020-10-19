# Cryptocurrencies

## Table of contents
* [Overview](#overview)
* [Data](#data)
* [Methodology](#methodology)
* [Results](#results)


### Overview
The cryptocurrencies project is an examination of unsupervised learning, which help us explore data when we’re not sure what we’re looking for. In the notebooks folder are jupyter notebooks containing practice with unsupervised machine learning algorithms like k-means and PCA. In this folder is also a challenge notebook that has a further application of unsupervised algorithms. The notebooks contains code examining the following:

- The differences between supervised and unsupervised learning, including real-world examples of each.
- Preprocessing data for unsupervised learning.
- Clustering data using the K-means algorithm.
- Determining the best amount of centroids for K-means using the elbow curve.
- Using PCA to limit features and speed up the model.

### Data

There are three data sources for this project. The first is the [iris data set](https://en.wikipedia.org/wiki/Iris_flower_data_set). This is a classical data set used with unsupervised learning. The data set consists of 50 samples from each of three species of Iris (Iris setosa, Iris virginica and Iris versicolor). Four features were measured from each sample: the length and the width of the sepals and petals, in centimeters. 

The second data set is a consumer shopping dataset. This data set has 203 data points and 5 features:CustomerID,	Card Member, Age, Annual Income, Spending Score (1-100). 

The final data set contains 1252 different cryptocurrencies and the following features: CoinName, Algorithm, IsTrading, ProofType, TotalCoinsMined, TotalCoinSupply.

All three datasets had to be cleaned slightly before analysis.

### Methodology
The cryptocurrency analysis (challenge) is an exploratory analysis of different cryptocurrencies for the Advisory Services Team at Accountability Accounting. Before any analysis there are number of things that need to be done to clean the data: 

- Remove all cryptocurrencies that aren’t trading.
- Remove all cryptocurrencies that don’t have an algorithm defined.
- Remove the IsTrading column.
- Remove all cryptocurrencies with at least one null value.
- Remove all cryptocurrencies without coins mined.
- Store the names of all cryptocurrencies on a DataFramed named coins_name, and use the crypto_df.index as the index for this new DataFrame.
- Remove the CoinName column.
- Create dummies variables for all of the text features, and store the resulting data on a DataFrame named X.
- Use the StandardScaler from sklearn (Links to an external site.) to standardize all of the data from the X DataFrame.

After this preprocessing I performed a dimension reducion using the PCA algorithms from sklearn. Now the data was in the format for analysis using unsupervised learning. For the analysis, I used the K-means algorithm to predict clusters using the cryptocurrencies data.

To select the number of clusters I plotted the elbow curve.

![Elbow Curve](https://github.com/Duvey314/Cryptocurrencies/blob/master/Resources/Elbow%20Curve.PNG)

From this I selected 5 clusters.

### Results

Here you can see the clusters created using 5 clusters.

![Clusters](https://github.com/Duvey314/Cryptocurrencies/blob/master/Resources/Groups.PNG)

The outlier (purple plus) is the bittorrent crypto. This currency has an order of magnitude more coins and thus is unlike any other currency.
