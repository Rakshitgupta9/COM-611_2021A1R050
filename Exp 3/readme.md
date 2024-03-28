## Ques: Assuming a set of data that need to be specifically used in the dataset applies the Data Wrangling by reading the training data from a .csv file.


# Automobile Data Cleaning and Preprocessing

## Overview
This repository contains a Python script for cleaning and preprocessing automobile data using the Pandas library. The dataset used is stored in a CSV file named "auto.csv," and it includes information about various attributes of automobiles.

## Dependencies
- pandas
- matplotlib
- numpy

## Usage
1. **Data Loading:**
   - The script loads the automobile dataset from the "auto.csv" file into a Pandas DataFrame.
   - Custom column headers are provided.

```python
import pandas as pd
filename = "auto.csv"
headers = ["symboling", "normalized-losses", "make", "fuel-type", "aspiration", "num-of-doors", "body-style", ...
df = pd.read_csv(filename, names=headers)
```

2. **Handling Missing Data:**
   - The script replaces "?" values with NaN and then addresses missing data.
   - For numerical columns with missing values, the mean is used to fill the gaps.

```python
import numpy as np
df.replace("?", np.nan, inplace=True)
# ...

# Example for "normalized-losses"
avg_norm_loss = df["normalized-losses"].astype("float").mean(axis=0)
df["normalized-losses"].replace(np.nan, avg_norm_loss, inplace=True)
```

3. **Data Type Conversion:**
   - Converts data types of specific columns to the appropriate types (e.g., float, int).

```python
df[["bore", "stroke"]] = df[["bore", "stroke"]].astype("float")
df[["normalized-losses"]] = df[["normalized-losses"]].astype("int")
# ...
```

4. **Feature Engineering:**
   - Creates new features like "city-L/100km" and "highway-L/100km."
   - Normalizes numerical features such as "length," "width," and "height."

```python
df["city-L/100km"] = 235 / df["city-mpg"]
df["highway-mpg"] = 235 / df["highway-mpg"]
df.rename(columns={'highway-mpg': 'highway-L/100km'}, inplace=True)
df["length"] = df["length"] / df["length"].max()
# ...
```

5. **Exploratory Data Analysis (EDA):**
   - Utilizes Matplotlib for EDA, such as creating a histogram for the "horsepower" attribute.

```python
import matplotlib.pyplot as plt
plt.hist(df["horsepower"])
plt.xlabel("horsepower")
plt.ylabel("count")
plt.title("HORSEPOWER BINS")
```

6. **Categorical Variable Encoding:**
   - Converts categorical variables into dummy/indicator variables using one-hot encoding.

```python
dummy_variable_1 = pd.get_dummies(df["fuel-type"])
dummy_variable_1.rename(columns={'fuel-type-diesel': 'gas', 'fuel-type-diesel': 'diesel'}, inplace=True)
df = pd.concat([df, dummy_variable_1], axis=1)
df.drop("fuel-type", axis=1, inplace=True)
# ...
```

7. **Save Cleaned Data:**
   - Saves the cleaned and preprocessed DataFrame to a new CSV file named "clean_df.csv."

```python
df.to_csv('clean_df.csv')
```

## Conclusion
This script demonstrates a step-by-step process for cleaning, preprocessing, and exploring automobile data. The resulting cleaned dataset, stored in "clean_df.csv," is ready for further analysis or machine learning tasks.
