# Medical and Non-Medical Document Classifier

This project aims to build a classifier to distinguish between medical and non-medical documents using Wikipedia data. Two approaches have been explored for model training and evaluation.

## Option One: Train a Model using Train-Test Split

### Libraries Used
- NLTK
- Requests
- Scikit-learn
- BeautifulSoup

### Approach
- Data is fetched from various Wikipedia categories related to medical and non-medical topics.
- Text preprocessing involves HTML tag removal, tokenization, and removing non-alphabetic characters, with options for stopwords removal, stemming, and lemmatization.
- Documents are labeled (1 for medical, 0 for non-medical) and split into training, validation, and test sets.
- Bag of Words models (Naive Bayes and Logistic Regression) are trained and evaluated on validation and test sets, yielding the following results:
  - Naive Bayes Validation Accuracy: 82.70%
  - Logistic Regression Validation Accuracy: 88.72%
  - Naive Bayes Test Accuracy: 79.70%
  - Logistic Regression Test Accuracy: 80.50%

## Option Two: Train a Model using Cross-Validation

### Approach
- Similar data preprocessing steps are employed.
- This approach involves using cross-validation (5-fold) on the training set for both Naive Bayes and Logistic Regression models.
- Cross-validation scores are as follows:
  - Naive Bayes Cross-Validation Scores: [82.40%, 82.40%, 79.60%, 86.50%, 69.50%]
  - Logistic Regression Cross-Validation Scores: [83.80%, 85.20%, 84.50%, 81.60%, 84.40%]
- Average cross-validation scores:
  - Naive Bayes: 80.10%
  - Logistic Regression: 83.90%
- Test set accuracies:
  - Naive Bayes: 81.40%
  - Logistic Regression: 83.10%

### Explanation for High Accuracy in Option Two

The second option, employing cross-validation, tends to provide a more robust evaluation of the model's performance compared to a simple train-test split. Here are some reasons why the accuracy becomes higher in the second option:

1. **Utilizing More Data for Training:** Cross-validation involves training the model on different subsets of the training data, ensuring that the model learns from a larger portion of the available data. This can lead to a more generalized and better-performing model.

2. **Reducing Variance:** Cross-validation helps reduce the variance in performance estimation. By training and evaluating the model multiple times on different data splits, the evaluation becomes less dependent on the specific random choice of training and testing instances.

3. **Mitigating Overfitting:** Cross-validation helps detect and mitigate overfitting by providing a more comprehensive assessment of how well the model generalizes to different subsets of the data.

In summary, the second option with cross-validation provides a more reliable estimate of the model's performance, contributing to higher accuracy scores compared to a simple train-test split.
