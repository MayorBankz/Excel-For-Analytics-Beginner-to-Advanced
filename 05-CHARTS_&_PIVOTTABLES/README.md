## TOPIC: Charts & PivotTables
## DATE: 27-08-2026

---

### Charts & PivotTables

A practical, beginner-friendly guide to turning Excel data into visualizations and useful summaries.

---

📑 Table of Contents

1. Excel Charts
2. Creating a Chart
3. Line Charts
4. Column/Bar Charts
5. Pie/Donut Charts
6. Scatter Plots
7. Choosing the Right Chart
8. PivotTables
9. Creating a PivotTable
10. PivotTable Areas
11. Rows
12. Values
13. Columns
14. Filters
15. Real-World PivotTable Examples
16. Key Takeaways

---

1. Excel Charts
What is a Chart?

A chart is a visual representation of data.

Instead of looking at a table full of numbers, charts make patterns, comparisons, and trends easier to understand.

For example:


| Product |    Revenue |
| ------- | ---------: |
| Whisky  | ₦5,000,000 |
| Gin     | ₦3,500,000 |
| Vodka   | ₦2,800,000 |

A chart can make it immediately obvious which product generated the most revenue.

---

Why Use Charts?

Charts are useful for:

* Comparing categories
* Identifying trends
* Showing proportions
* Identifying relationships
* Presenting reports
* Communicating business insights
* Important principle

Don't choose a chart because it looks nice. Choose it because it answers a question clearly.

---

2. Creating a Chart

A basic chart workflow is:

* Select the relevant dataset.
* Go to the Insert tab.
* Select the appropriate chart type.
* Add or edit the chart title.
* Format the chart if necessary.

---

Example

Suppose we have:

| Product | Revenue |
| ------- | ------: |
| Whisky  |      5M |
| Gin     |    3.5M |
| Vodka   |    2.8M |

---

Select the two columns:

Product + Revenue

```excel
Product + Revenue
```

Then:

Insert → Chart

Excel will use:

* Product → Category/Axis
* Revenue → Values

---

3. Line Charts
   
What is a Line Chart?

A Line Chart connects data points with lines to show how values change.

| Month    | Revenue |
| -------- | ------: |
| January  |     ₦2M |
| February |   ₦2.5M |
| March    |   ₦2.2M |
| April    |     ₦3M |

A Line Chart makes the movement of Revenue from month to month easy to see.

---

When to Use a Line Chart

Use a Line Chart when you want to answer questions such as:

* Is sales increasing?
* Is revenue declining?
* What is the monthly trend?
* How has performance changed over time?

Common use cases

* Monthly sales
* Annual revenue
* Profit trends
* Website traffic
* Production volume
🧠 Mental Shortcut

Trend over time → Line Chart

Line charts are particularly useful for showing trends over time.

---

4. Column/Bar Charts

What are Column and Bar Charts?

Column and Bar Charts are primarily used to compare categories.

Example:

| Product | Revenue |
| ------- | ------: |
| Whisky  |     ₦5M |
| Gin     |   ₦3.5M |
| Vodka   |   ₦2.8M |
| Brandy  |   ₦1.9M |

A Column or Bar Chart makes it easy to see which product has the highest revenue.

---

Column vs Bar
Column Chart

Bars are displayed vertically.

```excel
  █
  █     █
  █     █
  █  █  █
────────────
 A  B  C
```

Bar Chart

Bars are displayed horizontally.

```excel
A ███████████
B ███████
C █████
```

Both are useful for comparing categories.

---

When to Use Column/Bar Charts

Useful for:

* Sales by product
* Revenue by department
* Sales by region
* Customers by city
* Profit by branch
🧠 Mental Shortcut

Compare categories → Bar/Column Chart

---

5. Pie/Donut Charts
   
What is a Pie Chart?

A Pie Chart divides a circle into sections to show how different categories contribute to a whole.

Example:

| Department | Employees |
| ---------- | --------: |
| Sales      |        25 |
| IT         |        10 |
| Finance    |         8 |
| HR         |         7 |


