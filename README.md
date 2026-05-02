# Dirty Finance: Data Cleaning, Transformation, and Visualization

## 📌 Project Overview
This project focuses on analyzing and visualizing financial transaction data to identify patterns in user behavior, transaction types, and financial risk indicators. The study correlates financial behavior with economic markers like market volatility, inflation, and interest rates to support data-driven financial decision-making.

---

## 👤 Student Information
| Field | Details |
| :--- | :--- |
| **Name** | Akash. P |
| **Batch** | TN-DA-ANB11 |
| **Project Title** | Dirty Finance |
| **Domain** | Finance |
| **Timeline** | 2023 Dataset |
| **Mentor** | Kumaran. M |
| **Submission Date** | 07-01-2025 |

---

## 🔗 Resources
*   **[Raw Dataset](https://docs.google.com/spreadsheets/d/1AQUS-T5dK7Bf00cB0zf9bDvRUk07huhO/edit?usp=sharing)**
*   **[Cleaned Dataset](https://docs.google.com/spreadsheets/d/1a9xAhupc4kL4QP5WVaDxNwie1WM4S1Wx/edit?usp=sharing)**
*   **[Visuals Dashboard](https://drive.google.com/file/d/104UG2jpYtPYuZmtP8XF54VUzK2keq19U/view?usp=sharing)**

---

## 🛠️ Tools & Technologies
*   **Microsoft Excel:** Data cleaning, handling missing values, and feature engineering.
*   **Power BI:** Interactive dashboards and DAX for advanced financial KPIs.
*   **Power Query:** Data transformation and format standardization.

---

## 📊 Feature Engineering (Derived Columns)
To deepen the analysis, the following attributes were engineered:
*   **Net Transaction Amount:** Validated actual money flow based on transaction type.
*   **Transaction Month/Year:** Extracted from timestamps for trend analysis.
*   **Risk Category:** Classified users based on credit score and risk level.
*   **Market Condition Index:** Derived using volatility index, inflation, and interest rates.
*   **User Activity Level:** Grouped by transaction frequency and volume.

---

## 🧹 Data Cleaning Process

### 1. Header Standardization
Used the `=PROPER()` function in Excel to ensure all column headers followed a consistent naming convention (e.g., `Timestamp`, `User Id`, `Transaction Amount`).

### 2. Time & Date Separation
Used the **Text to Columns (Delimited)** wizard to split raw timestamps into distinct `Date` and `Time` columns for granular analysis.

### 3. Inconsistency Removal
*   **Date Formats:** Replaced inconsistent separators (e.g., changing `2023.08-22` to `2023-08-22`) using **Find & Replace**.
*   **Currency Cleaning:** Removed "USD" strings and "$" symbols from the `Transaction Amount` and `Account Balance` columns.
*   **Typo Correction:** Fixed misspelled transaction types (e.g., `waltiwdhar` → `Withdrawal`) using filter-based bulk updates.

### 4. Advanced Transformation (Power Query)
*   Identified and resolved `INVALID_DATE_FORMAT_STRING` errors.
*   Handled `INVALID_CATEGORY_DEFAULT` values in transaction types.
*   Imputed missing values (`N/A`, `NULL`, `None`) using statistical averages/medians.

---

## 📈 Power BI Visualizations & DAX
The following Key Performance Indicators (KPIs) were created using DAX:

*   **Total Transaction Amount:** 
    ```dax
    Total Transaction = SUM('Cleaned Data set Final'[Transaction_Amount])
    ```
*   **Average Credit Score:**
    ```dax
    Average credit score = AVERAGE('Cleaned Data set Final'[Credit_Score])
    ```

### Key Visual Insights
*   **Account Balance by Type (Pie Chart):** Investment transactions maintain the highest average balance (**12.94K** or **32.6%** of the total).
*   **Risk Assessment (Tree Map):** Investments carry the maximum risk value (**900**), while deposits are the safest (**599**).
*   **Market Volatility (Column Chart):** Investment-related activities show the highest sensitivity to market fluctuations (above **20K**).
*   **Interest Rate Trends (Line Chart):** There is a steady downward trend in interest rate impact moving from Investments to Transfers.

---

## 🏁 Summary & Conclusion
The analysis highlights that **Investment transactions** are the primary drivers of both capital growth and financial risk. While they offer higher account balances, they are significantly more sensitive to market volatility and interest rate shifts. Conversely, **Deposits and Transfers** represent a stable, conservative financial behavior. The interactive Power BI dashboard allows for dynamic filtering, enabling stakeholders to monitor high-risk users and market impacts in real-time.
