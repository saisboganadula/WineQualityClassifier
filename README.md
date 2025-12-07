# WineQualityClassifier

Wine Quality Classification (Assignment 1)

1. Project Description

This project trains and evaluates two machine-learning classifiers for predicting wine quality using the UCI Wine Quality dataset. The workflow includes data inspection, preprocessing, cross-validation, model comparison, imbalance handling, and final performance reporting on an unseen test set.

The implementation follows the assignment steps exactly:
• Dataset inspection, including class distribution
• Train/test split
• Scaling
• Repeated K-Fold Cross-Validation
• Performance comparison between two classifiers
• Handling class imbalance with imbalanced-learn
• Final model evaluation on the test set

⸻

2. Files Included

/main.py                # Main executable script
/utils.py               # Helper functions (loading data, preprocessing, evaluation)
/models.py              # Classifier definitions (e.g., RandomForest, SVM, etc.)
/plots/                 # Optional plots for class distribution, CV performance
/requirements.txt       # Python dependencies
winequality-white.csv   # (If included) or downloaded at runtime
winequality-red.csv     # (If included) or downloaded at runtime

3. How to Run the Code

3.1. Install Dependencies

Python 3.8+ required.

Run:
pip install -r requirements.txt

This installs:
	•	numpy
	•	pandas
	•	scikit-learn
	•	imbalanced-learn
	•	matplotlib (if used)

⸻

3.2. Execute the Project

Run the main script:
python main.py

The script will:
	1.	Load the wine dataset (red or white, depending on your selection in the code).
	2.	Inspect and print class distribution.
	3.	Split data into training and test sets.
	4.	Scale features.
	5.	Train two classifiers using Repeated KFold Cross-Validation.
	6.	Report mean and standard deviation for the chosen metric.
	7.	Select the best classifier.
	8.	Train a final model on the full training set.
	9.	Evaluate the model on the held-out test set.
	10.	Apply oversampling (SMOTE or another method) on the scaled train set.
	11.	Repeat cross-validation and test evaluation with the balanced dataset.

All results are printed to the console.

⸻

4. Configuration

Inside main.py, you may modify:
DATASET = "white"     # choose "white" or "red"
CLASSIFIERS = ["svm", "random_forest"]  # or any two models you implemented
METRIC = "f1_macro"   # recommended metric for imbalanced classification
BALANCING_METHOD = "smote"

5. Outputs

The script prints the following:
	•	Initial class distribution
	•	Cross-validation mean ± std for each classifier
	•	Best-performing classifier
	•	Test performance before and after balancing
	•	Balanced class distribution

If enabled, plots are stored in /plots/.
