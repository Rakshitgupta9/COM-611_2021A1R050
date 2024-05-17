## Ques: Apply the sentimental Analysis using Natural language Processing on Live Twitter data.

# Amazon Alexa Reviews Analysis

This repository contains a script to analyze Amazon Alexa reviews. The script performs data preprocessing, visualization, and generates word clouds for positive and negative reviews.

## Requirements

- Python 3.x
- Jupyter Notebook or any Python IDE

### Python Libraries

Ensure you have the following libraries installed:
- numpy
- pandas
- matplotlib
- seaborn
- nltk
- wordcloud
- scikit-learn

You can install the required libraries using the following commands:

```bash
pip install numpy pandas matplotlib seaborn nltk wordcloud scikit-learn
```

## Dataset

The dataset used in this analysis is `amazon_alexa.tsv`, which should be a tab-separated values file containing Amazon Alexa reviews.

## Script Overview

### Import Libraries

The necessary libraries are imported for data manipulation, visualization, natural language processing, and machine learning.

```python
import nltk
nltk.download('stopwords')
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from nltk.corpus import stopwords
from wordcloud import WordCloud
from sklearn.feature_extraction.text import CountVectorizer
```

### Data Loading

The dataset is loaded into a pandas DataFrame.

```python
data = pd.read_csv('amazon_alexa.tsv', delimiter='\t', quoting=3)
```

### Data Exploration and Cleaning

The data is explored to understand its structure and clean any missing values.

```python
data.columns
data.isna().sum()
data.dropna(inplace=True)
data.describe()
data['Length'] = data['verified_reviews'].apply(len)
data.dtypes
```

### Data Visualization

Various visualizations are created to understand the distribution of ratings, feedback, variations, and the length of reviews.

```python
data['rating'].value_counts().plot.bar(color='red')
plt.title('Rating distribution count')
plt.xlabel('Ratings')
plt.ylabel('Count')
plt.show()

data['feedback'].value_counts().plot.bar(color='blue')
plt.title('Feedback distribution count')
plt.xlabel('Feedback')
plt.ylabel('Count')
plt.show()

data['variation'].value_counts().plot.bar(color='violet')
plt.title('Variation distribution count')
plt.xlabel('Variation')
plt.ylabel('Count')
plt.show()

sns.histplot(data['Length'], color='blue').set(title='Distribution of length of review')
sns.histplot(data[data['feedback'] == 0]['Length'], color='red').set(title='Distribution of length of review if feedback = 0')
sns.histplot(data[data['feedback'] == 1]['Length'], color='green').set(title='Distribution of length of review if feedback = 1')
```

### Word Cloud Generation

Word clouds are generated for all reviews, as well as unique positive and negative reviews.

```python
cv = CountVectorizer(stop_words='english')
words = cv.fit_transform(data.verified_reviews)

reviews = " ".join([review for review in data['verified_reviews']])
wc = WordCloud(background_color='white', max_words=50)
plt.figure(figsize=(10,10))
plt.imshow(wc.generate(reviews))
plt.title('Wordcloud for all reviews', fontsize=10)
plt.axis('off')
plt.show()

neg_reviews = " ".join([review for review in data[data['feedback'] == 0]['verified_reviews']]).lower().split()
pos_reviews = " ".join([review for review in data[data['feedback'] == 1]['verified_reviews']]).lower().split()

unique_negative = [x for x in neg_reviews if x not in pos_reviews]
unique_negative = " ".join(unique_negative)

unique_positive = [x for x in pos_reviews if x not in neg_reviews]
unique_positive = " ".join(unique_positive)

wc = WordCloud(background_color='white', max_words=50)
plt.figure(figsize=(10,10))
plt.imshow(wc.generate(unique_negative))
plt.title('Wordcloud for negative reviews', fontsize=10)
plt.axis('off')
plt.show()

wc = WordCloud(background_color='white', max_words=50)
plt.figure(figsize=(10,10))
plt.imshow(wc.generate(unique_positive))
plt.title('Wordcloud for positive reviews', fontsize=10)
plt.axis('off')
plt.show()
```

## Conclusion

This script provides a comprehensive analysis of Amazon Alexa reviews, offering insights into review distribution and visual representations through word clouds. The analysis can help understand customer sentiments and key themes in the feedback.

