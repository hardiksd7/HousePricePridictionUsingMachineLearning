# House Price Prediction Using Regression

This project focuses on predicting house prices using various regression techniques. The dataset contains a variety of features related to houses, and the goal is to build a robust model that can accurately estimate their selling prices.

## Project Overview

The project involves data loading, feature engineering, data preprocessing, and training and evaluating different regression models. Key steps include:

* **Data Loading:** Reading the house price dataset into a pandas DataFrame.
* **Feature Engineering:** Creating new, more informative features from existing ones, such as calculating the 'age' of a house and considering the average price per zipcode (though the latter was noted but not explicitly implemented in the provided notebook).
* **Data Preprocessing:**
    * Converting the 'date' column to datetime objects.
    * Dropping irrelevant or redundant columns like 'id', 'date', 'yr_built', 'zipcode', 'lat', 'long', 'sqft_living', 'sqft_lot', and 'yr_renovated'.
    * Addressing data skewness in the 'sqft_lot15' column using Box-Cox transformation to achieve a more normal distribution.
* **Model Training & Evaluation:**
    * Splitting the data into training and testing sets.
    * Implementing and evaluating several regression models:
        * **Linear Regression:** A baseline model to understand initial performance.
        * **Lasso Regression:** Used for feature selection and regularization, helping to prevent overfitting by shrinking some coefficients to zero.
        * **Ridge Regression:** Another regularization technique that helps prevent overfitting by penalizing large coefficients.
        * **Polynomial Regression:** Exploring non-linear relationships between features and the target variable by creating polynomial features of degree 3. This is also evaluated with Ridge regularization.
    * Evaluating model performance using metrics such as R-squared ($R^2$), Mean Absolute Error (MAE), and Mean Squared Error (MSE).

## Dataset

The dataset used for this project is `house_price_prediction.csv`. It contains the following columns:

* `id`: Unique identifier for each house.
* `date`: Date when the house was sold.
* `price`: The selling price of the house (target variable).
* `bedrooms`: Number of bedrooms.
* `sqft_living`: Square footage of the living area.
* `sqft_lot`: Square footage of the lot.
* `floors`: Number of floors.
* `waterfront`: Whether the house has a waterfront view (0 or 1).
* `condition`: Condition of the house.
* `grade`: Grade of the house.
* `sqft_above`: Square footage of the house above ground.
* `sqft_basement`: Square footage of the basement.
* `yr_built`: Year the house was built.
* `yr_renovated`: Year the house was renovated.
* `zipcode`: Zipcode of the house.
* `lat`: Latitude.
* `long`: Longitude.
* `sqft_living15`: Square footage of living area for the 15 nearest neighbors.
* `sqft_lot15`: Square footage of lot for the 15 nearest neighbors.

## Installation

To run this notebook, you'll need the following libraries:

```bash
pip install pandas scikit-learn
