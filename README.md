# Amazon-Product-Review-Analysis-Capstone
This is where I started my Portfolio building while taking my Data Analysis class with the Incubator
## Project Topic: Amazon Product Review Analysis

### Project Overview
This Data Analysis project aims to generate insight into the product reviews of the Amazon Project and the impact. By analysing the various parameters in the data recieved we seek to gather enough insight to make a reasonable decisions and suggestions which enable us to tell compelling stories around our data from the insight gotten and to know the best reviews from our data.

### Data Sources
The primary source of Data used here is Amazon product review analysis.csv and this is provided by Capstone.

### Tools Used
- Ms Excel for Data Cleaning [Download Here](https://www.Microsoft.com)
    - For Manipulation
    - For Munchin 
- Ms Excel for Querryind and Analysis
- Ms Excel for creating report

### Explanatory Data Analysis
EDA involved the exploring of Data to answer some questions about the data...

✅ 1. Average Discount Percentage by Product Category

A → Build a Pivot Table:

Rows: Category

Values: Average of Discount %


B → Format Result:

Format as Percentage (0 or 1 decimal place)



---

✅ 2. Total Number of Products Listed Under Each Category

A → Pivot Table:

Rows: Category

Values: Count of Product Name


B → Result:
Gives number of unique product entries per category.


---

✅ 3. Total Number of Reviews per Category

A → Pivot Table:

Rows: Category

Values: Sum of Rating Count


B → Result:
Shows total customer review counts for each category.


---

✅ 4. Products with the Highest Average Ratings

A → Pivot Table:

Rows: Product Name

Values: Average of Rating


B → Sort:

Sort the Average Rating column → Descending → Top Rated Products appear first



---

✅ 5. Average Actual Price vs Discounted Price by Category

A → Pivot Table:

Rows: Category

Values:

Average of Actual Price

Average of Discounted Price



B → Result:
Compare Original vs Discounted Price side by side per category.


---

✅ 6. Products with the Highest Number of Reviews

A → Pivot Table:

Rows: Product Name

Values: Sum of Rating Count


B → Sort:

Sort by Rating Count → Descending → Top Reviewed Products appear first



---

✅ 7. Number of Products with Discount ≥ 50%

A → Calculated Column (Helper Field):

Formula in new column:

=IF([@[Discount %]]>=0.5,1,0)

(Where [Discount %] refers to your discount column)

B → Pivot Table:

Rows: (Optional: Category or leave blank)

Values: Sum of the new helper column


✅ Alternative:
Use:

=COUNTIF(G2:G1000, ">=0.5")

(If G2:G1000 = Discount column)


---

✅ 8. Distribution of Product Ratings (Rating Buckets)

A → Create a Pivot Table:

Rows: Rating (or rounded rating if you want whole number buckets)

Values: Count of Product Name


B → Result:
Shows how many products have rating 3.0, 4.0, 5.0, etc.

✅ Optional:
If ratings have decimals and you want grouping:
Create a helper column:

=ROUND(E2,0)

(Where E2 = Rating column)


---

✅ 9. Total Potential Revenue by Category (Actual Price × Rating Count)

A → Calculated Column (New Helper Field):

Formula:

=[@[Actual Price]]*[@[Rating Count]]

(Or: Actual Price × Rating Count)

B → Pivot Table:

Rows: Category

Values: Sum of the new revenue column



---

✅ 10. Unique Products per Price Range Bucket

A → Create Price Range Buckets (Helper Column):

Formula example (adjust ranges as needed):

=IF(D2<200,"<₹200",IF(D2<=500,"₹200–₹500",">₹500"))

(Where D2 = Actual Price)

B → Pivot Table:

Rows: Price Range Bucket

Values: Count of Distinct Products (Excel 2016 doesn't support DISTINCTCOUNT natively, but a normal COUNT of product names works if cleaned properly.)


✅ For Unique Count: Use a workaround or create a manual helper formula.


---

✅ 11. Relationship Between Rating and Discount Level

A → Scatter Chart OR Pivot Table with Matrix Style:

Rows: Discount Range Buckets (Example: 0–10%, 10–30%, 30–50%, etc.)

Values: Average Rating


B → Result:
Helps you see whether higher discounts are linked with higher or lower ratings.

✅ Optional: Use a scatter plot with Discount % on X-axis and Average Rating on Y-axis.


---

✅ 12. Products with Fewer Than 1,000 Reviews

A → Calculated Field (Helper Column):

Formula:

=IF([@[Rating Count]]<1000,1,0)

B → Pivot Table:

Values: Sum of the helper column


✅ Or: Simple formula outside Pivot:

=COUNTIF(F2:F1000,"<1000")

(Where F2:F1000 = Rating Count column)


---

✅ 13. Categories with Products Having the Highest Discounts

A → Pivot Table:

Rows: Category

Values: Max of Discount %


B → Result:
Shows maximum discount per category, helping identify where the deepest discounts are.


---

✅ 14. Top 5 Products Based on Rating and Review Count Combined

A → Create Weighted Score (New Helper Column):

Example Formula:

=([@[Rating]]*[@[Rating Count]])

(Weight = Rating × Number of Reviews)

B → Pivot Table:

Rows: Product Name

Values: Sum of Weighted Score


C → Sort & Filter:

Sort Weighted Score → Descending

Show Top 5 Products

### Data Analysis
This is where we inlude some basic lines of code or queries and columns during the analysis.

