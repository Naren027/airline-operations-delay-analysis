# Airline Flight Operations & Delay Analysis

## Business Intelligence & Data Analytics Project

An end-to-end **Power BI Business Intelligence project** analyzing airline flight operations, delays, cancellations, delay severity, airline performance, airport delay concentration, and recorded delay contributors using 2015 flight data.

---

## 📌 Project Overview

Airline operations generate large volumes of operational data, but raw flight records can be difficult to interpret directly.

This project transforms flight-level operational data into a structured analytical model and an interactive **Power BI Executive Overview dashboard** designed to help stakeholders understand:

- Overall flight operations
- Delayed and on-time flights
- Delay rate
- Cancellation volume
- Monthly delay patterns
- Airline delay-rate differences
- Origin airport delayed-flight concentration
- Delay severity
- Recorded delay contributors
- Cancellation reasons

The project follows an end-to-end analytics workflow:

**Business Requirements → Domain Understanding → Data Understanding → Data Preparation → Data Modeling → KPI Development → Dashboard Development → Validation → Business Insights → Recommendations**

---

# 🎯 Business Problem

Airline management and airport operations teams need a consolidated view of flight punctuality, delays, and cancellations.

Raw flight-level records contain valuable operational information, but they are not organized for rapid business analysis.

This project addresses that gap by creating an interactive Executive Overview dashboard that converts historical flight data into decision-ready KPIs and analytical insights.

---

# 🎯 Project Objectives

The project aims to:

1. Measure overall flight operational performance.
2. Analyze flight delay patterns across 2015.
3. Identify airlines with higher delay rates.
4. Identify origin airports with high volumes of delayed flights.
5. Analyze delay severity by duration.
6. Identify the largest recorded contributors to total delay minutes.
7. Analyze cancellation reasons.
8. Provide an interactive Power BI dashboard for business users.
9. Translate analytical findings into business recommendations.

---

# 📊 Dataset

## Dataset

**Airline Flight Delays**

## Source

**Maven Analytics Data Playground**

The dataset is based on U.S. Department of Transportation Air Travel Consumer Report data for **2015**.

The project uses three related tables:

- `flights`
- `airlines`
- `airports`

### Flights

Central fact table containing flight-level operational records.

### Airlines

Reference table containing airline information and IATA codes.

### Airports

Reference table containing airport information, including airport codes, names, cities, states, and countries.

---

# 🗓️ Analysis Period

**Calendar Year: 2015**

The project is limited to the available 2015 dataset.

Therefore, the findings represent historical observations and should not be interpreted as current airline performance.

---

# 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| Microsoft Power BI | Dashboard development and visualization |
| Power Query | Data preparation and transformation |
| DAX | KPI and analytical measure development |
| Data Modeling | Relationships between fact and reference tables |
| CSV | Source data format |
| GitHub | Project documentation and portfolio hosting |

---

# 🗂️ Data Model

The project uses a fact-and-dimension style analytical model.


                 ┌────────────────┐
                 │    Airlines    │
                 │                │
                 │ IATA_CODE      │
                 │ AIRLINE        │
                 └───────┬────────┘
                         │
                         │ AIRLINE
                         │
                  ┌──────▼───────┐
                  │   Flights    │
                  │              │
                  │ Flight Data  │
                  │ Delays       │
                  │ Cancellations│
                  │ Times        │
                  └──────┬───────┘
                         │
                         │ Airport Codes
                         │
                 ┌───────▼────────┐
                 │    Airports     │
                 │                 │
                 │ IATA_CODE       │
                 │ AIRPORT         │
                 │ CITY            │
                 │ STATE           │
                 └─────────────────┘

The flights table acts as the central fact table.

The airlines and airports tables provide descriptive reference information.

The airport table is used for both:

Origin Airport
Destination Airport
📈 Final Power BI Dashboard

The final Power BI deliverable contains one Executive Overview page.

The dashboard was intentionally kept focused and decision-oriented rather than adding unnecessary visuals.

Dashboard Preview

📊 Executive KPIs

The dashboard contains six KPI cards:

Total Flights
Delayed Flights
On-Time Flights
Delay Rate %
Cancelled Flights
Avg Duration (min)
Validated Dashboard Results
KPI	Result
Total Flights	5,819,079
Delayed Flights	2,086,896
On-Time Flights	3,627,112
Cancelled Flights	89,884
Delay Rate	35.9%
Average Flight Duration	137.01 minutes
📊 Analytical Visuals

The Executive Overview contains seven analytical visuals.

1. Flight Volume & Delays by Month

Shows how total flight volume and delayed-flight volume vary across the months of 2015.

2. Top 5 Airlines by Delay Rate

Identifies the five airlines with the highest delay rates in the selected context.

3. Flight Delay Distribution by Duration

Shows the distribution of delayed flights across different delay-duration categories.

4. Monthly Flight Delay Rate

Shows how the overall flight delay rate changes throughout the year.

