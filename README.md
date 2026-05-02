# Laboratory-Work5-Activity-PowerBI
# Guided Questions (Laboratory Work 5)

## I. Foundational Concepts

### 1. Defining DAX

DAX (Data Analysis Expressions) is a formula language used in Power BI to perform calculations on data models.

Unlike Excel formulas, which usually work on individual cells, DAX works on entire tables and is designed for data modeling and analytics.

In simple terms:
- Excel = cell-based calculations  
- DAX = data model and relationship-based calculations  

---

### 2. The "Why" of DAX

We cannot rely only on raw data because raw datasets do not provide insights.

DAX is needed because it:
- Creates dynamic calculations  
- Supports relationships between multiple tables  
- Enables advanced analytics (totals, percentages, trends, KPIs)  
- Responds to filters and user interactions  

Without DAX, Power BI would only display static data, not meaningful insights.

---

## II. Calculated Columns vs. Measures

### 3. The Storage Difference

Calculated Columns increase the file size of the Power BI model because:
- They are computed row-by-row and stored physically in the dataset

Measures, on the other hand:
- Are calculated on demand (runtime)
- Do not increase model storage significantly

This is important for large datasets because using too many calculated columns can slow performance and increase file size.

---

### 4. Context Clues (Filter Context)

Filter Context refers to how visuals, slicers, and filters affect DAX calculations.

For Measures:
- The result changes depending on filters applied in the report
- Example: Total Sales will change when selecting a specific product or region

For Calculated Columns:
- The value is fixed for each row and does not change with filters

This makes Measures more dynamic and powerful for dashboards.

---

## III. Function Application & Syntax

### 5. The RELATED Function

The RELATED function is used to fetch data from another table based on a relationship.

It is necessary because:
- Power BI uses a relational data model
- Data is often split across multiple tables (e.g., Orders, Customers)

For RELATED to work:
- A relationship must be established in the Model View
- Typically between a primary key and foreign key

Without relationships, RELATED cannot retrieve values.

---

### 6. Deconstructing the Formula

Formula:
```
Total Sales = SUM(Sales[Sales Amount])
```

Breakdown:
- Measure Name: Total Sales  
- Function: SUM  
- Table: Sales  
- Column: Sales Amount  

Best practice is to include the table name because:
- It avoids ambiguity when multiple tables have similar column names  
- It improves readability  
- It ensures clarity in large data models  

---

## IV. Analysis & Troubleshooting

### 7. Data Interpretation

If "Total Profit" shows a negative value, it does NOT automatically mean the DAX formula is broken.

It may indicate:
- The business has losses in that category  
- Costs are higher than revenue  

To verify:
- Check raw data values  
- Review individual components (Revenue vs Cost)  
- Validate filters applied in the visual  
- Cross-check with source dataset  

So, it is often a business insight, not a formula error.

---

### 8. Optimization (Profit Margin Percentage)

It is more efficient to use a **Measure** instead of a Calculated Column.

Reason:
- Profit Margin is an aggregate calculation  
- Measures are dynamic and respond to filters  
- Measures do not increase dataset size  
- Better performance for large datasets  

Therefore, a Measure is the best practice for Profit Margin calculations.

---

## Final Note

DAX is powerful because it transforms raw data into interactive business intelligence. Understanding context (row context vs filter context) is the key to mastering Power BI analytics.
