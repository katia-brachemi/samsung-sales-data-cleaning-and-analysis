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

<img width="554" height="406" alt="image" src="https://github.com/user-attachments/assets/135662f0-63d6-452a-af39-488809e3b91e" />

### 3. Physical stores Deep Dive: 
* **What I did:** Once I knew physical stores were having trouble, I filtered for the "Physical" channel only to check the health of every single product.
* **The discovery:** * **Smart TVs** had the worst drop (down over 30%).
  * Wearables are also struggling in stores (**Galaxy Buds** dropped over 20%, **Galaxy Watches** dropped nearly 18%).
  * On the bright side, **Galaxy S** phones and **Accessories** are doing great and actually growing in physical stores.

<img width="1002" height="485" alt="image" src="https://github.com/user-attachments/assets/4c860dcb-7496-4bdc-bfb1-3fa7e5718455" />

### 4. Digital Channels Deep Dive:
* **What I did:** I filtered for the "Digital" channel only and calculated the YoY percentage growth/decline for all product categories.
* **The discovery:** Online demand for **Smart TVs** did not crash. Furthermore, top-tier **Galaxy S** phones and **Accessories** showed strong upward trends online, confirming the company's digital ecosystem is highly resilient.
<img width="1015" height="490" alt="image" src="https://github.com/user-attachments/assets/ef1fcd06-42d2-4877-9527-1d35471654d7" />

### 5. Geographical and Product Root-Cause Isolation
* **What I did:** To find the exact operational breakdown, I filtered for physical Smart TV sales and broke them down by `region`. This revealed that the revenue crash was heavily concentrated in **Europe and Asia**. I then grouped the data by individual `product_name` within those regions to find the specific product responsible.
* **The discovery:** I successfully isolated the exact product driving the entire global decline: the **Samsung Neo QLED 8K QN900C**. 

### 6. Investigating the QN900C Sales Numbers
* **What I did:** I isolated the **QN900C** model inside physical stores across Europe and Asia. I used an aggregation function (`.agg()`) to track its average retail price (`unit_price_usd`), actual transaction price (`discounted_price_usd`), and total volume (`units_sold`) year-over-year.
* **The discovery:** The data revealed a catastrophic volume collapse. In 2023, physical stores sold **65 units** of this TV model. In 2024, sales plummeted to just **8 units**, even though the price remained stable around \$5,000. This single product drop-off explains the entire global revenue anomaly.

## 🖥️ Interactive Analytics Dashboard
* **What I did:** To present these insights clearly, I used **Streamlit** to build a dynamic sales analytics dashboard (`app.py`). 

 **Features:**
* **Summary Metrics:** Instantly shows the exact drop in dollars and the percentage of units lost for the TV model.
* **Side-by-Side View:** Puts the online growth charts right next to a colored table tracking individual TV models.
* **Analyst Notes:** Includes a quick summary box that explains the missing stock issue found in the data.

*How to run the dashboard locally:*
```bash
streamlit run app.py
