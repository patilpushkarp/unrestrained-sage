# Preprocessing

Preprocessing is a step which helps us to improve the quality of the raw data that is available. The quality of data determines the amount of information that can be derived thereby affecting the leanring ability of the algorithms. Sophisticated algorithms can not make up for the poor quality of data. It is necessary to follow the process of selecting, transforming and augmenting the source data so as to create powerful signals to the target vraiable. Preprocessing involves data engineering and feature engineering processes. Data engineering is the process of transforming raw data to prepared data. Feature engineering is the processing of tuning(performing specific operations) the features for the purpose of ML. It may also involve creating new features as per the requirements.

!!! info "Raw data"
    Raw data is the data in it's source form or transformed data that is not prepared specifically for ML tasks. 

!!! info "Prepared data"
    Prepared data is the form of data that is ready for ML tasks. Data sources have been parsed, joined, and put in tabular form. Data has been aggregated and summarized to the right granularity. In this data, irrelevant columns are dropped and invalid records are handled approriately.

Steps that are performed in preprocessing structured data are:  
1. Data cleansing - Removing unnecessary records or correcting invalid values.    
2. Instances selection and partitioning - Splitting datasets into training, validation and testing sets.  
3. Feature tuning - Includes performing feature scaling, handling of outliers, missing value imputation, and adjusting skewed distributions.  
4. Representation transformation - This invoves bucketization of numerical values and encoding of categorical values.  
5. Feature extraction - Reducing number of features by creating lower-dimension, more powerful data representations.   
6. Feature selection - Selecting subset of input for traning the model.  
7. Feature construction - Creating new features by using polynomial expansion or feature crossing. Features can also be created with the use of business logic from the domain of use case. 

For unstructured data, model architectures inherently determines preprocessing that may be required but constructing the right model requires empirical knowledge of the data. In addition some preprocessing that is standard for this type of data:  
- For text documents, stemming and lemmatization, TF-IDF calculation, and n-gram extraction, embedding lookup.  
- For images, clipping, resizing, cropping, Gaussian blur, and canary filters.  
- Transfer learning, in which you are treating all-but-last layers of the fully trained model as a feature engineering step. This applies to all types of data, including text and images.  


## References

- [Data Preprocessing for Machine Learning](https://medium.com/datadriveninvestor/data-preprocessing-for-machine-learning-188e9eef1d2c)  
- [Introduction to Data Preprocessing in Machine Learning](https://towardsdatascience.com/introduction-to-data-preprocessing-in-machine-learning-a9fa83a5dc9d)  
- [Data preprocessing for machine learning: options and recommendations](https://cloud.google.com/solutions/machine-learning/data-preprocessing-for-ml-with-tf-transform-pt1)  
