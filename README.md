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

## Model


