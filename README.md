Garment Productivity Classification

Project Overview

This project uses machine learning techniques to analyze garment
manufacturing data and classify productivity levels. The dataset
contains information related to production activities such as
department, working day, team, targeted productivity, standard minute
value (SMV), work in progress (WIP), overtime, incentives, idle time,
number of workers, and actual productivity.


The project follows a complete machine learning workflow starting from
data loading and preprocessing and continuing through feature selection,
feature scaling, train-test splitting, classification, and model
evaluation.


Dataset

The project uses the garment.csv dataset.


Dataset Information


Number of records: 1197

Number of columns: 15

Target variable: actual_productivity


The dataset contains both categorical and numerical attributes. Some
numerical columns also contain missing values, which are handled during
preprocessing.


Technologies Used


Python

Pandas

NumPy

Matplotlib

Seaborn

Scikit-learn

Jupyter Notebook


Machine Learning Workflow

The notebook follows these major steps:



Import required Python libraries.

Load the garment.csv dataset.

Convert the dataset into a Pandas DataFrame.

Explore the dataset using data inspection and visualization.

Handle missing values and preprocess the data.

Encode categorical variables into numerical form.

Transform and prepare the features.

Select relevant features.

Apply feature scaling using StandardScaler.

Split the data into training and testing sets.

Build classification models.

Generate predictions.

Evaluate model performance using classification metrics.

Compare the classification models and identify the best-performing model.


Feature Scaling

Feature scaling is performed using StandardScaler:


from sklearn.preprocessing import StandardScaler

ss = StandardScaler()
X_scaled = ss.fit_transform(X_selected)

The scaled data is then divided into training and testing sets:


from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X_scaled, y, test_size=0.2, random_state=40
)

Here, 80% of the data is used for training and 20% is used for testing.


Classification Models

The notebook includes the following classification algorithms:


1. Logistic Regression

Logistic Regression is used as a baseline classification algorithm for
predicting the productivity class.


2. Decision Tree Classifier

Decision Tree is used to classify productivity based on decision rules
generated from the input features.


3. Random Forest Classifier

Random Forest is an ensemble learning algorithm that combines multiple
decision trees to improve prediction performance.


4. AdaBoost Classifier

AdaBoost is an ensemble method that combines weak learners sequentially
to improve classification performance.


5. Gradient Boosting Classifier

Gradient Boosting builds multiple models sequentially, with each model
attempting to improve the errors made by the previous models.


Model Evaluation

The notebook evaluates the classification models using the following
metrics:



Accuracy -- Measures the overall percentage of correctly classified observations.

Precision -- Measures how many of the observations predicted as positive are actually positive.

Recall -- Measures how many of the actual positive observations are correctly identified.

F1-Score -- Provides a balance between precision and recall.


The evaluation is performed using Scikit-learn metrics such as:


from sklearn.metrics import accuracy_score
from sklearn.metrics import classification_report
from sklearn.metrics import f1_score
from sklearn.metrics import precision_score
from sklearn.metrics import recall_score

Current Evaluation Results

The notebook contains evaluated results for Logistic Regression and
Decision Tree.


Logistic Regression


Accuracy: 74.58%

Precision: 81.32%

Recall: 84.57%

F1-Score: 82.91%


Decision Tree


Accuracy: 79.58%

Precision: 85.00%

Recall: 87.43%

F1-Score: 86.20%


Based on these available results, the Decision Tree currently performs
better than Logistic Regression across the reported metrics.


Model Comparison

The notebook defines five classification models:


models = {
    "Logistic Regression": LogisticRegression(),
    "Decision Tree": DecisionTreeClassifier(),
    "Random Forest": RandomForestClassifier(n_estimators=100),
    "AdaBoost": AdaBoostClassifier(n_estimators=100),
    "Gradient Boosting": GradientBoostingClassifier(n_estimators=100)
}

A final comparison table should be generated after fitting and
evaluating all five models. The comparison should include Accuracy,
Precision, Recall, and F1-Score for each model.


This comparison will help identify the most suitable classifier for the
garment productivity classification problem.


Project Structure

Garment Productivity Classification/
│
├── garment.ipynb
├── garment.csv
└── README.md

How to Run the Project


Install Python.

Install the required libraries:


pip install numpy pandas matplotlib seaborn scikit-learn


Place garment.csv in the same directory as garment.ipynb.

Open the notebook using Jupyter Notebook or JupyterLab.

Run the cells sequentially from the beginning.

Review the preprocessing, feature scaling, classification, and evaluation results.


Conclusion

This project demonstrates the application of machine learning to garment
manufacturing productivity data. The workflow includes data
preprocessing, feature selection, feature scaling, train-test splitting,
and classification using multiple machine learning algorithms.


The currently available evaluation results show that the Decision Tree
classifier performs better than Logistic Regression based on accuracy,
precision, recall, and F1-score. A final comparison of all five
classifiers should be completed to select the best-performing model for
the project.

