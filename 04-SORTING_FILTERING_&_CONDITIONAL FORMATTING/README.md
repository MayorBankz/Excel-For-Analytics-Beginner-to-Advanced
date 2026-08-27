## TOPIC: Sorting, Filtering & Conditional Formatting
## DATE: 27-08-26

---

## **Sorting, Filtering & Conditional Formatting**

A practical, beginner-friendly guide to organizing datasets, finding relevant records, and visually highlighting important information in Excel.

---

📑 Table of Contents

* Sorting
* Filtering
* Multiple Filters
* Sorting and Filtering Together
* Conditional Formatting
* Highlight Cells Rules
* Top/Bottom Rules
* Data Bars
* Color Scales
* Removing Conditional Formatting
* Real-World Applications
* Key Takeaways

---

1. Sorting

What is Sorting?

Sorting changes the order in which data is displayed.

For example, a Sales column can be arranged from highest to lowest.

Example

Original:

| Employee | Sales |
| -------- | ----: |
| John     |   150 |
| Mary     |    80 |
| David    |   200 |
| Sarah    |   120 |

After sorting Largest to Smallest:

| Employee | Sales |
| -------- | ----: |
| David    |   200 |
| John     |   150 |
| Sarah    |   120 |
| Mary     |    80 |

---

Sort Largest to Smallest

To arrange numerical values from highest to lowest:

Column dropdown → Sort Largest to Smallest

Example:

```excel
200
150
120
80
```

---

Sort Smallest to Largest

To arrange numerical values from lowest to highest:

Column dropdown → Sort Smallest to Largest

Example:

```excel
80
120
150
200
```

---

Sorting Text

Sorting also works with text.

A → Z

Arranges text alphabetically:

```excel
Abuja
Ibadan
Lagos
```

Z → A

Arranges text in reverse alphabetical order:

```excel
Lagos
Ibadan
Abuja
```

⚠️ Important Rule When Sorting

When sorting a dataset, the entire row should move together.

For example:

| Employee | Department | Sales |
| -------- | ---------- | ----: |
| John     | Sales      |   150 |
| Mary     | Marketing  |    80 |


If Sales is sorted, the Employee and Department information must remain connected to the correct Sales value.

Never accidentally sort one column independently when the data belongs to a complete dataset.

---

2. Filtering

What is Filtering?

Filtering allows you to display only rows that meet specific conditions.

Filtering does not delete the other records. It temporarily hides rows that don't meet the criteria.

---

Example

Dataset:

| Employee | Department | Sales |
| -------- | ---------- | ----: |
| John     | Sales      |   150 |
| Mary     | Marketing  |    80 |
| David    | Sales      |   200 |
| Sarah    | HR         |   120 |

---

If you filter:

```excel
Department = Sales
```

Excel displays:

| Employee | Department | Sales |
| -------- | ---------- | ----: |
| John     | Sales      |   150 |
| David    | Sales      |   200 |

Mary and Sarah are still part of the dataset; they are simply hidden by the filter.

---

How to Filter

* Click the dropdown beside the relevant column.
* Uncheck Select All if necessary.
* Select the value(s) you want.
* Click OK.

---

3. Multiple Filters

You can apply multiple filters to the same dataset.

Example

Show employees from the Sales department whose sales are at least 150.

Apply:

```excel
Department = Sales
AND
Sales >= 150
```

Steps

Step 1

Filter Department:

```excel
Sales
```

Step 2

Open the Sales dropdown.

Select:

Number Filters → Greater Than or Equal To

Enter:

```excel
150
```
The resulting records satisfy both conditions.

---

Understanding the Logic

Multiple filters generally work like an AND condition:

```excel
Department = Sales
       AND
Sales >= 150
```

Only rows that satisfy both conditions remain visible.

---

4. Sorting and Filtering Together

Sorting and filtering can be used together to perform quick analysis.

Example

Show only Sales employees and arrange them from highest Sales to lowest.

Step 1 — Filter

Filter:

```excel
Department → Sales
```

Step 2 — Sort

Sort:

```excel
Sales → Largest to Smallest
```

Result

You now see only Sales employees, ranked by their Sales performance.

---

🧠 Easy Way to Remember

FILTER = What do I want to see?

SORT = How do I want to arrange what I see?

---

5. Conditional Formatting

What is Conditional Formatting?

Conditional Formatting automatically changes the appearance of cells when they meet specified conditions.

It allows you to identify important information quickly without manually checking every value.

---

Common Uses

Conditional Formatting can help identify:

