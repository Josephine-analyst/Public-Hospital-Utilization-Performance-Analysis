# PUBLIC HOSPITAL UTILIZATION & PERFORMANCE ANALYSIS

## PROJECT DESCRIPTION
   Interactive Power BI dashboard analyzing ~4,853 admissions, 243 mortalities (5% rate), and KPIs across departments, states, gender, and 20+ public hospitals in Nigeria. Built for resource allocation, capacity planning, and outcome monitoring in the public health sector.
   
   ![Main Dashboard Overview](Screenshot%20(116).png)](Screenshot%20(116).png

## 🎯 Business problem & Objectives
   - Track seasonal patient admissions and discharges
   - Identify high-utilization departments (e.g., Pediatrics, Surgery) and states (e.g., Kaduna)
   - Monitor mortality rates by department, gender, and hospital
   - Highlight capacity gaps and recommend staffing/training priorities
 
## 🛠️ Tools & Technologies
    - **Power BI Desktop** (Visualizations & Slicers)
    - **Power Query** (ETL/cleaning)
    - **Excel** (.xlsx source data)
    - **DAX Measures** (16+ Custom KPIs for dynamic KPIs)
    
## KEY DAX MEASURES AND CALCULATED TABLE
   ```dax
// Date Table
'DATE TABLE' = CALENDARAUTO()
   *Extracting the month and day from the Date Table

      Month = FORMAT('DATE TABLE'[Date], "MMMM")
      Day = FORMAT('DATE TABLE'[Date], "DDDD")

// Sample Measures
    
   TOTAL ADMISSIONS = SUM('Public_Hospital_Utilization_Dat'[Patients Admitted])

   TOTAL DISCHARGES = SUM(Public_Hospital_Utilization_Dat[Patients Discharged])

   TOTAL MORTALITY = SUM('Public_Hospital_Utilization_Dat'[Mortality Count])

   MORTALITY RATE% = ('DATE TABLE'[TOTAL MORTALITY]/'DATE TABLE'[TOTAL ADMISSIONS]*100)

   DISCHARGE RATE = DIVIDE(SUM('Public_Hospital_Utilization_Dat'[Patients Discharged]),[TOTAL ADMISSIONS],0)

   AVERAGE LENGTH OF STAY = AVERAGE(Public_Hospital_Utilization_Dat[Avg Stay (Days)])

   NET CHANGE IN PATIENTS = [TOTAL ADMISSIONS]-[TOTAL DISCHARGES]

## 📈 VISUALIZATION
     
   - **Patient Admission Counts by Month:** 
       This Line Chart tracks monthly patient admission counts across 2022, starting low in January(~300), peaking sharply in July(~480),
       with subsequent spikes and dips(e.g., ~450 in late months), reflecting seasonal or event-driven surges in hospital visits.

 ![Overall Admissions & Mortalities Overview](Screenshot%20(105).png)](Screenshot%20(105).png
  
   - **Mortality Count by Department:**
       The horizontal bar chart ranks departments by mortality count: Outpatients leads at 47, followed by Pediatrics(46), Internal Medicine (41),
       Maternity (40), Emergency (35) and Surgery (34), pinpointing high-risk areas.

<img width="1366" height="768" alt="Screenshot (106)" src="https://github.com/user-attachments/assets/abe733b6-4081-4d37-9ffb-d6da0607cc8c" />

   - **Patient Admission by Department:**
       The Tree Map Chart shows patient admissions by department: Pediatrics (~47), Surgery (~24), Maternity (~23), Internal Medicine (~19),
       Outpatient (~18), totalling around 243 visits, with Pediatrics dominating volume.

<img width="1366" height="768" alt="Screenshot (107)" src="https://github.com/user-attachments/assets/cae7f9a6-b106-4e92-afd6-41b9e4f6f989" />

   - **Patient Admissions by Gender:**
       The Donut Chart divides admissions nearly evenly: Female(~50%), Male (~50%), providing a balanced gender distribution snapshot.

 <img width="1366" height="768" alt="Screenshot (108)" src="https://github.com/user-attachments/assets/7e6a0321-e0c8-406a-ad64-1c5b5cbd1eed" />


   - **Admissions by State:**
       The Area Chart displays declining admissions: high in Kaduna(~850), dropping sharply to Lagos(~450) and others (Oyo, Ogun, Delta ~400-500),
       overlaid with gender splits.

<img width="1366" height="768" alt="Screenshot (110)" src="https://github.com/user-attachments/assets/eb5ecc3f-7340-4fd2-8b18-6e4bca7fd03f" />

 
   - **Patient Mortality Count by State:**
       The Horizontal Bar Chart ranks top states by patient mortality count: Kaduna leads(~32 deaths), followed by  Oyo, Delta and others(~20-25), 
       highlighting geographic disparities in outcomes possibly tied to population, facilties or health events.

<img width="1366" height="768" alt="Screenshot (111)" src="https://github.com/user-attachments/assets/a4336025-1b1f-4e69-b90f-d4847612a79f" />

 
   - **Top 5 Mortality Count by Hospital:**
       Bars detail top hospitals: 17,15,15,15 and 14 deaths, for comparing facility performance.

 <img width="1366" height="768" alt="Screenshot (111)" src="https://github.com/user-attachments/assets/cfeca424-30d3-4126-9c4f-18654bdda7f3" />

 
   - **Patient Admission Count by Service**
       The Pie Chart distributes 772 total admissions by service: Delivery(25%,~193), Surgery(18%,~139), Lab Test(18%,~139), Consultancy(~17%)
       and others, emphasizing service loads.

<img width="1366" height="768" alt="Screenshot (112)" src="https://github.com/user-attachments/assets/adb62619-3484-4ea9-a300-c6865ba7c9e0" />

 
     - **Mortality Count by Month:**
         Line Chart depict flunctuating mortality counts(peaks ~30),highlighting seasonal outcome patterns.

 <img width="1366" height="768" alt="Screenshot (114)" src="https://github.com/user-attachments/assets/5bfae3ce-1ed4-4650-ba7e-6a18f81f9476" />

 
     - **Mortality Count by Gender:**
         The Pie Chart shows male mortality dominant(~74%,119 cases) vs female (~26), indicating gender disparities in outcomes.

<img width="1366" height="768" alt="Screenshot (115)" src="https://github.com/user-attachments/assets/2115daee-ccc4-4ea3-b1d7-54be4c2236ec" />

 

## INTERACTIVE SLICERS
   - Month
   - Department
   - Gender
   - Hospital

## 🔍 KEY BUSINESS INSIGHTS & RECOMMENDATIONS
   1. High Demand Departments — Pediatrics & Surgery dominate admissions → prioritize staffing and training here.
   2. Mortality Hotspots — Outpatients & Pediatrics show elevated rates → recommend clinical audits and protocol reviews.
   3. Gender Disparity — Males have ~74% of mortalities → investigate underlying factors (e.g., access, delayed care).
   4. Regional Focus — Kaduna has highest volume → allocate resources for capacity expansion.
 
## How to Use / Explore This Project

   1. Clone or download the repo
   2. Open PUBLIC HOSPITAL UTILIZATION & PERFORMANCE ANALYSIS.pbix in Power BI Desktop
   3. If data path broken: Update source to Excel New Project(Public Hospital Utilization).xlsx
   4. Refresh → interact with slicers!
   5. (Optional) Publish to Power BI Service for a live public link (add here if you do).

## CONCLUSION
   High admissions (4,852 total) peak seasonally and concentrate in Pediatrics, Surgery and states like Kaduna, while mortality (243 cases, ~5% rate) clusters
   in Outpatients/Pediatrics and males, signalling targeted risks. Gender-balanced admissions contrast with male-skewed mortality and department disparities 
   highlight case-mix severity over volume alone.
