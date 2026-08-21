## TOPIC : LOGICAL, CONDITIONAL & LOOKUP FUNCTIONS
## DATE: 21-08-2026

---

## **📁 Table of Contents**
1. IF Function
2. Nested IF
3. IFS Function
4. AND Function
5. OR Function
6. COUNTIF
7. SUMIF
8. AVERAGEIF
9. COUNTIFS
10. SUMIFS
11. AVERAGEIFS
12. XLOOKUP
13. Absolute, Relative & Mixed References
14. Combining Functions
15. Common Mistakes
16. Quick Reference
17. Real-World Applications

---

1. **IF Function**

IF() is used to make a decision based on whether a condition is TRUE or FALSE.
Syntax

=IF(condition, value_if_true, value_if_false)

Example

If sales are 100 or more, classify the employee as "Good":

=IF(B2>=100,"Good","Needs Improvement")

If B2 = 120:

120 >= 100 → TRUE

Result:

Good

If B2 = 80:

80 >= 100 → FALSE

Result:

Needs Improvement
Basic structure
IF
├── Condition
├── What to return if TRUE
└── What to return if FALSE

---

2. Nested IF

A nested IF() is an IF() placed inside another IF().

It is useful when there are multiple possible outcomes.

Example

Suppose:

* Sales >= 150 → Excellent
* Sales >= 100 → Good
* Sales < 100 → Needs Improvement

=IF(B2>=150,"Excellent",IF(B2>=100,"Good","Needs Improvement"))

How Excel evaluates it

If B2 = 120:

120 >= 150 → FALSE
120 >= 100 → TRUE

Result:

Good

Important principle

When checking conditions from highest to lowest, you don't need to explicitly test every upper boundary.

For example, after:

B2>=150

returns FALSE, Excel already knows that the value is below 150.

Therefore the next condition can simply be:

B2>=100

---

3. **IFS Function**
   
IFS() is useful when you have multiple conditions and want a cleaner alternative to deeply nested IF() formulas.

Syntax

=IFS( 
    B2>=150,"Excellent",
    B2>=100,"Good",
    B2<100,"Needs Improvement"
    )

Excel checks the conditions from left to right and returns the result associated with the first TRUE condition.

Using TRUE as "otherwise"
You can use:

TRUE,"Needs Improvement"
as a final catch-all condition.

Example:
=IFS(
    AND(B2>=150,C2>=90%),"Top Performer",
    AND(B2>=100,C2>=80%),"Good Performer",
    TRUE,"Needs Improvement"
)

This means:

Condition 1 → Top Performer
Condition 2 → Good Performer
Anything else → Needs Improvement

---

4. **AND Function**

AND() checks multiple conditions.

It returns TRUE only when all conditions are TRUE.
Syntax

=AND(condition1,condition2,...)

Example

An employee receives a bonus if:
* Sales >= 100
* Attendance >= 90%

=IF(AND(B2>=100,C2>=90%),"Bonus","No Bonus")

Example

If:

Sales = 120
Attendance = 95%

Both conditions are TRUE.
Result:

Bonus

But if:

Sales = 150
Attendance = 85%

Sales passes, but attendance fails.

Result:

No Bonus

Key idea

  AND() = ALL conditions must be TRUE

---

5. **OR Function**

OR() checks multiple conditions and returns TRUE when at least one condition is TRUE.

Syntax

=OR(condition1,condition2,...)

Example

An employee gets a bonus if:

* Sales >= 150 OR
* Attendance >= 95%

=IF(OR(B2>=150,C2>=95%),"Bonus","No Bonus")
If either condition is satisfied, the employee receives the bonus.

Key idea
  OR() = At least ONE condition must be TRUE

---

6. **COUNTIF**

COUNTIF() counts cells that meet one condition. 

Syntax

=COUNTIF(range,criteria)

Example

Count employees with sales of 100 or more:

=COUNTIF(C8:C12,">=100")

Example

Count employees in the Sales department:

=COUNTIF(B8:B12,"Sales")

Common criteria

">100"
">=100"
"<100"
"=100"
"Sales"
"Whisky"

---

7. **SUMIF**

SUMIF() adds values that meet one condition.

Syntax

=SUMIF(range,criteria,sum_range)

Example

Calculate total sales for the Sales department:

=SUMIF(B8:B12,"Sales",C8:C12)

Breakdown:

B8:B12 → Range to check

"Sales" → Condition

C8:C12 → Values to add

---

8. **AVERAGEIF**

AVERAGEIF() calculates the average of values that meet one condition.

Syntax
=AVERAGEIF(range,criteria,average_range)
Example

Calculate average sales for the Sales department:

=AVERAGEIF(B8:B12,"Sales",C8:C12)

If Sales employees have:

