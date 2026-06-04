💧 Water Quality Prediction — Potability Classification
A machine learning project that predicts whether water is safe for drinking based on chemical composition. Built end-to-end — from raw data cleaning to model comparison and evaluation.

📌 Problem Statement
Access to safe drinking water is a global health concern. Manually testing water quality is time-consuming and expensive. This project builds a classification model that predicts water potability based on measurable chemical properties — helping automate the safety assessment process.

📂 Dataset

Source: Public dataset (water_potability.csv)
Records: 3,276 rows
Target: Potability — 0 (Not Safe) / 1 (Safe)

FeatureDescriptionpHAcid-base balance of waterHardnessCalcium and magnesium contentSolidsTotal dissolved solidsChloraminesChlorine and ammonia levelsSulfateDissolved sulfate amountConductivityElectrical conductivityOrganic CarbonCarbon from organic compoundsTrihalomethanesChemical byproducts of disinfectionTurbidityClarity of water

🔧 Tech Stack

Python
Pandas, NumPy
Matplotlib, Seaborn
Scikit-learn


📊 Project Workflow
1. Basic EDA

Checked shape, columns, data types, statistical summary
Analyzed class distribution — dataset is imbalanced (61% not potable / 39% potable)

2. Missing Data Handling

Identified null values in ph, Sulfate, and Trihalomethanes
Analyzed mean and median distributions for each null column
Filled missing values with column mean

3. Duplicate Data

Checked and removed duplicate records

4. Outlier Detection & Removal

Box plots for all features individually
Calculated IQR, lower and upper bounds
Removed 610 outlier rows (3,276 → 2,666 records)

5. Feature Selection

Correlation heatmap across all 10 features
All features showed near-zero correlation with Potability — confirming the classification challenge

6. Model Building

Split data: 80% train / 20% test
Applied StandardScaler for feature scaling
Trained and compared two models:

Logistic Regression
Decision Tree Classifier (max_depth=5)



7. Model Evaluation
ModelTrain AccuracyTest AccuracyLogistic Regression~68%~66%Decision TreeHigherHigher
Evaluated using confusion matrix, accuracy score, and classification report. Tested on new unseen data samples.

📈 Key Findings

All features have near-zero correlation with Potability — this is a genuinely hard classification problem
Decision Tree outperformed Logistic Regression due to its ability to capture non-linear patterns
Low overall accuracy reflects the real-world difficulty of predicting water safety from chemical properties alone
