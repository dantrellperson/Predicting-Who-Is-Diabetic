![Diabetes Image](assets/images/diabetes-stock-image.png)

# Predicting-Who-Is-Diabetic
Dataset: [Kaggle Pima People Dataset](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)

*Problem Statement:* 
---
My goal for this personal data project was to use binary classification/logistic regression model on a dataset originally from the National Institute of Diabetes and Digestive and Kidney Diseases about the Pima People to predict if patient has diabetes or not.

*Impact*
---

This model will help predict the onset of diabetes in women who are a part of Pima People community.

*Stakeholders*
---
Health care professionals
Hospitals

*Systems used*
---
Jupyter Lab, Python, Supervised Learning: Classification, Logistic Regression, Matplotlib, Yellowbrick, Seaborn, Gradient Descent

## Metrics
---

*Get to know our dataset*
---
**Link to Tableau infographic:** [Pima-Women-Infographic](https://public.tableau.com/app/profile/dantrell.person/viz/Predicting-Diabetes-In-Pima-Women/Predicting-Diabetes-In-Pima-Women)

![Infographic](assets/images/Infographic.png)
---

*Visualize available features*
---
*Available features are 'Pregnancies', 'Glucose', 'BloodPressure', 'SkinThickness', 'Insulin',
       'BMI', 'DiabetesPedigreeFunction', 'Age', & 'Outcome'*
       
Visualize a count of diabetic test results
---
![Diabetic Count](assets/screenshots/only_bmi_and_glucose/who-is-diabetic-countplot.png)
---

Visualize feature importance 
---
![Feature Importance](assets/images/feature-importance.png)
---

Visualize age group frequency
---
![Frequency Count](assets/screenshots/only_bmi_and_glucose/age-frequency.png)
---

Visualize BMI group frequency
---
![Frequency Count](assets/screenshots/only_bmi_and_glucose/BMI-frequency.png)
---

Visualize Glucose group frequency
---
![Frequency Count](assets/screenshots/only_bmi_and_glucose/Glucose-frequency.png)
---

Utilize the Shapiro-Wilk algorithm to assess the normality of the distribution of instances with respect to the feature. A barplot is then drawn showing the relative ranks of each feature.
---
![Feature Ranking](assets/screenshots/only_bmi_and_glucose/feature-ranking.png)
---

*Key Milestones*
---

Trial 1: Only features used were Glucose and BMI, and a learning rate of 0.001

Description: During the first trial of 1,000 iterations with an alpha of 0.001 we see the cost jumping up and down
    - starting at 0.62, and increasing to 1.30 by the 100th iteration, when I J_history is printed out you can see the values fluctuating each iteration
    - if you only view each 100th iteration it will appear as if cost is constantly decreasing, this is not the case, visualizing every 99th value below to illustrate
    - if everything is set correctly cost function should never increase
    
![Bad Cost Function](assets/screenshots/only_bmi_and_glucose/badcost1000iterations.png)

Successes: With this trial I discovered a learning rate of 0.001 can give the false appearance of gradient descent working correctly(decreasing)

Failures: My cost function did not consistently decrease as intended 

Recommendations: Test for different learning rates that cause gradient descent to function as intended

- - - - - - - - - - - - - - -  

**Trial 2:** Only features used were Glucose and BMI, and a learning rate of 0.0001 at 1,000 , 10,000 , and 100,000 iterations

Visualize train data:

![Train Data 2 Features](assets/screenshots/only_bmi_and_glucose/visualizations/glucoseVSbmi.png)

Successes: Adjusting my learning rate caused my cost to consistently decrease , visualized below. The model accuracy achieved with only BMI & Glucose as features is 78.12%

![Cost Function 1,000 iterations](assets/screenshots/only_bmi_and_glucose/cost1000iterations.png)
- During the first trial of 1,000 iterations with an alpha of 0.0001 we see the cost start at 3.50 and consistently decreases to 0.50

![Cost Function 10,000 iterations](assets/screenshots/only_bmi_and_glucose/cost10000iterations.png)
- During the next trial of 10,000 iterations we see the cost start at 3.50 and decreases to 0.50, no change from 1000 iterations

![Cost Function 100,000 iterations](assets/screenshots/only_bmi_and_glucose/cost100000iterations.png)
- During the final trial of 100,000 iterations we see the cost start at 3.50 and decreases to 0.50

Visualize predicted data:

![Train Data 2 Features](assets/screenshots/only_bmi_and_glucose/visualizations/predictglucoseVSbmi.png)


Failures: The lowest cost value achieved at 1,000, 10,000, and 100,000 iterations is 0.50 The object was to achieve a lower cost.

Recommendations: Test working model with 3 features (Chosen features are Glucose, BMI, & Age)


- - - - - - - - - - - - - - - 
Trial 3(adding Age as 3rd feature): Features used were Glucose BMI and Age, and a learning rate of 0.0001 at 1,000 , 10,000 , and 100,000 iterations

Visualize train data:
![Train Data 3 Features](assets/screenshots/bmi_glucose_age/glucoseBmiAge.png)

Successes: A lower cost of 0.48 was achieved. The model accuracy achieved with BMI, Glucose, & Age as features is 75.52%

![Trial 3 Cost Function 1,000 iterations](assets/screenshots/bmi_glucose_age/3featuresCost1000Iterations.png)

- During the first trial of 1,000 iterations we see the cost start at 2.54 and decreases to 0.48

![Trial 3 Cost Function 10,000 iterations](assets/screenshots/bmi_glucose_age/3featuresCost10000Iterations.png)

- During the next trial of 10,000 iterations we see the cost start at 2.44 and decreases to 0.50

![Trial 3 Cost Function 100,000 iterations](assets/screenshots/bmi_glucose_age/3featuresCost100000Iterations.png)

- During the final trial of 100,000 iterations we see the cost start at 2.44 and decreases to 0.50

Visualize predicted data:
![Train Data 3 Features](assets/screenshots/bmi_glucose_age/predictGlucoseBmiAge.png)


Failures: The model accuracy score is lower than Trial 2

Recommendations: Lowest cost at optimal w & b is determined to be 0.48. Adding the additional feature did not improve model accuracy, I recommend testing a new model using insulin as a fourth feature.

- - - - - - - - - - - - - - - 

Trial 4(adding Insulin as 4th feature): Features used were Glucose BMI and Insulin, and a learning rate of 0.0001 at 1,000 , 10,000 , and 100,000 iterations

Successes: While a lower cost was not achieved. The model accuracy achieved with BMI, Glucose, Age & Insulin as features is 78.13%

![Trial 4 Cost Function 1,000 iterations](assets/screenshots/bmi_glucose_age_insulin/3featuresCost1000Iterations.png)

- During the first trial of 1,000 iterations we see the cost start at 2.50 and decreases to 0.50

![Trial 4 Cost Function 10,000 iterations](assets/screenshots/bmi_glucose_age_insulin/4featuresCost10000Iterations.png)

- During the next trial of 10,000 iterations we see the cost start at 2.50 and decreases to 0.50, no difference from 1,000 iterations

![Trial 4Cost Function 100,000 iterations](assets/screenshots/bmi_glucose_age_insulin/4featuresCost100000Iterations.png)

- During the final trial of 100,000 iterations we see the cost start at 2.50 and decreases to 0.50, no difference from 1,000 iterations



Failures: The lowest cost value achieved at 1,000, 10,000, and 100,000 iterations is 0.50.

Recommendations: Lowest cost at optimal w & b is determined to be 0.50, adding an additional feature improved model accuracy from Trial 3. I acheived a model score of 78.13%. I recommend trying one final trial with all features to try and improve accuracy

- - - - - - - - - - - - - - -  
Trial 5(all avaiable variables):

Successes: Using all features available a cost of 0.49 and a model accuracy of 80.21% 

![Cost Function 1,000 iterations](assets/screenshots/all_features/visualizations/allfeatCost1000Iterations.png)

During the first trial of 1,000 iterations we see the cost start at 2.60 and decreases to 0.50

![Cost Function 10,000 iterations](assets/screenshots/all_features/visualizations/allfeatCost10000Iterations.png)

During the next trial of 10,000 iterations we see the cost start at 2.60 and decreases to 0.49.

![Cost Function 100,000 iterations](assets/screenshots/all_features/visualizations/allfeatCost100000Iterations.png)

During the next trial of 100,000 iterations we see the cost start at 2.60 and decreases to 0.49. No change from 10,000 iterations

Failures: The lowest cost value achieved at 1,000, 10,000, and 100,000 iterations is 0.49. Would have hoped it would be lower

Recommendations: Lowest cost at optimal w & b is determined to be 0.49, using all features improved model accuracy from Trial 3. I acheived a model score of 80.21%. I recommend using predicted data from this model.


- - - - - - - - - - - - - - - 

*Tasks*
---

    1. Review data to get an initial understanding.
        - Do basic statistics.
        - visualize how many patients are diabetic vs who aren't diabetic 
        - Visualize patients with a positive diabetes test result(1) and patients with a negative diabetes test result using original BMI vs Glucose
    2. Define Logistic Model
    3. Define Cost Function
    4. Define Gradient Function
    5. Define Gradient Descent Function
    6. Define Prediction Function
    7. Store predicted results in dataframe and export csv
    8. Visualize predicted results.
    9. Load Dataset into SQL database.
    
    
# Recommendations


*The model accuracy achieved with all availables features is **80.21%** after 5 trials I recommend moving forward with data predicted from Trial 5. 


