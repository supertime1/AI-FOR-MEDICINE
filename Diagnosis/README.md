# AI for medical diagnosis

## Week 1: Chest X-Ray Medical Diagonosis with Deep Learning
### 1. Data preparation
  - Visualizaing data
  - Preventing data leakage: no overlapping of patients in training and test dataset
  - Data input pipeline: use different generators (e.g. ImageDataGenerator) for train and test, if normalization is used in this step 
  
### 2. Model Development: How to address Medical Data Challenges
  - Addressing class imbalance: weighted loss or resampling
  - Dataset size: Leveraging pre-trained models using transfer learning + Data augmentation
  - Multi-Task: Sum loss across different labels, often combined with weighted loss to address class imbalance
  
### 3. Evaluation
  - AUC and ROC curves
  - GradCAMs

## Week 2: Evaluation of Diagnostic Models
### 1. Accuracy
### 2. Prevalance
  - Proportion of positive examples
### 3. Sensitivity (Recall) & Specificity
  - Sensitivity = TP/(TP + FN)
  - Specificity = TN/(TN + FP)
### 4. PPV (Precision) and NPV
  - Positive predictive value (PPV) = TP/(TP + FP)
  - Negative predictive value (NPV) = TN/(TN + FN)
### 5. ROC curve and AURCROC (c-statistic)
### 6. Confidence Intervals
  - bootstrap samples and compute sample AUCs from those samples, then calcuate confidence intervals
### 7. PRC
  - Precision - Recall (Sensitivity) Curve (PRC) is used to measure success of prediction when classes are very imbalanced
### 8. F1 Score
  - F1 = 2 * (Precision * Recall)/(Precision + Recall)
### 9. Calibration
  - In calibration we try to improve our model such that the distribution and behavior of the probability predicted is similar to the distribution and behavior of probability observed in training data.
  