High sales
Low sales
Top performers
Poor performers
Values above targets
Values below targets
Patterns
Relative differences

---

6. Highlight Cells Rules

Highlight Cells Rules allow you to format cells based on their values.

---

Greater Than or Equal To
Example

Highlight Sales greater than or equal to 100.

Steps:

Conditional Formatting → Highlight Cells Rules → Greater Than or Equal To

Enter:

```excel
100
```

Then select the desired formatting and click OK.

---

Less Than
Example

Highlight Sales below 100.

Steps:

Conditional Formatting → Highlight Cells Rules → Less Than

Enter:

```excel
100
```

Then click OK.

---

Other Highlight Cells Rules

Excel also provides options such as:

Greater Than
Less Than
Between
Equal To
Text That Contains
A Date Occurring
Duplicate Values

These are useful for quickly identifying specific values or records.

---

7. Top/Bottom Rules

Top/Bottom Rules allow you to identify the highest or lowest values in a dataset.

---

Top 10 Items

Despite the name, you can change the number of items.

Example

Highlight the top 3 Sales values.

Steps:

* Select the Sales range.
* Go to Conditional Formatting.
* Select Top/Bottom Rules.
* Select Top 10 Items.

Change:

```excel
10 → 3
```

* Select the desired formatting.
* Click OK.

Excel highlights the three highest values.

---

Real-World Applications

Useful for identifying:

* Top salespeople
* Best-performing products
* Highest-revenue customers
* Best-performing branches
* Top-performing territories

---

8. Data Bars

What are Data Bars?

Data Bars add horizontal bars inside cells to represent the relative size of each value.

Example:

```excel
50     █████
100    ██████████
150    ███████████████
200    ████████████████████
```

The larger the value, the longer the bar.

---

### **How to Apply Data Bars**

* Select the numerical range.
* Go to Conditional Formatting.
* Select Data Bars.
* Choose a style.

---

### **When to Use Data Bars**

Data Bars are useful for comparing:

* Sales
* Revenue
* Profit
* Quantity
* Performance scores
* Production volume

They provide a quick visual comparison without requiring a separate chart.

---

9. Color Scales

What are Color Scales?

Color Scales use different shades to represent the relative size of values.

A typical 3-color scale represents:

```excel
Low → Medium → High
```

---

### **How to Apply Color Scales**

* Select the numerical range.
* Go to Conditional Formatting.
* Select Color Scales.
* Choose a 3-Color Scale.

Excel automatically applies the scale based on the relative values.

---

## When to Use Color Scales

Useful for:

* Sales performance
* Revenue analysis
* Employee scores
* Financial data
* Large datasets
* Identifying high and low values

---

10. Removing Conditional Formatting

Sometimes you may want to remove a conditional formatting rule.

* Clear Selected Cells
* Select the affected cells.
* Go to Conditional Formatting.
* Select Clear Rules.
* Choose:

Clear Rules from Selected Cells

---

Clear Entire Sheet

To remove all conditional formatting from the worksheet:

Conditional Formatting → Clear Rules → Clear Rules from Entire Sheet

⚠️ Be careful with this option because it removes all conditional formatting rules on the worksheet.

---

11. Real-World Applications

Sorting, filtering, and conditional formatting are commonly used together in business analysis.

Example Business Request

"Show only Lagos sales representatives, rank them by Sales, and highlight anyone below target."

You could solve this with:

Step 1 — Filter

```excel
City = Lagos
```

Step 2 — Sort

```excel
Sales → Largest to Smallest
```

Step 3 — Conditional Formatting

```excel
Sales → Less Than Target
```

---

Example Workflow

```excel
Raw Dataset
     ↓
Filter
     ↓
Sort
     ↓
Conditional Formatting
     ↓
Identify Important Records
     ↓
Make Business Decision
```

This is a simple but realistic Excel analysis workflow.

---

12. Key Takeaways
Sorting

Changes the order of your data.

Examples:

```excel
Largest → Smallest
Smallest → Largest
A → Z
Z → A
```

---

Filtering

Controls which rows are visible.

Example:

```excel
Department = Sales
```

---

Conditional Formatting

Automatically highlights data based on rules or values.

---

Highlight Cells Rules

Use when you want to identify specific values.

```excel
Sales >= 100
Sales < 100
```

---

Top/Bottom Rules

Use when you want to identify high or low performers.

```excel
Top 3
Bottom 5
```

---

Data Bars

Use when you want to visually compare the magnitude of values.

```excel
50    █████
100   ██████████
200   ████████████████████
```

Color Scales

Use when you want to visualize:

Low → Medium → High

