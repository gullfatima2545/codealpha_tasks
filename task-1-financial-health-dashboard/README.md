# Financial Health Dashboard, SME Portfolio Analysis

## CodeAlpha Task 1 | Power BI | Gull Fatima

### Business Question
How financially healthy are the SMEs in this portfolio? Specifically: are they growing profitably, is the balance sheet getting stronger or riskier, is cash flow sustainable, and what should the next 6 months look like for budgeting?

### Dataset
Simulated but realistic monthly financial data for 3 Pakistani SMEs (Jan 2022 – Dec 2025, 48 months each):
- BrightLeaf Traders: Wholesale & Retail
- PakTech Solutions: IT Services
- FreshFarm Foods: Food Processing
- 
Three files mirroring the core financial statements:
- income_statement_monthly.csv: Revenue, COGS, Gross Profit, Opex, EBITDA, Depreciation, EBIT, Interest, Tax, Net Income
- balance_sheet_monthly.csv: Cash, Receivables, Inventory, PPE, Payables, Debt, Equity
- cashflow_monthly.csv: Operating, Investing and Financing cash flows
### Approach
- Built a star schema in Power BI: a central calendar table (DateTable) and a company dimension (CompanyDim), each related one-to-many to all three fact tables, so every slicer and visual filters consistently.
- DAX measures: Gross Margin %, Total Revenue M (millions formatting).
- Two report pages: Overview (KPIs, trends, forecast) and Balance Sheet & Cash Flow.
- Used Power BI's built-in forecasting (6 months, seasonality = 12) on the revenue trend for budgeting.
### Key Findings
1. Profitable growth, not just growth. Portfolio revenue grew 50% from 2022 (PKR 315M) to 2025 (PKR 473M), while net income grew even faster at 69% (PKR 36M → 61M). Margins are expanding.
2. PakTech Solutions is the efficiency leader. 25% net margin and 64% gross margin vs 6–9% net margins for the other two, a services model with far better unit economics than retail/food.
3. The mid-2023 dip was real but temporary. BrightLeaf's monthly profit fell to PKR 0.15M in Jul 2023 during the economic slowdown; all three companies recovered strongly through 2024–2025.
4. Deleveraging while growing. Total assets more than doubled (PKR 111M → 248M), funded mainly by retained profits, equity grew from 75M to 196M while debt-to-equity fell from 0.48 to 0.26.
5. Cash engine is healthy. Operating cash flow is positive every year and growing (PKR 40M → 65M); steady investing outflows show continuous reinvestment, and cash reserves nearly tripled to PKR 41M.
6. Forecast supports continued growth. The 6-month revenue forecast projects the upward trend continuing into 2026, within a stable confidence band.
### Recommendations
- Study and replicate PakTech's cost structure across the portfolio, its margin advantage is the single biggest value lever.
- Build a buffer for retail cyclicality, BrightLeaf's 2023 dip shows wholesale/retail needs 2–3 months of operating expenses in reserve.
- Keep funding growth from profits, not debt, the falling debt-to-equity ratio is a strength; protect it in the 2026 budget.
- Budget 2026 revenue ~5–8% above 2025 based on the forecast trend, with contingency at the lower confidence bound.
### Files in this submission
- Financial_Health_Dashboard.pbix: the interactive Power BI report (2 pages)
- income_statement_monthly.csv, balance_sheet_monthly.csv, cashflow_monthly.csv — source datasets
