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
