## TOPIC: SUMPRODUCT(), TABLES & STRUCTURED REFERENCE
## DATE: 26-08-2026

---

### **SUMPRODUCT, Excel Tables & Structured References**

A practical, beginner-friendly guide to using SUMPRODUCT(), Excel Tables, and Structured References for data analysis.

📑 Table of Contents
* SUMPRODUCT
* SUMPRODUCT with Conditions
* SUMPRODUCT with Multiple Conditions
* Excel Tables
* Benefits of Excel Tables
* Structured References
* Current Row References
* Calculated Columns
* SUMIFS with Structured References
* Key Takeaways

---

1. SUMPRODUCT
What is SUMPRODUCT?

SUMPRODUCT() multiplies corresponding values from two or more ranges and then adds the results together.

Syntax

```excel
=SUMPRODUCT(array1, array2)
```

---

Basic Example

Suppose we have:

| Product | Quantity |  Price |
| ------- | -------: | -----: |
| Whisky  |        5 | 25,000 |
| Gin     |        3 | 18,000 |
| Vodka   |        4 | 22,000 |


We can calculate total revenue using:

```excel
=SUMPRODUCT(B2:B4,C2:C4)
```

Excel performs:

```excel
(5 × 25,000)
+ (3 × 18,000)
+ (4 × 22,000)
```

Result:

```excel
₦286,000
```

Why use SUMPRODUCT?

Without SUMPRODUCT(), you might create a separate Revenue column:

```excel
=B2*C2
```

and then calculate:

```excel
=SUM(D2:D4)
```

SUMPRODUCT() allows you to perform the multiplication and addition in one formula.

---

2. SUMPRODUCT with Conditions

SUMPRODUCT() can also be used with logical conditions.

Example

Calculate revenue only for products where Quantity is greater than or equal to 4.

```excel
=SUMPRODUCT((B2:B5>=4)*B2:B5*C2:C5)
```

The condition:

```excel
(B2:B5>=4)
```

produces TRUE/FALSE results.

SUMPRODUCT() effectively treats them as:

```excel
TRUE  → 1
FALSE → 0
```

Therefore, rows that don't meet the condition contribute nothing to the calculation.

General Pattern

```excel
=SUMPRODUCT((condition)*calculation)
```

---

3. SUMPRODUCT with Multiple Conditions

SUMPRODUCT() can evaluate multiple conditions at the same time.

Example

Calculate discounted revenue where Quantity is at least 3 and Discount is 10% or less.

Assume:

B = Quantity
C = Price
D = Discount

Formula:

```excel
=SUMPRODUCT(
    (B2:B5>=3)*
    (D2:D5<=10%)*
    B2:B5*
    C2:C5*
    (1-D2:D5)
)
```

The calculation is essentially:

```excel
IF Quantity >= 3
AND Discount <= 10%

THEN

Quantity × Price × (1 - Discount)
```

General Pattern

```excel
=SUMPRODUCT(
    (condition1)*
    (condition2)*
    calculation
)
```

---

Revenue After Discount

A simpler example:

```excel
=SUMPRODUCT(B2:B5,C2:C5*(1-D2:D5))
```

This calculates:

```excel
Quantity × Price × (1 - Discount)
```
This calculates:

```excel
Quantity × Price × (1 - Discount)
```

for each row and returns the total.

---

Common Uses of SUMPRODUCT

SUMPRODUCT() is useful for:

* Sales calculations
* Revenue calculations
* Discount calculations
* Weighted calculations
* Inventory analysis
* Financial analysis
* Conditional calculations

---

4. Excel Tables

What is an Excel Table?

An Excel Table converts a normal dataset into a structured and dynamic dataset.

Tables make datasets easier to manage, analyze, and reference.

---

Creating an Excel Table

1.Select your dataset.
2. Press:

```excel
Ctrl + T
```

3. Confirm:

My table has headers

4. Click OK.

Excel will convert the selected range into a Table.

---

Naming the Table

After creating the Table, give it a meaningful name.

For example:

```excel
SalesData
```

Instead of the default:

```excel
Table1
```

A meaningful name makes formulas easier to understand.

---

5. Benefits of Excel Tables

Excel Tables are particularly useful for datasets that are regularly updated.

1. Automatic Expansion

When new rows are added, Excel automatically includes them in the Table.

2. Automatic Formulas

