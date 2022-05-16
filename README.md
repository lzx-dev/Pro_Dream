# Pro_Dream

## Intro
A project to help community college students transfer to well-known universities. Based on data from Questionnaire, I did Random Forest and Support Vector Classification models. The main goal here is to achive higher prediction accuracy and interpret feature importance.

## Datasets

### Pro_Dream Questionaire data: 

| Attribute | DataType | Detail |
|--------|--------|--------|
| `Act_commu_ser_num` | Numeric | how many time of community serving the applicant had done|
| `Hours_commu_ser` | Numeric | how many hours of community serving the applicant had done|
| `Chall_rate` | Categorical | chall_rate of applicant |
| `Sex` | Categorical | the gender of applicant |
| `House_income` | Categorical | house income level of applicant |
| `State` | Categorical | which state the applicant live in |
| `Major` | Categorical | which major the applicant applied for |
| `Declare_transfer_major_dummy` | Categorical | whether the applicant had declaed his or her transfer major|
| `Credits_num` | Numeric | how many credits the applicant earned |
| `Courses_major_num` | Numeric | how many coureses the applicant had taken in his major |
| `GPA` | Numeric | GPA of applicant |
| `Part_time_dummy` | Categorical | whether the applicant had done a part time job before |
| `Work_hours` | Categorical | how many hours the applicant had worked |
| `Residency` | Categorical | Nationality of applicant |
| `Extra_curr_dummy` | Categorical | whether applicant had extra curriculum |
| `University_enc` | Categorical | the encode of each University |
| `Admission` | Categorical | whether the applicant get admitted|


The dataset contains:
- 348 Unique rows
- 16 attributes selected based on significance of univariate logistic regression


#### Data preprocess


<img width="436" alt="Screen Shot 2022-05-16 at 2 13 10 PM" src="https://user-images.githubusercontent.com/75053989/168656417-166f00c3-500d-48cd-8187-fe8fcfe77770.png">
Little Unbalcned problem here, not no severe, so I did not do oversampling.      <br>                                     
217 rows data with label 1 and 131 rows data with label  0          <br>                          
217/348 = 62.356   This is our naive benchmark.                 <br>
   <br>
   <br>

Missing Value
<img width="338" alt="Screen Shot 2022-05-16 at 2 14 18 PM" src="https://user-images.githubusercontent.com/75053989/168656557-22d69e04-c066-4039-ab9a-cb9f80565d0f.png">
<br>
For attributes that could be zero like Act_commu_ser_num and Hours_commu_ser, I filled na with 0. For attributes that could not be zero like GPA and credits number, I filled na with the mean of corresponding attrtibutes group by the same major. If the applicant has a unique major, then na value is filled with global mean.


## Model and Metrics
I did Random Forest Classifition and Bootstrapping SVC. Both of them are Ensemble Models. Here is a brief introduction.

#### Random Forest
Random forest is a supervised machine learning algorithm that is constructed from decision tree. One random forest algorithm consists of many decision trees. The ‘forest’ generated by the random forest algorithm is trained through bagging or bootstrap aggregating. A forest is difficult to interpret (unlike trees). One piece of information that is still available is feature importance. 

#### Support Vector Classification
<img width="768" alt="Screen Shot 2022-05-16 at 2 31 34 PM" src="https://user-images.githubusercontent.com/75053989/168659042-a8fc8dc9-1fe1-4d78-9ecf-d047571a9d00.png">
<br>
The main objective in SVC is to find the optimal hyperplane to correctly classify between data points of different classes.
For SVM with non-linear kernel functions, it is not possible to interpert feature importance, 
when the SVM is Non-linear the dataset is mapped into a space of higher dimension, which is quite different from the parent dataset and the property is changed here, So I did not do non-lienar SVM in this project.

#### Metrics
I used accuracy and F1 score to evaluated trained model. <br>
<table width="120">
<tbody>
<tr>
<td style="font-weight: 300;" colspan="3" width="120">Confusion&nbsp;Matrix</td>
</tr>
<tr>
<td>&nbsp;</td>
<td style="font-weight: 300;" width="53">Actually&nbsp;Positive&nbsp;(1)</td>
<td style="font-weight: 300;" width="51">Actually&nbsp;Negative&nbsp;(0)</td>
</tr>
<tr>
<td style="font-weight: 300;" width="51">Predicted&nbsp;Positive&nbsp;(1)</td>
<td style="font-weight: 300;" width="53"><b>TP</b></td>
<td style="font-weight: 300;" width="51">FP</td>
</tr>
<tr>
<td style="font-weight: 300;" width="51">Predicted&nbsp;Negative&nbsp;(0)</td>
<td style="font-weight: 300;" width="53">FN</td>
<td style="font-weight: 300;" width="51"><b>TN</b></td>
</tr>
</tbody>
</table
   
Accuracy = (TN + TP)/(TP + TN + FN + FP) <br>
percison = TP/(TP+ FP) <br>
recall = TP/(TP+ FN) <br>
F1 = 2/ (1/percison + 1/recall)<br>
F1 the harmonic mean of Precision and Recall and gives a better measure of the incorrectly classified cases than the Accuracy Metric


## Results

#### Random Forest
Random forest model with default hyperparameters.
<img width="838" alt="Screen Shot 2022-05-16 at 4 55 17 PM" src="https://user-images.githubusercontent.com/75053989/168681043-0c5a2a7a-0d52-4fe7-93f3-dae94ec83d72.png">
<br>
#### Random forest After tunning by grid search
<img width="700" alt="Screen Shot 2022-05-16 at 4 57 53 PM" src="https://user-images.githubusercontent.com/75053989/168681445-1771e412-ec65-4510-b489-41e6566ffb46.png">
<br>
Feature importance
<img width="640" alt="Screen Shot 2022-05-16 at 4 59 17 PM" src="https://user-images.githubusercontent.com/75053989/168681649-dc639e84-7db8-431a-b9c1-e13f5b29f0f9.png">

#### SVC
SVC model with penalty 1.
<br>
<img width="725" alt="Screen Shot 2022-05-16 at 5 03 06 PM" src="https://user-images.githubusercontent.com/75053989/168682164-be3df957-f068-49cd-ad41-fa32d889f690.png">
<br>
#### SVC model with tunned penalty
<img width="826" alt="Screen Shot 2022-05-16 at 5 03 31 PM" src="https://user-images.githubusercontent.com/75053989/168682211-be78edc9-412d-4003-a0bb-7b7932470835.png">
<br>

#### Boostrap 95% confidence Interval
<img width="1010" alt="Screen Shot 2022-05-16 at 5 03 58 PM" src="https://user-images.githubusercontent.com/75053989/168682270-17a0eb70-a988-4dd0-8973-ab0e0f8bfea3.png">
<br>

#### Feature Importance
<img width="792" alt="Screen Shot 2022-05-16 at 5 04 27 PM" src="https://user-images.githubusercontent.com/75053989/168682339-f9c5cea0-a4f3-4951-8e72-ac786cf131b2.png">

## Model comparison







