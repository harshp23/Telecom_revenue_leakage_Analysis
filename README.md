# Revenue Leakage Detection Dashboard

A Power BI + Python project that identifies and visualizes revenue leakage patterns in a telecom dataset using segmentation, KPIs, and advanced dashboards.

---

## Dataset Source

- Dataset: [Telecom IoT CRM Dataset - Kaggle](https://www.kaggle.com/datasets/krishnacheedella/telecom-iot-crm-dataset)
- Provided by: Krishna Cheedella
- Contains:  
  - `crm1.csv` — User data  
  - `device.csv` — Revenue details per user/week  
  - `rev1.csv` — Session-level behavior  
- Total Rows: Over **11 million records** combined across files

---

##  Project Objective

To detect revenue leakage by identifying users whose actual revenue is lower than expected, based on segmentation and behavioral metrics. The insights can guide:
- Customer retention strategies
- Operational improvements

---

##  Data Pipeline

1. **Data Cleaning**  
   - Merged and filtered 3 raw CSVs  
   - Removed nulls, duplicate IDs  
   - Standardized segment and date fields  

2. **Feature Engineering**  
   - Created `total_revenue`, `active_weeks`, and segment-wise aggregates  
   - Calculated `leakage = expected_revenue - actual_revenue`  
   - Derived user-level metrics like age group, tenure, etc.

3. **Final Processed Dataset**  
   - Exported as `final_leakage_data.csv`  
   - Used for Power BI visualization

---

## Power BI Dashboard Features

- **Total Revenue vs Leakage** by Segment
- **Leakage % by Age Group**
- **Top N Users with Highest Leakage**
- **Funnel of Users**: Total → Active → Revenue → Leakage
- **Time-Based Trends** (weekly)
- **Stacked Column Revenue (Leaked vs Non-Leaked)**

###  Filters Applied:
- User Segment
- Age Group
- Region
- Gender
- Activity Level
- Revenue Threshold
- Week Number

---

##  Challenges Faced

- Original dataset was over 11 million rows — slow to process in Power BI , but after anlysis i found that it only 97k users have active weeks and revenue , other has null values and missing values.
- So many null values in all files
- Leakage % required engineered KPIs from external scripts
- Dataset lacked directly usable indicators, so we had to **create business logic from scratch**

---

##  Results
- Total users are 97k with Total revenue is $17M ,
- Leaked users are 14k with Leaked revenue of 133k
- Detected **14% high usage low revenue users**
- Identified top user segments and weeks with poor conversions