A Pie Chart can show each department's share of the total workforce.

---

Donut Chart

A Donut Chart works similarly to a Pie Chart but has a hole in the center.

Both are useful for displaying proportions.

---

When to Use Pie/Donut Charts

Use them when the question is:

"What percentage/share of the total does each category represent?"

Examples:

* Market share
* Revenue contribution
* Budget allocation
* Employee distribution

🧠 Mental Shortcut

Parts of a whole → Pie/Donut

---

⚠️ Avoid Too Many Categories

Pie and Donut Charts become difficult to read when there are many categories.

For many categories, a Bar/Column Chart is often easier to understand.

---

6. Scatter Plots
   
What is a Scatter Plot?

A Scatter Plot displays individual points based on two numerical variables.

It is mainly used to investigate whether there is a relationship between two variables.

---

Example

Suppose we want to investigate:

```excel
Advertising Spend ↔ Sales Revenue
```

| Advertising |     Sales |
| ----------: | --------: |
|     100,000 | 1,200,000 |
|     200,000 | 1,600,000 |
|     300,000 | 2,100,000 |
|     400,000 | 2,500,000 |

A Scatter Plot can help us visually investigate whether higher advertising spending is associated with higher sales.

---

Other Examples

Scatter Plots can be used for:

* Price vs Quantity Sold
* Experience vs Salary
* Advertising vs Revenue
* Temperature vs Sales
* Study Hours vs Exam Score
🧠 Mental Shortcut

Relationship between two numerical variables → Scatter Plot

---

7. Choosing the Right Chart

| Question                                       | Recommended Chart |
| ---------------------------------------------- | ----------------- |
| How did sales change over time?                | **Line**          |
| Which product generated the most revenue?      | **Bar/Column**    |
| What percentage does each category contribute? | **Pie/Donut**     |
| Is advertising related to sales?               | **Scatter**       |

---

🧠 The Chart Selection Rule

Before creating a chart, ask:

"What question am I trying to answer?"

Then choose the chart.

```excel
Trend over time
       ↓
    LINE

Compare categories
       ↓
  BAR / COLUMN

Parts of a whole
       ↓
  PIE / DONUT

Relationship between numbers
       ↓
   SCATTER
```

---

8. PivotTables
What is a PivotTable?

A PivotTable is an Excel tool used to quickly summarize and analyze large datasets.

Instead of manually writing many formulas, you can drag fields into different areas and allow Excel to summarize the information.

---

Questions PivotTables Can Answer

For example:

* What are total sales by department?
* Which product generated the most revenue?
* What is the average sales per employee?
* How many customers are in each city?
* What are sales by region?
* What is the total quantity sold by product?

---

9. Creating a PivotTable

Recommended Process

If your dataset is not already a Table:

Step 1

Select the entire dataset.

Step 2

Press:

```excel
Ctrl + T
```

Check:

My table has headers

Then click OK.

Step 3

Go to:

Insert → PivotTable

Step 4

Excel will identify the Table/range.

Step 5

Choose where you want the PivotTable to appear.

Step 6

Click OK.

You will now see the PivotTable Fields panel.

---

10. PivotTable Areas

A PivotTable has four major areas:

```excel
┌─────────────────────────────┐
│           FILTERS           │
├─────────────────────────────┤
│           COLUMNS           │
├─────────────────────────────┤
│             ROWS            │
├─────────────────────────────┤
│            VALUES           │
└─────────────────────────────┘
```

Each area has a different purpose.

---

11. Rows

The Rows area determines how you want to group your data.

Example

Suppose your dataset contains:

```
Employee
Department
Sales
```

If you place:

```excel
Department → Rows
```

Excel might produce:

| Department |
| ---------- |
| Finance    |
| HR         |
| Marketing  |
| Sales      |

Each department becomes a group.

---

🧠 Mental Shortcut

ROWS = What am I grouping by?

---

12. Values

The Values area determines what you want Excel to calculate.

For example:

```excel
Sales → Values
```

Excel may automatically use:

```excel
Sum of Sales
```

You could get:

