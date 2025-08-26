# Construction-and-Optimization-of-Music-Comment-Decision-System-

# System Description
Completed on April 22, 2025)
This project is to classify comments into positive and negative categories.The entire project proceeded through the following five steps:

**1.Baseline model:**

We used a simpler TFIDF-logistic regression combination as a baseline model to compare with more complex models (such as random forests, gradient boosting, etc.)

Before conducting model experiments, we need to preprocess the dataset. We deleted rows with missing values, converted ratings to categories (for example, 3.0 above are positive, 3.0 and below are negative), converted vector features, divided the dataset (80% training set and 20% test set, random_state=42), and performed SMOTE oversampling operations.


**2.Compare with different models:**

In the word embedding model, we used four word embedding models: TF-IDF, Word2Vec, Glove, and BERT; in the data analysis model, we used five classification models: logistic regression, SVM, random forest, gradient boosting tree, and decision tree. The output result indicators are combined in pairs, accuracy, F1 score, recall, and precision.


**3.Fine-tuning hyperparameters**

In this part, we start by tuning the hyperparameters in the same way for four different models, TFIDF_RF, GLOVE_SVM, BERT_RF, TFIDF_SVM. Then the optimal model was selected for testing by different methods, GridSearchCV, RandomizedSearchCV, Optuna (Bayesian), and through comparison, we finally found that TFIDF_RF+RandomizedSearchCV could get the best tuning performance.

**4.Data visualization**

In this stage, a variety of statistical and visualization techniques are employed to gain multi-faceted insights into the data and model performance. Visualization tools such as histograms, box plots, and dimensionality reduction scatter plots are used to validate measures of central tendency (mean, median, mode) and dispersion (range, variance, standard deviation, quartiles).

**5.Different ways to improve the baseline modeln**

We thought of the following methods to improve the baseline model:

1) Word vector fusion: Combine TF-IDF features with Glove.

2) Multi-model fusion: Fusion of TF-IDF - logistic regression model with other different types of classification models (support vector machine, decision tree).

3) TFIDF-XGBOOST (At first, I thought that the data set was simple and there was no need to use XGBOOST, but later I found that it also had good results).
