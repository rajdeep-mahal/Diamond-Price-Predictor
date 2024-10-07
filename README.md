# Diamond Price Prediction Project

## Table of Contents
1. [Business Background](#business-background)
2. [Objective](#objective)
3. [Data](#data)  
   a. [Data Source](#data-source)  
   b. [Feature Included](#feature-included)  
   c. [Data Cleaning](#data-cleaning)  
   d. [Feature Engineering](#feature-engineering)  
   e. [Dimension Reduction](#dimension-reduction)  
   f. [Variable Selection](#variable-selection)  
   g. [Regularization](#regularization)
4. [Methodology Exploration](#methodology-exploration)
5. [Required Assumption](#required-assumption)
6. [Model Equation](#model-equation)
7. [In-Sample Validation and Performance Metric](#in-sample-validation-and-performance-metric)
8. [Monitoring and Maintenance Plan](#monitoring-and-maintenance-plan)
9. [Conclusion](#conclusion)
10. [Appendix](#appendix)
11. [References](#references)

## I. Business Background <a name="business-background"></a>
Diamonds are one of the most expensive and sought-after materials in the world, used in both jewelry and industry. Their prices vary significantly depending on factors such as color, carat, cut, and clarity. This project aims to develop a predictive model to estimate the price of diamonds based on these attributes, helping buyers understand pricing dynamics better.

## II. Objective <a name="objective"></a>
The main goal of this project is to build a machine learning model that accurately predicts diamond prices based on various features. The model aims to demonstrate how different factors affect the final price of diamonds. Additionally, we will compare six different algorithms to determine which performs best. The model should also suggest diamonds within a user's budget.

## III. Data <a name="data"></a>

### a. Data Source <a name="data-source"></a>
The dataset is sourced from [Kaggle](https://www.kaggle.com/datasets/nancyalaswad90/diamonds-prices) and contains approximately 54,000 round-cut diamonds. It was last updated on July 1, 2021.

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

## VI. Model Equation <a name="model-equation"></a>
Several models were used with different equations, including:
- **Ridge Regression**
- **Lasso Regression**
- **Simple Linear Regression**
- **KNN Regression**
- **Gradient Boosting Regression**
- **AdaBoost Regression**
- **Random Forest Regression**
- **Support Vector Regression**

## VII. In-Sample Validation and Performance Metric <a name="in-sample-validation-and-performance-metric"></a>
- **Cross-Validation**: Applied 5-fold cross-validation, evaluating models based on the mean absolute error (MAE). The MAE scores obtained were: `[0.06362084, 0.06342369, 0.06294201, 0.06408969, 0.062644]`
- **Training Results**: Heatmap analysis was used to assess feature correlations with price.
- **Test Results**: The model achieved an R-squared value of `0.99`, indicating excellent predictive performance.

## VIII. Monitoring and Maintenance Plan <a name="monitoring-and-maintenance-plan"></a>
The current analysis focuses on 10 features provided in the dataset, but there are potential hidden variables such as location, origin, and date sold. These could be incorporated into future iterations of the model. This dataset is specific to round-cut diamonds, and future models may expand to other diamond cuts with unique attributes.

## IX. Conclusion <a name="conclusion"></a>
Machine learning has proven effective in predicting diamond prices based on key attributes. Among the various algorithms tested, the Random Forest Regressor performed best. In the future, the results could be improved by implementing more complex models, such as Convolutional Neural Networks (CNNs).

## X. Appendix <a name="appendix"></a>
- **Figure 1**: Round-cut diamond dataset from Kaggle with ten features for machine learning algorithms.
- **Figure 2**: Relation between features and diamond prices.
- **Figure 3**: Distribution of color, cut, and clarity in the dataset.
- **Figure 4**: Distribution of continuous data.
- **Figure 5**: Diamond price histogram.
- **Figure 6**: Correlation between independent and dependent variables.
- **Figure 7**: Outliers in the dataset (table and depth).
- **Figure 8**: Dataset after removing outliers using the IQR method.
- **Figure 9**: Overview of Random Forest Regression algorithm.
- **Figure 10**: Random Forest Regressor’s best prediction score.

## References <a name="references"></a>
1. Brownlee, Jason. “Linear Regression for Machine Learning.” MachineLearningMastery.com, 14 Aug. 2020.
2. Gandhi, Rohith. “Introduction to Machine Learning Algorithms: Linear Regression.” Medium, Towards Data Science, 28 May 2018.
3. Muhajir, Imam. “K-Neighbors Regression Analysis in Python.” Medium, Analytics Vidhya, 8 Feb. 2020.
4. Singh, Aishwarya. “K-Nearest Neighbors Algorithm: KNN Regression Python.” Analytics Vidhya, 1 Dec. 2022.
5. Masui, Tomonori. “All You Need to Know about Gradient Boosting Algorithm.” Medium, Towards Data Science, 12 Feb. 2022.
6. Brownlee, Jason. “How to Develop an ADABOOST Ensemble in Python.” MachineLearningMastery.com, 26 Apr. 2021.
7. Desarda, Akash. “Understanding Adaboost.” Medium, Towards Data Science, 17 Jan. 2019.
8. Beheshti, Nima. “Random Forest Regression.” Medium, Towards Data Science, 2 Mar. 2022.
9. Sruthi E. R. “Random Forest: Introduction to Random Forest Algorithm.” Analytics Vidhya, 30 Nov. 2022.
10. Sharp, Tom. “An Introduction to Support Vector Regression (SVR).” Medium, Towards Data Science, 6 May 2020.
11. Patel, Dhrumil. “Predicting Diamond Prices Using Basic Measurement Metrics.” Medium, Towards Data Science, 16 May 2020.
12. Aswad, Nancy Al. “Diamonds-Prices database.” Kaggle.
