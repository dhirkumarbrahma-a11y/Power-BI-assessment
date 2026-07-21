Power BI Assessment 

Theme:Sales Performance Dashboard  
Dataset:Sample Superstore Datase

Section A: Concept Application

1. Compare the technical differences between Import and DirectQuery modes and identify which is suitable for a static CSV file.
Import Mode: Loads a complete copy of the dataset directly into Power BI's in-memory VertiPaq engine. It provides fast query speeds, full DAX functionality, and complete Power Query transformation capabilities.
DirectQuery Mode: Keeps the data at the source and generates live SQL queries on the fly as users interact with the dashboard. It supports real-time data but limits certain DAX/Power Query functions and depends heavily on source database performance.
Suitable Mode for Static CSV: Import Mode is required. DirectQuery does not support flat CSV files because it requires a relational database engine (like SQL Server or PostgreSQL).

2. Explain the consequence of a "Text" data type on a Card visual displaying sales and identify where in the workflow to correct this.
Consequence:** Power BI cannot perform numerical aggregations (like `SUM` or `AVERAGE`) on text data. A Card visual will display non-numeric options like First or Last text string values instead of calculating total revenue.
* **Where to Correct It: Correct this in Power Query Editor by selecting the `Sales` column header and changing its Data Type to **Fixed Decimal Number** (or Currency). Alternatively, update it in the Data View under the Column Tools tab.

3. Identify the specific menu or pane used to change a bar chart's sort order from alphabetical to descending by value.
Location:Click on the **More Options (...) icon located at the top-right corner of the Bar Chart visual.
* Steps:
  1. Click More Options (...).
  2. Select Sort axis.
  3. Choose the metric field (e.g., `Sales` or `Profit`).
  4. Select Sort descending.

4. Contrast filtering in Power Query versus using a visual-level "Top N" filter regarding their impact on other report visuals.
Power Query Filter: Permanently removes rows during the ETL/data loading stage. Those rows are completely excluded from the data model, affecting all visuals, pages, and DAX measures globally.
Visual-Level "Top N" Filter: Applies only to the specific visual where it is configured. The underlying data model retains all rows, leaving all other report visuals and calculations unaffected.

5. Describe how to modify a bar chart or use a DAX measure to show a region's percentage of total sales instead of absolute values.
Method 1 (UI Option): Drag `Sales` into the Values field of the chart, right-click the field, select Show value as, and choose Percent of grand total.
Method 2 (DAX Measure):Write a measure that divides regional sales by all-region sales:
  ```dax
  % of Total Sales = 
  DIVIDE(
      SUM('Orders'[Sales]), 
      CALCULATE(SUM('Orders'[Sales]), ALL('Orders'[Region]))
  )

