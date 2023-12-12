# Wikipedia Text Classification Pipeline

This document provides an overview of the pipeline for text classification of Wikipedia documents into medical and non-medical categories using machine learning models.

## 1. Data Collection

The script begins by fetching documents from Wikipedia based on specified categories. Two sets of categories are considered: medical and non-medical. The `get_documents_from_category` function utilizes the Wikipedia API to retrieve documents. The obtained documents are stored in separate lists for medical and non-medical categories.

## 2. Data Preprocessing

### 2.1. Text Cleaning

The `preprocess_text` function is applied to clean the retrieved text data. This function performs the following tasks:

- Removal of HTML tags using BeautifulSoup.
- Tokenization of the text.
- Removal of non-alphabetic characters.
- Optionally, removal of stopwords, stemming, and lemmatization based on user preferences.

### 2.2. Handling Empty Documents

An additional step is added to remove empty documents after preprocessing. The `if doc.strip():` condition checks if the document is non-empty after stripping leading and trailing whitespace. Empty documents are excluded from further processing.

## 3. Data Storage

The preprocessed data is then stored in a CSV file named `wikipedia_documents_labels.csv`. This CSV file contains two columns: 'Text' for the preprocessed documents and 'Label' indicating whether the document belongs to the medical (1) or non-medical (0) category.

## 4. Model Training and Evaluation

### 4.1. Train-Test Split

The data is split into training and test sets using the `train_test_split` function.

### 4.2. Model Creation

Two machine learning models are employed:

- Naive Bayes model (`MultinomialNB`) using the `CountVectorizer`.
- Logistic Regression model (`LogisticRegression`) using the `CountVectorizer`.

### 4.3. Cross-Validation

Cross-validation is performed on the training set to assess the models' performance using accuracy scores.

### 4.4. Model Training

The models are trained on the entire training set.

### 4.5. Model Evaluation

The trained models are evaluated on the test set, and metrics such as accuracy, precision, and F1 score are calculated.

## 5. Results

The results are displayed in a DataFrame, showing the accuracy, precision, and F1 score for both the Naive Bayes and Logistic Regression models.

## 6. Conclusion

The pipeline demonstrates the process of collecting, preprocessing, and classifying Wikipedia documents into medical and non-medical categories using machine learning models. Users can explore and modify the pipeline for other text classification tasks.
