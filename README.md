# SMS Spam Detection   

## Project Overview

This project is a machine learning-based solution to classify SMS messages as spam or ham (non-spam). The goal is to develop a reliable spam filter by processing and analyzing SMS text data and applying classification algorithms.

---

## Project Flow

1. **Data Cleaning**
2. **Exploratory Data Analysis (EDA)**  
3. **Data Preprocessing**  
4. **Model Building**  

---

## Dataset Details

The dataset contains SMS messages labeled as spam (1) or ham (0) for building a spam detection model.

- **target**: Label indicating spam (1) or ham (0).
- **text**: The SMS message content.

---

## Data Cleaning

- **Dropped Unnecessary Columns**: Removed columns that were irrelevant for the analysis.
- **Renamed Columns**: Renamed columns for clarity (v1 to target, v2 to text).
- **Label Encoding**: Converted the target variable into numeric values (0 for ham, 1 for spam).
- **Checked for Missing Values**: Ensured there were no missing values in the dataset.
- **Removed Duplicates**: Identified and removed duplicate rows to maintain data integrity.

---

## Exploratory Data Analysis (EDA)

### Spam vs. Ham Distribution

A pie chart was plotted to visualize the distribution of spam and ham messages in the dataset. It is observed that **the data is imbalanced**.

![Spam vs Ham Distribution](https://github.com/user-attachments/assets/e7266c88-6ad7-4d80-9062-0fa213e06065)

### Summary of Ham Messages

| Statistic    | num_characters | num_words | num_sentences |
|--------------|----------------|-----------|---------------|
| **Count**    | 4516           | 4516      | 4516          |
| **Mean**     | 70.46          | 17.12     | 1.82          |
| **Std**      | 56.36          | 13.49     | 1.36          |
| **Min**      | 2              | 1         | 1             |
| **25%**      | 34             | 8         | 1             |
| **50%**      | 52             | 13        | 1             |
| **75%**      | 90             | 22        | 2             |
| **Max**      | 910            | 220       | 38            |

### Summary of Spam Messages

| Statistic    | num_characters | num_words | num_sentences |
|--------------|----------------|-----------|---------------|
| **Count**    | 653            | 653       | 653           |
| **Mean**     | 137.48         | 27.68     | 2.98          |
| **Std**      | 30.01          | 7.01      | 1.49          |
| **Min**      | 13             | 2         | 1             |
| **25%**      | 131            | 25        | 2             |
| **50%**      | 148            | 29        | 3             |
| **75%**      | 157            | 32        | 4             |
| **Max**      | 223            | 46        | 9             |

### Graphical Representation for `num_characters` and `num_words`

- **Number of characters and words used in spam messages is more compared to ham messages.**

![num_characters for Ham vs Spam](https://github.com/user-attachments/assets/af9e5fae-e215-44ee-88a9-464c160e6878)

![num_words for Ham vs Spam](https://github.com/user-attachments/assets/a6a5059c-e8b5-40c4-a41f-a8a4cd2ebb68)

### Correlation Heatmap

![Correlation Heatmap](https://github.com/user-attachments/assets/15c1adb3-5879-4519-b9f1-0e42f8400c72)

---

## Data Preprocessing

Following steps were performed in Data Preprocessing:

- **Lowercase conversion**
- **Tokenization**
- **Removing special characters**
- **Removing stop words and punctuation**
- **Stemming**

---

### Wordcloud of Spam Messages

![Spam Wordcloud](https://github.com/user-attachments/assets/d5b6a96b-844b-4100-bd7b-91e9a0164b15)

### Wordcloud of Ham Messages

![Ham Wordcloud](https://github.com/user-attachments/assets/7dd5680c-9191-477b-bbf0-454997a24f06)

---

## Model Building

- **TF-IDF Vectorization** was used to convert the transformed text into numerical features.
- The dataset was split into training and testing sets with an 80-20 split using `train_test_split`.

---

## Model Evaluation

The models were evaluated using **accuracy**, **confusion matrix**, and **precision score**. Below are the results for each model:

### 1. Gaussian Naive Bayes (GNB):

- **Accuracy**: 0.89
- **Confusion Matrix**:
    ```
    [[808  88]
     [ 24 114]]
    ```
- **Precision**: 0.56

### 2. Multinomial Naive Bayes (MNB):

- **Accuracy**: 0.97
- **Confusion Matrix**:
    ```
    [[896   0]
     [ 29 109]]
    ```
- **Precision**: 1.0

### 3. Bernoulli Naive Bayes (BNB):

- **Accuracy**: 0.98
- **Confusion Matrix**:
    ```
    [[895   1]
     [ 16 122]]
    ```
- **Precision**: 0.99

### Best Performing Model:

Based on accuracy and precision scores, **Multinomial Naive Bayes (MNB)** using **TF-IDF** vectorization was selected as the best model for this classification task.

---
