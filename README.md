![Diabetes Image](assets/images/diabetes-stock-image.png)

# Predicting-Who-Is-Diabetic
Dataset: [Kaggle Pima People Dataset](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)

**Problem Statement:** 
*My goal for this personal data project was to use binary classification/logistic regression model on a dataset originally from the National Institute of Diabetes and Digestive and Kidney Diseases about the Pima People to predict if patient has diabetes or not.*

**Impact**

This model will help predict the onset of diabetes in women who are a part of Pima People community.

**Stakeholders**
Health care professionals
Hospitals

**Scope (systems used)**
Jupyter Lab, Python, Supervised Learning: Classification, Logistic Regression, Matplotlib, Seaborn Gradient Descent

**Metrics(what is being tracked)**
Available features from dataset are: Pregnancies, Blood Pressure, Glucose, BMI, Skin Thickness, Insulin, and Age

After various readings online I hypothesized BMI and Glucose will be the two best features used in conjuction to predict if a patient is diabetic or not.

**Visualize available features**

Visualize a count of diabetic test results

![Diabetic Count](assets/screenshots/only_bmi_and_glucose/who-is-diabetic-countplot.png)

Visualize age group frequency
![Frequency Count](assets/screenshots/only_bmi_and_glucose/age-frequency.png)

Visualize BMI group frequency
![Frequency Count](assets/screenshots/only_bmi_and_glucose/BMI-frequency.png)

Visualize Glucose group frequency
![Frequency Count](assets/screenshots/only_bmi_and_glucose/Glucose-frequency.png)

Utilize the Shapiro-Wilk algorithm to assess the normality of the distribution of instances with respect to the feature. A barplot is then drawn showing the relative ranks of each feature.
![Feature Ranking](assets/screenshots/only_bmi_and_glucose/feature-ranking.png)


**Key Milestones**

Trial 1: Only features used were Glucose and BMI, and a learning rate of 0.001

Description: During the first trial of 1,000 iterations with an alpha of 0.001 we see the cost jumping up and down
    - starting at 0.58, and increasing to 1.30 by the 100th iteration, when I J_history is printed out you can see the values fluctuating each iteration
    - if you only view each 100th iteration it will appear as if cost is constantly decreasing, this is not the case, visualizing every 99th value below to illustrate
    - if everything is set correctly cost function should never increase
    
![Bad Cost Function](assets/screenshots/only_bmi_and_glucose/badcost1000iterations.png)

Successes: With this trial I discovered a learning rate of 0.001 can give the false appearance of gradient descent working correctly(decreasing)

Failures: My cost function did not consistently decrease as intended 

Recommendations: Test for different learning rates that cause gradient descent to function as intended

- - - - - - - - - - - - - - -  

Trial 2: Only features used were Glucose and BMI, and a learning rate of 0.0001 at 1,000 , 10,000 , and 100,000 iterations

Successes: Adjusting my learning rate caused my cost to consistently decrease , visualized below

![Cost Function 1,000 iterations](assets/screenshots/only_bmi_and_glucose/cost1000iterations.png)

Failures: The lowest cost value achieved at 1,000, 10,000, and 100,000 iterations is 0.50 The object was to achieve a lower cost.

![Cost Function 10,000 iterations](assets/screenshots/only_bmi_and_glucose/cost10000iterations.png)

![Cost Function 100,000 iterations](assets/screenshots/only_bmi_and_glucose/cost100000iterations.png)

Visualize predicted data:

![Train Data 2 Features](assets/screenshots/only_bmi_and_glucose/visualizations/predictglucoseVSbmi.png)


Recommendations: Test working model with 3 features (Chosen features are Glucose, BMI, & Prenancies)


- - - - - - - - - - - - - - -  

Trial 3(adding 3rd feature): Features used were Glucose BMI and Pregnancies, and a learning rate of 0.0001 at 1,000 , 10,000 , and 100,000 iterations

Visualize train data:

![Train Data 3 Features](assets/screenshots/bmi_glucose_pregnancies/visualizations/glucoseBmiPreg.png)

Successes: Gained more insight and confidence with my early prediction of glucose and BMI as adding pregnancy as a feature caused the model to perform more poorly

![Cost Function 1,000 iterations](assets/screenshots/bmi_glucose_pregnancies/3featuresCost1000Iterations.png)

Failures: The lowest cost value achieved at 1,000, 10,000, and 100,000 iterations is 0.50. Adding pregnancy as an additional feature caused the model to perform with less accuracy. The model failed to achieve a lower cost.

![Cost Function 10,000 iterations](assets/screenshots/bmi_glucose_pregnancies/visualizations/3featuresCost10000Iterations.png)

![Cost Function 100,000 iterations](assets/screenshots/bmi_glucose_pregnancies/visualizations/3featuresCost100000Iterations.png)


Recommendations: Lowest cost at optimal w & b is determined to be 0.50, adding an additional feature did not improve model accuracy. I acheived a model score of 76.21%. I recommend trying a different variable as a third feature to try and improve accuracy




**Tasks**

    1. Review data to get an initial understanding.
        - Do basic statistics.
        - visualize how many patients are diabetic vs who aren't diabetic 
        - Visualize patients with a postive diabetes test result(1) and patients with a negative diabetes test result using original BMI vs Glucose
    2. Define Logistic Model
    3. Define Cost Function
    4. Defie Gradient Function
    5. Define Gradient Descent Function
    6. Define Prediction Function
    7. Store predicted results in dataframe and export csv
    8. Visualize predicted results.
    
    
**Recommendations**

**In progress**

*The model accuracy achieved with only BMI & Glucose as features is 80.21*


