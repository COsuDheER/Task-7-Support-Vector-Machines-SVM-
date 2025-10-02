# Task-7-Support-Vector-Machines-SVM-

This project demonstrates the application and optimization of Support Vector Machines (SVM) for binary classification using the Breast Cancer Wisconsin (Diagnostic) Dataset. The objective was to build and tune highly accurate models to distinguish between Malignant (Class 1) and Benign (Class 0) tumors.

Objective:
Implement SVMs with both Linear and Radial Basis Function (RBF) kernels.

Visualize decision boundaries in a reduced 2D feature space.

Optimize the non-linear RBF kernel model using cross-validation and Grid Search.

Key Steps Performed

Data Preparation: The raw dataset was loaded, the categorical diagnosis column was mapped to numerical values (M=1, B=0), and the dataset was cleaned by dropping irrelevant columns (id, Unnamed: 32).

Feature Scaling: All 30 features were standardized using StandardScaler. This is critical for SVM performance, as it is highly sensitive to the magnitude of features.

Initial Model Training: SVMs with linear and rbf kernels were trained on the scaled data to establish baseline performance.

Dimensionality Reduction & Visualization (PCA):

Principal Component Analysis (PCA) was applied to reduce the 30 features down to 2 principal components, capturing the maximum variance.

Decision boundaries for both the Linear and RBF SVMs were plotted in this 2D PCA space, clearly showing the models' separation strategies.

Hyperparameter Tuning & Cross-Validation:

GridSearchCV with 5-fold cross-validation (cv=5) was used to exhaustively search for the optimal combination of the RBF kernel hyperparameters:

C (Regularization): Controls the tolerance for misclassification.

gamma (Kernel Coefficient): Defines the influence of individual training examples.

Final Evaluation: The best-tuned model was evaluated on a completely held-out test set, and its performance was visualized using a Confusion Matrix.

Results Summary:

The final, tuned RBF SVM model achieved exceptional generalization performance:

Metric	Cross-Validation Score (Training Estimate)	Test Set Accuracy (Final Performance)
Accuracy	0.9758	0.9561
F1-Score (Malignant/Class 1)	N/A	0.94

Optimal Hyperparameters Found:

C: 100

gamma: 0.01

The final model made only 5 total errors (2 False Positives, 3 False Negatives) on the test set, demonstrating the effectiveness of kernel methods on this highly separable, real-world data.
