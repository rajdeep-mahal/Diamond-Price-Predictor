# Diamond Price Prediction Project

## I. Business Background <a name="business-background"></a>
Diamonds are one of the most expensive and sought-after materials in the world, used in both jewelry and industry. Their prices vary significantly depending on factors such as color, carat, cut, and clarity. This project aims to develop a predictive model to estimate the price of diamonds based on these attributes, helping buyers understand pricing dynamics better.

## II. Objective <a name="objective"></a>
The main goal of this project is to build a machine learning model that accurately predicts diamond prices based on various features. The model aims to demonstrate how different factors affect the final price of diamonds. Additionally, we will compare six different algorithms to determine which performs best. The model should also suggest diamonds within a user's budget.

## III. Data <a name="data"></a>

### a. Data Source <a name="data-source"></a>
The dataset is sourced from [Kaggle](https://www.kaggle.com/datasets/nancyalaswad90/diamonds-prices) and contains approximately 54,000 round-cut diamonds.

### b. Feature Included <a name="feature-included"></a>
The dataset contains 10 features:  
- **Carat**  
- **Cut** (ordered categorical)  
- **Color** (ordered categorical)  
- **Clarity** (ordered categorical)  
- **Depth**, **Table**, **X**, **Y**, **Z** (all numerical)  
- **Price** (in USD)

### c. Data Cleaning <a name="data-cleaning"></a>
- Dropped an unnecessary unnamed column.  
- No null values were present.  
- Used the IQR method to remove outliers.

### d. Feature Engineering <a name="feature-engineering"></a>
Applied log transformation to numerical continuous variables using `numpy.log()` to improve visualization and trends. Due to high variance, binning was not performed.

### e. Dimension Reduction <a name="dimension-reduction"></a>
No dimensionality reduction was applied as the dataset is not highly dimensional and reduction techniques were not necessary.

### f. Variable Selection <a name="variable-selection"></a>
Correlation analysis showed that "table" and "depth" had little correlation with price, while **X**, **Y**, and **Z** exhibited high correlation. However, all variables were retained for the analysis.

### g. Regularization <a name="regularization"></a>
- **Ridge Regularization**: A method for tuning regression models when independent variables are highly correlated.
- **Lasso Regularization**: Shrinks data values towards a central point. Lasso can set some coefficients to zero, while Ridge will not.
- **Elastic Net**: Combines both Ridge and Lasso penalties.

## IV. Methodology Exploration <a name="methodology-exploration"></a>
The following six machine learning algorithms were used to predict diamond prices:
1. **Linear Regression**
2. **K Neighbors Regressor**
3. **Gradient Boosting Regressor**
4. **AdaBoost Regressor**
5. **Random Forest Regressor**
6. **Support Vector Regression (SVR)**

The Random Forest Regressor yielded the best prediction accuracy compared to other algorithms. It uses an ensemble of decision trees and averages the results for regression tasks.

## V. Required Assumption <a name="required-assumption"></a>
- **Price** is the dependent variable.
- **X**, **Y**, **Z**, and other factors are independent variables.
- Before and after transformation, the data shows consistent patterns, with slight changes in value distributions.

## VI. In-Sample Validation and Performance Metric <a name="in-sample-validation-and-performance-metric"></a>
- **Cross-Validation**: Applied 5-fold cross-validation, evaluating models based on the mean absolute error (MAE). The MAE scores obtained were: `[0.06362084, 0.06342369, 0.06294201, 0.06408969, 0.062644]`
- **Training Results**: Heatmap analysis was used to assess feature correlations with price.
- **Test Results**: The model achieved an R-squared value of `0.99`, indicating excellent predictive performance.

## VII. Monitoring and Maintenance Plan <a name="monitoring-and-maintenance-plan"></a>
The current analysis focuses on 10 features provided in the dataset, but there are potential hidden variables such as location, origin, and date sold. These could be incorporated into future iterations of the model. This dataset is specific to round-cut diamonds, and future models may expand to other diamond cuts with unique attributes.

## VIII. Conclusion <a name="conclusion"></a>
Machine learning has proven effective in predicting diamond prices based on key attributes. Among the various algorithms tested, the Random Forest Regressor performed best. In the future, the results could be improved by implementing more complex models, such as Convolutional Neural Networks (CNNs).
