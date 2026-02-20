# Institutional Intelligence Platform for Technological Universities

This project demonstrates an end-to-end institutional research and business intelligence environment aligned with the TU sector’s Targeted Enhancement Fund (TEF) vision.

The platform integrates HEA aggregate data with synthetic student microdata to deliver governed, self-service analytics, student success risk modelling, and enrolment forecasting. It showcases modern higher-education data architecture, including a curated star schema, certified semantic model, robust data governance framework, and usage analytics to support evidence-based decision-making.

## Executive Summary

This project demonstrates a modern institutional research and business intelligence environment aligned with the TU sector’s Targeted Enhancement Fund (TEF) vision.

The solution integrates HEA aggregate data with synthetic student microdata to enable:

1. evidence-based decision support

2. governed self-service analytics

3. student success risk modelling

4. enrolment projection and planning

5. access and equity monitoring

6. usage and adoption analytics

The platform is designed to reflect the analytical and governance needs of Irish technological universities.

## Business Context

Higher education institutions require timely, consistent, and governed analytics to support strategic planning, student success, and statutory reporting to bodies such as the HEA.

Common sector challenges include:

1. fragmented reporting environments

2. limited predictive capability

3. inconsistent KPI definitions

4. weak self-service governance

5. insufficient visibility of student risk

This project presents a scalable institutional intelligence architecture to address these challenges.

## Solution Overview

The platform implements an end-to-end analytics pipeline:

1. Data ingestion from HEA aggregates and synthetic student microdata

2. Curated star schema within a lakehouse/warehouse layer

3. Certified semantic model for consistent KPI delivery

4. Power BI applications for executive and operational users

5. Self-service analytics with row-level security and guardrails

6. Advanced analytics for student success and enrolment forecasting

7. Data governance framework including glossary, catalog, and data quality monitoring

8. Usage analytics to track adoption and inform continuous improvement

## Architecture

See: architecture/high-level-architecture.png

The solution follows a layered data architecture:

1. Sources → Ingestion → Landing → Curated Warehouse → Semantic Model → BI Apps & Self-Service

2. Advanced analytics workloads operationalised back into the warehouse

3. Governance and monitoring embedded across the platform

Key design principles:

1. single source of truth

2. governed self-service

3. reproducibility and auditability

4. GDPR-ready design

5. performance and scalability

## Data Model

See: architecture/erd.png

The model follows a conformed star schema design.

Core fact domains

1. FactEnrolmentAgg — HEA institutional aggregates

2. FactStudentTerm — synthetic student microdata for success modelling

3. FactGraduateOutcome — graduate employment outcomes (optional extension)

Key dimensions

1. Institution

2. Time

3. Programme / Faculty

4. Domicile

5. Level

6. Student profile

This structure supports both strategic reporting and advanced analytics use cases.

## Advanced Analytics

The platform includes production-style analytical models.

Student Success Risk Model

Objective: predict likelihood of non-progression.

Features include:

1. entry points

2. attendance proxy

3. mode of study

4. domicile

5. socio-economic group

6. year of study

Models evaluated:

1. Logistic Regression

2. Random Forest

3. Gradient Boosting

Outputs are written back to the warehouse for BI consumption.

## Enrolment Forecasting

Objective: support strategic planning and resource allocation.

Approaches:

1. time-series baseline

2. machine learning regression

Evaluation metrics:

1. MAE

2. RMSE

3. MAPE

## Data Governance Framework

See: governance/

The platform embeds governance by design.

Components

1. Business glossary

2. Data dictionary

3. Metric catalog

4. Data quality rules

5. Access and security matrix

6. GDPR considerations

Key principles

1. standardised KPI definitions

2. measurable data quality

3. role-based access control

4. full process documentation

5. auditability and lineage awareness

## GDPR & Privacy Considerations

This project uses synthetic student data for demonstration purposes.

The architecture is designed to be GDPR-ready through:

1. pseudonymised student keys

2. data minimisation principles

3. role-based access control

4. row-level security

5. usage auditing

6. defined retention approach

No personally identifiable information (PII) is included.

## Monitoring & Adoption

See: monitoring/

The platform tracks:

1. report usage

2. active users

3. adoption trends

4. data quality incidents

5. refresh performance

This supports continuous improvement of the BI environment.

## Tech Stack

Microsoft Fabric / Lakehouse (conceptual)

Power BI

Python (pandas, scikit-learn)

Power Query

DAX

GitHub

## Author

Akash Deep Sinha
Analytics & Growth Lead — Higher Education
MSc Business Analytics

