# NYC 311 Service Request Analysis Project
This project uses AWS and cloud computing tools such as SageMaker to answer a stakeholder question.  The dataset contains 
information regarding incident tickets, resolution times, and the city/department in which the incident took place.  The project aims to analyze what factors drive high ticket resolution times. 

## Data Source and Provenance
- **Source**: [NYC Open Data 311 Service Requests](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2020-to-Present/erm2-nwe9/)
- **Time period**: Jan 29–Mar 21, 2026 (Q1 2026)
- **Prep**: Instructor-generated random sample of 200k complaints from 15 agencies
- **Files**: 
  - `raw/complaints.csv` (200k rows, main requests table)
  - `raw/agencies.csv` (unique agencies lookup table)
- **S3 paths** (fill after upload):
  - `s3://cmse492-hopki219-nyc311/raw/complaints.csv`
  - `s3://cmse492-hopki219-nyc311/raw/agencies.csv`

## Project Structure

```
aws-nyc311-hopki219/      # Update with your GitHub repo name
├── README.md                 # Data source, S3 paths, assumptions
├── data-dictionary.md        # Column details
├── raw/                      # Local copies of S3 uploads
│   ├── complaints.csv
│   └── agencies.csv
├── sql/                      # Athena queries
├── notes/                    # Observations, decisions
└── reports/                  # Stakeholder outputs
```

## Data Summary
See `data-dictionary.md` for full schema.

**Key relationships**: Join `complaints.agency = agencies.agency`

**Stakeholder questions**:
- Agency directors want a tool that estimates expected resolution time at the moment a complaint is filed, so they can set realistic expectations with residents. What factors drive that time?

## Assumptions and Known Issues
- Empty `closed_date` = open/unresolved requests
- Some `incident_zip` values are 0 or missing
- String dates need parsing in Athena/SQL
