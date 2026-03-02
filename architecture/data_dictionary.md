# Data Dictionary  
Institutional Analytics Model (HEA-Aligned Structure)

This document defines the structure, grain, and business meaning of all tables and fields within the Institutional Analytics Data Model.


## Dimensional Tables



### dim_domicile
**Grain:** One row per domicile category

| Field Name        | Type    | Description |
|-------------------|---------|------------|
| Domicile_Key (PK) | Integer | Surrogate key for domicile |
| Domicile          | String  | Country or region of origin |
| Domicile_Group    | String  | Grouped classification (e.g., EU, Non-EU, Domestic) |



### dim_faculty
**Grain:** One row per faculty

| Field Name        | Type    | Description |
|-------------------|---------|------------|
| Faculty_Key (PK)  | Integer | Surrogate key for faculty |
| Faculty           | String  | Academic faculty name |


### dim_institution
**Grain:** One row per institution

| Field Name             | Type    | Description |
|------------------------|---------|------------|
| Institution_Key (PK)   | Integer | Surrogate key for institution |
| Institution            | String  | Institution name |
| Institution_Type       | String  | Classification (e.g., TU, University, College) |


### dim_level
**Grain:** One row per academic level

| Field Name        | Type    | Description |
|-------------------|---------|------------|
| Level_Key (PK)    | Integer | Surrogate key for academic level |
| Level             | String  | NFQ Level (e.g., Level 6, Level 7, Level 8) |


### dim_student_profile
**Grain:** One row per demographic profile combination

| Field Name                | Type    | Description |
|---------------------------|---------|------------|
| Student_Profile_Key (PK)  | Integer | Surrogate key |
| Age_Band                  | String  | Age classification |
| Gender                    | String  | Gender category |
| Socio_Economic_Group      | String  | Socio-economic classification |


### dim_time
**Grain:** One row per academic year

| Field Name         | Type    | Description |
|--------------------|---------|------------|
| Time_Key (PK)      | Integer | Surrogate key |
| Academic_Year      | String  | Academic year (e.g., 2023/24) |
| Year_Start         | Date    | Start date of academic year |
| Year_End           | Date    | End date of academic year |
| Year_Label         | String  | Reporting-friendly label |


## Fact Tables


### fact_student_term
**Grain:** One row per student per academic term

| Field Name              | Type    | Description |
|-------------------------|---------|------------|
| Student_ID              | Integer | Anonymised unique student identifier |
| Domicile_Key (FK)       | Integer | Links to dim_domicile |
| Faculty_Key (FK)        | Integer | Links to dim_faculty |
| Institution_Key (FK)    | Integer | Links to dim_institution |
| Level_Key (FK)          | Integer | Links to dim_level |
| Student_Profile_Key (FK)| Integer | Links to dim_student_profile |
| Time_Key (FK)           | Integer | Links to dim_time |
| Year_of_Study           | Integer | Year within programme (e.g., 1, 2, 3) |
| Attendance_Rate         | Float   | Percentage attendance for term |
| Completion_Flag         | Boolean | Indicates successful completion |
| Progression_Flag        | Boolean | Indicates progression to next year |
| Entry_Points            | Integer | Points achieved at entry |
| Risk_Score              | Float   | Model-derived student risk indicator |


### fact_enrolment_hea
**Grain:** One row per institution, level, domicile, and academic year

| Field Name              | Type    | Description |
|-------------------------|---------|------------|
| Time_Key (FK)           | Integer | Links to dim_time |
| Domicile_Key (FK)       | Integer | Links to dim_domicile |
| Institution_Key (FK)    | Integer | Links to dim_institution |
| Level_Key (FK)          | Integer | Links to dim_level |
| Enrolments              | Integer | Total student enrolments (aggregated count) |


## Data Governance Notes

- Student_ID is anonymised; no PII is stored.
- Synthetic dataset used for development to ensure GDPR compliance.
- Surrogate keys are generated during transformation layer.
- Fact tables conform to a star schema design.
- Dimensions are shared across fact tables to ensure consistency in reporting.


## Model Design Principles

- Star schema for analytical efficiency
- Clear separation of dimension and fact layers
- Conformed dimensions across multiple fact tables
- Designed for BI semantic modelling and role-based access control