5. Top 5 Origin Airports by Delayed Flights

Identifies origin airports with the highest volumes of delayed flights.

This is a volume-based ranking and should not be interpreted as a ranking of the "worst" airports.

6. Total Delay Minutes by Cause

Shows the recorded delay contributors responsible for the largest amounts of total delay minutes.

7. Flight Cancellations by Reason

Shows the distribution of cancelled flights across recorded cancellation reasons.

🎛️ Dashboard Interactivity

The dashboard contains two primary slicers.

Month

Allows users to filter dashboard results by month.

Airline

Allows users to filter dashboard results by airline.

The dashboard also supports standard Power BI visual interactions and cross-filtering.

🔎 Key Business Insights
1. Overall Flight Operations

The dataset contains:

5.82M total flights
2.09M delayed flights
3.63M on-time flights
89.9K cancelled flights

The implemented dashboard delay rate is 35.9%.

This establishes flight delays as a significant operational issue within the analyzed dataset.

2. Monthly Delay Variation

Flight volume remains relatively stable throughout the year, while delay rates vary noticeably between months.

February and June are among the higher-delay-rate periods, while September and October are among the lower-delay-rate periods.

These observations identify temporal patterns but do not independently establish their underlying causes.

3. Airline Delay-Rate Differences

The Top 5 airlines by delay rate are:

NK
F9
HA
VX
US

The leading airlines in the selected group reach approximately 40–48% delay rates.

These results identify areas for further investigation rather than proving that a specific operational factor caused the differences.

4. Delayed-Flight Concentration at Major Airports

The Top 5 origin airports by delayed-flight volume are:

ATL
ORD
DFW
DEN
LAX

ATL and ORD each exceed approximately 100,000 delayed flights.

Because this is a volume-based measure, airports with more flight activity naturally have more opportunities to accumulate delayed flights.

Normalized delay rates should therefore be used for direct airport performance benchmarking.

5. Delay Severity

The distribution of delayed flights is approximately:

Delay Duration	Share of Delayed Flights
1–15 minutes	50.96%
16–30 minutes	18.73%
31–60 minutes	15.03%
61–120 minutes	9.81%
120+ minutes	~5.47%

The largest individual category is the 1–15 minute range.

However, approximately half of delayed flights fall into categories beyond 15 minutes.

Longer delays can have greater operational consequences because they may affect aircraft rotations, crew schedules, connecting passengers, and subsequent flights.

6. Recorded Delay Contributors

The largest contributors to total recorded delay minutes are:

Late Aircraft
Air Carrier
National Air System
Weather
Security

The project uses the term recorded contributor because the dashboard is descriptive and does not establish causal relationships.

7. Cancellation Reasons

Weather accounts for approximately 54.35% of cancellations.

Other major recorded cancellation reasons include:

Cancellation Reason	Share
Weather	54.35%
Airline / Carrier	28.11%
National Air System	17.52%
Security	Smaller share

This indicates that cancellation management and delay management should be treated as related but distinct operational challenges.

💡 Business Recommendations
1. Focus on Late-Aircraft Operations

Late Aircraft is the largest recorded contributor to total delay minutes.

Airline operations teams should investigate:

Aircraft turnaround time
Aircraft rotation planning
Schedule buffers
Previous-leg delays
Delay propagation
2. Investigate Airline Performance

Airlines with higher delay rates should be investigated using additional operational context.

Future analysis should compare:

Delay rate
Delay severity
Cancellation rate
Delay contributors
Airport mix
Route mix
3. Prioritize High-Volume Airports

ATL, ORD, DFW, DEN, and LAX should be considered investigation priorities because they contain high volumes of delayed flights.

However, airport performance should ultimately be evaluated using normalized metrics rather than raw delayed-flight counts alone.

4. Monitor Delay Severity

Operational teams should distinguish between:

Minor delays
Moderate delays
Severe delays

Particular attention should be given to the 61–120 minute and 120+ minute categories because of their potential operational impact.

5. Strengthen Weather Contingency Planning

Since weather represents the majority of recorded cancellations, airlines and airports can improve disruption resilience through:

Weather forecasting
Proactive passenger communication
Rebooking capacity
Crew contingency planning
Aircraft contingency planning
Disruption-response procedures
6. Monitor Air-System Constraints

National Air System delays represent a major contributor to total delay minutes.

Further investigation should examine:

Airport congestion
Airspace constraints
Time-of-day patterns
Recurring congestion periods
Route-level system constraints
⚠️ Project Limitations
Historical Dataset

The dataset covers 2015 and does not represent current airline operations.

Descriptive Analysis

The dashboard identifies patterns and concentrations but does not prove causation.

Volume Bias

Raw delayed-flight counts are influenced by the number of flights operated.

Limited Business Context

The dataset does not contain:

Revenue
Operating cost
Passenger-level information
Compensation
Customer satisfaction

Therefore, financial and customer-impact estimates are outside the scope of this project.

