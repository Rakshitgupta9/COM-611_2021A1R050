## Ques: Implement the KNN IRIS Image Classification based on a given set of training data samples. Read the training data from a .CSV file.

## KNN Prediction with Numpy

This repository contains a Python script that demonstrates how to use the K Nearest Neighbors (KNN) algorithm for making predictions using the NumPy library.

### Description

The provided Python script demonstrates how to predict using KNN with an input array using NumPy. Here's a breakdown of what the script does:

1. **Importing Libraries**: The script imports the necessary libraries, mainly NumPy, which is a powerful library for numerical computations in Python.

2. **Defining the Input Array**: An input array `X_pred` is defined. This array represents the features for which we want to make predictions. In this case, it's a 1D array `[3, 5, 4, 2]`.

3. **Reshaping the Input Array**: Before making predictions, the input array is reshaped to be 2D using NumPy's `reshape()` function. This is done because scikit-learn's KNN classifier expects a 2D array as input.

4. **Predicting**: The script then makes predictions using the KNN classifier (`knn`) on the reshaped input array (`X_pred`). The result is stored in the variable `prediction`.

5. **Printing Prediction**: Finally, the predicted value is printed to the console.

### Usage

To use this script:

1. Clone this repository to your local machine.
   ```bash
   git clone https://github.com/your_username/knn-prediction-numpy.git
   ```

2. Navigate to the directory.
   ```bash
   cd knn-prediction-numpy
   ```

3. Run the script.
   ```bash
   python knn_prediction.py
   ```

### Requirements

- Python 3.x
- NumPy
- scikit-learn (for the KNN classifier, not explicitly used in this script but assumed for completeness)
