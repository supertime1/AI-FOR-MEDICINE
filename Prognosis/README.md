# AI for Medical Prognosis

## Week 1: Linear Prognostic Models
### 1. Prognostic models in medical practice
  - Afib: for patients with Afib, what is 1-year risk of stroke
  - Liver Disease Mortality: for patients >=12 on liver transplant waiting lists, provides estimate of 3-month mortality for patients
  - Risk of heart disease: For patients 20 or older who do not already have heart disease. what's 10-year risk of heart disease
  
### 2. Prognostic Model Evalution: 

- Concordant paris (CP): actual outcome and risk score agrees
- Risk ties (RT): actual outcome is the same
- Permissible paris (PP): actual outcome and risk score disagrees
- C-index = (CP + 0.5 * RT)/PP


## Week 2: Tree-based Models
### 1. Decision Tree
### 2. Identify Missing Data 
- Missing completely at random: missingness not dependent on anything
- Missing at random: missingness dependent only on available information (e.g. age)
- Missing not at random: missingness dependent on unavailable information (e.g. if the waiting line is long, don’t do BP test)


### 3. Imputation to Handle Missing Data
- Mean imputation
- Regression Imputation

  
## Week 3: Survival Models and Time
### 1. Survival Estimates
- Difference to Risk Model:
  - risk: what is the probability of death in 5 years = Pr
  - survival: what is the probability of survival past 5 years = 1 - Pr
- Survival function: what is the probability of survival past any time t?
  - S(t) = Pr(T>t)
  - S(u) <= S(v) if u >= v
  - S(t) = 1 if t = 0, and S(t) = 0 if t = +infinite
   
### 2. Time to Event Data (Surival data)
- Y is time to event, instead of 0 or 1 in risk model
- Right Censoring: event always after, if any
  - end of study censoringg
  - loss-to-follow-up cens
  - loss-to-follow-up censoring
- Left Censoring: event happened before a cetain time, but don't know when exactly

### 3. Estimate Survival with Censored Data
- Use chain rule of conditional probability: P(A,B,C) = P(A|B,C) x P(B|C) x P(C)
  - S(25) = P(T>=26,T>=25,...,T>=0) = P(T>=26|T>=25) x P(T>=25|T>=24) x ... P(T>=1|T>=0) x P(T>=0) = (1 - Pr(T=25|T>=25))...(1-P(T=0|T>=0))
  - In general, Kaplan Meier Estimate: S(t) = PI(1- d(i)/n(i))

## Week 4: Build a risk model using linear and tree-based models
### 1. Suvival and hazard functions
- Survival to Hazard: what is the probability of survival past any time t -> what's a patient's immediate risk of death if they make it to time t
- Hazard function: lambda(t) = P(T=t | T>=t) = - S'(t)/S(t)
- Cumulative Hazard: sum of lambada(t) x t

### 2. Customizing risk models to individual patients
- Individualized predictions can be made by using a baseline hazard function with a scaling factor (e.g smokings, ages..)
- Cox Proportional Hazards model: lambda(t) = lambda(t0) x exp(WX) -> linear risk models
- Cox Proportional Hazards model gives both Hazard Function and Risk Score 

### 3. Non-Linear risk model with Survival Trees
- Survival trees use decision trees to categorize survival data into different category (accumulative hazard group) based on factors such as smokings, ages, and then calculate the accumulative hazardous function for each category by using Nelson Aalen estimator
- Nelson Aalen estimator: H(t) = sum(d(i)/n(i)), where d(i) = num died at time i, n(i) = num survived to time i (don't included right censoring data)

### 4. Evaluation of Survival Model
- Harrell's C-index: similar to previous defined C-index but with 