No Predictive Modeling

The current project focuses on descriptive and diagnostic analytics.

Predictive delay forecasting is considered a future extension.

🚀 Future Enhancements

The following areas can be implemented in future versions of the project.

Airline Performance Analysis

A dedicated analysis page could provide normalized airline benchmarking using:

Delay rate
Cancellation rate
Delay severity
Delay contributors
Airport & Route Analysis

Future analysis could include:

Airport delay rate
Route performance
Origin-destination relationships
Airport congestion patterns
Delay Cause Deep-Dive

A dedicated analytical page could further classify:

Controllable delays
Non-controllable delays
Delay severity
Delay propagation
Additional Time Analysis

Future versions could include:

Day-of-week analysis
Time-of-day analysis
Seasonal analysis
Predictive Analytics

If additional historical data becomes available, the project could be extended into:

Delay prediction
Cancellation prediction
Risk scoring
Forecasting
📁 Project Structure
airline-operations-delay-analysis/
│
├── README.md
│
├── Dashboard/
│   └── Airline_Operations_Dashboard.png
│
├── Documentation/
│   ├── Airline_Flight_Operations_Report.pdf
│   ├── Business_Requirement_Document.pdf
│   ├── Dashboard_Requirements_FINAL.pdf
│   ├── Data_Dictionary.pdf
│   ├── Domain_Document.pdf
│   ├── ER_Diagram.pdf
│   ├── Insights_and_Recommendations.pdf
│   └── KPI_Document.pdf
│
└── Data/
    └── README.md

The Power BI .pbix file is not included in the GitHub repository because the final file is approximately 131 MB, exceeding GitHub's standard individual file upload limit. The repository therefore includes the final dashboard preview and complete project documentation.

📚 Project Documentation

The complete project documentation is available in the Documentation folder.

Document	Purpose
Business Requirement Document	Defines the business problem, objectives, scope, stakeholders, and business questions
Domain Document	Explains the airline operations domain and terminology
Data Dictionary	Documents tables, columns, data types, keys, and business meanings
ER Diagram	Documents relationships between the project tables
KPI Document	Defines KPI calculations, business meanings, and measurement logic
Dashboard Requirements	Defines the final dashboard structure, visuals, filters, and acceptance criteria
Insights & Recommendations	Documents business findings and recommended actions
Final Project Report	Provides the complete end-to-end project case study
📌 Project Deliverables
Deliverable	Status
Business Requirement Document	✅ Completed
Domain Document	✅ Completed
Data Dictionary	✅ Completed
ER Diagram	✅ Completed
KPI Document	✅ Completed
Dashboard Requirements	✅ Completed
Power BI Dashboard	✅ Completed
Insights & Recommendations	✅ Completed
Final Project Report	✅ Completed
GitHub Documentation	✅ Completed
🧠 Skills Demonstrated

This project demonstrates practical experience with:

Business Requirement Analysis
Business Process Understanding
Data Understanding
Data Cleaning
Data Transformation
Data Modeling
Relational Database Concepts
Fact and Dimension Modeling
Power Query
DAX
KPI Development
Power BI
Dashboard Development
Data Visualization
Interactive Filtering
Business Analysis
Data Storytelling
Insight Generation
Business Recommendations
Analytical Documentation
GitHub Portfolio Development
🔄 End-to-End Project Workflow
Business Problem
       ↓
Business Requirements
       ↓
Domain Understanding
       ↓
Data Understanding
       ↓
Data Dictionary
       ↓
ER / Data Model
       ↓
Data Preparation
       ↓
DAX Measures & KPIs
       ↓
Power BI Dashboard
       ↓
Validation
       ↓
Business Insights
       ↓
Recommendations
       ↓
Final Report
       ↓
GitHub Portfolio
🏁 Conclusion

The Airline Flight Operations & Delay Analysis project demonstrates an end-to-end Business Intelligence workflow.

The project starts with a business problem, documents the domain and requirements, prepares and models the underlying data, develops validated KPIs, builds an interactive Power BI dashboard, identifies operational patterns, and translates those findings into business recommendations.

The final dashboard shows that flight delays represent a significant operational challenge within the analyzed 2015 dataset.

Late Aircraft, Air Carrier, and National Air System are the largest recorded contributors to total delay minutes, while Weather is the dominant recorded cancellation reason.

The project is intentionally positioned as a descriptive and diagnostic Business Intelligence case study, rather than a predictive or causal model.

📎 Dataset Source

Dataset: Airline Flight Delays
Platform: Maven Analytics Data Playground
Analysis Period: 2015
Original Data Source: U.S. Department of Transportation Air Travel Consumer Report

👤 Project Information

Project: Airline Flight Operations & Delay Analysis

Domain: Airline Operations / Transportation

Analysis Type: Business Intelligence & Descriptive Analytics

Primary Tool: Microsoft Power BI

Dataset Period: 2015

Project Status: Completed
