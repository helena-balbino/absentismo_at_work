# 📊 Absenteeism at Work 

This project focuses on predicting employee absenteeism levels using supervised machine learning, with an emphasis on model interpretability, class imbalance handling, and decision-oriented evaluation.

Using the Absenteeism at Work dataset from the UCI Machine Learning Repository, the goal is to classify absence behavior into three categories: No Absence, Moderate Absence, and High Absence, supporting analytical use cases in **human resources and workforce management**.

## Problem Context

Employee absenteeism has direct operational and financial impacts on organizations. From a business perspective, misclassifying high-absence profiles is significantly more costly than occasional overprediction.

This project approaches absenteeism prediction as a cost-sensitive multiclass classification problem, prioritizing recall and balanced performance across classes rather than raw accuracy alone.

## Modeling Strategy

A **Multiclass Logistic Regression** model was selected due to its balance between predictive performance and interpretability, which is critical in HR-related applications.

Key modeling decisions included:

- Explicit handling of class imbalance using **SMOTE**
- Metric-driven evaluation prioritizing **Recall and F1-score**
- Comparative analysis between original and balanced datasets
- Error analysis based on confusion matrices per class

This approach ensures that minority absence patterns are properly captured without sacrificing model transparency.

## Results and Evaluation

The baseline model trained on the original dataset achieved an accuracy of 59.5 percent, with strong performance for the Moderate Absence class but limited sensitivity to minority classes.

After applying SMOTE, overall accuracy increased to 61 percent, accompanied by improved recall and F1-score for underrepresented absence levels:

- No Absence: Recall 0.67, F1-score 0.27
- Moderate Absence: F1-score 0.67
- High Absence: F1-score 0.68

The balanced model demonstrated more consistent behavior across all classes, reducing systematic misclassification of high-risk absence profiles.

## Visual Insights and Interpretation

The repository includes visual diagnostics used to support model selection and evaluation:

![Distribution of Disciplinary Failure](plot_disciplinary_failure.png)

The distribution of disciplinary failure highlights a strong imbalance in employee behavior, with the vast majority of records showing no disciplinary issues.
This asymmetry reflects a common real-world HR scenario, where adverse behaviors are relatively rare but carry disproportionately higher organizational impact.
From a modeling perspective, this imbalance reinforces the need for techniques that prevent minority patterns from being ignored during training, particularly when predicting higher-risk absenteeism profiles.


![Confusion Matrix Comparison](logistic_regression_smote.png)

The confusion matrix of the Logistic Regression model trained with SMOTE reveals a more balanced classification behavior across absence levels compared to the original dataset.

Key observations include:
- Improved recall for high absenteeism profiles, reducing the likelihood of underestimating employees with recurrent absence patterns.
- Controlled misclassification between moderate and high absence classes, indicating that the model captures meaningful behavioral gradients rather than random noise.
- Residual confusion for the lowest absence class, which is acceptable in a cost-sensitive context where false negatives are more critical than false positives.

This behavior aligns with the project’s objective of prioritizing risk detection over raw accuracy, ensuring that higher-impact absence patterns are not systematically overlooked.

Despite its relative simplicity, Logistic Regression provides transparent decision boundaries, allowing insights into how different variables contribute to absenteeism classification.

Combined with balanced training and targeted evaluation metrics, the model delivers actionable signals for human resources analytics, supporting early identification of employees who may require intervention, policy review, or workload adjustment.

The visual diagnostics confirm that model performance must be interpreted through the lens of business cost and behavioral rarity, rather than accuracy alone.
By explicitly addressing class imbalance and focusing on recall-driven evaluation, the project demonstrates how interpretable models can be effectively applied to real organizational decision-making contexts.

## Academic Context and Language Note

This repository includes a complete academic paper written in Portuguese, available in the `paper/` directory. The manuscript was developed as part of a Brazilian undergraduate program, which required submission in Portuguese.

The paper presents the **full case study**, including detailed exploratory analysis, methodological choices, experimental design, and result interpretation. While the manuscript language reflects academic requirements, all modeling decisions, experiments, and conclusions follow industry-standard data science practices.

This README is provided in English to ensure broader accessibility and to summarize the key insights of the project.

## Conclusions

The results demonstrate that even relatively simple and interpretable models can provide actionable insights when supported by appropriate evaluation strategies and class imbalance handling.

The project highlights the importance of aligning model evaluation with business costs, particularly in human-centered analytical domains such as human resources.

## Author

Helena de Souza Balbino  
