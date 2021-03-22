# Feature Extraction Techniques

## Principal Component Analysis (PCA)

PCA is a prime linear method used for dimensionality reduction. It works on a condition that while the data in a higher dimensional space is mapped to data in a lower dimensional space, the variance of the data in the lower dimensional space should be maximum.  
It involves following steps:  
1. Construct the covariance of the matrix  
2. Compute the eigen vectors of that matrix  
3. Eigenvectors corresponding to the largest eigenvalues are used to reconstruct a large fraction of variance of the original data.  

Since lesser number of eigenvectors remains, there is data loss in this method but the most important variances should be retained by the remaining eigenvectors. Since PCA finds linear correlations, this behavior may be undeisrable for some usecases. PCA also fails in cases where mean and covariance are not enough to define datasets. Also number of principal components to keep may be unknown.  
PCA is sensitive to the ranges of the data and hence normalization is recommended before applying it.  
Applying PCA to data makes it non-interpretable.  

## Linear Discriminant Analysis

Linear Discriminant Analysis seeks to best separate (or discriminate) the samples in the training dataset by their class value. Specifically, the model seeks to find a linear combination of input variables that achieves the maximum separation for samples between classes (class centroids or means) and the minimum separation of samples within each class.  
LDA assumes data are normally distributed and dis-tinct classes share the same covariance matrix; then it ﬁnds a linear transformation of the feature vectors.

## Generalized Discriminant Analysis

Similar to LDA, the objective of GDA is to find a projection for the features into a lower dimensional space by maximizing the ratio of between-class scatter to within-class scatter.  
GDA ﬁrst maps the data into a new feature space and then ﬁnds a linear transformation. Mapping to the new space is carried outusing kernel methods. As the mapped feature vectors are non-linearly related to the input versions, GDA effectively provides a non-linear discriminant analysis for the input feature data.

## t-Distributed Stochastic Neighbor Embedding (t-SNE)

t-Distributed Stochastic Neighbor Embedding (t-SNE) is a non-linear technique for dimensionality reduction that is particularly well suited for the visualization of high-dimensional datasets. It is extensively applied in image processing, NLP, genomic data and speech processing.  
t-Distributed stochastic neighbor embedding (t-SNE) minimizes the divergence between two distributions: a distribution that measures pairwise similarities of the input objects and a distribution that measures pairwise similarities of the corresponding low-dimensional points in the embedding.  
t-SNE maps the multi-dimensional data to a lower dimensional space and attempts to find patterns in the data by identifying observed clusters based on similarity of data points with multiple features. However, after this process, the input features are no longer identifiable, and no inference can be made based only on the output of t-SNE. Hence it is mainly a data exploration and visualization technique.


## References

- [Seven Techniques for Data Dimensionality Reduction](https://www.knime.com/blog/seven-techniques-for-data-dimensionality-reduction)
- [Introduction to Dimensionality Reduction for Machine Learning](https://machinelearningmastery.com/dimensionality-reduction-for-machine-learning/)
- [Introduction to Dimensionality Reduction](https://www.geeksforgeeks.org/dimensionality-reduction/)
- [Linear Discriminant Analysis for Dimensionality Reduction in Python](https://machinelearningmastery.com/linear-discriminant-analysis-for-dimensionality-reduction-in-python/)
- [Dimensionality reduction](https://en.wikipedia.org/wiki/Dimensionality_reduction#Generalized_discriminant_analysis_(GDA))
- [Introduction to t-SNE](https://www.datacamp.com/community/tutorials/introduction-t-sne?utm_source=adwords_ppc&utm_campaignid=1455363063&utm_adgroupid=65083631748&utm_device=c&utm_keyword=&utm_matchtype=b&utm_network=g&utm_adpostion=&utm_creative=332602034358&utm_targetid=dsa-429603003980&utm_loc_interest_ms=&utm_loc_physical_ms=1007788&gclid=EAIaIQobChMIo_uO6uGn6wIVT9eWCh1j8w9GEAAYASAAEgLz-_D_BwE)