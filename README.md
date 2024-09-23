# News Group Classification

A machine learning project that classifies news articles into 20 different categories.

## Table of Contents
- [Project Overview](#project-overview)
- [Steps](#steps)
  - [Read Data](#read-data)
  - [Data Preprocessing](#data-preprocessing)
  - [Feature Extraction](#feature-extraction)
  - [Model Training and Testing](#model-training-and-testing)
  - [Visualizing Results](#visualizing-results)
  - [Saving the Models](#saving-the-models)
- [Technologies Used](#technologies-used)
- [Results](#results)
- [How to Run](#how-to-run)
- [Acknowledgments](#acknowledgments)

---

## Project Overview
This project aims to classify news articles into one of 20 categories using natural language processing (NLP) techniques. We implemented various steps, including data preprocessing, feature extraction using TF-IDF, model training using Logistic Regression and Naive Bayes, and model evaluation.

---

## Steps

### Read Data
- A loop reads through each folder containing articles. 
- Inside each folder, a second loop reads each file, extracting the content and assigning a target label (folder name). 
- The data is collected into a list, which is later converted into a DataFrame.

### Data Preprocessing
Several preprocessing steps are applied to clean and prepare the data for analysis:
- **Remove Stop Words**: The text is converted to lowercase, and common stop words are removed.
- **Pattern Removal**: Lines ending with words like "writes" or "wrote" are removed. Additionally, lines starting with patterns like "from", "subject", "archive-name" are also excluded.
- **PGP Signature Removal**: Lines starting with “-----BEGIN PGP SIGNATURE-----” and the lines following them are removed.
- **Regular Expression Filtering**: Lines matching patterns like `.*@,*` are removed to eliminate email addresses.
- **Non-Alphanumeric Removal**: Non-alphanumeric characters are stripped from the text.
- **Stemming**: PorterStemmer is applied to reduce words to their base form.

### Feature Extraction
- **TF-IDF (Term Frequency - Inverse Document Frequency)**: This algorithm is applied to extract relevant words for each topic, assigning a weight to each word to measure its importance.

### Model Training and Testing
Two models were trained and tested for this classification task:
- **Logistic Regression**
  - Train Accuracy: 95.21%
  - Test Accuracy: 85.13%
- **Naive Bayes**
  - Train Accuracy: 95.10%
  - Test Accuracy: 85.02%

### Visualizing Results
- **Confusion Matrix**: To analyze the performance of the models.
 ![image](https://github.com/user-attachments/assets/c467013a-b08c-41fb-8d8e-0569f7d50c3c)

- **Bar Plot**: Visual representation of the accuracy and performance metrics.
![image](https://github.com/user-attachments/assets/f64c7bcf-95ec-481e-a8e5-61b1513871e4)

### Saving the Models
Both the Logistic Regression and Naive Bayes models are saved for future use.

---

## Technologies Used
- **Python** 
- **Scikit-learn**: For TF-IDF, Logistic Regression, and Naive Bayes.
- **Pandas**: Data handling and manipulation.
- **Matplotlib/Seaborn**: For visualizing results with confusion matrices and bar plots.

---

## Results
- Logistic Regression achieved a train accuracy of 95.21% and a test accuracy of 85.13%.
- Naive Bayes achieved a train accuracy of 95.10% and a test accuracy of 85.02%.
  
The models perform well on the dataset, with some variance in their performance on unseen data. The confusion matrix and bar plots provide insights into the classification results.

---

