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
EMR DATA - Electronic medical records 
            * Patients, 
            * Providers, 
            - Departments, 
            - Transactions, 
            - Encounter
NPI DATA
ICD DATA
# Process
Getting data stored in Datalake on monthly basis in Landing Folder.
