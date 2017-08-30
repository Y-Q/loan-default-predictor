# Test procedures, top importance features and results:

1. Random Forest classification was used as the main method in predicting whether a loan would be in default and the default probability:
    * The method doesn’t require data transformation, is robust about outliers and is less prune to over-fitting data.
    * Fine tuning certain tree parameters showed improvement on classification accuracy
2. The most important features are split from the random forest classification are shown in the notebook file
3. I have included both the straight accuracy score (number of records that are predicted correctly/total number of records) as well as a ROC curve. Since the data is very skewed (default represents about 33% of total tested/trained dataset), ROC would be a much better indicator for accuracy. The ROC score for random forest is about 65% whereas the accuracy score is 88%.

# Potential improvements:
1. One downside for Python random forest implementation is that the algorithm doesn’t handle string features naturally. I have converted important features into numbers so that they can be used. However the string features such as ‘’ zip_code” can be further explored. Zip code can be mapped to income level in the area, or employment rate, which could provide additional information for the model.
2. I removed rows with missing values after selecting the feature columns. However the missing values could also be filled with median imputation and/or proximity based measures. It is unclear which approach would produce better results but can certainly be explored.
3. Another way to split data in this case would be using one of the date columns, i.e. issue_d, however there could be seasonality which wouldn’t be captured if the data is split by a point in time. The data is therefore not split by time sequence. This can be further tested.
4. I have included the LinearCVS and the NaiveBay classifier as well. The models could be mixed and the result could be improved. The mixed model is not implemented yet. 
