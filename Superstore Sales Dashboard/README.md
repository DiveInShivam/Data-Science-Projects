# 📊 Superstore Sales Performance Dashboard — Excel Project

An end-to-end Excel analytics project built on the **Sample Superstore dataset** (8,399 real sales transactions from 2009–2012). The workbook transforms raw data into an interactive, multi-sheet dashboard covering sales trends, regional performance, product analysis, and shipping efficiency.

---

## 📁 Repository Contents

| File | Description |
|---|---|
| `Superstore_Sales_Dashboard.xlsx` | Main Excel workbook (7 sheets, 183 formulas) |
| `README.md` | Project documentation |

---

## 🗂️ Dataset Details

| Attribute | Value |
|---|---|
| **Source** | Sample Superstore Dataset (Kaggle / Tableau Public) |
| **Rows** | 8,399 orders |
| **Columns** | 25 (21 original + 4 derived) |
| **Time Period** | 2009 – 2012 |
| **Geography** | 8 regions across Canada |
| **Categories** | Furniture, Office Supplies, Technology |

### Derived Columns Added
- `Days_to_Ship` — Ship Date minus Order Date
- `Net_Sales` — Sales × (1 − Discount)
- `Profit_Margin_%` — Profit / Sales × 100
- `Year`, `Quarter`, `Month` — extracted from Order Date

---

## 📋 Workbook Structure

### Sheet 1 — Raw_Data
- All 8,399 rows with 25 columns
- Freeze panes on header row
- Zebra striping for readability
- **Conditional formatting:** color scale on Profit column (red → yellow → green)

### Sheet 2 — Executive_Dashboard
- **5 KPI Cards:** Total Sales, Total Profit, Profit Margin %, Total Orders, Avg Order Value
- **Region breakdown table:** Sales, Profit, Margin % per region using `SUMIF`
- **Category breakdown table:** Sales, Profit, Margin % per category
- **Customer Segment table:** Sales, Profit, Orders per segment

### Sheet 3 — Yearly_Trend
- Year-over-year comparison (2009–2012)
- Metrics: Total Sales, Total Profit, Margin %, Orders, Avg Order Value
- **YoY Growth %** calculated for both Sales and Profit
- **Color scale** on growth column (red = decline, green = growth)
- **Line chart:** Annual sales trend visualization

### Sheet 4 — Category_Region
- **Cross-tab pivot matrix** — Product Category × Region using `SUMPRODUCT`
- Grand totals for rows and columns
- **Heat-map conditional formatting** — darker blue = higher sales
- **Stacked bar chart:** Sales by category per region

### Sheet 5 — Shipping_Analysis
- **Ship Mode performance:** Orders, Sales, Profit, Avg Shipping Cost, Avg Days to Ship
- **Order Priority breakdown:** Sales and Profit by priority level
- **Pie chart:** Order distribution by ship mode

### Sheet 6 — Top_Products
- **Top 10 products by Total Sales** — with category and profit
- **Top 10 products by Total Profit** — negative profits highlighted in red
- Hardcoded from Python analysis, ready to present in interviews

### Sheet 7 — Data_Dictionary
- Every column documented with: data type, description, and a real example value
- Demonstrates professional data documentation practices

---

## 🔧 Excel Skills Demonstrated

| Skill | Where Used |
|---|---|
| `SUMIF` | Regional & category breakdowns |
| `SUMPRODUCT` (multi-criteria) | Category × Region pivot matrix |
| `AVERAGEIF` | Shipping cost & days per mode |
| `COUNTIF` / `COUNTA` | Order counts across all sheets |
| `IFERROR` | Division-by-zero protection |
| Conditional Formatting — Color Scale | Profit column, YoY growth, heat map |
| Freeze Panes | Raw_Data header row |
| Line Chart | Annual sales trend |
| Stacked Bar Chart | Category × Region |
| Pie Chart | Ship mode distribution |
| Number Formatting | Currency ($), percentage (%), decimals |
| Zebra Striping | All analysis sheets |
| Data Dictionary | Sheet 7 |
| Derived Column Calculation | Net Sales, Margin %, Days to Ship |

---

## 💡 Key Insights from the Data

- **Technology** is the highest revenue category but **Office Supplies** has the most orders
- **Regular Air** is the dominant shipping mode, used in the majority of orders
- **Ontario** and **West** are the top-performing regions by total sales
- Several high-selling products still generate **negative profit** due to heavy discounting
- Sales show a **consistent growth trend** from 2009 to 2012

---

## 🚀 How to Use

1. Download `Superstore_Sales_Dashboard.xlsx`
2. Open in **Microsoft Excel** (2016 or later recommended)
3. Start on the **Executive_Dashboard** tab for a high-level overview
4. Navigate to individual sheets for deeper analysis
5. All formulas are live and reference the Raw_Data sheet

> **Note:** Google Sheets may not render all conditional formatting and charts correctly. Microsoft Excel is recommended.

---



## 📄 License

Dataset: Sample Superstore is a publicly available dataset originally distributed by Tableau.  
This project (workbook design, analysis, and documentation) is open for educational and portfolio use.
