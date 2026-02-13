# PUBLIC HOSPITAL UTILIZATION & PERFORMANCE ANALYSIS

## PROJECT DESCRIPTION
   Interactive Power BI dashboard analyzing 4,852 admissions, 243 mortalities (5% rate) and KPIs across departments,states,gender and 20+ hospitals for Nigeria's public health sector.

## 🎯 Objectives
   The goal is to build an interactive power BI report that helps healthcare stakeholders 
   - Track Patient Flow: Monitor admissions(4,852 total), discharges(90% rate) and net growth(+463) to utilization across 20 hospitals
   - Understand utilization patterns
   - Identify capacity gaps and monitor outcomes.
   - Identify high-utilization states and hospitals for targeted resource allocation and capacity planning.
   - Understand which departments(e.g.,Pediatrics, Surgery) experiences the highest demand and where to focus staffing and training.
 
## 🛠️ Tools & Technologies
    - **Power BI Desktop** (Visualizations & Slicers)
    - **Power Query** (ETL/cleaning)
    - **Excel** (.xlsx source data)
    - **DAX Measures** (16 Custom KPIs for dynamic analysis)
    
## ADD CALCULATED TABLE
   *Using the Date column from the dataset to create a date table
      . DATE TABLE = CALENDARAUTO()

   *Extracting the month and day from the Date Table
      - MONTH = FORMAT('DATE TABLE'[Date],"MMMM")
      - DAY = FORMAT('DATE TABLE'[Date],"DDDD")


## 📊 KEY METRICS & DAX MEASURES
    
   From the model, the following aggregate metrics are observed:
    
   - TOTAL ADMISSIONS = SUM('Public_Hospital_Utilization_Dat'[Patients Admitted])

   - TOTAL DISCHARGES = SUM(Public_Hospital_Utilization_Dat[Patients Discharged])

   - TOTAL MORTALITY = SUM('Public_Hospital_Utilization_Dat'[Mortality Count])

   - MORTALITY RATE% = ('DATE TABLE'[TOTAL MORTALITY]/'DATE TABLE'[TOTAL ADMISSIONS]*100)

   - DISCHARGE RATE = DIVIDE(SUM('Public_Hospital_Utilization_Dat'[Patients Discharged]),[TOTAL ADMISSIONS],0)

   - AVERAGE LENGTH OF STAY = AVERAGE(Public_Hospital_Utilization_Dat[Avg Stay (Days)])

   - NET CHANGE IN PATIENTS = [TOTAL ADMISSIONS]-[TOTAL DISCHARGES]

## 📈 VISUALIZATION
     
   - **Patient Admission Counts by Month:** 
       This Line Chart tracks monthly patient admission counts across 2022, starting low in January(~300), peaking sharply in July(~480),
       with subsequent spikes and dips(e.g., ~450 in late months), reflecting seasonal or event-driven surges in hospital visits.
https://github.com/Josephine-analyst/Public-Hospital-Utilization-Performance-Analysis/issues/9
   - **Mortality Count by Department:**
       The horizontal bar chart ranks departments by mortality count: Outpatients leads at 47, followed by Pediatrics(46), Internal Medicine (41),
       Maternity (40), Emergency (35) and Surgery (34), pinpointing high-risk areas.

   - **Patient Admission by Department:**
       The Tree Map Chart shows patient admissions by department: Pediatrics (~47), Surgery (~24), Maternity (~23), Internal Medicine (~19),
       Outpatient (~18), totalling around 243 visits, with Pediatrics dominating volume.

   - **Patient Admissions by Gender:**
       The Donut Chart divides admissions nearly evenly: Female(~50%), Male (~50%), providing a balanced gender distribution snapshot.

   - **Admissions by State:**
       The Area Chart displays declining admissions: high in Kaduna(~850), dropping sharply to Lagos(~450) and others (Oyo, Ogun, Delta ~400-500),
       overlaid with gender splits.

   - **Patient Mortality Count by State:**
       The Horizontal Bar Chart ranks top states by patient mortality count: Kaduna leads(~32 deaths), followed by  Oyo, Delta and others(~20-25), 
       highlighting geographic disparities in outcomes possibly tied to population, facilties or health events.

   - **Top 5 Mortality Count by Hospital:**
       Bars detail top hospitals: 17,15,15,15 and 14 deaths, for comparing facility performance.

   - **Patient Admission Count by Service**
       The Pie Chart distributes 772 total admissions by service: Delivery(25%,~193), Surgery(18%,~139), Lab Test(18%,~139), Consultancy(~17%)
       and others, emphasizing service loads.
     
   - **Mortality Count by Month:**
       Line Chart deoict flunctuating mortality counts(peaks ~30),highlighting seasonal outcome patterns.

   - **Mortality Count by Gender:**
       The Pie Chart shows male mortality dominant(~74%,119 cases) vs female (~26), indicating gender disparities in outcomes.


## INTERACTIVE SLICERS
   - Month
   - Department
   - Gender
   - Hospital

## 🔍 KEY BUSINESS INSIGHTS
   1. Pediatrics, Surgery, Emergency and Maternity together account for majority of admissions, meaning most demand is clinical rather than administrative.

      **Recommendation:** Priortize staffing, beds and supplies in peak months; use this pattern to plan roasters and elective procedures.

   2. Total Mortality is 243, giving a mortality rate of about 5%, which is one of the key indicators used to evaluate hospital quality. Outpatients,
      Pediatrics, Internal Medicine and Maternity record the highest mortality counts(around 40-47 each), higher than Emergency and Surgery.

      **Recommendation:** Conduct focused clinical audits in departments with high mortality(especially Outpatients and Pediatrics) to identify causes: late
      presentation, medication delays or limited ICU access.

   3. Admissions by gender are roughly balanced, but mortality is higher in males(around 124 deaths, ~51%) than female.

      **Recommendation:** Flag male patients with severe conditions for closer monitoring, early escalation and more aggressive management pathways.

   4. Pediatrics and Surgery together drive a large share of admissions, while service types like Delivery, Surgery, Lab tests and Consultations dominate
      the service-level pie chart.

      **Recommendation:** In high-risk services (e.g., Delivery, Surgery), standardized clinical pathways and checklists to reduce preventable complications
      and errors.
 
## How to Use / Explore This Project

   - Clone or download the repository.
   - Obtain the original Excel dataset 
   - Open PUBLIC HOSPITAL UTILIZATION & PERFORMANCE ANALYSIS.pbix in Power BI Desktop.
   - If prompted, update the data source path to point to your local .xlsx file.
   - Refresh the data and interact with slicers/visuals.

## CONCLUSION
   High admissions (4,852 total) peak seasonally and concentrate in Pediatrics, Surgery and states like Kaduna, while mortality (243 cases, ~5% rate) clusters
   in Outpatients/Pediatrics and males, signalling targeted risks. Gender-balanced admissions contrast with male-skewed mortality and department disparities 
   highlight case-mix severity over volume alone.
