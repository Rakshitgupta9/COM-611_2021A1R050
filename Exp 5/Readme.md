## Ques: Implement the Linear regression on the salary Prediction based on a given set of training data samples. Read the training data from a .CSV file.

**Linear Regression for Salary Prediction**

This repository contains Python code for implementing linear regression to predict salaries based on years of experience. The dataset used for training is read from a .CSV file. The implementation utilizes various libraries including pandas, matplotlib, seaborn, statsmodels, and scikit-learn.

**Code Explanation:**

1. **Importing Libraries:** 
   - We begin by importing necessary libraries and suppressing warnings for cleaner output.

2. **Data Loading and Exploration:** 
   - The training data is loaded from a CSV file named 'Salary_Data.csv'.
   - Basic exploration of the data is performed using methods like `.head()`, `.shape`, `.describe()`, and `sns.pairplot()` to understand the relationship between 'YearsExperience' and 'Salary' features.

3. **Data Preprocessing:**
   - The data is split into features ('YearsExperience') and target ('Salary').
   - Further, the data is divided into training and testing sets using `train_test_split()`.

4. **Model Training:**
   - We add a constant term to the feature matrix of the training set using `sm.add_constant()` to fit the intercept term of the linear regression model.
   - The Ordinary Least Squares (OLS) method from the statsmodels library is used to fit the linear regression model to the training data.

5. **Model Evaluation:**
   - Summary statistics of the trained model are printed using `model.summary()` to assess the model's goodness-of-fit.
   - A scatter plot of the training data along with the regression line is plotted using matplotlib.
   - Predictions are made on the training set and residuals are calculated.
   - Distribution of residuals is visualized using `sns.distplot()` and a scatter plot of residuals against the independent variable is created.

6. **Model Testing:**
   - Similar to training data, a constant term is added to the feature matrix of the testing set.
   - Predictions are made on the testing set.
   - Root Mean Squared Error (RMSE) and R-squared score are calculated to evaluate the model's performance on unseen data.
   - A scatter plot of the testing data along with the regression line is plotted.

**Files Included:**
- `salary_prediction.ipynb`: Jupyter notebook containing the complete code implementation.
- `Salary_Data.csv`: CSV file containing the training data.
- `README.md`: This README file providing an overview of the project.

**Dependencies:**
- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- statsmodels
- scikit-learn

**Usage:**
- Clone the repository.
- Ensure all dependencies are installed.
- Run `salary_prediction.ipynb` in a Jupyter notebook environment.

Feel free to reach out for any questions or improvements!
