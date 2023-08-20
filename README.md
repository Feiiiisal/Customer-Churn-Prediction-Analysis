# Customer-Churn-Prediction-Analysis

**Customer Churn Classification Project**

Welcome to the Customer Churn Classification Project! In this project, we focus on building classification models to perform churn analysis on customer data, a critical task for companies looking to enhance their revenue by retaining customers. Classification is a supervised learning approach where the goal is to predict the class or category that new data instances belong to.

**Data Sources**
In this project, the dataset is spread across three different sources:

1. First Data Set: The initial 3000 records of the dataset are stored in a remote SQL database. You will need to access this database to gather the data.

2. Second Data Set: The next 2000 records are available on OneDrive in an Excel file named "Telco-churn-second-2000.xlsx". This dataset serves as the test dataset.

3. Third Data Set: The final portion of the data, comprising 2000 records, is hosted on this GitHub Repository in a CSV file named "LP2_Telco-churn-last-2000.csv". Additional information about the dataset's features and context can also be found in this repository.

**Models and Results**

The following classification models were trained on the dataset:

    Support Vector Classifier (SVC)
    Gaussian Naive Bayes (GaussianNB)
    Decision Tree Classifier (DecisionTreeClassifier)
    Random Forest Classifier (RandomForestClassifier)
    XGBoost Classifier (XGBClassifier)
    Gradient Boosting Classifier (GradientBoostingClassifier)
    AdaBoost Classifier (AdaBoostClassifier)
    Logistic Regression (LogisticRegression)

After evaluating the models, the RandomForestClassifier stood out with consistent performance in terms of precision, recall, and F1-score for both the Churn and Non-Churn classes. It achieved high scores across all metrics, indicating a balanced identification of Churn and Non-Churn cases.

Key metrics from the classification report for RandomForestClassifier:

    Precision (Churn): 0.87
    Precision (Non-Churn): 0.86
    Recall (Churn): 0.87
    Recall (Non-Churn): 0.86
    F1-score (Churn): 0.87
    F1-score (Non-Churn): 0.87
    Accuracy: 0.87
Both Churn and Non-Churn classes have well-balanced precision and recall values, leading to a high overall F1-score and accuracy. The RandomForestClassifier demonstrates strong performance in classifying customer churn.

**Conclusion**

Through a combination of data preprocessing, feature engineering, and model training, we successfully built a RandomForestClassifier model that achieved an accuracy score of 0.865. This indicates our model's ability to effectively differentiate between loyal customers and those at risk of churning.

**Usage**
To replicate or build upon this project:

Access the required data from the specified sources.
Install the necessary dependencies by running:

  pip install -r requirements.txt.

Execute the classification scripts and notebooks provided in the repository.

**Contributing**

Contributions to this project are welcome! If you'd like to contribute, please follow the standard GitHub workflow:

**Fork the repository.**

Create a new branch for your feature/fix:

  git checkout -b feature/your-feature-name

Commit your changes: 

  git commit -m "Add a new feature"

Push to the branch: 

  git push origin feature/your-feature-name

Open a pull request.

**License**
This project is licensed under the MIT License.
