# Assumptions & Development Considerations  
Institutional Analytics Model

This document outlines the key assumptions made during the development of this institutional analytics model.


## Use of Synthetic Data

This project utilises a synthetic dataset to replicate student-level records and HEA-aligned reporting structures. 

Granular student-level datasets containing attendance, progression, risk indicators, and demographic variables are not publicly available due to data protection and privacy constraints. To demonstrate end-to-end data engineering and BI modelling capability, a realistic synthetic dataset was generated that mirrors institutional reporting structures while ensuring GDPR-safe development.

The synthetic data:

- Preserves realistic relationships between dimensions and fact tables  
- Simulates common higher education analytical scenarios  
- Maintains structural alignment with HEA-style aggregated reporting  
- Does not contain any personally identifiable information (PII)

The objective is to showcase architectural, transformation, and modelling capability rather than reproduce confidential institutional data.

## Grain Assumptions

The following grains were assumed:

- **fact_student_term**: One row per student per academic term  
- **fact_enrolment_hea**: One row per institution, level, domicile, and academic year  

These grains were selected to support both micro-level student analysis and macro-level institutional reporting.

## Surrogate Key Strategy

Surrogate keys were generated for all dimension tables during transformation to ensure:

- Stable relationships  
- BI tool compatibility  
- Improved model performance  
- Clear separation between business attributes and join logic  


## Data Scope Assumptions

The model assumes:

- Academic year as the primary time aggregation level  
- Attendance and progression as representative student success indicators  
- Risk score as a derived analytical feature rather than a validated institutional metric  

The model is designed to be extensible should additional attributes or real institutional datasets become available.

## Governance & Compliance

Given the sensitive nature of student data:

- All student identifiers are anonymised  
- No direct PII fields are included  
- The dataset is structured to be compatible with role-based access control and row-level security  

## Development Intent

This project is intentionally scoped as a demonstration of:

- End-to-end data engineering  
- Dimensional modelling  
- Governance-aware design  
- BI semantic modelling  
- Institutional analytics thinking  

Significant additional development could be undertaken in a production setting, including automated validation pipelines, incremental refresh logic, predictive modelling calibration, and enhanced metadata management.
