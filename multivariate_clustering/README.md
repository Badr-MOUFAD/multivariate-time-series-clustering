# Overview

Here I perform a multivariate clustering. I cluster crop years according to a given a set of weather variables (in my cased, I worked on four weather variables). I have followed three approaches:

1. Basic approach
2. **Dimension reduction** on the times spaces
3. **Dimension reduction** on weahter variables

I compared finally the three approaches and concluded the suited one.


# Clustering specification

- **Data point**: crop years a represented as cumulative sum vector of the weather variables - the same as the univariate clustering - except that this time the vector will hold tuples instead of values. The final matrix of vectors comprises $39$ rows (*number of crop years*) and column $269$ (*number of records in each crop year*) where each entry is a tuple of values. Hence the final matrix can be perceived as a $3D$ matrix with rows (crop years), columns (times dimensions), and depth number of weahter variables.

- **Measure of dissimilarity between data points**, **Measure of dissimilarity between clusters**, **Algorithm of clustering** are the same as univariate clustering.


**Note**: 
When using euclidean distance, we can prove that the representation of data in a form of vector of tuples isequivalent to flattening the vector.
e.g. $$[(a_1, b_1, c_1, d_1), (a_2, b_2, c_2, d_2), ...] \rightarrow [a_1, a_2, ..., b_1, b_2, ..., c_1, c_2, ..., d_1, d_2, ...]$$


# Description of the pipeline
## 1. Basic approach

- use the same pipeline as in univariate clustering. (Use the new data representation)
- characterize the clusters using also the same procedure followed in univaraite clustering
- compute the C-H index

## 2. Dimension reduction on times dimensions

- Center columns by subtracting the mean. 
- Apply an explanatory **PCA**
    - before merging
    - after merging
- Select the number of PCs to keep using a cumulative explained variance ratio plot
- Transform data to the new space
- Apply clustering

## 3. Dimension reduction on weather variables

Here we make a slight modification on the crop year representation. Each crop year is represented using a matrix of 269 rows and 4 columns (number of weathear variables).

- Compute the mean for every weather variables (mean on the crop years). After doing that, we will obtain a matrix 269 row and 4 columns (number of weather variables).
- Perform dimension reduction on this matrix. Note that we select one principal component.
- We reduce dimension of each crop year. Therefore, each crop year is represented using a vector.
- Gather these crop years in a matrix then perfrom clustering on them.

#  Summary table

| Approach | Basic       | PCA on times dimensions (before) | PCA on times dimensions (after)  | PCA on weather variables
| ---------| ----------- | -----------                      | -----------                      | ----------- 
| **Score**| 00.00       | 00.00                            | 00.00                            | 00.00
