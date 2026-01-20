# nyc-311-resolution-time-ml
End-to-end machine learning project predicting NYC 311 complaint resolution time using classical ML, robust preprocessing pipelines, and feature importance analysis.

📊 Predicting NYC 311 Service Request Resolution Time

End-to-End Machine Learning Project (Hands-On ML Ch. 1–6)

🔍 Project Overview

This project builds an end-to-end machine learning pipeline to predict NYC 311 service request resolution time using publicly available civic data.
The goal is not only prediction accuracy, but understanding what factors actually drive response delays in real-world systems.

The project follows industry-standard ML practices including exploratory data analysis, target engineering, baseline modeling, nonlinear model comparison, and feature importance analysis.

📁 Dataset

Source: NYC Open Data – 311 Service Requests

Scope:

Borough: Manhattan

Timeframe: 6 months

Records: ~118,000

Features Used:

Agency

Complaint Type

Complaint Detail

Location Type

ZIP Code

Borough

🎯 Target Variable

Resolution Time (minutes)
Computed as the difference between Closed Date and Created Date.

Due to extreme right skew (long-tail delays), a log transformation was applied to stabilize variance.

🧠 Modeling Approach
1️⃣ Baseline Model — Linear Regression

Built using a full preprocessing pipeline with:

OneHotEncoding for categorical variables

Proper train/test split to avoid leakage

Initial performance was poor due to skewed target distribution

2️⃣ Target Transformation

Applied log(1 + resolution_minutes)

Resulted in a significant reduction in error

Demonstrated the importance of aligning data with model assumptions

3️⃣ Nonlinear Model — Random Forest

Trained a Random Forest Regressor on the transformed target

Compared performance against the linear baseline

Observed marginal improvements, highlighting data limitations rather than model weakness

📈 Model Performance (Log Scale)
Model	MAE	RMSE
Linear Regression	~0.65	~0.86
Random Forest	~0.65	~0.85
🔑 Key Insights

Responding agency (NYPD) was the dominant factor influencing resolution time

Complaint type and location semantics mattered more than geography

ZIP code had limited predictive power compared to organizational factors

Increasing model complexity did not significantly improve results due to missing real-world signals (staffing, workload, policy)

🧪 Techniques Demonstrated

Exploratory Data Analysis (EDA)

Target engineering & log transformation

Pipeline-based preprocessing

Linear vs nonlinear model comparison

Feature importance interpretation

Real-world ML reasoning beyond metrics

🛠 Tools & Libraries

Python

pandas, NumPy

scikit-learn

matplotlib

Google Colab

📌 Key Takeaway

Machine learning models often explain system behavior as much as they predict outcomes.
In this case, organizational structure outweighed geographic factors in determining service response time.

🚀 How to Run

Open the notebook in Google Colab

Upload the CSV dataset

Run cells top to bottom

📄 Author

Krish
Computer Science | Machine Learning | Cloud
Building real-world ML systems with practical understanding