120
80
200

The result is:

133.33

---

9. **COUNTIFS()**

COUNTIFS() counts rows that satisfy multiple conditions.

Syntax
=COUNTIFS(criteria_range1,criteria1,criteria_range2,criteria2,...)
Example

Count employees who:

Are in Sales
Have sales >= 100
=COUNTIFS(
    B8:B12,"Sales",
    C8:C12,">=100"
)

Both conditions must be satisfied.

Example result

| Employee	| Department	| Sales	Counted? |
| --------- | ---------- | --------------- |
| John |	Sales	120	| Yes |
| Mary	| IT	150	| No |
| David	| Sales	80	| No |
| Sarah	| HR	100	| No |
| James	| Sales	200	| Yes |

Result: 2

---

10. **SUMIFS()**

SUMIFS() adds values that satisfy multiple conditions.

Syntax
=SUMIFS(sum_range,criteria_range1,criteria1,criteria_range2,criteria2,...)
Important Difference

Notice that SUMIFS() starts with the sum range.

=SUMIFS(sum_range,...)

Whereas SUMIF() starts with the range to check:

=SUMIF(range,criteria,sum_range)
Example

Calculate total sales for Sales employees whose sales are at least 100:

=SUMIFS(
    C8:C12,
    B8:B12,"Sales",
    C8:C12,">=100"
)

Result:

120 + 200 = 320
Real-world example

Find total Whisky sales in Lagos:

=SUMIFS(
    D19:D24,
    C19:C24,"Whisky",
    B19:B24,"Lagos"
)

This means:

Add the Sales column where Product is Whisky AND Region is Lagos.

---

11. **AVERAGEIFS()**

AVERAGEIFS() calculates the average of values that satisfy multiple conditions.

Syntax
=AVERAGEIFS(
    average_range,
    criteria_range1,criteria1,
    criteria_range2,criteria2
)
Example

Calculate average sales for Sales employees with sales >= 100:

=AVERAGEIFS(
    C8:C12,
    B8:B12,"Sales",
    C8:C12,">=100"
)

The qualifying sales are:

120
200

Result:

160

---


12. **XLOOKUP**

XLOOKUP() searches for a value in one range and returns the corresponding value from another range.

It is extremely useful for connecting information between tables.

Basic Syntax
=XLOOKUP(lookup_value,lookup_array,return_array)

Think:

What am I looking for?
        ↓
Where should I look?
        ↓
What should I return?

---

Basic Example

Suppose:

| Product ID	| Product	| Price |
| -------- | --------- | ------ |
| P001	| Whisky	| 5000 |
| P002	| Vodka	| 4000 |
| P003	| Brandy	| 6500 |
| P004	| Gin	| 3500 |

If G9 contains a Product ID:

=XLOOKUP(G9,A9:A12,C9:C12)

This means:

G9       → Lookup value
A9:A12   → Lookup array
C9:C12   → Return array

If G9 = P003, the result is:

6500

---

**XLOOKUP with if_not_found**

By default, an unsuccessful lookup can return:

#N/A

You can provide your own message.

Syntax
=XLOOKUP(
    lookup_value,
    lookup_array,
    return_array,
    if_not_found
)
Example
=XLOOKUP(
    G9,
    A9:A12,
    C9:C12,
    "Product Not Found"
)

If the product doesn't exist:

Product Not Found

---

**XLOOKUP Inside a Calculation**

One of the most useful applications is retrieving a value and immediately using it in a calculation.

Suppose:

B24 = Product ID
C24 = Quantity
$A$17:$A$20 = Product IDs
$C$17:$C$20 = Prices

To calculate total order value:

=C24*XLOOKUP(B24,$A$17:$A$20,$C$17:$C$20)

The formula works like this:

Quantity
   ×
Matching Product Price
   =
Total Order Value

For example:

Quantity = 10
Price = 6500

10 × 6500 = 65000

---

**XLOOKUP Can Look in Different Directions**

Unlike older lookup approaches that commonly require the lookup column to be positioned to the left of the return column, XLOOKUP() can search a range and return a value from another range without that limitation.

Example:

=XLOOKUP(G37,B37:B40,A37:A40)

This can search Product Names and return Product IDs.

---

13. Absolute, Relative & Mixed References

Excel references can behave differently when formulas are copied or dragged.

---

Relative Reference

Example:

A1

When copied down one row:

A1 → A2

The reference changes.

---

Absolute Reference

Example:

$A$1

When copied:

$A$1 → $A$1

The reference stays fixed.

Example
=XLOOKUP(B24,$A$17:$A$20,$C$17:$C$20)

The lookup ranges remain fixed when the formula is copied down.

---

**Mixed References**

A mixed reference locks either the row or the column.

Column fixed
$A1

