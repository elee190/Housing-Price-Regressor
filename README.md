# Ames-Iowa Housing Corporation

**What are the primary features that can explain housing sale prices in Ame, Iowa?**

1. House-specific variable
2. Neighborhood-related variables
3. Property size variables
4. Market/macroeconomic variables

While we are unable to access market/macroeconomic variables, we are able to access the remaining factors with our given datasets. A full data dictionary is available here: http://jse.amstat.org/v19n3/decock/DataDocumentation.txt .


### EDA/Preprocessing
---
Due to a large volume of null inputs in our datasets, preliminary cleaning had to be performed. Null values for categorical features were converted to string 'NA' representing 'None,' in accordance with the data dictionary. This was performed for both the training and testing datasets. For numeric features, null values were converted to zeros, in accordance with the data dictionary. Initial research allowed us to make educated assumptions that numeric feature null values are indeed zero.
Ordinal categories were converted to ordinal integers, to allow for MLR without creating an excessive volume of binary variables. 

### Feature Selection & Engineering
---
Our choice of features to include in our model was based on correlation. The features with the highest positive, and lowest negative, were selected. Amongst our selected features, interaction terms (sklearn PolynomialFeatures) were created, for a total of 90 parameters to our model.

### Modeling
---
Following a train-test split on our training data, we obtained a cross validated R2 score of 80%. Introducing our aforementioned polynomial features boosted our R2 to 87%. While a Ridge regression did not perform any better than our polynomial features MLR, introduction of Lasso Ridge improved our R2 to its high of 90.4%.

### Conclusion
---
There is a 90% reduction in variation in Housing Prices when we take our features into account.

Our features explain 90.4% of the variation in Sale Price.