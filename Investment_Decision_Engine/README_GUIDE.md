# Investment Decision Engine — User Guide & Documentation

## 1. Overview
The Investment Decision Engine is a quantitative analysis tool that evaluates stocks using a multi-factor composite scoring model. It incorporates established financial frameworks from legendary investors and academic research, including Benjamin Graham, Joseph Piotroski, Edward Altman, Joel Greenblatt, Peter Lynch, and Aswath Damodaran.

---

## 2. Advanced Features (New)

### A. Calculations Audit Tab
Located in the results panel, this tab provides 100% transparency for every metric.
*   **Formula Transparency:** Lists the textbook mathematical formula for 20+ metrics.
*   **Real-Time Math:** Shows your **actual inputs** being plugged into the equation.
*   **Educational Significance:** Explains *why* the metric matters and provides common industry thresholds (e.g., Peter Lynch's PEG target or Ken Fisher's P/S ratio).

### B. Project Persistence (Save & Restore)
You can now save your entire analysis session to a file for later use.
*   **💾 Save Project (CSV):** Downloads a specialized CSV containing all inputs, assumptions (WACC, growth), and manual overrides.
*   **📂 Restore Project:** Upload your saved `_Project_Save.csv` via the "Choose CSV Files" button to instantly recall your entire analysis with 100% data fidelity.
*   **📊 Export Audit:** Download a human-readable CSV report of your calculation breakdowns for documentation or study.

### C. Live UI Feedback
*   **Auto-Calc Previews:** Fields like **Market Cap**, **Net Debt**, and **Free Cash Flow** show their calculated values in the placeholder as you type dependent variables (e.g., as you type Price/Shares, the Market Cap placeholder updates to `Auto: ¥43.2T`).
*   **Field Synchronization:** Redundant fields like **Net Income Prior Year** are automatically mirrored across different tabs (Growth <-> Health) to reduce entry errors.

---

## 3. How to Automate Data Entry (Yahoo Finance)
To avoid manual entry, you can export financial data directly from Yahoo Finance and upload it to the engine.

### Step-by-Step Instructions:
1.  **Search for a Stock:** Go to [Yahoo Finance](https://finance.yahoo.com).
2.  **Navigate to Financials:** Click on the **"Financials"** tab and click **"Expand All"**.
3.  **Download CSV:** Click the **Download** icon for Income Statement, Balance Sheet, and Cash Flow.
4.  **Upload to Engine:** Select all downloaded CSVs at once in the **"Data Automation"** section. The engine automatically handles scaling (Millions vs Units) and maps 50+ fields.

---

## 4. Financial Formulas & Methodology

### A. Graham Number
Estimate of a stock's defensive price ceiling.
`GN = √(22.5 × EPS × BVPS)`

### B. Piotroski F-Score
A 9-point scale measuring binary financial quality improvements across Profitability, Leverage, and Efficiency.

### C. Altman Z-Score
A predictive model for bankruptcy risk.
`Z = 1.2X₁ + 1.4X₂ + 3.3X₃ + 0.6X₄ + 1.0X₅`
*   **Zones:** Safe (> 2.99), Grey (1.81 - 2.99), Distress (< 1.81).

### D. Magic Formula (Greenblatt)
Identifies quality businesses (ROIC) at cheap prices (Earnings Yield).

### E. PEG Ratio (Lynch)
Adjusts P/E for earnings growth. Target < 1.0.

### F. DCF — Intrinsic Value
A 5-year FCF projection discounted at WACC + terminal value via Gordon Growth Model.

---

## 5. Tips for Accuracy
*   **Fidelity Scaling:** The engine intelligently handles scaling. Large financial values (Revenue, Debt) are treated as Millions, while per-share and percentage values (Price, EPS, WACC) are kept as absolute units.
*   **Manual Overrides:** Use the "Override" fields to ignore automatic calculations (e.g., if you have a specific Net Debt figure from an analyst report).
*   **Negative Retained Earnings:** Common in companies with aggressive buyback programs (e.g., AAPL). The engine notes this in the Altman Z-Score breakdown.

---
## 6. Legal Disclaimer & Terms of Use
**NOT FINANCIAL ADVICE.** This engine is for educational and research purposes only. All results depend on user inputs. The authors are not liable for any financial losses resulting from its use. Consult a licensed financial advisor before investing.