The column stays fixed, but the row can change.

Row fixed
A$1

The row stays fixed, but the column can change.

---

**Quick Reference**

| Reference	| Column	| Row |
| --------- | ------- | ----- |
| A1	| Changes	| Changes |
| $A$1	| Fixed	| Fixed |
| $A1	| Fixed	| Changes |
| A$1	| Changes	| Fixed |

---

14. **Combining Functions**

Excel becomes particularly powerful when functions are combined.

IF + AND
=IF(AND(B2>=100,C2>=90%),"Bonus","No Bonus")
IF + OR
=IF(OR(B2>=150,C2>=95%),"Bonus","No Bonus")
IFS + AND
=IFS(
    AND(B2>=150,C2>=90%),"Top Performer",
    AND(B2>=100,C2>=80%),"Good Performer",
    TRUE,"Needs Improvement"
)
XLOOKUP + Arithmetic
=C24*XLOOKUP(B24,$A$17:$A$20,$C$17:$C$20)

This retrieves a price and multiplies it by quantity.

---

15. **Common Mistakes**

**Mistake 1 — Using > instead of >=**

If the requirement says:

Sales of 100 or more

Use:

B2>=100

Not:

B2>100

Because 100 > 100 is FALSE.

---

**Mistake 2 — Incorrect nested IF logic**

Avoid unnecessarily testing conditions that have already been eliminated.

Instead of:

=IF(B2>=150,"Excellent",IF(B2<150,"Good",...))

use:

=IF(B2>=150,"Excellent",IF(B2>=100,"Good","Needs Improvement"))

Once Excel knows the first condition is FALSE, it already knows the value is below 150.

---

**Mistake 3 — Confusing AND and OR**
AND

All conditions must be TRUE:

=AND(B2>=100,C2>=90%)
OR

At least one condition must be TRUE:

=OR(B2>=150,C2>=95%)

---

Mistake 4 — Forgetting the extra S

One condition:

COUNTIF
SUMIF
AVERAGEIF

Multiple conditions:

COUNTIFS
SUMIFS
AVERAGEIFS

The S indicates that multiple criteria can be supplied.

---

**Mistake 5 — Forgetting the SUMIFS structure**

SUMIF():

=SUMIF(range,criteria,sum_range)

SUMIFS():

=SUMIFS(sum_range,criteria_range1,criteria1,...)

The position of sum_range is different.

---

Mistake 6 — Forgetting absolute references

If a lookup table must remain fixed when copying a formula:

$A$17:$A$20

is safer than:

A17:A20

---

16. **Quick Reference**

| Function	| Purpose	| Number of Conditions |
| -------- | ------- | -------------------- |
| IF()	| Make a decision	| 1 |
| IFS()	| Evaluate multiple conditions	| Multiple |
| AND()	| All conditions must be TRUE	| Multiple |
| OR()	| At least one condition TRUE	| Multiple |
| COUNTIF()	| Count based on a condition	| 1 |
| COUNTIFS()	| Count based on multiple conditions	| Multiple |
| SUMIF()	| Sum based on a condition	| 1 |
| SUMIFS()	| Sum based on multiple conditions	| Multiple |
| AVERAGEIF()	| Average based on a condition	| 1 |
| AVERAGEIFS()	| Average based on multiple conditions	| Multiple |
| XLOOKUP()	| Find and return related data	| Lookup |

---

17. Real-World Applications

These functions are particularly useful in business and data analysis.

Sales Analysis
=SUMIFS(Sales,Region,"Lagos",Product,"Whisky")

Find total Whisky sales in Lagos.

Employee Performance
=IF(AND(Sales>=100,Attendance>=90%),"Bonus","No Bonus")

Determine bonus eligibility.

Customer Analysis
=XLOOKUP(CustomerID,CustomerIDs,CustomerNames)

Retrieve a customer's name using their ID.

Order Analysis
=Quantity*XLOOKUP(ProductID,ProductIDs,Prices)

Calculate order value using a product lookup.

Reporting

COUNTIFS(), SUMIFS(), and AVERAGEIFS() can be used to build:

Regional sales reports
Product performance reports
Distributor analysis
Employee performance reports
Customer segmentation
Monthly sales summaries

---

Key Takeaways

The most important concepts to remember are:

IF
→ Make a decision

IFS
→ Multiple decision rules

AND
→ Everything must be TRUE

OR
→ At least one condition must be TRUE

COUNTIF / SUMIF / AVERAGEIF
→ One condition

COUNTIFS / SUMIFS / AVERAGEIFS
→ Multiple conditions

XLOOKUP
→ Find something and return related information

$A$1
→ Keep a reference fixed

The goal is not to memorize every formula. Instead, understand what question you're asking Excel and choose the function that answers that question.
