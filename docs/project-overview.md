# Project Overview  
Institutional Analytics Model (HEA-Aligned Structure)

## Scope & Development Note

This project is intentionally scoped as a demonstration of end-to-end data engineering and BI modelling capability rather than a fully productionised institutional system. 

There is significant potential for further expansion, including deeper integration with live student systems, advanced predictive modelling, automated validation pipelines, metadata management layers, and enhanced governance controls.

The primary purpose of this project is to showcase the ability to design, structure, document, and govern an institutional analytics model from ingestion through to reporting. It reflects my capability to think across architecture, transformation, modelling, and BI enablement within a higher education context.

## Purpose

This project was designed to simulate a robust institutional analytics environment aligned with Higher Education Authority (HEA) reporting structures. The objective is to demonstrate how student-level and aggregated enrolment data can be modelled, governed, and analysed to support evidence-based decision-making within a higher education institution.

The model replicates common institutional research use cases such as enrolment tracking, student progression analysis, risk identification, and strategic performance reporting.


## Business Context

Universities increasingly rely on structured data environments to inform decisions around:

- Enrolment planning and forecasting  
- Student success and retention monitoring  
- Faculty-level performance insights  
- Strategic planning and reporting  
- Regulatory and HEA-aligned submissions  

This project reflects those needs by building a clean, star-schema data model that separates dimensions (who, where, when, what) from facts (measures and outcomes).


## Data Sources

The project uses HEA-aligned data structures and a synthetic dataset to ensure GDPR-safe development while maintaining realistic analytical conditions.

Two primary fact tables were modelled:

- **fact_student_term** – Student-level term data  
- **fact_enrolment_hea** – Aggregated enrolment data  

These are supported by shared dimension tables including domicile, faculty, institution, level, time, and student profile.


## Model Design Approach

The model follows established BI architecture principles:

- Star schema design for performance and clarity  
- Conformed dimensions across fact tables  
- Surrogate key generation during transformation  
- Clear grain definition for each fact table  
- Separation of transformation and reporting layers  

The structure is designed to be compatible with modern BI tools such as Power BI and to support semantic modelling and row-level security.


## Analytical Capabilities

The model enables analysis across multiple perspectives, including:

- Enrolment trends by institution, level, and domicile  
- Completion and progression rates  
- Attendance performance tracking  
- Risk score segmentation  
- Socio-economic and demographic breakdowns  

It is structured to support both descriptive reporting and predictive modelling use cases.


## Governance Considerations

Given the sensitivity of student data, the project incorporates:

- Anonymised student identifiers  
- Synthetic datasets for development  
- Clear data dictionary documentation  
- Design readiness for role-based access control  

This reflects the governance expectations typical of institutional research environments.


## Future Enhancements

Planned extensions include:

- Predictive modelling for student retention  
- Automated data refresh pipelines  
- Advanced role-based security implementation  
- Dashboard deployment layer with controlled self-service  


## Summary

This project demonstrates end-to-end capability in designing, documenting, and structuring an institutional analytics model aligned with higher education reporting needs. It combines technical data modelling with governance awareness and sector understanding, reflecting the principles required in a modern Institutional Research and Data Analytics function.

