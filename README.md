###  **Hip Replacement Surgery Analysis Project**

---

### **Project Overview**
This project focuses on analyzing **hip replacement surgeries** across hospitals to evaluate cost efficiency, length of stay (LOS), and other key metrics. By identifying outliers and drivers of variability, this report supports decision-making for hospital resource optimization and performance improvement.

---

### **Tools and Techniques**
- **Tool Used:** Microsoft Power BI  
- **Data Sources:** Hospital Discharge Data  
- **Techniques:**  
  - DAX for creating metrics and calculations.  
  - Advanced visualizations (e.g., scatter plots, bar charts, quadrant charts).  
  - Key Influencers visuals to identify drivers of LOS and costs.

---

### **Key Calculations**
1. **Average Cost Per Discharge**  
   Formula:  
   ```DAX
   avg cost per discharge = DIVIDE(SUM(hospital_discharges[total_costs]), [Total Discharge], 0)
   ```  
   - **Purpose:** To measure cost efficiency per discharged patient.  

   ![Snap_1](https://github.com/user-attachments/assets/39bacac6-b379-43ac-a094-213efae982aa)

2. **% Variance in Average Cost Per Discharge**  
   Formula:  
   ```DAX
   % Var Avg Cost per Discharge = CALCULATE(DIVIDE([avg cost per discharge] - [avg cost per discharge hospitalWise], [avg cost per discharge hospitalWise], 0))
   ```  
   - **Purpose:** Highlights cost deviations compared to the overall state average.

   

3. **90th Percentile Average Cost Per Discharge**  
   Formula:  
   ```DAX
   90th percentile average cost per discharge = PERCENTILE.INC(hospital_discharges[total_costs], 0.9)
   ```  

   

4. **Average LOS and % Variance in LOS**  
   Formulas:  
   - Average LOS:  
     ```DAX
     Avg LOS = AVERAGE(hospital_discharges[length_of_stay])
     ```  
   - % Variance in LOS:  
     ```DAX
     % Var Avg LOS per Discharge = CALCULATE(DIVIDE([Avg LOS] - [Avg LOS HospitalWise], [Avg LOS HospitalWise], 0))
     ```  

  

5. **Dynamic Title for Hospital Profiles**  
   Formula:  
   ```DAX
   Title Selected Facility = "Hospital Profile: " & SELECTEDVALUE(Hospital_Discharges[facility_name])
   ```  
 ![Snap_1](https://github.com/user-attachments/assets/8e8fff80-6404-4809-8d80-5540d18aa4f9)
  

---

### **Dashboard Pages**

#### **1. Home Page**
- **Purpose:** Provides navigation and summary metrics for quick access to report sections.  
- **Components:**
  - Navigator buttons for seamless transitions between sections.
  - Summary cards for:
    - Total Discharges
    - Total Hospitals
    - Average LOS and Cost Per Discharge.

![Snap_1](https://github.com/user-attachments/assets/35687520-d2f6-40e2-924b-83833606ac6a)
---

#### **2. LOS Comparison Page**
- **Purpose:** Highlights hospital performance in terms of LOS and identifies influencing factors.  
- **Key Visuals:**
  - **Top 5 and Bottom 5 Hospitals by Average LOS:**  
    - Clustered bar charts showing hospitals with highest/lowest LOS.  

  - **Key Influencers Visual:**  
    - Highlights key drivers of LOS variability (e.g., illness severity, mortality risk).  
    
  - **Summary Cards:**  
    - Total Hospitals, Discharges, and Average LOS.  
    ![Snap_1](https://github.com/user-attachments/assets/1fe4f023-4a42-4503-8472-790de82755a7)

---

#### **3. Cost Comparison Page**
- **Purpose:** Analyze cost variability across hospitals and identify drivers.  
- **Key Visuals:**  
  - **Top 5 and Bottom 5 Hospitals by Cost Per Discharge:**  
    - Highlights facilities with the highest/lowest costs.  
     ![Snap_1](https://github.com/user-attachments/assets/2c1118d1-65fa-4501-8780-6abf4c34c46f)*  
  - **Scatter Plot (Quadrant Chart):**  
    - X-Axis: Average LOS, Y-Axis: Average Cost Per Discharge.  
    - Bubble Size: Total Discharges; Colored by Health Service Area.  
    - Reference Lines for 90th Percentile Cost and Overall Average.  
    
  - **Key Influencers Visual:**  
    - Displays key drivers for cost variability.  
    ![Snap_1](https://github.com/user-attachments/assets/1fe4f023-4a42-4503-8472-790de82755a7)

---

#### **4. Hospital Profile Page**
- **Purpose:** Deep-dive into individual hospital performance.  
- **Key Visuals:**
  - **Dynamic Title:** Displays selected hospital name.
    
  - **Gauges:** Compare LOS and cost against state averages.  
    
  - **Column Charts:** Discharges by Severity of Illness and Risk of Mortality.  
    
  - **Donut Charts:** Discharges by Diagnosis and Patient Disposition.  
     breakdowns.*
  - **Slicer:** Single-select hospital slicer to filter visuals.  
    ![Snap_1](https://github.com/user-attachments/assets/6b41f1b3-d053-417a-a492-d161fdb57f8b)

---

### **Key Findings**

#### **Average Metrics**
- **Average Cost Per Discharge:** $20,910.  
- **Average LOS:** 2.65 days.

![Snap_1](https://github.com/user-attachments/assets/42b27f46-d9f7-4aa7-9f5a-01a22200cdda)

#### **Cost Outliers**
- **Top 2 Hospitals by Cost:**
  - NYU Lutheran Medical Center ($84,601).
  - Olean General Hospital ($81,265).  


#### **LOS Outliers**
- **Highest LOS:** Kings County Hospital Center (12.0 days).  
- **Lowest LOS:** Northern Dutchess Hospital (1.4 days).  



#### **Key Drivers of Variability**
- **LOS Influencers:**  
  - Extreme Severity of Illness.  
  - Major Mortality Risk.  
  - Patient disposition to skilled nursing homes.  
- **Cost Influencers:**  
  - Location (e.g., NYC hospitals).  
  - Diagnosis complexity.



---

### **Conclusion**
This dashboard provides actionable insights into hip replacement surgery performance across hospitals. It identifies high-cost and high-LOS outliers, along with key influencing factors. These findings can guide targeted interventions for operational efficiency and better patient outcomes.
![Snap_1](https://github.com/user-attachments/assets/74f358e2-4b24-45b4-8477-7c82b045dffa)

---

This structure ensures your visualizations are integrated seamlessly and enhance the narrative flow of your documentation. Let me know if you need help formatting or refining the visuals further!
