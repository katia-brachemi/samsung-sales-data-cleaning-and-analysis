## Still Working on it

# Samsung Global Product Sales Analysis (2021 – 2024) 📱📊
This dataset found on Kaggle simulates a realistic global sales records for Samsung Electronics products presenting **5,500 synthetic transactions** across **52 countries and 555+ cities**.

## 🎯 Business Objective 
This analysis tracks sales performance across product categories and distribution channels between 2021 and 2024. The primary objective was to explore the shifting of the revenue, categorize sales into groups (digital, physical), and pinpoint specific underperforming categories within physical retail spaces to conclude strategic decision-making.

---
## 🛠️ Tech Stack & Python Libraries
* **Language:** Python
* **Libraries Used:** 
  * `pandas` & `numpy` 
  * `matplotlib` & `seaborn`
---

## ⚙️ Data Engineering & Cleaning Process
Before extracting insights, the raw dataset underwent rigorous data cleaning to ensure mathematical accuracy and standardized data presentation:
* **Handling Missing Data:** Filled missing text (`storage`, `previous_device_os`) with `"Unknown"` and imputed missing `customer_rating` values using the column average (`mean`).
* **Text Standardization:** Applied `.str.strip()` to remove accidental whitespaces and used `.str.title()` to fix capitalization issues across geographic and product columns (`country`, `region`, `city`, `category`).
* **Financial Formatting:** Rounded `revenue_usd` to two decimal places for consistent financial data presentation.

## 📈 Key Insights & Visualizations

### 1. Global Revenue Drop Driven by Smart TV Sales (2023 vs. 2024)
* **The Discovery:** Global revenue experienced a sharp decline of **$176,619.09** in 2024 compared to 2023. 
* **The Root Cause:** By isolating the year-over-year revenue impact using mathematical deltas, I discovered that **Smart TVs** were almost entirely responsible for the shortfall, suffering a massive individual loss of **$178,551.48**. 

<img width="944" height="530" alt="image" src="https://github.com/user-attachments/assets/7e524bcb-c452-4769-8290-b61e93d61f4d" />

### 2. Channel Deep-Dive: 
* **The Discovery:** To uncover *where* the Smart TV crash occurred, I segmented 2023 vs. 2024 revenue specifically for Smart TVs across **Digital vs. Physical** sales channels.
* **The Root Cause:** The data revealed that **Physical Stores** suffered a catastrophic drop of **$257,054.43** in Smart TV sales. 

<img width="570" height="456" alt="image" src="https://github.com/user-attachments/assets/47751e06-127a-476e-902e-2c8395a7e4fc" />

