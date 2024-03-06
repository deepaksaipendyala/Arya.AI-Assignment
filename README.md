# Arya.AI-Assignment Summary
This repository contains the implementation and results of various machine learning models on a dataset devoid of null values and comprised entirely of numeric features. Initial analysis revealed substantial skewness across most features, which persisted despite attempts at log transformation. Further investigation using boxplots identified the presence of numerous outliers in many features.

Given these findings, PCA was favored over traditional feature selection methods like ANOVA F-test due to its effectiveness in capturing inherent variance and complex feature interactions, as well as its ability to convert correlated features into linearly uncorrelated principal components. This approach not only facilitated dimensionality reduction, thus holding overfitting, but also improved the efficiency of model training, which was reflected in the enhanced performance metrics post-PCA.

StandardScaler was used for feature scaling, and PCA was applied to capture 95% of the dataset's variance, resulting in 48 principal components. A decision was made to proceed with the 30 most significant components, as this number was sufficient to encompass a substantial proportion of variance and was considered beneficial for subsequent analytical tasks.

Hyperparameter tuning was done using GridSearchCV in conjunction with StratifiedKFold to identify the optimal parameters for a Random Forest classifier. The best parameters extracted from this process were then utilized to train the final model on the dimensionality-reduced and scaled dataset.

Model explainability was addressed through SHAP analysis on both validation and test data, clarifying the impact of principal components on the model's predictions, with PC1 and PC2 being the most influential.

This repository provides two output files: one containing only the predicted values and the other combining these predictions with the corresponding test features.


