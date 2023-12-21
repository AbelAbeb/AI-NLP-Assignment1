# Wikipedia Text Classification

This project involves classifying Wikipedia documents into medical and non-medical categories using machine learning models. The pipeline includes data retrieval, preprocessing, model training, and evaluation. Below is an overview of the steps and pipeline:

## Overview

### 1. **Data Collection**

- Fetch documents from Wikipedia based on medical and non-medical categories.
- Utilize the Wikipedia API to retrieve documents using the `get_documents_from_category` function.

### 2. **Data Preprocessing**

#### 2.1. **Text Cleaning**

- Clean the retrieved text data using the `preprocess_text` function.
- Tasks include removing HTML tags, tokenization, and removing non-alphabetic characters.
- Optional removal of stopwords, stemming, and lemmatization based on user preferences.

#### 2.2. **Handling Empty Documents**

- Exclude empty documents after preprocessing using the condition `if doc.strip():`.

### 3. **Data Storage**

- Store the preprocessed data in a CSV file named `wikipedia_documents_labels.csv`.
- The CSV file contains 'Text' for preprocessed documents and 'Label' indicating medical (1) or non-medical (0) category.

### 4. **Model Training and Evaluation**

#### 4.1. **Train-Test Split**

- Split the data into training and test sets using `train_test_split`.

#### 4.2. **Model Creation**

- Use two machine learning models:
  - Naive Bayes model (`MultinomialNB`) with `CountVectorizer`.
  - Logistic Regression model (`LogisticRegression`) with `CountVectorizer`.

#### 4.3. **Cross-Validation**

- Perform cross-validation on the training set to assess model performance using accuracy scores.

#### 4.4. **Model Training**

- Train the models on the entire training set.

#### 4.5. **Model Evaluation**

- Evaluate the trained models on the test set.
- Calculate metrics such as accuracy, precision, and F1 score.

### 5. **Results**

- Display results in a DataFrame, showcasing accuracy, precision, and F1 score for both Naive Bayes and Logistic Regression models.

## Usage

1. **Requirements:**
   - Ensure required libraries are installed (`scikit-learn`, `nltk`, `requests`, `pandas`, `beautifulsoup4`).

2. **Run the Code:**
   - Execute the code to fetch, preprocess, train models, and evaluate.

3. **Review Results:**
   - Examine cross-validation scores, model evaluation metrics, and predictions for custom text.

4. **Custom Predictions:**
   - Modify the `custom_text` variable to test the models on your input.

5. **Save/Load Models:**
   - Trained models are saved to files (`naive_bayes_model.joblib` and `logistic_regression_model.joblib`). They can be loaded for future use.

6. **Review Dataset:**
   - The preprocessed dataset is saved in `wikipedia_documents_labels.csv`. Review data in this file.

## Wikipedia Text Classification Pipeline

This section provides additional details on the pipeline steps.

### 1. **Data Collection**

- Fetch documents from Wikipedia based on specified categories.
- Separate categories for medical and non-medical documents.

### 2. **Data Preprocessing**

#### 2.1. **Text Cleaning**

- Clean text data using BeautifulSoup for HTML tag removal, tokenization, and removal of non-alphabetic characters.
- Optional tasks include removing stopwords, stemming, and lemmatization.

#### 2.2. **Handling Empty Documents**

- Exclude empty documents from further processing.

### 3. **Data Storage**

- Store preprocessed data in a CSV file (`wikipedia_documents_labels.csv`).
- Two columns: 'Text' for preprocessed documents and 'Label' for medical (1) or non-medical (0) category.

### 4. **Model Training and Evaluation**

#### 4.1. **Train-Test Split**

- Split data into training and test sets.

#### 4.2. **Model Creation**

- Use Naive Bayes and Logistic Regression models with CountVectorizer.

#### 4.3. **Cross-Validation**

- Assess model performance using cross-validation on the training set.

#### 4.4. **Model Training**

- Train models on the entire training set.

#### 4.5. **Model Evaluation**

- Evaluate models on the test set, calculate accuracy, precision, and F1 score.

### 5. **Results**

- Display results in a DataFrame with accuracy, precision, and F1 score for both Naive Bayes and Logistic Regression models.

### 6. **Conclusion**

- The pipeline demonstrates collecting, preprocessing, and classifying Wikipedia documents into medical and non-medical categories using machine learning models.
- Users can explore and modify the pipeline for other text classification tasks.