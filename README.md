# Introduction

Crop yield is among the fundamental metrics in agriculture. It is not only important in determining the effectiveness of planification strategies such as irrigation and fertilization but also in decision making (e.g. selling the final harvest).

In light of that, and within the organization where I was having my research intership, several attempts were made to predict the crop yield using data related to weather (temperature, rain, …), vegetation indexes, and aerial images (satellite images). 
However, and despite diversifying the models, a stagnation in the prediction accuracy (limited to 0.7) was noticed.

To improve the accuracy, a first thought is to change the approach followed to a data-driven approach. Instead of enhancing the accuracy through complexifying the model, we might think of re-organizing data.


# Objective

My mission is to explore whether a time series clustering of weather data would enhance the performance of models used to predict crop yield.

Based on that, my research subject is entitled: **Improving the accuracy of crop yield prediction through time series clustering of weather data**.


# Specifications

I will perform this study on the weather data of the region **SIDI SLIMAN**, which is a Moroccan region highly reputed for agriculture. I will also be targeting the **wheat crop**.

For more detail about the data and how it was processed, check the folder `data_processing`.


#  Methods and summary results
For more detail about this section, refer to `/univariate_clustering` and `/multivaraite_clustering` folders.

## Univaraite clustering
Clusterings crop years according to a given weather variable.

| Approach               | Precipitation | GDD   | Wind  | Humidity
| ---------              | -----------   | ---   | ----- | --------
| **Number of clusters** | 4             | 3     | 3     | 2
| **Score**              | 58.00         | 40.50 | 51.30 | 54.20
|

## Multivariate clustering
Clustering crop years according to a set of weather variables. 

| Approach               | Basic       | PCA on weather variables | PCA on times dimensions (before) | PCA on times dimensions (after)
| ---------              | ----------- | -----------              | -----------                      | -----------
| **Number of clusters** | 4           | 3                        | 4                                | 4                   
| **Score**              | 51.30       | 57.30                    | 52.75                            | 41.70
|


# Conclusions

From one hand Refering to the scores, if we opt for a univariate clustering of crop years, It is better to cluster according to **Precipitation**.

Similarly, when perfoming clustering by considering all weather variables, the scores suggest **reducing the dimension of weather variables and then applying clustering**.
