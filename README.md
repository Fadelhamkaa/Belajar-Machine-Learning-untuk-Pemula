# Belajar-Machine-Learning-untuk-Pemula

# Clustering and Classification on NYC Environmental Data

This project demonstrates the application of unsupervised clustering and supervised classification techniques on environmental data from NYC. The initial dataset is sourced from the [NYC Department of Health Environment Data](http://nyc.gov/health/environmentdata), and it served as the foundation for creating well-separated clusters and building robust classification models.

---

## Overview

- **Objective:**  
  To segment environmental data into distinct clusters and build classification models that can accurately predict cluster membership. The ultimate goal is to gain insights into environmental factors across NYC and evaluate model performance for potential real-world applications.

- **Key Highlights:**  
  - **Clustering:** Achieved an impressive silhouette score of **0.999**, indicating that the clusters are very well separated.
  - **Classification:** Developed three classification models (Decision Tree, Random Forest, and SVM) that all reached 100% accuracy after hyperparameter tuning.
  - **Data Imbalance:** Despite a significant imbalance between clusters, the models classified both groups perfectly, warranting further investigation to ensure generalization.

---

## Data Source

The dataset was originally obtained from the [NYC Department of Health Environment Data](http://nyc.gov/health/environmentdata). It contains various environmental measures and indicators that provide insights into urban health and environmental quality.

---

## Project Workflow

1. **Data Loading and Preprocessing:**  
   - Loaded the dataset and dropped unnecessary columns (e.g., IDs, redundant labels).
   - Separated the features and target variable (`cluster_label_after_featureSelection`).
   - Split the data into training and testing sets using stratified sampling.

2. **Clustering:**  
   - Applied clustering techniques to group the data.
   - Achieved a **silhouette score of 0.999**, confirming the high quality of the clustering process.

3. **Classification:**  
   - Built classification models using Decision Tree, Random Forest, and Support Vector Machine (SVM).
   - Developed pipelines to preprocess data (using OneHotEncoder and StandardScaler where applicable).
   - Evaluated models using metrics such as Accuracy, Precision, Recall, and F1-Score.

4. **Hyperparameter Tuning:**  
   - Performed GridSearchCV to optimize model parameters.
   - Re-evaluated models after tuning, with all models achieving 100% accuracy on the test set.

5. **Model Evaluation:**  
   - Compared evaluation metrics before and after tuning.
   - Visualized model performance using confusion matrices.
   - Discussed potential overfitting and the impact of data imbalance.

---

## Final Results and Insights

- **Clustering Outcome:**  
  The clustering phase produced very distinct groups (silhouette score = 0.999), indicating clear separation in the data.

- **Classification Performance:**  
  All three models (Decision Tree, Random Forest, and SVM) achieved 100% accuracy post-tuning, with perfect precision, recall, and F1-score for both clusters.

- **Analysis and Future Recommendations:**  
  - **Model Generalization:** Despite perfect scores, the high performance warrants further validation (e.g., cross-validation or testing on external data) to ensure the model is not overfitting.
  - **Addressing Imbalance:** With a significant disparity in the number of samples per cluster, additional techniques such as oversampling or cost-sensitive learning should be explored.
  - **Algorithm Exploration:** Consider testing other advanced algorithms (e.g., Gradient Boosting or Neural Networks) to verify if similar performance can be achieved under different modeling conditions.

---

## Technologies Used

- **Programming Language:** Python
- **Libraries:**  
  - Pandas
  - NumPy
  - Scikit-Learn
  - Matplotlib
  - Seaborn

---

Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/fadelhamka/) for further discussion or collaboration on similar data science projects!
