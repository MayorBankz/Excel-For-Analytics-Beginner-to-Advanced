## TOPIC: TEXT FUNCTIONS
## DATE: 18-08-2026

---

### **TOPICS COVERED**
* TRIM
* LEN
* LEFT / RIGHT
* MID
* FIND / SEARCH
* SUBSTITUTE / REPLACE
* TEXTBEFORE / TEXTAFTER
* TEXTSPLIT

---

1. **TRIM**

What does it do?

TRIM() removes unnecessary spaces from text.

SYNTAX

```excel
=TRIM(text)
```

Example

If `A2` contains 

```excel
   John Adeleke
```

Use:

```excel
=TRIM(A2)
```

### Result
```excel
John Adeleke
```

### **Real-world Application**
Imagine a customer database contains:

```excel
"  Mayowa  "
"Mayowa"
"   Mayowa"
```

Those may look identical to us, but Excel can treat them differently in certain operations.

cleaning them with:

```excel
=TRIM(A2)
```

helps standardize the data

---


2. **LEN()**

What is LEN()?

LEN() counts the number of characters in a text string.

SYNTAX

```excel
=LEN(text)
```

For example:

```excel
=LEN("Python")
```

returns: 6

Because:

```excel
P y t h o n
1 2 3 4 5 6
```

Spaces also count as characters.

Therefore:

```excel
=LEN("John Doe")
```

returns: 8

because: 

```excel
John → 4
space → 1
Doe → 3
--------------
total → 8
```

### Real-world application
Suppose you're cleaning customer IDs.

```excel
NG123456
NG1234
NG12345678
```

You expect every to contain 8 characters.

You could use: =LEN(A2)

and then identify IDs that don't meet the expected length.

---

3. **LEFT()**

Suppose:

```excel
A2 = NG123456
```
and you want to extract the country code:

```excel
NG
```

You can use:

:```excel
=LEFT(A2,2)
```

**How it works**

```excel
LEFT(text, number_of_characters)
```

so:

```excel
=LEFT(A2,2)
```

means:
  Start from the left and return the first two characters

Result:
  2

---

4. **RIGHT()**

`RIGHT()` works exactly like `LEFT()`, except it starts from the right side of the text.

SYNTAX

```excel
=RIGHT(text, number_of_characters)
```

For example:

```excek
=RIGHT(B2,4)
```

If:
```excel
B2 = NG123456
```

the result is:

3456

Because excel takes the last 4 characters.

---

5. **MID()**

What does MID() do?

MID() extracts a specified number of characters starting from a position you choose.

SYNTAX

```excel
=MID(text, start_num, num_chars)
```

For example:

```excel
B2 = NG123456
```

Suppose we want:

```excel
123
```

We could use:
```excel
=MID(B2,3,3)
```

Why?

```excel
N G 1 2 3 4 5 6
1 2 3 4 5 6 7 8
    ↑─────↑
   start  3 characters
```

* `B2` → Text
* `3` → Start
* `3` → return 3 characters

Result: 123

---

6. **FIND()**

Instead of asking: 
  "What character position is the hyphen?"

We can ask Excel:
  "Where is the hyphen?"

That's what `FIND()` does.

SYNTAX

```excel
=FIND(find_text, within_text)
```

Example

```excel
=FIND("-",F2)
```

For:

```excel
NDL-LAG-2026-0045
```

Excel finds the first hyphen.

Result: 4

Because:

```excel
N D L -
1 2 3 4
```

---

💡 **FIND() vs MID()**

Notice the difference:

```excel
=MID(F2,9,4)
```

Extracts characters.

While

```excel
=FIND("-",F2)
```

Finds the position of a character.

This distinction becomes very powerful when we combine functions.

For example, suppose:

```excel
F2 = NDL-LAG-2026-0045
```

We could use:

```excel
=LEFT(F2,FIND("-",F2)-1)
```

to extract:

```excel
NDL
```

Why?

1. FIND("-", F2) → Finds the first hyphen at position 4
2. `4-1` → gives 3
3. `LEFT(F2, 3) → returns NDL

This is the kind of function combination you'll need for real-world data cleaning.

---

