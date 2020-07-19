# AI for medical diagnosis

## Week 1: Chest X-Ray Medical Diagonosis with Deep Learning
### 1. Data preparation
  - Visualizaing data
  - Preventing data leakage: no overlapping of patients in training and test dataset
  - Data input pipeline：use different generators (e.g. ImageDataGenerator) for train and test, if normalization is used in this step 
  
### 2. Model Development: How to address Medical Data Challenges
  - Addressing class imbalance: weighted loss or resampling
  - Dataset size: Leveraging pre-trained models using transfer learning + Data augmentation
  - Multi-Task: Sum loss across different labels, often combined with weighted loss to address class imbalance
  
### 3. Evaluation
  - AUC and ROC curves
  - GradCAMs

## Week 2: Evaluation of Diagnostic Models
  ###1. Accuracy
  ###2. Prevalance
  ###3. Specificity & Sensitivity
  ###4. PPV and NPV
  ###5. ROC curve and AURCROC (c-statistic)
  ###6. Confidence Intervals
  
