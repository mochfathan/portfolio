# Investment Decision Engine — User Guide & Documentation

## 1. Overview
The Investment Decision Engine is a quantitative analysis tool that evaluates stocks using a multi-factor composite scoring model. It incorporates established financial frameworks from legendary investors and academic research, including Benjamin Graham, Joseph Piotroski, Edward Altman, and Aswath Damodaran.

---

## 2. How to Automate Data Entry (Yahoo Finance)
To avoid manual entry, you can export financial data directly from Yahoo Finance and upload it to the engine.

### Step-by-Step Instructions:
1.  **Search for a Stock:** Go to [Yahoo Finance](https://finance.yahoo.com) and enter a ticker symbol (e.g., `AAPL`).
2.  **Navigate to Financials:** Click on the **"Financials"** tab.
3.  **Expand Data:** Click the **"Expand All"** button to ensure all sub-line items are visible.
4.  **Download CSV:**
    *   Click the **Download icon** (usually a down arrow or cloud icon) above the data table.
    *   This will download `financials.csv` (Income Statement).
5.  **Repeat for other statements:**
    *   Select **"Balance Sheet"** and click Download.
    *   Select **"Cash Flow"** and click Download.
6.  **Upload to Engine:**
    *   In the Investment Decision Engine, look for the **"Data Import"** section in the left panel.
    *   Select the downloaded CSV files. You can upload them one by one or select multiple.
    *   The engine will automatically map the "TTM" (Trailing Twelve Months) or the most recent annual data to the input fields.

---

## 3. Financial Formulas & Methodology

### A. Graham Number
**Concept:** A conservative estimate of a stock's intrinsic value based on earnings power and book value.
**Formula:** `Graham Number = √(22.5 × EPS × BVPS)`
*   `22.5` is the product of Graham's maximum P/E (15) and maximum P/B (1.5).
*   `EPS`: Earnings Per Share (Diluted).
*   `BVPS`: Book Value Per Share.

### B. Piotroski F-Score
**Concept:** A 9-point scale used to determine the financial strength of a firm.
**Binary Criteria (1 point if true):**
1.  **ROA > 0**: Positive Return on Assets.
2.  **OCF > 0**: Positive Operating Cash Flow.
3.  **ΔROA > 0**: ROA is higher than the previous year.
4.  **Accrual < 0**: OCF is greater than Net Income (higher quality earnings).
5.  **ΔLeverage < 0**: Debt-to-Asset ratio decreased.
6.  **ΔLiquidity > 0**: Current Ratio increased.
7.  **No Dilution**: No new shares issued.
8.  **ΔGross Margin > 0**: Gross Margin increased.
9.  **ΔAsset Turnover > 0**: Asset Turnover ratio increased.

### C. Altman Z-Score
**Concept:** A predictive model for bankruptcy risk.
**Formula:** `Z = 1.2X₁ + 1.4X₂ + 3.3X₃ + 0.6X₄ + 1.0X₅`
*   `X₁`: Working Capital / Total Assets
*   `X₂`: Retained Earnings / Total Assets
*   `X₃`: EBIT / Total Assets
*   `X₄`: Market Value of Equity / Total Liabilities
*   `X₅`: Sales / Total Assets
*   **Zones:** Safe (> 2.99), Grey (1.81 - 2.99), Distress (< 1.81).

### D. Magic Formula (Greenblatt)
**Concept:** Ranking companies based on Quality (ROIC) and Price (Earnings Yield).
*   **Earnings Yield:** `EBIT / Enterprise Value`
*   **ROIC:** `EBIT / (Net Working Capital + Net Fixed Assets)`

### E. Discounted Cash Flow (DCF)
**Concept:** Estimating the value of an investment based on its future cash flows.
**Process:**
1.  Project Free Cash Flow (FCF) for the next 5 years based on a growth rate.
2.  Calculate the **Terminal Value** using the Gordon Growth Model.
3.  Discount all future flows back to the present using the **WACC** (Weighted Average Cost of Capital).
4.  Intrinsic Value = (PV of FCFs + PV of Terminal Value - Net Debt) / Shares Outstanding.

---

## 4. Tips for Accuracy
*   **Currency:** Ensure the currency in the engine matches the CSV (usually USD for US stocks).
*   **Shares Outstanding:** Yahoo sometimes reports shares in different units (thousands vs. millions). Double-check the "Market" tab if the Market Cap looks incorrect.
*   **Negative Retained Earnings:** For companies that perform heavy share buybacks (like Apple or McDonald's), the Altman Z-Score might show "Distress" due to negative Retained Earnings. Use professional judgment in these cases.

---
*Disclaimer: This tool is for educational purposes only. Always verify data against primary SEC filings.*
