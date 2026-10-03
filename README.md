# 💳 Credit Card Spending Analysis

**Where does the money go, who spends it, and where is the risk?**
An end-to-end analytics project on 750 credit card transactions using **Excel, Power BI (DAX) and PowerPoint**.

> ⚠️ **Data note:** the dataset is **synthetic** (generated for learning and practice). It has no real customer or bank data, so the findings demonstrate the analysis approach and are not statements about a real portfolio.




## At a glance

| 💰 Total spend | 🧾 Transactions | 👥 Customers | 📈 Avg. transaction | 🎁 Cashback | 🚩 High-risk |
|:---:|:---:|:---:|:---:|:---:|:---:|
| **₹67.79 L** | **750** | **120** | **₹9,038** | **₹1.07 L** (1.58%) | **64** (8.5%) |

Period: **Jul-2025 to Jun-2026** · Currency: **INR**

---

## Key findings

**Spend by category** (share of total spend; each █ ≈ 4%)

```text
Shopping    ████████████████  63.8%   ₹43.24 L
Travel      ███               12.0%   ₹8.13 L
Healthcare  █                  5.1%   ₹3.46 L
Education   █                  4.2%   ₹2.83 L
Utilities   █                  4.0%   ₹2.69 L
```

**Spend by card tier**

```text
Platinum    █████████████████  32.9%
Gold        ███████████████    29.8%
Silver      ██████████████     27.1%
Signature   █████              10.2%   ← highest avg ticket: ₹10,296
```

**Risk: count vs. value** (the most important insight)

```text
By count    High ████ 8.5%              Medium ███████████ 21.2%   Low ███████████████████████████████████ 70.3%
By spend    High ███████████████ 30.1%  Medium ███████████████████████ 46.0%   Low ████████████ 23.9%
```

<details>
<summary><b>📅 More findings (click to expand)</b></summary>

- **Channel:** Online leads with 52.5% of spend, then POS (27.2%) and Tap-to-Pay (12.0%)
- **Peak month:** Oct-2025 (₹9.64 L); Oct and Nov record the most transactions (82 each)
- **Segments:** ages 26-35 and 36-45 together account for 71.7% of spend
- **Gender split:** Male 57.0% · Female 38.3% · Other 4.8%
- **Cities:** Mumbai leads with ₹14.83 L (21.9%); Kolkata has the highest average ticket (₹11,762)
- **Payment status:** Paid 616 (82.1%) · Pending 99 (13.2%) · Overdue 35 (4.7%)
- **International:** 20 transactions (2.7%), with a higher average ticket (₹12,235 vs ₹8,951)
- **Rewards:** cashback totals ₹1.07 L; Shopping generates 64.2% of it; 96,505 reward points issued

</details>

---

## Dashboard

The Power BI report (`Credit Card Spending.pbix`) is built to be explored:

- **6 KPI cards:** Total Spend, Total Transactions, Average Transaction, Cashback, High-Risk Transactions, Overdue Transactions
- **Visuals:** monthly spending trend, spend by category, payment channel share, spend by card type, risk and payment status
- **Slicers:** filter by card type, payment status, risk flag, channel, month, category and city
- **Measures:** written in DAX

<details>
<summary><b>🖱️ Try these questions on the dashboard</b></summary>

1. Filter **Risk Flag = High**. Which category and channel dominate?
2. Filter **Payment Status = Overdue**. Which card tier is most affected?
3. Select a single **month**. Does the category mix change in the peak month (Oct-2025)?
4. Compare **Platinum vs. Signature**. Who spends more per transaction?

</details>

---

## Project files

| File | What it is |
|---|---|
| 📗 `credit_card_spending_analysis_dataset.xlsx` | Dataset: `Transactions` (750 rows, 20 fields), `Dashboard` (summary tables), `Data Dictionary` |
| 📊 `Credit Card Spending.pbix` | Interactive Power BI report with KPI cards, charts and slicers |
| 📙 `Credit Card Spending Presentation.pptx` | 12-slide findings deck with recommendations |

---

## Data dictionary

<details>
<summary><b>🧾 20 fields in the Transactions sheet (click to expand)</b></summary>

| Field | Description |
|---|---|
| `Transaction_ID`, `Customer_ID` | Unique transaction and (synthetic) customer identifiers |
| `Card_Type` | Silver, Gold, Platinum, Signature |
| `Transaction_Date`, `Month`, `Weekday` | Date and time, with month-year and day of week extracted |
| `Merchant`, `Category` | Merchant name and spend category (10 categories) |
| `City` | Transaction city (10 cities) |
| `Payment_Channel` | Online, POS, Tap-to-Pay, ATM, Auto-Debit |
| `Amount_INR`, `Cashback_INR`, `Reward_Points` | Transaction amount, estimated cashback and reward points |
| `International_Txn` | Whether the transaction is international (Yes/No) |
| `Credit_Limit_INR`, `Utilization_Pct` | Card limit and transaction amount as % of that limit |
| `Payment_Status` | Paid, Pending, Overdue |
| `Risk_Flag` | Simple rule-based label: Low, Medium, High |
| `Age_Group`, `Gender` | Customer demographics |

</details>

---

## Recommendations

- [x] Target offers at **Shopping and Travel**, which together drive about 76% of spend
- [x] Run online and card-tier campaigns for **Platinum and Gold** users
- [x] Track **high-risk, high-value** transactions closely, since 8.5% of transactions carry 30.1% of spend
- [x] Reduce overdue transactions with reminders and follow-up
- [x] Watch cashback concentration in Shopping to protect profitability

---

## Skills demonstrated

`Excel` · `Power BI` · `DAX` · `Data modelling` · `Data visualization` · `KPI design` · `Segmentation analysis` · `Risk analysis` · `Data storytelling`

---

## How to open

1. Download or clone the repository.
2. Open `Credit Card Spending.pbix` in **Power BI Desktop**.
3. If Power BI asks for the data source, point it to `credit_card_spending_analysis_dataset.xlsx` (Home → Transform data → Data source settings).


 https://github.com/pritammanik597-cpu/Credit-Card-Spending.git


## Limitations

- Synthetic data, so no real-world conclusions.
- `Risk_Flag` is a rule-based label (amount, payment status, international flag), not a predictive risk score. Findings such as "Shopping has the most high-risk transactions" partly reflect large ticket sizes.
- `Utilization_Pct` is calculated per transaction (amount ÷ credit limit), not as a monthly customer balance.

---


