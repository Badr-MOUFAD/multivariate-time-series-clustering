# Overview

Here I perform a univaraite clustering, specifically I cluster crop years according to a single weather variable. Later, I characterize the resulting clusters and assess the final clustering procedure.


# Clustering specification

- **Data point**: crop years a represented as cumulative sum vector of the weather variables. The final matrix of vectors comprises 39 rows (*number of crop years*) and column 269 (*number of records in each crop year*)

- **Measure of dissimilarity between data points**: the use of generalized euclidean distance.

- **Measure of dissimilarity between clusters**: the use of ward linkage method. A measure that takes on account both distance between centroids and the number of data points in each cluster.

- **Algorithm of clustering**: The use of Hierarchical clustering (agglomerative clustering). Motivation behind this choice is to have access to dendrogram and thereby use it to pick up the right number of clusters.


# Assessing the quality of the final clustering

Use a metric to judge the clustering procedure and hence compare between different clustering procedures. The selected metric is **Calanski - Harabasz index**. It takes on consideration **WGSS** (dispersion within groups), **BGSS**(dispersion within clusters), and the **number of clusters**.


# Description of the pipeline

For a given weather variables (e.g. precipitation, GDD)

1. Split data according to selected weather varialble to obtain a matrix (*39 x 269*).

2. Perform Hierarchical clustering and use dendrogram to select the appropriate number of clusters.

3. Perform clustering with the selected number of clusters then assign cluster labels to observations.

4. Characterize clusters by ploting observations whitin each cluster as well as the clusters' centroids.

5. Assess the clustering procedure by ploting the C-H index as a function of the number of clusters.



> The univariate clustering served as a tool to define the clustering framework to use in multivaraite clustering.
