# Semiconductor Yield Predictor: Manufacturing Quality Control
This project focuses on building a robust classification model to predict the Pass/Fail yield of semiconductor manufacturing entities. By analyzing complex sensor data, the model identifies potential failures early in the production line, helping to reduce waste and optimize manufacturing efficiency.

# 🧪 The Challenge: Real-World Data Constraints
Unlike other datasets, this project addresses two major hurdles common in industrial data science:

High Dimensionality: The dataset contains 591 features representing various sensor signals. This requires strategic feature selection and dimensionality reduction to avoid the "curse of dimensionality."

Severe Class Imbalance: In semiconductor manufacturing, "Pass" entities vastly outnumber "Fail" entities. Standard accuracy is a misleading metric here, necessitating specialized techniques to ensure the model actually detects the rare failure cases.

# 🛠️ Tech Stack
Language: Python

Libraries:

Pandas & NumPy for data manipulation.

Scikit-learn for modeling and preprocessing.

Imbalanced-learn (SMOTE) for handling class distribution.

Matplotlib & Seaborn for statistical visualization.

# 📊 Project Workflow
1. Data Cleaning & Preprocessing
Handling Missing Values: Sensor data often contains nulls due to equipment downtime or signal loss.

Scaling: Standardizing features to ensure sensor readings with different units are comparable.

2. Addressing Class Imbalance
To ensure the model doesn't simply predict "Pass" for every entry, I implemented:

Synthetic Minority Over-sampling Technique (SMOTE) to balance the training set.

3. Modeling & Evaluation

I compared three distinct models:

Random Forest, Support Vector Machine (SVM), and Naive Bayes.

Random Forest proved to be robust against the high number of features and performed well after hyperparameter tuning.

SVM benefitted significantly from the data standardization but required careful tuning of the 'C' and 'Gamma' parameters.

Naive Bayes provided a baseline but generally struggled with the complex interdependencies between sensors compared to the ensemble methods.

# 📂 Repository Structure
Data_Science_Minor_Project_2.ipynb : Jupyter/Colab notebooks containing the EDA and Model Training.

signal-data.csv : Dataset used in this project

🚀 Installation & Usage
Clone the repository:

git clone https://github.com/your-username/semiconductor-predictor.git

Install dependencies.

Run the analysis:

jupyter notebook notebooks/Data_Science_Minor_Project_2.ipynb

# 📈 Key Results
Based on the testing phase, the SVM was selected as the final model.

Test Accuracy: 0.9342

Reason for Selection: This model achieved the best balance between Precision and Recall. In semiconductor manufacturing, identifying "Fail" cases (Recall) is critical to prevent yield excursions, and this model demonstrated the superior ability to detect these faults on unseen test data.
