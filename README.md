# Green Risk Red Returns: Mapping The Financial Impact of Climate Risk Across High- and Low- Risk Regions
This repository contains the code and methodology for the research project, *"Green Risk Red Returns: Mapping The Financial Impact of Climate Risk Across High- and Low- Risk Regions."*

---

### **1. Overview**
The project addresses a critical knowledge gap in climate finance: how regional climate risk classification (high- or low- risk) influences the relationship between climate adversities and stock returns.<br/>
While climate risk significantly impacts financial markets, its effects vary geographically.<br/>
Empirical evidence on how these regional factors influence stock returns has been limited, especially comparative analysis between risk classes in emerging markets like Asia.<br/>
- **Business Problem:** The financial impact of climate risk is heterogeneous, making a universal approach to risk management insufficient.
- **Goal:** To analyse the differential effects of climate risk (quantified by Extreme Temperature Days) on stock performance in high-risk regions (India, Signapore, China) versus low-risk regions (Japan, South Korea, Indonesia).
- **Target Audience:** Investors, policymakers, and businesses navigating climate challenges, seeking insights into the geographic and firm-level nuances of climate-related financial impacts.

### **2. Methodology and Data**
The study employed **multiple linear regression** to model the relationship between Extreme Temperature Days (ETD) and stock returns. Two models were used to capture both overall and context-specific effects:<br/>
- **Model 1 (Mixed Study):** Tested overall differences using an interaction term between ETD and Regional Risk Classification.
$$r_{i}=\beta_{0}+\beta_{1}ETD_{1}+\beta_{2}ETD\cdot RiskClass_{2}+\beta_{3}FL_{3}+\beta_{4}MC_{4}+\beta_{5}RiskClass_{5}+e_{i} \quad$$
- **Model 2 (High/Low-Risk Studies):** Explored specific patterns and magnitudes within each region type.
$$r_{t}=\beta_{0}+\beta_{1}ETD_{1}+\beta_{2}FL_{2}+\beta_{3}MC_{3}+e_{t} \quad$$
<br/>

**Data and Variables**<br/>
- **Sample Selection:** 210 companies (35 per country) selected based on large market capitalisation, consistent data availability, and industry relevance (energy, agriculture, and infrastructure/construction). Countries were classified based on the Germanwatch Climate Risk Index (CRI).
  * **High-Risk Regions:** India (CRI Rank 1-10), Thailand (CRI Rank 11-20), China (CRI Rank 21-50).
  * **Low-Risk Regions:** Singapore, South Korea, Japan (CRI Rank 51-100).
- **Data Sources:** Financial and stock data (e.g., EIKON Tickers, Yahoo Finance Tickers) and weather data collected at company headquarters.
- **Dependent Variable:** Monthly Stock Returns (first difference log returns).
- **Independent Variable:** Extreme Temperature Days (ETD), defined as days where temperature exceeds $30^{\circ}\text{C}$ or falls below $0^{\circ}\text{C}$.
- **Moderator Variable:** Risk Classification (High vs. Low Risk Region).
- **Control Variables:** Financial Leverage (FL) and Market Capitalisation (MC).

### 3. Key Findings
The central hypothesis ($\text{H}_1$)—that climate adversities have a stronger statistically significant negative impact on stock performance in high-risk regions compared to low-risk regions—was rejected.<br/>
While the overall model lacked significance, the region-specific analysis supports the conclusion that regional climate risk influences financial performance. The negative and significant effect in high-risk regions aligns with existing literature on climate sensitivity. The negligible impact in low-risk areas suggests firms there are either more resilient or investors may not be fully pricing in climate risk due to factors like lack of historical data or inconsistent methodologies. The study underscores the importance of tailored climate adaptation strategies for firms in high-risk areas.

### 4. Technical Stack
The following tools and libraries were used to conduct data processing, analysis, and visualisation:
- **Language:** Python
- **Core Libraries:**
  * Pandas: Data manipulation and cleaning (e.g., handling market capitalisation and financial leverage data).
  * NumPy: Numerical operations (e.g., log returns calculation).
  * SQL: Data storing.
  * Statsmodels: Implementation of the Ordinary Least Squares (OLS) regression models.
  * Matplotlib/Seaborn: Data visualisation (generating figures and correlation plots).
- **Environment:** Spyder

### 5. Future Work
Based on the study's conclusions, potential directions for future research include:
- Exploring sector-specific vulnerabilities to climate adversities.
- Evaluating the effectiveness of various corporate adaptation strategies in mitigating negative impacts.
- Comparing the impact of climate risk before and after the surge in sustainability awareness.