| Department      |   Sum of Sales |
| --------------- | -------------: |
| Finance         |       ₦200,000 |
| HR              |       ₦150,000 |
| Marketing       |       ₦300,000 |
| Sales           |       ₦750,000 |
| **Grand Total** | **₦1,400,000** |

---

🧠 Mental Shortcut

VALUES = What am I calculating?

---

13. Columns

The Columns area creates an additional grouping across the columns of the PivotTable.

Example

Suppose your data contains:

```excel
Department
Month
Sales
```

You could use:

```excel
Department → Rows
Month → Columns
Sales → Values
```

This could produce a summary like:

| Department |  Jan |  Feb |  Mar |
| ---------- | ---: | ---: | ---: |
| Sales      | 200K | 250K | 300K |
| Marketing  | 100K | 150K | 180K |

This allows you to compare departments across months.

---

🧠 Mental Shortcut

COLUMNS = What additional category do I want across the table?

---

14. Filters

The Filters area allows you to control which records are included in the PivotTable.

Example

Suppose your dataset contains:

```excel
Region
Department
Sales
```

You could place:

```excel
Region → Filters
Department → Rows
Sales → Values
```

Then you can select a specific region and see the Sales breakdown by Department for that region.

---

🧠 Mental Shortcut

FILTERS = What subset of the data do I want to analyze?

---

🧠 The PivotTable Mental Model

Whenever you receive a PivotTable question, break it down into four questions:

1. What am I grouping by?

→ ROWS

2. What am I calculating?

→ VALUES

3. Do I need another category across the table?

→ COLUMNS

4. Do I want to restrict the data?

→ FILTERS

---

Example
Business Question:

"What is the total Sales for each Department?"

Think:

```excel
Department → ROWS
Sales      → VALUES
```

---

Business Question:

"What are monthly Sales for each Department?"

Think:

```excel
Department → ROWS
Month      → COLUMNS
Sales      → VALUES
```

15. Real-World PivotTable Examples
Example 1 — Sales by Department

Question:

What is total Sales by Department?

Setup:

```excel
ROWS
→ Department

VALUES
→ Sales
```

---

Example 2 — Revenue by Product

Question:

What is total Revenue generated by each Product?

Setup:

```excel
ROWS
→ Product

VALUES
→ Revenue
```

---

Example 3 — Monthly Sales by Department

Question:

How much did each Department sell each month?

Setup:

```excel
ROWS
→ Department

COLUMNS
→ Month

VALUES
→ Sales
```

---

Example 4 — Sales by Department for One Region

Question:

What are Sales by Department in Lagos?

Setup:

```excel
Example 4 — Sales by Department for One Region

Question:

What are Sales by Department in Lagos?

Setup:
```

Then select:

```excel
Region = Lagos
```

---

### Key Takeaways

📈 Charts
Line

Shows trends over time

```excel
Time → Line
```

Bar/Column

Compares categories.

```excel
Categories → Bar/Column
```

Pie/Donut

Shows parts of a whole.

```excel
Parts of Whole → Pie/Donut
```

Scatter

Shows relationships between two numerical variables.

```excel
Numerical Relationship → Scatter
```

---

📊 PivotTables
Rows

What am I grouping by?

Values

What am I calculating?

Columns

What additional category do I want across the table?

Filters

What subset of the data do I want to analyze?

---

🧠 Final Mental Model

                 DATASET
                    │
          ┌─────────┴─────────┐
          ↓                   ↓
       CHARTS             PIVOTTABLE
          │                   │
          ↓                   ↓
   Visual Analysis       Data Summary
          │                   │
     ┌────┼────┐        ┌─────┼─────┐
     ↓    ↓    ↓        ↓     ↓     ↓
   Trend Compare Share  Rows Values Columns
                        │
                        ↓
                     Filters

The overall Excel analysis workflow you've learned is:


RAW DATA
   ↓
EXCEL TABLE
   ↓
SORT / FILTER
   ↓
CONDITIONAL FORMATTING
   ↓
PIVOTTABLE
   ↓
CHART
   ↓
BUSINESS INSIGHT



