# Pro_Dream

## Intro
A project to help community college students transfer to well-known universities. Based on data from Questionnaire, I did Random Forest and Support Vector Classification models. The main goal here is to achive higher prediction accuracy and interpret feature importance.

## Datasets

### Pro_Dream Questionaire data: 

| Attribute | DataType | Detail |
|--------|--------|--------|
| `Act_commu_ser_num` | Numeric | how many time the applicant did community serving |
| `Hours_commu_ser` | Numeric | how many hours the applicant did community serving |
| `Chall_rate` | Categorical |  |
| `Sex` | Categorical | the gender of applicant |
| `House_income` | Categorical | house income level of applicant |
| `State` | Categorical | which state the applicant live in |
| `Major` | Categorical | which major the applicant applied for |
| `Declare_transfer_major_dummy` | Categorical |  |
| `Credits_num` | Numeric | how many credits the applicant earned |
| `Courses_major_num` | Numeric |  |
| `GPA` | Numeric | GPA of applicant |
| `Part_time_dummy` | Categorical | whether the applicant had done a part time job before |
| `Work_hours` | Categorical |  |
| `Residency` | Categorical |  |
| `Extra_curr_dummy` | Categorical | xx |
| `University_enc` | Categorical | the encode of each University |
| `Admission` | Categorical | whether the applicant get admitted|


The dataset contains:
- 348 Unique rows
- 16 attributes selected based on significance of univariate logistic regression