When you create a calculated column, Excel automatically applies the formula to the other rows.

3. Built-in Filtering

Tables automatically provide dropdown filters for each column.

4. Easier Formulas

Instead of:

```excel
=SUM(D2:D500)
```

you can use:

```excel
=SUM(SalesData[Revenue])
```
The second formula is easier to understand.

5. Works Well with Other Excel Tools

Tables integrate well with:

* PivotTables
* Charts
* Formulas
* Structured References
* Data analysis

---

6. Structured References
What are Structured References?

Structured References allow you to refer to Excel Table columns using their column names rather than traditional cell ranges.

---

Traditional Cell Reference

```excel
=SUM(D2:D500)
```

This refers to a specific range of cells.

---

Structured Reference

```excel
=SUM(SalesData[Revenue])
```

This means:

Sum the entire Revenue column in the SalesData Table.

Structure

```excel
TableName[ColumnName]
```

Example:

```excel
SalesData[Revenue]
```

---

Another Example

If your Table is called SalesData and contains:

```excel
Product
Department
Quantity
Price
Revenue
```

You can reference the entire Quantity column using:

```excel
SalesData[Quantity]
```

---

7. Current Row References

Excel Tables also allow you to reference a value from the current row using the @ symbol.

Example

```excel
=[@Quantity]*[@Price]
```

Here:

```excel
[@Quantity]
```

means:

Quantity from the current row.

And:

```excel
[@Price]
```

means:

Price from the current row.

---

Entire Column vs Current Row

This is an important distinction.

Entire Column

```excel
SalesData[Revenue]
```

Means:

Every value in the Revenue column.

Current Row

```excel
[@Revenue]
```

Means:

Revenue for the current row.

Easy Way to Remember

```excel
SalesData[Revenue]
        ↓
   Entire column
```

```excel
SalesData[Revenue]
        ↓
   Entire column
```

```excel
[@Revenue]
    ↓
Current row
```

---

8. Calculated Columns

A calculated column is a Table column where a formula is automatically applied to every row.

Suppose your Table contains:

| Product | Quantity |  Price | Revenue |
| ------- | -------: | -----: | ------: |
| Whisky  |        5 | 25,000 |         |
| Gin     |        3 | 18,000 |         |
| Vodka   |        4 | 22,000 |         |

In the Revenue column:

```excel
=[@Quantity]*[@Price]
```

Excel automatically fills the formula down the entire column.

---

Revenue After Discount

Suppose we also have a Discount column.

Formula:

```excel
=[@Quantity]*[@Price]*(1-[@Discount])
```

This calculates:

```excel
Quantity × Price × (1 - Discount)
```

Example

If:

```excel
Quantity = 5
Price = ₦25,000
Discount = 10%
```

Then:

```excel
5 × 25,000 × (1 - 10%)
```

Result:

```excel
₦112,500
```

---

9. SUMIFS with Structured References

Structured References work very well with functions such as SUMIFS().

Example

Calculate total Revenue generated by the Sales department.

```excel
=SUMIFS(
    SalesData[Revenue],
    SalesData[Department],
    "Sales"
)
```

---

Multiple Criteria

Example:

Calculate Revenue for the Sales department where Quantity is at least 5.

```excel
=SUMIFS(
    SalesData[Revenue],
    SalesData[Department],"Sales",
    SalesData[Quantity],">=5"
)
```

This means:

```excel
Add → Revenue

Where → Department = Sales

AND → Quantity >= 5
```

---


10. Key Takeaways
SUMPRODUCT

Use:

```excel
=SUMPRODUCT(array1,array2)
```

when you need to multiply corresponding values and return their total.

It can also handle conditions:

```excel
=SUMPRODUCT((condition)*calculation)
```

---

Excel Tables

Create a Table using:

```excel
Ctrl + T
```

Tables provide:

* Automatic expansion
* Automatic formulas
* Built-in filtering
* Easier data management
* Structured References
* Better integration with PivotTables and charts

---

Structured References
Entire column

```excel
SalesData[Revenue]
```

Current row

```excel
[@Revenue]
```

Calculated column

```excel
=[@Quantity]*[@Price]
```

Conditional analysis

```excel
=SUMIFS(
    SalesData[Revenue],
    SalesData[Department],"Sales",
    SalesData[Quantity],">=5"
)
```
