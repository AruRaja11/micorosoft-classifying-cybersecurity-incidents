## 🛡️ Microsoft - Cybersecurity Incident Grade Classification
# 📌 Project Summary
In today’s evolving cybersecurity landscape, Security Operation Centers (SOCs) manage a flood of alerts daily. The aim of this project is to build a machine learning model that assists SOC analysts by automatically classifying incidents into:

* ✅ True Positive (TP) – Genuine security threats

* ⚠️ Benign Positive (BP) – Harmless incidents that appear suspicious

* ❌ False Positive (FP) – Incorrect or irrelevant alerts

By integrating this model into guided response systems, the solution aims to reduce investigation time and enhance enterprise security posture.

# 📊 Dataset
The model is trained on the GUIDE dataset, a simulated real-world dataset for security incident management.

# Key Features:
* Incident Metadata: IncidentId, OrgId, AlertId, Timestamp

* Alert Info: AlertTitle, Category, MitreTechniques, DetectorId

* Entity Details: EntityType, DeviceId, IpAddress, AccountUpn, Url

* Target: IncidentGrade → [TP, BP, FP]

# 🔍 Data Exploration & Cleaning
* Loaded and explored dataset using pandas

* Dropped columns with >50% missing values

* Filled remaining nulls using:

* .mean() / .median() → for numerical columns

* .mode() → for categorical columns

* Removed outliers using IQR method

# ⚙️ Feature Engineering
* Timestamp split into Date, Month, Year, Hour to capture time-based patterns

* Categorical features encoded using LabelEncoder (One-Hot avoided due to high dimensionality)

# 📐 Feature Scaling
Used MinMaxScaler to normalize feature ranges for better model convergence.

# 🤖 Model Building
Train-test split: 80% Training / 20% Validation

# Algorithms Tested:
* Logistic Regression

* Decision Tree Classifier

* Random Forest Classifier

* K-Nearest Neighbors (KNN)

* XGBoost Classifier

# Metrics Used:
* Accuracy

* Precision

* Recall

* F1-Score

# 🔧 Model Tuning & Evaluation
* Performed hyperparameter tuning with GridSearchCV

* Best model: XGBoost Classifier

    * 📈 91% Accuracy (Validation Set)

    * 📊 Weighted Avg F1-Score: 91%

* 🧪 Test Accuracy on GUIDE_Test.csv: 86%

# 🏁 Key Outcomes
* ✅ XGBoost demonstrated the best performance and generalization
* ✅ Achieved high accuracy and F1-score across all classes
* ✅ Ready for deployment in SOC environments for real-time triage support

#🛠️ Tools & Libraries
* Python

* Pandas, NumPy

* Scikit-learn

*Matplotlib, Seaborn

