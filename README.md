# Analysis-of-Stroke-Patients

**Author**: Nicholas Orgel

![stroke1](https://user-images.githubusercontent.com/107963606/202544219-46699fd1-188f-49f9-8074-c333bf382dd0.jpg)

---
**Description:**
This dataset is a compilation of patients of various ages and different variables and how likely they are or have had a stroke.

### Problem: Find the best model and methods on how to predict patient stroke likelyhood based on conditions given including age, work status, residency, body mass index (bmi), average level of glucose, smoking habits, marital status, and history of hypertension.
---
<img width="382" alt="image" src="https://user-images.githubusercontent.com/107963606/202542099-20e22b9b-2da4-482d-888f-1e5ca08dc2cf.png">

---
#**Exploratory Data Visualizations**

![correlation heatmap](https://user-images.githubusercontent.com/107963606/203833637-8d5c64a2-21cd-485b-a627-3f434f525b87.png)

Pictured above is a correlation heatmap of all of the features relevant to the prediction of a stroke. The darker the shade of green, the better a correlation is.

- The features that best align with others or the stroke probabilities itself are:
  - Age
  - Ever Married
  - BMI
  - Smoking Status
  - Heart Disease

---

##Correlation Visualizations

![age marriage correlation](https://user-images.githubusercontent.com/107963606/203834650-0764d74b-45ec-49a8-adcd-df5de158cb5f.png)

- There is a moderate correlation between a patient's age and their marital status. In the lineplot above, it calculates the mean or average of the percentage of patients in the dataset based on their age and marriage status.
- Many patients start to get married in their 20's and 30's.
- Nearly half of the patients in the data that are present are married by the time they reach 30 years of age.
- By age 65, the average percentage of patients who are married is close to 100%, but there is soon a slight decrease at age 70.
  - The decrease goes to a percentage around 85% where one can assume that people in this age group no longer wish to be married or have never been married at all.

---
![download](https://user-images.githubusercontent.com/107963606/203835803-78e67abb-b9e9-43f5-ad87-83db3d04680d.png)

The next lineplot shows the correlation between a patients age and their probability of having a stroke.

- As the older a person gets their likelyhood of having a stroke increases.
  - However, by early 60 years of age, the average percentage drops to almost 0%, the assumption here being that by this time patients are more considerate about their overall health for a small time.
- The most significant age where someone is likely to have a stroke is around age 80 with a 25% chance probability.
- While the lineplot gives the interpretation that infants are at high risk of a stroke, this is only from 13 values that are present in the age column that are less than 20 years of age. It has no significant impact on the risk at early developmental stages.

---
![download](https://user-images.githubusercontent.com/107963606/203836561-1b3424ec-a440-4797-9658-816e8d2bc983.png)

The scatterplot above shows that when comparing patient's age and bmi and the likelyhood of having a stroke; there seems to be no major significance as only a small minority of patients the age groups of 60-80 have had a stroke.

---
![download](https://user-images.githubusercontent.com/107963606/203836639-778b6573-b6b1-49f3-af87-4927931ff6a1.png)

There seems to be no major impact that heart disease has on a patients' age and their likelyhood of having a stroke.

---
##**Preprocessing and Model Tuning

When trying to best predict the likelyhood of patients having a stroke, various models can be used to choose which will be the most accurate and whether it will be useful for production for the business.

When models are chosen, the things to focus on should be the True Positves and True Negatives in a Confusion Matrix Display which is in the shape of a 2x2 grid. These numbers are displayed with True Postive in the Top Left and True Positive in the Bottom Right. The other numbers on display are False Postive (Top Right) where the model in this instance would predict a patient has had a stroke, when in actuality they have not. The inverse of this is called False Negative which is the number in the Bottom Left.

---
- Models are also chosen by something called a classification report where the model shows how it best fits the current problem it is presented with.
- Recall is especially import in this case, where it shows a percentage of the model predicting the correct number of true postive and true negative numbers out of everything that it is given. The higher the recall, the better the model is.

On first inspection, two models stood out because they had the **lowest amount of False Postives and False Negatives** and had the **highest recall score**

**Logistic Regression**


![download](https://user-images.githubusercontent.com/107963606/203837850-8e9812ba-6589-4e7c-a168-10af054561da.png)


<img width="314" alt="image" src="https://user-images.githubusercontent.com/107963606/203838452-3aa6a2ea-0048-4ba3-bed9-0f84a18e0c1f.png">

**And ADABoost**

![download](https://user-images.githubusercontent.com/107963606/203838523-4c0c8de5-0b25-4036-a143-1d80205a0d52.png)

<img width="314" alt="image" src="https://user-images.githubusercontent.com/107963606/203838561-658ffa68-23dc-40a7-8f2a-451161ee6b1d.png">

- These models can later be adjusted or "tuned" to be even more accurate. Once this is done, a decision is made on the best model and whether it is viable for production.

##**Best Tuned Model For Recommendation**

Both the Logistic Regression and AdaBoost models were "tuned" with the goal to increase the accuracy or 'accuracy_score'.

The model that ultimately performed the best in this case was a **Tuned ADABoost Model** because it was the most accurate and lead to the lowest number of False Postives and False Negatives which would mean a misdiagnosis for the patient, and less chance of error. This would be the best model to recommend to a business such as a hospital to better guide patients on how to maintain a healthy lifestyle as they get older. Concerns that doctors could use to further accentuate the concern for patients and make them more aware are how their heart condition, BMI, and other factors contribute to the possibility of having a stroke.


