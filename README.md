
# Predicting Used Car Prices 

In this project, we will use a secondhand [car prediction dataset from Kaggle](https://www.kaggle.com/datasets/sujithmandala/second-hand-car-price-prediction) to predict the price of a car based on its specifications by implementing a **linear/polynomial regression model from scratch.**

**Components:**

- Defining the model
- Defining the loss/cost function
- Implementing Backpropagation
- Feature Selection
- Feature Normalization
- Applying regularization


## Outline

### Data Pre-Processing

#### Data Analysis
- Analyzed the components of the data to determine whether to convert it. \
- Determined the *shape* of data, *datatypes* of each feature, and the existence of **null values**. 

#### Data Cleaning
- Used *Ordinal encoding* and *One-hot encoding* to convert non-numeric data into numeric data.

### Building the Model

#### Feature Selection
- Plot feature vs price and determine if there is any correlation between the feature and price.

#### Feature Scaling
- Apply Z-score normalization to the data. This ensures there is no problem in choosing a learning rate. (refer to the notebook for an in-depth explanation)

#### Defining the Cost/Loss Function
- Defined the mean square cost function that will be used in back-propagation.
- Calculated the cost function in 3 different ways to compare the speeds of matrix multiplication, vector dot product, and looping


### Training the Model

#### Creating Training Sets for Cross-Validation
- Created *5 different sets for cross-validation by making five folds manually* using a for-loop and iloc.

#### Model Fitting
- *Applied Gradient Descent* to each of the five training Sets to find the Weights and *plotted the best-fit lines*

#### Model Validation
- Used the validation set to validate the model and determine the absolute and percent errors.

## Results

- The number of data points used in validation = 100, i.e., five validation sets with 20 data points each.
- The mean percent error in the prediction over five cross-validation sets is about +/- 22% which corresponds to an absolute error of 2,85,025
- The first quartile of predictions has a percent error of less than 8%
- The median percent error in prediction is 16.6%, which means 50 data points have a predicted price with an error of less than 16.6%
- The third quartile of predictions has a percent error between 16.6% and 31%
- The max error is 158%, and the last quartile has an error between 31% and 158%

#### Analysis

- There are only 100 data points in the given data. This made it a little harder for the training model to learn more precise relationships between features and output
- Further, we have selected five different features that the model has to use; since all five features have an impact on price, the polynomial model of third order was not able to fit all the data
- The first quartile of the predictions was accurate enough. However, the last quartile of predictions was highly inaccurate, which can be attributed to the above 2 points

## Project Analysis

### Learning Outcomes

1. The primary learning outcomes of this project were understanding and implementing the underlying functions of the Cost function, Gradient Descent , Prediction Model , Feature Scaling, Model Fitting, Model Validation, and Cross-Validation from scratch using only basic Python and minimal libraries, which helped me strengthen my core ML (and consequently DL) concepts.
2. Got hands-on with the process of Data Cleaning and Pre-Processing for model usage
3. Visualize the difference between many alternatives
  - Time Taken by Vector Dot Product vs Matrix Operations vs Loop
  - Gradient Descent with Normalized features vs Unnormalized features
  - Model fitting with Linear Regression model vs Polynomial Regression Model

4. Basic Plotting with Matplotlib
   
### Future Scope
1. Add more graphs for visualization of gradient descent, feature scaling, etc.
2. Create a model that uses standard libraries like sci-kit learn and compare the difference in accuracy
3. Adding regularization
4. Feature Engineering - PCA (principal component analysis)
