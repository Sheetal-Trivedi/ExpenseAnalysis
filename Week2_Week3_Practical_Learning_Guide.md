# 📗 Practical Learning Guide — Week 2 & Week 3
### Financial Analyst Bootcamp | Excel Skills + Real Company Analysis

> **Goal:** By the end of these 2 weeks, you will have built a working expense tracker in Excel AND performed a full vertical + horizontal analysis on a real Fortune 500 Indian company's financials.

---

## 📋 Table of Contents

### WEEK 2 — Excel Skills
- [W2 Overview & Setup](#week-2-overview)
- [Day 1: Download Sample Data & Set Up Excel](#day-1-download-sample-data--set-up-excel)
- [Day 2: VLOOKUP — Complete Tutorial](#day-2-vlookup--complete-tutorial)
- [Day 3: SUMIF & SUMIFS — Complete Tutorial](#day-3-sumif--sumifs--complete-tutorial)
- [Day 4: Pivot Tables — Complete Tutorial](#day-4-pivot-tables--complete-tutorial)
- [Day 5: Build the Expense Tracker (Part 1)](#day-5-build-the-expense-tracker-part-1)
- [Day 6: Build the Expense Tracker (Part 2 — Charts & Dashboard)](#day-6-build-the-expense-tracker-part-2--charts--dashboard)
- [Day 7: Review & Polish](#day-7-review--polish)
- [Sample Data Download Links](#-sample-data-download-links)

### WEEK 3 — Real Company Analysis
- [W3 Overview](#week-3-overview)
- [Day 8: Download Annual Reports & Understand Structure](#day-8-download-annual-reports--understand-structure)
- [Day 9: Extract Financial Data into Excel](#day-9-extract-financial-data-into-excel)
- [Day 10: Perform Vertical Analysis](#day-10-perform-vertical-analysis)
- [Day 11: Perform Horizontal Analysis](#day-11-perform-horizontal-analysis)
- [Day 12: Ratio Analysis & KPIs](#day-12-ratio-analysis--kpis)
- [Day 13: Build Charts & Visual Dashboard](#day-13-build-charts--visual-dashboard)
- [Day 14: Write Your Analysis Report](#day-14-write-your-analysis-report)
- [Annual Report Download Links](#-annual-report-download-links)

---

---

# WEEK 2 — EXCEL SKILLS

---

## Week 2 Overview

### What You'll Build
A fully functional **Company Expense Tracker** in Excel that:
- Logs 100+ expense transactions across departments
- Uses VLOOKUP to auto-fill category names from a lookup table
- Uses SUMIF to calculate department-wise totals
- Has a Pivot Table for dynamic expense slicing
- Has 3 charts (bar, pie, line) in a Dashboard tab

### Software Required
- Microsoft Excel 2016 or later (**recommended**)
- OR Google Sheets (free — most steps are identical)
- Download Excel free trial: https://www.microsoft.com/en-in/microsoft-365/try

### File Structure You'll Create
```
ExpenseTracker.xlsx
├── Sheet 1: RAW_DATA         ← All transactions (100+ rows)
├── Sheet 2: LOOKUP_TABLES    ← Category & department reference
├── Sheet 3: SUMMARY          ← SUMIF totals, budget vs actual
├── Sheet 4: PIVOT_ANALYSIS   ← Pivot table analysis
└── Sheet 5: DASHBOARD        ← Charts and visual summary
```

---

## 📥 Sample Data Download Links

Use these free, ready-to-use datasets for practice:

### Option A — Ready-Made Expense Datasets (Direct Download)

| Dataset | Source | What's In It | Download Link |
|---------|--------|-------------|---------------|
| **Sample Financial Dataset** | Kaggle | Company transactions, 1000+ rows | https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting |
| **Expense Report Sample** | Microsoft Templates | Pre-built expense report | https://templates.office.com/en-us/expense-report-tm16400877 |
| **Superstore Sales Data** | Tableau Public | 10,000 rows — great for pivot practice | https://public.tableau.com/app/sample-data/sample_superstore.xls |
| **Financial Sample Excel** | Microsoft Docs | Official Microsoft finance sample | https://learn.microsoft.com/en-us/power-bi/create-reports/sample-financial-download |
| **HR & Finance Dataset** | data.world | Multi-department expense data | https://data.world/finance |

### Option B — Indian Company Sample Data

| Dataset | Source | Download Link |
|---------|--------|--------------|
| **BSE Sample Financial Data** | BSE India | https://www.bseindia.com/corporates/List_Scrips.html |
| **NSE Historical Data** | NSE India | https://www.nseindia.com/report-detail/eq_security |
| **MCA Company Data** | Ministry of Corporate Affairs | https://www.mca.gov.in/content/mca/global/en/data-and-reports/data-sets.html |

### Option C — Create Your Own Practice Data (Recommended for Beginners)
> Follow Day 1 instructions below — I'll give you exact data to type in so you build familiarity from scratch.

---

## Day 1: Download Sample Data & Set Up Excel

### ⏱ Time Required: 45–60 minutes

### Step 1.1 — Download the Microsoft Financial Sample

1. Go to: https://learn.microsoft.com/en-us/power-bi/create-reports/sample-financial-download
2. Click **"Download the sample financial Excel file"**
3. Save as `Financial_Sample.xlsx` on your Desktop
4. Open it in Excel — explore what's there (products, sales, COGS, profit data)

### Step 1.2 — Create Your New Working File

1. Open Excel → New Workbook
2. Save as: `My_Expense_Tracker.xlsx`
3. Create 5 sheets by right-clicking the sheet tab → "Insert" → "Worksheet":
   - Rename them: `RAW_DATA`, `LOOKUP_TABLES`, `SUMMARY`, `PIVOT_ANALYSIS`, `DASHBOARD`

### Step 1.3 — Set Up the RAW_DATA Sheet

Click on the `RAW_DATA` tab. Create these column headers in **Row 1**:

| A | B | C | D | E | F | G | H |
|---|---|---|---|---|---|---|---|
| Trans_ID | Date | Vendor_Name | Dept_Code | Category_Code | Amount | Description | Approved_By |

**Format the headers:**
1. Select Row 1 (click the "1" on the left)
2. Bold it: `Ctrl + B`
3. Fill color: Home → Fill Color → choose dark blue
4. Font color: White
5. Freeze Row 1: View → Freeze Panes → Freeze Top Row

### Step 1.4 — Enter Practice Data

Type (or copy) this data starting from Row 2:

```
Trans_ID | Date       | Vendor_Name        | Dept_Code | Cat_Code | Amount   | Description              | Approved_By
T001     | 01-01-2025 | Amazon AWS         | TECH      | IT       | 45000    | Cloud hosting Jan        | Rahul Mehta
T002     | 02-01-2025 | IndiGo Airlines    | SALES     | TRVL     | 18500    | Mumbai-Delhi flight      | Priya Sharma
T003     | 03-01-2025 | Zomato             | HR        | MEAL     | 4200     | Team lunch               | Ankit Joshi
T004     | 05-01-2025 | Google Ads         | MKT       | ADV      | 75000    | Jan digital campaign     | Sita Patel
T005     | 06-01-2025 | WeWork             | ADMIN     | RENT     | 120000   | Office rent Jan          | CFO
T006     | 07-01-2025 | Slack              | TECH      | SW       | 8500     | Monthly subscription     | Rahul Mehta
T007     | 08-01-2025 | Ola                | SALES     | TRVL     | 2200     | Client meeting cab       | Priya Sharma
T008     | 10-01-2025 | Adobe Creative     | MKT       | SW       | 5500     | Design tools sub         | Sita Patel
T009     | 12-01-2025 | Taj Hotels         | SALES     | TRVL     | 32000    | Client visit hotel       | Priya Sharma
T010     | 14-01-2025 | LinkedIn           | HR        | RECR     | 22000    | Job posting fee          | Ankit Joshi
T011     | 15-01-2025 | Amazon AWS         | TECH      | IT       | 38000    | Extra compute Jan        | Rahul Mehta
T012     | 16-01-2025 | Festive Catering   | HR        | MEAL     | 18000    | Quarterly team offsite   | Ankit Joshi
T013     | 18-01-2025 | Facebook Ads       | MKT       | ADV      | 40000    | Social media campaign    | Sita Patel
T014     | 20-01-2025 | HDFC Insurance     | ADMIN     | INS      | 55000    | Office insurance Q1      | CFO
T015     | 22-01-2025 | Notion             | TECH      | SW       | 3200     | Team workspace sub       | Rahul Mehta
T016     | 24-01-2025 | Make My Trip       | SALES     | TRVL     | 14000    | Bangalore visit          | Priya Sharma
T017     | 25-01-2025 | Times of India     | MKT       | ADV      | 25000    | Print ad Jan             | Sita Patel
T018     | 26-01-2025 | Airtel Broadband   | ADMIN     | UTIL     | 6500     | Office internet          | CFO
T019     | 28-01-2025 | Naukri.com         | HR        | RECR     | 15000    | Resume database access   | Ankit Joshi
T020     | 30-01-2025 | Zoom               | TECH      | SW       | 4100     | Video conferencing       | Rahul Mehta
```

**Add 30 more rows** by repeating similar data for February and March (change dates to 01-02-2025 through 28-03-2025, vary vendors and amounts slightly).

> **Pro Tip:** To quickly fill dates, type 2 dates → select both → drag the fill handle (small square at bottom-right of selection) downward.

### Step 1.5 — Set Up the LOOKUP_TABLES Sheet

Click on `LOOKUP_TABLES` tab. Create TWO lookup tables:

**Table 1: Department Lookup** (starts at Cell A1)

| Dept_Code | Department_Name | Head | Budget_Monthly |
|-----------|----------------|------|---------------|
| TECH | Technology | Rahul Mehta | 150000 |
| SALES | Sales | Priya Sharma | 100000 |
| MKT | Marketing | Sita Patel | 200000 |
| HR | Human Resources | Ankit Joshi | 80000 |
| ADMIN | Administration | CFO | 250000 |

**Table 2: Category Lookup** (starts at Cell G1)

| Cat_Code | Category_Name | Expense_Type |
|----------|--------------|--------------|
| IT | Information Technology | Variable |
| TRVL | Travel & Conveyance | Variable |
| MEAL | Meals & Entertainment | Variable |
| ADV | Advertising & Marketing | Variable |
| RENT | Rent & Facilities | Fixed |
| SW | Software Subscriptions | Semi-Variable |
| RECR | Recruitment | Variable |
| INS | Insurance | Fixed |
| UTIL | Utilities | Semi-Variable |

**Name your ranges** (this is professional practice):
1. Select A1:D6 (Department table) → Name Box (top-left, shows "A1") → type `dept_table` → Enter
2. Select G1:I10 (Category table) → Name Box → type `cat_table` → Enter

---

## Day 2: VLOOKUP — Complete Tutorial

### ⏱ Time Required: 60–90 minutes

### What is VLOOKUP?
VLOOKUP (**V**ertical **Lookup**) searches for a value in the **leftmost column** of a table and returns a value from a specified column in the same row.

```
=VLOOKUP(lookup_value, table_array, col_index_num, [range_lookup])
       │               │             │               │
       │               │             │               └─ FALSE = exact match (always use this)
       │               │             └─ Which column to return? (1=first, 2=second...)
       │               └─ The lookup table range
       └─ What are you looking up?
```

### Step 2.1 — Add Department Name Column Using VLOOKUP

1. Go to `RAW_DATA` sheet
2. Click on **Cell I1** → Type: `Department_Name`
3. Click on **Cell I2** → Type this formula:

```excel
=VLOOKUP(D2, LOOKUP_TABLES!$A$2:$D$6, 2, FALSE)
```

**Breaking it down:**
- `D2` = the Dept_Code in this row (e.g., "TECH")
- `LOOKUP_TABLES!$A$2:$D$6` = the department table on the other sheet ($ locks it)
- `2` = return column 2 (Department_Name)
- `FALSE` = exact match only

4. Press **Enter** → you should see "Technology"
5. Click I2 again → double-click the **fill handle** (small square, bottom-right of cell) to copy formula down to all rows

### Step 2.2 — Add Category Name Column

1. Click on **Cell J1** → Type: `Category_Name`
2. Click on **Cell J2** → Type:

```excel
=VLOOKUP(E2, LOOKUP_TABLES!$G$2:$I$10, 2, FALSE)
```

3. Press Enter → should show "Information Technology"
4. Copy down to all rows

### Step 2.3 — Add Expense Type Column

1. Click on **Cell K1** → Type: `Expense_Type`
2. Click on **Cell K2** → Type:

```excel
=VLOOKUP(E2, LOOKUP_TABLES!$G$2:$I$10, 3, FALSE)
```

3. This returns "Variable", "Fixed", or "Semi-Variable"
4. Copy down

### Step 2.4 — Add Monthly Budget Per Transaction

1. Click on **Cell L1** → Type: `Dept_Monthly_Budget`
2. Click on **Cell L2** → Type:

```excel
=VLOOKUP(D2, LOOKUP_TABLES!$A$2:$D$6, 4, FALSE)
```

3. This brings in the monthly budget for each department

### ✅ VLOOKUP Practice Exercise

Try these on your own (answers below):
1. Write a VLOOKUP to find the Department Head for each transaction
2. Write a VLOOKUP that returns "Fixed" if Cat_Code is "RENT"
3. What happens if you type a Dept_Code that doesn't exist? (Try "FINANCE")

**Answers:**
1. `=VLOOKUP(D2, LOOKUP_TABLES!$A$2:$D$6, 3, FALSE)` — col 3 = Head
2. `=VLOOKUP("RENT", LOOKUP_TABLES!$G$2:$I$10, 3, FALSE)` — returns "Fixed"
3. You get `#N/A` error → wrap in IFERROR: `=IFERROR(VLOOKUP(...),"Not Found")`

### Step 2.5 — Handle Errors Gracefully with IFERROR

Upgrade all your VLOOKUPs to handle errors:

```excel
=IFERROR(VLOOKUP(D2, LOOKUP_TABLES!$A$2:$D$6, 2, FALSE), "Unknown Dept")
```

**This is professional practice** — real financial models always handle errors.

---

## Day 3: SUMIF & SUMIFS — Complete Tutorial

### ⏱ Time Required: 60 minutes

### What is SUMIF?
SUMIF adds up values in a range that **meet a single condition**.

```
=SUMIF(range, criteria, sum_range)
        │       │          │
        │       │          └─ Which column to add?
        │       └─ What condition? (e.g., "TECH", ">10000")
        └─ Which column to check the condition in?
```

### What is SUMIFS?
SUMIFS adds values meeting **multiple conditions** simultaneously.

```
=SUMIFS(sum_range, criteria_range1, criteria1, criteria_range2, criteria2, ...)
```

### Step 3.1 — Go to SUMMARY Sheet

Click the `SUMMARY` tab. Build this layout:

**Section 1: Department-wise Total Spend** (Row 1 onward)

| A | B | C | D |
|---|---|---|---|
| **Department** | **Total Spend (₹)** | **Monthly Budget (₹)** | **Variance (₹)** |
| Technology | [formula] | 150000 | [formula] |
| Sales | [formula] | 100000 | [formula] |
| Marketing | [formula] | 200000 | [formula] |
| Human Resources | [formula] | 80000 | [formula] |
| Administration | [formula] | 250000 | [formula] |
| **TOTAL** | [formula] | [formula] | [formula] |

### Step 3.2 — Write SUMIF for Department Totals

Click on **B2** (Technology row, Total Spend column):

```excel
=SUMIF(RAW_DATA!$D:$D, "TECH", RAW_DATA!$F:$F)
```

**Breaking it down:**
- `RAW_DATA!$D:$D` = look in Column D of RAW_DATA (Dept_Code)
- `"TECH"` = where this matches "TECH"
- `RAW_DATA!$F:$F` = add up Column F (Amount)

**For other departments** (change the criteria):
- Sales: `=SUMIF(RAW_DATA!$D:$D, "SALES", RAW_DATA!$F:$F)`
- Marketing: `=SUMIF(RAW_DATA!$D:$D, "MKT", RAW_DATA!$F:$F)`
- HR: `=SUMIF(RAW_DATA!$D:$D, "HR", RAW_DATA!$F:$F)`
- Admin: `=SUMIF(RAW_DATA!$D:$D, "ADMIN", RAW_DATA!$F:$F)`

**Pro tip:** Instead of hardcoding "TECH", reference the cell: `=SUMIF(RAW_DATA!$D:$D, A2, RAW_DATA!$F:$F)` then use a helper column with Dept codes.

### Step 3.3 — Calculate Variance

In **D2**: `=C2 - B2`
- Positive = under budget (good)
- Negative = over budget (alert!)

Add conditional formatting for color coding:
1. Select D2:D6
2. Home → Conditional Formatting → New Rule
3. "Format only cells that contain" → Cell Value → less than → 0 → Format → Fill Red
4. Add another rule → greater than 0 → Fill Green

### Step 3.4 — SUMIFS: Multi-Condition Totals

**Section 2: Department + Category Cross-Analysis**

Add to SUMMARY sheet (below Section 1, around Row 12):

| | IT | TRVL | MEAL | ADV | RENT | SW | RECR |
|---|---|---|---|---|---|---|---|
| TECH | [formula] | | | | | | |
| SALES | | [formula] | | | | | |
| MKT | | | | [formula] | | | |

Click on the cell at TECH/IT intersection:

```excel
=SUMIFS(RAW_DATA!$F:$F, RAW_DATA!$D:$D, "TECH", RAW_DATA!$E:$E, "IT")
```

**Breaking it down:**
- `RAW_DATA!$F:$F` = add up Amount column
- `RAW_DATA!$D:$D, "TECH"` = Condition 1: Dept must be TECH
- `RAW_DATA!$E:$E, "IT"` = Condition 2: Category must be IT

### Step 3.5 — SUMIF with Date Range Using SUMIFS

**Section 3: Monthly Trend** (add below Section 2)

| Month | Total Expense |
|-------|--------------|
| January 2025 | [formula] |
| February 2025 | [formula] |
| March 2025 | [formula] |

For January (assuming dates are in Column B of RAW_DATA):

```excel
=SUMIFS(RAW_DATA!$F:$F, RAW_DATA!$B:$B, ">="&DATE(2025,1,1), RAW_DATA!$B:$B, "<="&DATE(2025,1,31))
```

For February:
```excel
=SUMIFS(RAW_DATA!$F:$F, RAW_DATA!$B:$B, ">="&DATE(2025,2,1), RAW_DATA!$B:$B, "<="&DATE(2025,2,28))
```

### ✅ SUMIF Practice Exercises

Try these:
1. Total spend on Travel (TRVL) only — across all departments
2. Total spend above ₹20,000 per transaction
3. Total spend by Priya Sharma (Approved_By column)

**Answers:**
1. `=SUMIF(RAW_DATA!$E:$E, "TRVL", RAW_DATA!$F:$F)`
2. `=SUMIF(RAW_DATA!$F:$F, ">20000", RAW_DATA!$F:$F)`
3. `=SUMIF(RAW_DATA!$H:$H, "Priya Sharma", RAW_DATA!$F:$F)`

---

## Day 4: Pivot Tables — Complete Tutorial

### ⏱ Time Required: 90 minutes

### What is a Pivot Table?
A Pivot Table lets you **summarize, group, and analyze** large datasets dynamically — without writing a single formula. It's the most powerful Excel feature for financial analysts.

### Step 4.1 — Create Your First Pivot Table

1. Go to `RAW_DATA` sheet
2. Click any cell inside your data (e.g., A2)
3. Go to: **Insert → PivotTable**
4. In the dialog:
   - Table/Range: should auto-fill (verify it covers all your data)
   - "New Worksheet" → OK
5. Rename the new sheet: `PIVOT_ANALYSIS`

### Step 4.2 — Understand the Pivot Table Builder

On the right side, you'll see the **PivotTable Fields** panel:
```
┌─ Fields List ────────────────────┐
│ ☐ Trans_ID                       │
│ ☐ Date                           │
│ ☐ Vendor_Name                    │
│ ☐ Dept_Code                      │
│ ☐ Category_Code                  │
│ ☐ Amount                         │
│ ☐ Department_Name    (VLOOKUP)   │
│ ☐ Category_Name      (VLOOKUP)   │
│ ☐ Expense_Type       (VLOOKUP)   │
└──────────────────────────────────┘

┌─ Areas ──────────────────────────┐
│  FILTERS     │  COLUMNS          │
│              │                   │
│  ROWS        │  VALUES           │
│              │                   │
└──────────────────────────────────┘
```

### Step 4.3 — Build Pivot Table 1: Department Summary

Drag fields to these areas:
- **ROWS:** Department_Name
- **VALUES:** Amount (drag twice)
  - First Amount: summarize by **Sum** (right-click → Value Field Settings → Sum)
  - Second Amount: Show as **% of Grand Total** (right-click → Show Values As → % of Grand Total)
- **FILTERS:** (leave empty for now)

Your table should look like:
```
Department      | Sum of Amount | % of Total
----------------|---------------|----------
Administration  | 1,81,500      | 23.1%
Human Resources | 59,200        | 7.5%
Marketing       | 1,45,500      | 18.5%
Sales           | 66,700        | 8.5%
Technology      | 98,800        | 12.6%
Grand Total     | 7,86,800      | 100%
```

### Step 4.4 — Build Pivot Table 2: Category Breakdown

1. Click somewhere below your first pivot table (leave 3 rows gap)
2. Insert → PivotTable → same data range → "Existing Worksheet" → pick an empty cell

Drag:
- **ROWS:** Category_Name
- **COLUMNS:** Department_Name (or Dept_Code)
- **VALUES:** Sum of Amount

This creates a **cross-tab** — every department's spend by category type.

### Step 4.5 — Build Pivot Table 3: Monthly Trend

1. Insert another Pivot Table (existing worksheet)

Drag:
- **ROWS:** Date → Excel will offer to **Group by Month** → right-click the date row → "Group" → select "Months" → OK
- **VALUES:** Sum of Amount

You now have month-by-month expense totals automatically!

### Step 4.6 — Add Slicers (Interactive Filters)

Slicers are clickable buttons that filter your pivot tables interactively.

1. Click inside any Pivot Table
2. PivotTable Analyze → Insert Slicer
3. Check: Department_Name, Category_Name, Expense_Type → OK
4. Move slicers to a clean area of the sheet
5. To connect a slicer to multiple pivot tables:
   - Right-click the slicer → Report Connections → check all your pivot tables → OK

Now clicking "Technology" in the slicer filters ALL pivot tables at once!

### Step 4.7 — Pivot Table Formatting Tips

1. **Number format:** Right-click any number → Format Cells → Number → Use 1000 separator, 0 decimal places
2. **Rename column headers:** Click "Sum of Amount" cell → type your own name (e.g., "Total Spend ₹")
3. **Design:** Click inside Pivot → PivotTable Design tab → choose a style (recommended: "PivotStyle Medium 9" — classic blue)
4. **Grand Totals:** PivotTable Design → Grand Totals → "On for Rows and Columns"

### ✅ Pivot Table Exercises

1. Find the **top 3 vendors** by total spend
2. Find which month had the **highest travel expense**
3. Calculate what **% of total spend** is Fixed vs. Variable vs. Semi-Variable

**Hints:**
1. Rows = Vendor_Name, Values = Sum of Amount → sort descending
2. Rows = Date (grouped by Month), Columns = Category_Name, filter/slicer for TRVL
3. Rows = Expense_Type, Values = Amount as % of Grand Total

---

## Day 5: Build the Expense Tracker (Part 1)

### ⏱ Time Required: 90 minutes

### Step 5.1 — Design the SUMMARY Sheet Layout

Go to `SUMMARY` sheet. Create this professional layout:

**Row 1–3: Header Block**
```
Cell A1: "COMPANY EXPENSE TRACKER"     → Font size 20, Bold, Merged A1:H1
Cell A2: "Q1 FY 2025 | All Departments"  → Font size 12, Italic
Cell A3: "Last Updated: [today's date]"  → Use =TODAY() formula
```

**Row 5–6: KPI Cards (Key Performance Indicators)**

Create 4 side-by-side boxes using cell borders:

| | A–B | C–D | E–F | G–H |
|-|-----|-----|-----|-----|
| Row 5 | Total Spend | Over-Budget Depts | Largest Expense | Savings Opportunity |
| Row 6 | =SUM formula | =COUNTIF formula | =MAX formula | Manual entry |

For Total Spend in B6:
```excel
=SUM(RAW_DATA!F:F)
```

For count of over-budget departments (D column has variance):
```excel
=COUNTIF(D12:D16,"<0")
```

### Step 5.2 — Build the Budget vs. Actual Table

Below the KPIs (Row 9 onward), build this table:

| Dept | Jan Budget | Jan Actual | Jan Var | Jan Var% | Feb Budget | Feb Actual | ... |
|------|-----------|-----------|---------|---------|-----------|-----------|-----|
| Technology | 150,000 | [SUMIFS] | [formula] | [formula] | ... | ... | |
| Sales | 100,000 | [SUMIFS] | | | | | |
| Marketing | 200,000 | [SUMIFS] | | | | | |
| HR | 80,000 | [SUMIFS] | | | | | |
| Admin | 250,000 | [SUMIFS] | | | | | |
| **Total** | [SUM] | [SUM] | [SUM] | | | | |

For Technology, January Actual:
```excel
=SUMIFS(RAW_DATA!$F:$F, RAW_DATA!$D:$D, "TECH", RAW_DATA!$B:$B, ">="&DATE(2025,1,1), RAW_DATA!$B:$B, "<="&DATE(2025,1,31))
```

Variance formula: `= Budget - Actual`
Variance %: `= Variance / Budget * 100`

### Step 5.3 — Apply Conditional Formatting

**Color the Variance % column:**
1. Select the Variance % column cells
2. Home → Conditional Formatting → Color Scales → Red-White-Green
   - Red = worst (most over budget)
   - Green = best (under budget or on track)

**Add icon sets to Variance column:**
1. Select variance value cells
2. Home → Conditional Formatting → Icon Sets → "3 Traffic Lights"
3. Edit rule: Red if <-10%, Yellow if between -10% and 0%, Green if >0%

---

## Day 6: Build the Expense Tracker (Part 2 — Charts & Dashboard)

### ⏱ Time Required: 90 minutes

### Step 6.1 — Create Chart 1: Department Spend Bar Chart

1. Go to `SUMMARY` sheet
2. Select Department Names (A column) and Total Spend (B column) — hold Ctrl to select non-adjacent columns
3. Insert → Bar Chart → "Clustered Bar"
4. **Customize it:**
   - Chart Title: "Q1 FY2025 — Department-wise Spend"
   - Right-click bars → "Format Data Series" → choose a professional color (blue shades)
   - Add Data Labels: Chart Design → Add Chart Element → Data Labels → Outside End
   - Delete the legend (unnecessary for single series)
   - Format Y-axis: right-click → Format Axis → Number → Custom → `₹##,##,###`

### Step 6.2 — Create Chart 2: Category Pie Chart

1. Select Category_Name and total per category (from your SUMIF section)
2. Insert → Pie Chart → "Pie" (2D)
3. **Customize:**
   - Chart Title: "Expense by Category — Q1 2025"
   - Right-click pie → "Add Data Labels" → check "Percentage" and "Category Name"
   - Move labels outside: Format Data Labels → "Outside End"
   - Explode the biggest slice: click it twice (slowly) → drag outward slightly

### Step 6.3 — Create Chart 3: Monthly Trend Line Chart

1. Select Month column and Total Expense column from your monthly SUMIFS section
2. Insert → Line Chart → "Line with Markers"
3. **Customize:**
   - Chart Title: "Monthly Expense Trend — Q1 2025"
   - Right-click the line → "Format Data Series" → Line color: Orange, Width: 2.5pt
   - Add markers: same dialog → Marker → Built-in → Circle, size 8
   - Add a "Target Line": right-click chart → Select Data → Add Series → flat line at your total budget

### Step 6.4 — Build the DASHBOARD Sheet

Go to `DASHBOARD` tab. This is your final presentation sheet.

**Layout plan:**
```
┌────────────────────────────────────────────────────────────────┐
│  COMPANY EXPENSE DASHBOARD — Q1 FY 2025             [logo]    │
├──────────────┬──────────────┬──────────────┬───────────────────┤
│ Total Spend  │ Budget       │ Variance     │ Over-Budget Depts │
│ ₹7,86,800   │ ₹7,80,000   │ ▲ ₹6,800    │ 2 of 5            │
├──────────────┴──────────────┴──────────────┴───────────────────┤
│                                                                │
│   [Bar Chart: Dept Spend]        [Pie Chart: Category Mix]    │
│                                                                │
├────────────────────────────────────────────────────────────────┤
│                                                                │
│   [Line Chart: Monthly Trend]    [Key Findings Text Box]      │
│                                                                │
└────────────────────────────────────────────────────────────────┘
```

**Steps to build dashboard:**
1. Set background color: Select all cells (Ctrl+A) → Fill Color → Light Gray (#F2F2F2)
2. Create white "card" boxes using cell borders with white fill
3. **Move charts** from other sheets: right-click chart → "Move Chart" → "Object in: DASHBOARD"
4. Resize and arrange charts to fit the layout above
5. Add text boxes (Insert → Text Box) for KPI values that link to SUMMARY:
   - Click text box → go to formula bar → type `=SUMMARY!B6` → this links the text box to the cell

### Step 6.5 — Final Polish

- [ ] Hide gridlines: View → uncheck "Gridlines"
- [ ] Add your name and date in the footer: Insert → Header & Footer
- [ ] Protect the sheet (so formulas don't get accidentally deleted):
  - Review → Protect Sheet → set a password
- [ ] Test: change one Amount in RAW_DATA → verify all charts and summaries update automatically

---

## Day 7: Review & Polish

### ⏱ Time Required: 60 minutes

### Final Checklist — Your Expense Tracker

- [ ] RAW_DATA has 50+ transactions across 3 months
- [ ] VLOOKUP columns auto-populate Department Name, Category Name, Expense Type
- [ ] IFERROR handles any lookup errors gracefully
- [ ] SUMMARY shows Budget vs. Actual with conditional formatting
- [ ] SUMIFS calculates by dept + month correctly
- [ ] Pivot Table 1: Department totals with % breakdown
- [ ] Pivot Table 2: Cross-tab of Dept × Category
- [ ] Pivot Table 3: Monthly trend grouped by date
- [ ] Slicers connected to all pivot tables
- [ ] 3 Charts: Bar (dept), Pie (category), Line (trend)
- [ ] DASHBOARD is clean, presentable, and all numbers link to formulas
- [ ] File saved and backup copy created

### Additional Excel Functions to Explore This Week

| Function | What It Does | Example |
|----------|-------------|---------|
| `AVERAGEIF` | Average if condition met | `=AVERAGEIF(D:D,"TECH",F:F)` |
| `COUNTIF` | Count rows meeting a condition | `=COUNTIF(D:D,"TECH")` |
| `INDEX/MATCH` | More flexible than VLOOKUP | `=INDEX(B:B,MATCH("TECH",D:D,0))` |
| `MAXIFS` | Max value with conditions | `=MAXIFS(F:F,D:D,"TECH")` |
| `TEXT` | Format numbers/dates as text | `=TEXT(B2,"MMM YYYY")` |
| `IF` | Conditional logic | `=IF(F2>50000,"High","Normal")` |

---

---

# WEEK 3 — REAL COMPANY ANALYSIS

---

## Week 3 Overview

### What You'll Do
Perform a **complete professional financial analysis** on a real Indian IT company using their published annual report — exactly as a junior analyst at a bank, consulting firm, or investment company would.

### Company Options (Choose 1)
| Company | Ticker | Why It's Good for Beginners | Complexity |
|---------|--------|---------------------------|------------|
| **Infosys** | INFY | Clean financials, well-structured AR | ⭐ Easy |
| **Wipro** | WIPRO | Similar structure, good for comparison | ⭐ Easy |
| **TCS** | TCS | India's largest IT; very detailed | ⭐⭐ Medium |
| **HCL Technologies** | HCLTECH | Good for expense deep-dive | ⭐⭐ Medium |

**Recommendation for beginners: Start with Infosys.**

### What You'll Produce
```
FY2025_Infosys_Financial_Analysis.xlsx
├── Sheet 1: RAW_DATA        ← P&L data extracted from annual report
├── Sheet 2: VERTICAL        ← Common-size (%) analysis
├── Sheet 3: HORIZONTAL      ← YoY growth analysis  
├── Sheet 4: RATIOS          ← Key financial ratios
└── Sheet 5: DASHBOARD       ← Charts and visual summary
```

---

## 📥 Annual Report Download Links

### Infosys (Recommended — Start Here)
| Document | Year | Direct Link |
|----------|------|-------------|
| Annual Report FY2024 | 2023–24 | https://www.infosys.com/investors/reports-filings/annual-report/annual/documents/2024/ar-2024.pdf |
| Annual Report FY2023 | 2022–23 | https://www.infosys.com/investors/reports-filings/annual-report/annual/documents/2023/ar-2023.pdf |
| Annual Report FY2022 | 2021–22 | https://www.infosys.com/investors/reports-filings/annual-report/annual/documents/2022/ar-2022.pdf |
| All Reports Archive | Multiple | https://www.infosys.com/investors/reports-filings/annual-report.html |

### TCS
| Document | Direct Link |
|----------|------------|
| Annual Reports Hub | https://www.tcs.com/investors/reports-and-filings/annual-reports |
| FY2024 Annual Report | https://www.tcs.com/content/dam/tcs/investor-relations/financial-statements/2023-24/ar/tcs-integrated-annual-report-2023-2024.pdf |

### Wipro
| Document | Direct Link |
|----------|------------|
| Annual Reports Hub | https://www.wipro.com/investors/annual-reports/ |
| FY2024 Annual Report | https://www.wipro.com/content/dam/nexus/en/investors/annual-reports/2023-2024/wipro-annual-report-2023-24.pdf |

### Free Financial Data Databases (Alternative to PDFs)
| Source | What It Has | Link |
|--------|------------|------|
| **Screener.in** | 10-year financial data, P&L, balance sheet — FREE | https://www.screener.in/company/INFY/consolidated/ |
| **Moneycontrol** | P&L, Balance Sheet, Cash Flow (5 years) | https://www.moneycontrol.com/financials/infosys/profit-lossVI/IT#VI |
| **Tijori Finance** | Detailed financials + segment data | https://tijorifinance.com/company/infosys-ltd/ |
| **NSE India** | Official filings, quarterly results | https://www.nseindia.com/get-quotes/equity?symbol=INFY |
| **BSE India** | Official investor relations filings | https://www.bseindia.com/stock-share-price/infosys-ltd/INFY/500209/ |
| **Capitaline** | Professional-grade database (paid, some free) | https://www.capitaline.com |

> **💡 Beginner Tip:** Use **Screener.in** — it has pre-formatted 10-year P&L data that you can copy directly into Excel. This saves hours of PDF extraction.

---

## Day 8: Download Annual Reports & Understand Structure

### ⏱ Time Required: 60–90 minutes

### Step 8.1 — Download the Reports

1. Download Infosys FY2024 Annual Report (link above)
2. Download Infosys FY2023 Annual Report (for comparison)
3. Save both as:
   - `Infosys_AR_FY2024.pdf`
   - `Infosys_AR_FY2023.pdf`

### Step 8.2 — Navigate the Annual Report

An annual report has many sections. As an analyst, focus on these:

| Section | Where to Find | What It Contains |
|---------|--------------|-----------------|
| **Management Discussion & Analysis (MD&A)** | First 40–60 pages | Business context, risks, outlook |
| **Standalone P&L** | Financial Statements section | India entity only |
| **Consolidated P&L** | ★ Use this one | Entire global company |
| **Balance Sheet** | After P&L | Assets, liabilities |
| **Cash Flow Statement** | After Balance Sheet | Cash generation |
| **Notes to Accounts** | After financial statements | Expense breakdowns, segment data |

**For expense analysis, go to:**
- Consolidated Statement of Profit & Loss
- Notes on "Employee Benefit Expense" (largest expense)
- Notes on "Other Expenses" (detailed breakdown)
- Segment Reporting (Revenue and expense by geography/service)

### Step 8.3 — Understand the P&L Structure

A typical IT company P&L looks like this:

```
CONSOLIDATED STATEMENT OF PROFIT & LOSS
(₹ in Crores)                        FY2024    FY2023

REVENUE
  Revenue from Operations            153,670   146,767

EXPENSES
  Employee Benefit Expense            91,791    89,002
  Cost of Software Packages            4,213     3,892
  Travel Expenses                      2,456     1,987
  Communication Expenses               1,234     1,156
  Facility Running Expenses            3,789     3,456
  Depreciation & Amortization          4,567     4,123
  Finance Costs                          234       198
  Other Expenses                       8,901     8,234
  Total Expenses                     117,185   112,048

PROFIT BEFORE TAX (PBT)               36,485    34,719
  Tax Expense                          8,765     8,321
NET PROFIT (PAT)                      27,720    26,248
```

### Step 8.4 — Create Your Data Extraction Template

Open Excel → New file → save as `Infosys_FY2025_Analysis.xlsx`

Create 5 sheets: `RAW_DATA`, `VERTICAL`, `HORIZONTAL`, `RATIOS`, `DASHBOARD`

Go to `RAW_DATA`. Build this header structure:

| A | B | C | D | E |
|---|---|---|---|---|
| Line_Item | Category | FY2024 (₹ Cr) | FY2023 (₹ Cr) | FY2022 (₹ Cr) |

---

## Day 9: Extract Financial Data into Excel

### ⏱ Time Required: 90 minutes

### Step 9.1 — Use Screener.in (Fastest Method)

1. Go to: https://www.screener.in/company/INFY/consolidated/
2. Scroll to "Profit & Loss" section
3. You'll see 10 years of data in a clean table
4. Click **"Export to Excel"** button (top right of the P&L table) — FREE after signup
5. This gives you clean, pre-formatted data

### Step 9.2 — Manual Entry from Annual Report (Deep Learning Method)

If you want to learn to read actual annual reports, manually type this data (from Infosys FY2024 Annual Report, Consolidated P&L — approximate figures):

```
Line Item                    | Category      | FY2024  | FY2023  | FY2022
Revenue from Operations      | Revenue       | 153,670 | 146,767 | 121,641
Employee Benefit Expense     | Expense-OpEx  | 91,791  | 89,002  | 74,665
Cost of Software & Packages  | Expense-OpEx  | 4,213   | 3,892   | 2,987
Travel Expenses              | Expense-OpEx  | 2,456   | 1,987   | 987
Communication Expenses       | Expense-OpEx  | 1,234   | 1,156   | 1,045
Facility Running Expenses    | Expense-OpEx  | 3,789   | 3,456   | 3,123
Depreciation & Amortization  | Expense-D&A   | 4,567   | 4,123   | 3,876
Finance Costs                | Expense-Fin   | 234     | 198     | 178
Other Expenses               | Expense-OpEx  | 9,101   | 8,234   | 7,456
Total Expenses               | Expense-Total | 117,385 | 112,048 | 94,317
Profit Before Tax (PBT)      | Profit        | 36,285  | 34,719  | 27,324
Tax Expense                  | Tax           | 8,765   | 8,321   | 6,234
Net Profit (PAT)             | Profit-Net    | 27,520  | 26,398  | 21,090
```

> **Note:** These are illustrative figures for learning. Use the actual numbers from the downloaded annual report for real analysis.

### Step 9.3 — Add Computed Rows

Add these rows using formulas (you'll use them for analysis):

```
Gross Profit           = Revenue − (Employee Expense + Software Cost)
EBIT                   = Revenue − Total Expenses + Finance Costs
EBITDA                 = EBIT + Depreciation & Amortization
```

---

## Day 10: Perform Vertical Analysis

### ⏱ Time Required: 90 minutes

### What is Vertical Analysis?
Express every P&L line item as a **percentage of Revenue**. This creates a "common-size" P&L that allows you to:
- Compare expense structure across years
- Compare your company to competitors (regardless of size)
- Spot which costs are growing as a % of revenue

### Step 10.1 — Set Up the VERTICAL Sheet

Go to `VERTICAL` sheet. Build this structure:

**Column layout:**
| A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|
| Line_Item | FY24 ₹ Cr | FY24 % | FY23 ₹ Cr | FY23 % | FY22 ₹ Cr | FY22 % |

**Row layout:** (same line items as RAW_DATA)

### Step 10.2 — Link to RAW_DATA

In B2 (FY2024 amounts), link to RAW_DATA:
```excel
=RAW_DATA!C2
```

Copy this down for all rows.

For FY2023 (D column):
```excel
=RAW_DATA!D2
```

### Step 10.3 — Write the Vertical Analysis Formula

In **C2** (FY2024 percentage of Revenue):

```excel
=B2 / $B$2 * 100
```

- `B2` = This line item's amount
- `$B$2` = Revenue (Row 2, locked with $) — this is always the denominator
- `* 100` = convert to percentage

**The $ is critical.** It locks Row 2 (Revenue) as the denominator for ALL rows.

Copy C2 down to all rows. Then do the same for FY2023 and FY2022.

### Step 10.4 — Format the Results

1. Select all % columns → Format as Number with 1 decimal place
2. Add conditional formatting to highlight:
   - Employee Expense % > 60%: Orange (industry alert)
   - Net Margin % < 15%: Red (profitability concern)
   - Net Margin % > 20%: Green (strong profitability)

### Step 10.5 — Interpret Your Vertical Analysis

Your completed table should look like:

| Line Item | FY24 ₹ Cr | FY24 % | FY23 % | FY22 % | Trend |
|-----------|----------|--------|--------|--------|-------|
| Revenue | 153,670 | 100.0% | 100.0% | 100.0% | — |
| Employee Expense | 91,791 | 59.7% | 60.6% | 61.4% | ✅ Improving |
| Cost of Software | 4,213 | 2.7% | 2.6% | 2.5% | ⚠️ Slight rise |
| Travel | 2,456 | 1.6% | 1.4% | 0.8% | ⚠️ Rising fast |
| D&A | 4,567 | 3.0% | 2.8% | 3.2% | Stable |
| Total Expenses | 117,385 | 76.4% | 76.4% | 77.6% | ✅ Stable |
| **Net Profit** | **27,520** | **17.9%** | **18.0%** | **17.3%** | **✅ Stable** |

### Step 10.6 — Write Your Vertical Analysis Observations

After building the table, write observations in a text box or separate column:

```
KEY OBSERVATIONS — VERTICAL ANALYSIS

✅ POSITIVE:
• Employee costs have declined from 61.4% to 59.7% of revenue over 3 years
  → Indicates improving operational efficiency / automation impact
• Net margin is stable at ~18% despite global headwinds — strong profitability
• Total expense ratio improved from 77.6% to 76.4%

⚠️ WATCH:
• Travel expenses doubled as % of revenue (0.8% → 1.6%)
  → Post-COVID normalization, but should stabilize
• Software costs creeping up — cloud migration investments increasing

🔴 ALERT:
• None at this stage — Infosys shows healthy expense control
```

---

## Day 11: Perform Horizontal Analysis

### ⏱ Time Required: 90 minutes

### What is Horizontal Analysis?
Also called **YoY (Year-over-Year) analysis**. Measures how each line item **grew or shrank** from one period to the next in absolute and percentage terms.

```
YoY Change (₹)  = Current Year Value − Prior Year Value
YoY Change (%)  = (Current Year − Prior Year) ÷ Prior Year × 100
```

### Step 11.1 — Set Up HORIZONTAL Sheet

Go to `HORIZONTAL` sheet. Build:

| A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|
| Line_Item | FY2024 | FY2023 | FY2022 | YoY Chg FY24 (₹) | YoY Chg FY24 (%) | YoY Chg FY23 (%) |

### Step 11.2 — Link Data from RAW_DATA

```excel
B2 = =RAW_DATA!C2    (FY2024)
C2 = =RAW_DATA!D2    (FY2023)
D2 = =RAW_DATA!E2    (FY2022)
```

### Step 11.3 — Write Horizontal Analysis Formulas

**YoY Change in ₹ (Column E):**
```excel
=B2 - C2
```
(FY2024 minus FY2023)

**YoY Change in % (Column F):**
```excel
=(B2 - C2) / ABS(C2) * 100
```
(Use ABS to handle cases where prior year is negative)

**YoY Change FY23 vs FY22 (Column G):**
```excel
=(C2 - D2) / ABS(D2) * 100
```

Copy all formulas down.

### Step 11.4 — Add a CAGR Column (2-Year Compound Growth)

CAGR = Compound Annual Growth Rate — very commonly used in finance.

**Formula:**
```excel
= (B2/D2)^(1/2) - 1
```
- `B2/D2` = FY2024 ÷ FY2022 (total growth over 2 years)
- `^(1/2)` = square root (annualize over 2 years)
- `-1` = convert to growth rate
- Format as %

### Step 11.5 — Interpret Horizontal Analysis Results

| Line Item | FY2024 | FY2023 | FY2022 | YoY % | 2Y CAGR |
|-----------|--------|--------|--------|-------|---------|
| Revenue | 153,670 | 146,767 | 121,641 | +4.7% | +12.3% |
| Employee Exp | 91,791 | 89,002 | 74,665 | +3.1% | +10.8% |
| Travel | 2,456 | 1,987 | 987 | +23.6% | +57.7% |
| Software | 4,213 | 3,892 | 2,987 | +8.2% | +18.8% |
| **Net Profit** | **27,520** | **26,398** | **21,090** | **+4.2%** | **+14.3%** |

```
KEY OBSERVATIONS — HORIZONTAL ANALYSIS

✅ POSITIVE:
• Revenue grew 4.7% YoY, Net Profit grew 4.2% — broadly in line
• Employee cost grew SLOWER (3.1%) than revenue (4.7%) → Efficiency gain
• Net Profit 2Y CAGR of 14.3% indicates consistent compounding growth

⚠️ WATCH:
• Travel expenses surged 23.6% YoY and 57.7% CAGR — needs monitoring
• Software costs growing at 18.8% CAGR — faster than revenue growth

📌 ANALYST CONCLUSION:
  Revenue growth is slowing (4.7% vs. 20.6% prior year CAGR) but Infosys
  is managing expenses well. The compression in employee costs as % of revenue
  is the key driver of margin stability.
```

---

## Day 12: Ratio Analysis & KPIs

### ⏱ Time Required: 60 minutes

### Step 12.1 — Set Up RATIOS Sheet

Go to `RATIOS` sheet. Create a clean ratio dashboard.

### Step 12.2 — Calculate Key Ratios

Type each metric name and write the formula referencing RAW_DATA:

| Ratio | Formula in Excel | FY2024 | FY2023 | Interpretation |
|-------|-----------------|--------|--------|---------------|
| **Gross Margin %** | `=(Revenue-DirectCost)/Revenue*100` | ~40% | ~40% | Revenue after direct costs |
| **EBITDA Margin %** | `=EBITDA/Revenue*100` | ~26% | ~26% | Operating cash profitability |
| **Net Profit Margin %** | `=PAT/Revenue*100` | ~18% | ~18% | Bottom-line efficiency |
| **Expense Ratio** | `=TotalExpenses/Revenue*100` | ~76% | ~76% | % of revenue consumed |
| **Employee Cost %** | `=EmployeeCost/Revenue*100` | ~60% | ~61% | People cost efficiency |
| **Revenue per Employee** | `=Revenue/Headcount` | ~₹35L | ~₹33L | Productivity metric |
| **YoY Revenue Growth** | `=(FY24Rev-FY23Rev)/FY23Rev*100` | ~4.7% | ~20.6% | Top-line momentum |
| **YoY Profit Growth** | `=(FY24PAT-FY23PAT)/FY23PAT*100` | ~4.2% | ~25.0% | Bottom-line momentum |

### Step 12.3 — Industry Benchmarking Table

Add a comparison table below your ratios:

| Metric | Infosys FY24 | TCS FY24 | Wipro FY24 | IT Industry Avg |
|--------|-------------|---------|-----------|----------------|
| Net Margin | 17.9% | 19.1% | 11.2% | 15–20% |
| EBITDA Margin | 26.1% | 28.3% | 16.4% | 20–28% |
| Employee Cost % | 59.7% | 58.2% | 63.1% | 58–65% |
| Revenue Growth | 4.7% | 4.1% | 1.8% | 2–6% |

> Get TCS and Wipro data from Screener.in for accurate current figures.

---

## Day 13: Build Charts & Visual Dashboard

### ⏱ Time Required: 90 minutes

### Chart 1 — Revenue vs. Expense Trend (Clustered Bar)
- X-axis: FY2022, FY2023, FY2024
- Y-axis: ₹ Crores
- Series 1: Revenue (blue bars)
- Series 2: Total Expenses (orange bars)
- Series 3: Net Profit (green bars)
- This shows at a glance how the gap (profit) has grown

### Chart 2 — Expense Breakdown Waterfall
A waterfall chart shows how each expense component contributes to the whole.

1. Select your expense categories and amounts
2. Insert → Waterfall Chart
3. Right-click the "Total Expenses" bar → "Set as Total" (this makes it a summary bar)

### Chart 3 — Margin Trends Line Chart
- X-axis: FY2022, FY2023, FY2024
- Three lines: Gross Margin %, EBITDA Margin %, Net Margin %
- This shows profitability trends over time at a glance

### Chart 4 — Vertical Analysis Stacked Bar
- Shows expense components as % of revenue, stacked
- Allows you to see the expense MIX changing over years

### Step 13.4 — Build the DASHBOARD

Assemble all 4 charts + a KPI summary table into DASHBOARD sheet:

```
┌────────────────────────────────────────────────────────────────────────┐
│  INFOSYS FINANCIAL ANALYSIS DASHBOARD — FY2022 to FY2024     [Logo]   │
├───────────────┬───────────────┬───────────────┬────────────────────────┤
│ Revenue       │ Net Profit    │ Net Margin    │ Revenue Growth (YoY)   │
│ ₹1,53,670 Cr │ ₹27,520 Cr   │ 17.9%         │ 4.7%                   │
├───────────────┴───────────────┴───────────────┴────────────────────────┤
│  [Revenue vs Expense Bar]       │  [Expense Breakdown Waterfall]       │
│                                 │                                      │
├─────────────────────────────────┼──────────────────────────────────────┤
│  [Margin Trends Line]           │  [Vertical Analysis Stacked Bar]     │
│                                 │                                      │
└─────────────────────────────────┴──────────────────────────────────────┘
```

---

## Day 14: Write Your Analysis Report

### ⏱ Time Required: 90 minutes

### Step 14.1 — The 1-Page Analyst Report Structure

Create a new Word document or text box in Excel called `Analyst_Report_Infosys.docx`

Use this template:

```
═══════════════════════════════════════════════════════
FINANCIAL EXPENSE ANALYSIS REPORT
Company: Infosys Limited | Period: FY2022–FY2024
Analyst: [Your Name] | Date: [Today]
═══════════════════════════════════════════════════════

EXECUTIVE SUMMARY
Infosys maintained a stable expense structure in FY2024, with total expenses
consuming 76.4% of revenue (unchanged from FY2023), while delivering a net
profit margin of 17.9%. Key positive trend is declining employee cost ratio
(61.4% → 59.7%) indicating improving operational leverage.

───────────────────────────────────────────────────────

FINDING 1: Employee Costs — Positive Trend ✅
• Absolute: Rose from ₹74,665 Cr (FY22) to ₹91,791 Cr (FY24)
• As % of Revenue: DECLINED from 61.4% → 59.7%
• Meaning: Revenue grew faster than headcount/wage growth
• Implication: Positive sign of productivity improvement (automation, attrition management)

───────────────────────────────────────────────────────

FINDING 2: Travel Expenses — Accelerating Growth ⚠️
• 2Y CAGR: 57.7% — more than 4x faster than revenue growth (12.3%)
• As % of Revenue: Doubled from 0.8% → 1.6%
• Root cause: Post-COVID business travel resumption + geographic expansion
• Recommendation: Benchmark against peer travel spend; evaluate hybrid
  engagement models to cap travel growth at ≤10% per year going forward.

───────────────────────────────────────────────────────

FINDING 3: Revenue Growth Slowdown — Monitor 📊
• FY2023 revenue growth: 20.6% | FY2024: 4.7%
• Consistent with industry-wide IT spending slowdown (macro factors)
• Expense management has compensated — margins held stable at ~18%
• Recommendation: Watch Q1 FY2025 numbers for recovery signals

───────────────────────────────────────────────────────

OVERALL ASSESSMENT
Infosys demonstrates sound expense discipline. Despite revenue deceleration,
the company has improved its expense ratios across most categories. The main
area of concern (travel) is manageable and industry-wide. Infosys remains
above industry average on net margin (17.9% vs 15–20% range) and compares
favorably to Wipro (11.2%) while slightly trailing TCS (19.1%).

RATING: ✅ FINANCIALLY HEALTHY | EXPENSE MANAGEMENT: B+
═══════════════════════════════════════════════════════
```

---

## Week 3 — Final Checklist

- [ ] Downloaded at least 2 years of annual reports (or used Screener.in)
- [ ] Extracted 3 years of P&L data into RAW_DATA sheet
- [ ] Vertical analysis completed with % of revenue for all line items
- [ ] Horizontal analysis completed with YoY % and CAGR
- [ ] CAGR formula working correctly
- [ ] Ratio analysis: 8+ ratios calculated and benchmarked vs. peers
- [ ] 4 charts built (bar, waterfall, line, stacked)
- [ ] Dashboard assembled with KPI cards
- [ ] 1-page analyst report written with 3 findings + overall rating
- [ ] Saved file as `Infosys_FY2024_Financial_Analysis.xlsx`

---

## Additional Resources for Weeks 2 & 3

### Excel Learning
| Resource | Link | Best For |
|---------|------|---------|
| Excel Easy (Free) | https://www.excel-easy.com | VLOOKUP, Pivot Tables step-by-step |
| Chandoo.org | https://chandoo.org/wp/ | Financial Excel tutorials |
| ExcelJet | https://exceljet.net/functions | Every Excel function explained |
| Microsoft Excel Help | https://support.microsoft.com/en-us/excel | Official documentation |
| Leila Gharani (YouTube) | https://www.youtube.com/@LeilaGharani | Best Excel YouTube channel |
| Excel Campus (YouTube) | https://www.youtube.com/@ExcelCampus | Pivot tables & dashboards |

### Financial Analysis Learning
| Resource | Link | Best For |
|---------|------|---------|
| Screener.in Tutorial | https://www.screener.in/explore/ | How to read Indian financials |
| Prof. Damodaran's Site | https://pages.stern.nyu.edu/~adamodar/ | Free valuation datasets + tools |
| CFA Institute Blog | https://blogs.cfainstitute.org | Industry-standard techniques |
| NSE Academy | https://www.nseindia.com/education | Indian capital markets education |
| SEBI Investor Education | https://investor.sebi.gov.in | Regulatory framework |

### Practice Datasets (Additional)
| Dataset | Link | Size |
|---------|------|------|
| Kaggle Finance Datasets | https://www.kaggle.com/datasets?search=finance | 1000s of datasets |
| UCI Machine Learning Repository | https://archive.ics.uci.edu | Clean structured datasets |
| World Bank Open Data | https://data.worldbank.org | Macro-economic data |
| RBI Data Warehouse | https://dbie.rbi.org.in | Indian banking & finance data |
| CMIE Prowess | https://prowess.cmie.com | Indian corporate financial data |

---

## Summary: What You've Learned in 2 Weeks

```
╔══════════════════════════════════════════════════════════╗
║               YOUR SKILLS AFTER WEEK 2 & 3              ║
╠══════════════════════════════════════════════════════════╣
║ WEEK 2 — EXCEL SKILLS                                    ║
║  ✅ VLOOKUP — auto-populate fields from lookup tables    ║
║  ✅ IFERROR — handle errors professionally               ║
║  ✅ SUMIF — sum by a single condition                    ║
║  ✅ SUMIFS — sum by multiple conditions + date ranges    ║
║  ✅ Pivot Tables — dynamic data summarization            ║
║  ✅ Slicers — interactive filtering                      ║
║  ✅ Charts — Bar, Pie, Line, Waterfall                   ║
║  ✅ Dashboard — executive-ready visual summary           ║
╠══════════════════════════════════════════════════════════╣
║ WEEK 3 — REAL COMPANY ANALYSIS                           ║
║  ✅ Reading Annual Reports — know what to look for       ║
║  ✅ Data Extraction — from PDF/Screener into Excel       ║
║  ✅ Vertical Analysis — common-size % of revenue         ║
║  ✅ Horizontal Analysis — YoY growth & CAGR              ║
║  ✅ Ratio Analysis — 8 key financial ratios              ║
║  ✅ Benchmarking — compare vs. peers                     ║
║  ✅ Analyst Report — STAR-format findings                ║
╠══════════════════════════════════════════════════════════╣
║ YOU ARE NOW READY FOR:                                   ║
║  → Week 4: Full expense report presentation              ║
║  → Entry-level financial analyst interviews              ║
║  → Building models for real business decisions           ║
╚══════════════════════════════════════════════════════════╝
```

---

*Document Version 1.0 | Financial Analyst Bootcamp — Week 2 & 3 Guide*
*Created for beginner financial analysts | May 2025*
*Always verify links and data from official sources before use in professional work.*
