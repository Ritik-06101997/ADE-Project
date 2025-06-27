# Description

# Health Care Revenue cycle management (RCM)
RCM is the process that hospitals use to manage the financial aspects from time to time, the patient schedules an appointment till the time 
the provider gets paid.
- Process Follows here:
1. Patient visit
2. Services are provided
3. Billings happens
4. claims are reviewed
5. Payments and followups
6. Tracking and improvements
- RCM ensures the hospital can provide quality care while also staying financially healthy.
* As part of RCM we have 2 main aspects
    * Account Receivables
    * Account Payable
 
* 2 objectives of Account Receivables
  - Bring cash
  - Minimize the collection period
As the probability of collecting your full amount decreases with time.

KPIs that are common to measure AR
* AR > 90
* AR in Days

# We need to create pipeline, the result of this pipeline will be fact tables and dimension tables, which will help the reporting team to generate the KPIs.
We are getting data from mainly 2 sources (2 Hospitals a and b). We have

claim files from Insurance companies in the form of flat files.

* EMR DATA - Electronic medical records 
   * Patients, 
   * Providers, 
   * Departments, 
   * Transactions, 
   * Encounter
     
* NPI DATA - National Provider Identifier (Public API)

* ICD DATA - ICD codes are a standardized system used by healthcare providers map diagnosis code and description (API). 
# Process
Getting data stored in Datalake on monthly basis in Landing Folder.
we are following medallion Architecture
 # Landing -> Bronze ->Silver -> Gold

 # EMR (SQL DB)

 # Claims (Flat Files)

 # Codes (Parquest Files)

Bronze - Parquet Format (source of Truth)
Silver - Data Cleaning, enrich, CDM (Common Data Model), SCD Type 2

Data Scientist , ML team, Data Analyst team need this data.

Gold Layer - Aggregation, Facts and Dimension Table
Business user need this.

# Architecture Diagram
![image](https://github.com/user-attachments/assets/432017d0-4695-4fcd-9c51-8bf2ca0f6e59)

# Fact and Dimension table
![image](https://github.com/user-attachments/assets/a7d34c62-6267-4228-8625-c812c0bbf811)

* Dimension table (SCD 2)
  
* For EMR data we use Azure Data Factory for ingestion

* We will need ADLS gen 2 and created folder landing, bronze, silver and gold as part of medallion architecture.
  
* Also we create one separate folder configs ( metadata driven pipelines)

* It will have data like database, data source, tablename, load type(Incremental/Full), watermark, is_active, targetpath
  


