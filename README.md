# Rent-prediction

In this project, I study the Kaggle dataset "House Rent Prediction Dataset" available at the URL
https://www.kaggle.com/datasets/iamsouravbanerjee/house-rent-prediction-dataset.
In the file model.ipynb, I perform feature engineering on this dataset, then apply several
appropriate sklearn models (linear models, random forests, and gradient boosting) to predict
the rents in the dataset.

# The data
This dataset gives information including rent and basic properties (area, number of rooms, etc) for 
4746 properties in 6 Indian cities. The dataset was originally submitted to Kaggle by Sourav
Banerjee, who scraped the data from the Indian realty site Magicbricks.

# Conclusions

Because of the presence of extreme outliers (most relevantly, a rent of 3.5 million among 
average rents of 35,000), using RMSE to evaluate models will primarily describe their
performance at the outliers. Rather than remove or cap the outliers themselves, I evaluate model
performance using a modified RMSE, which caps the error for any particular data point at 300,000.
With this metric, linear models accounted for about 20% of the variance in rents, while
ensemble models account for about 40% of the variance.

# Follow-up

One relevant feature was excluded entirely because it was a categorical variable with 2235 values
in a dataset with 4746 elements. This category is called "Area Locality", and could be converted
to latitudes and longitudes. It is likely that those new features would improve the error
of the ensemble models. 

That said, the features of this dataset are also likely not enough information to create a robustt model 
that predicts the rent of apartments accurately, and additional features are likely necessary,
especially to identify the handful of very expensive apartments that (on inspection) closely resemble
other much less expensive apartments with respect to their other features.

V1 committed 2022-09-25
