# 📦 Optimizing Excess Inventory Process to Mitigate Financial Risk
### Teradyne – Supply Base Management (SBM) Capstone Project

---

## 📌 Project Overview
Developed in collaboration with **Teradyne’s Supply Base Management (SBM) group**, this project optimizes the excess inventory approval process. By addressing demand volatility and long supplier lead times, we transitioned Teradyne from a subjective, manual oversight model to a **data-driven, algorithmic decision framework**.

**Goal:** Reduce bias, improve approval efficiency, and enhance capital utilization using Python-based quantitative modeling.

---

## 🎯 Business Problem
Teradyne faced recurring excess inventory and financial leakage due to:
* **Demand Volatility:** Rapid shifts in market requirements.
* **Lead Time Complexity:** Long and variable supplier lead times.
* **Subjective Workflows:** Approval systems relied on qualitative judgment rather than real-time data.

**Financial Impact:**
* Increased holding costs and reduced profitability.
* Significant capital tied up on the balance sheet.
* Lower operational efficiency in the supply chain.

---

## 📊 Data Landscape
We synthesized 18 months of historical data across three primary domains:

| Data Source | Scope | Key Attributes |
| :--- | :--- | :--- |
| **Excess Inventory** | 1,408 requests | Site, Part Number, PO Price, Qty Ordered |
| **Demand Data** | 17 Files | Planned Demand, Parent Site, Due Date |
| **Parts Data** | 17 Files | Cumulative Lead Time (weeks), Site |

---

## ⚙️ Methodology & Core Logic



### 1. Data Integration
The pipeline cleanses and merges disparate datasets (Demand, Inventory, and Lead Times) into structured snapshots for specific fiscal periods (2022 H2, 2023 H1, and 2023 H2).

### 2. The Decision Algorithm
The framework utilizes **Lead-Time-Adjusted Demand** to determine if a purchase is truly necessary.

* **Adjusted Date Calculation:**
    $$\text{Adjusted Date} = \text{Requested Date} + (\text{Cumulative Lead Time} \times 2 \times 7)$$
* **Lead Time Segmentation:** * Short-term (< 182 days)
    * Medium-term (182–365 days)
    * Long-term (> 365 days)
* **Suggested Need Formula:**
    $$\text{Suggested Need} = \text{Aggregated Demand} - (\text{On Hand} + \text{Open Orders})$$
* **Potential Excess Quantification:**
    $$\text{Total Excess Cost} = (\text{Suggested Need} - \text{Quantity Ordered}) \times \text{PO Price}$$

---

## 📈 Key Results & Business Impact
The implementation of the algorithmic framework led to immediate improvements in financial oversight:

* **⚡ Enhanced Oversight:** 8% increase in requests escalated for high-level management review, ensuring better control over high-spend approvals.
* **🔍 Risk Visibility:** Identified hidden excess risk across multiple periods:
    * **2022 H2:** 7% visibility
    * **2023 H1:** 43% visibility
    * **2023 H2:** 55% visibility
* **💰 Capital Efficiency:** Significant reduction in projected excess spend and optimized working capital.



---

## 🛠 Tech Stack
* **Language:** Python
* **Libraries:** Pandas (Data Manipulation), NumPy (Numerical Logic), Matplotlib/Seaborn (Visualization)
* **Environment:** Jupyter Notebook / Google Colab

---

## 🔮 Future Enhancements
* ML Integration: Implementing machine learning for predictive demand forecasting.
* Real-time Monitoring: Dashboard for real-time stockout and excess monitoring.
* MOQ Optimization: Incorporating Minimum Order Quantities into the "Suggested Need" logic.

---

## 👥 Team & Credits
W.P. Carey School of Business – MSBA Applied Project
* Term: Spring 2024
* Team: 441

## 📌 Conclusion
This project proves that transitioning from subjective judgment to objective, lead-time-adjusted modeling allows supply chain groups to proactively mitigate financial risk and improve overall resilience.
