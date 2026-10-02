# Presentation Content: Sales Data Analysis Dashboard
*(Copy each slide into PowerPoint / Google Slides. Suggested charts are in `reports/figures/`. About 10 slides, 8-10 minutes.)*

---
## Slide 1 - Title
**Sales Data Analysis Dashboard**
Superstore sales, 2014-2017
Your Name | Data Analysis Intern | Date

---
## Slide 2 - Objective
- Understand how the business is performing
- Find the best months, products, regions and categories
- Find problems that reduce profit
- Present the results in a simple dashboard

*Speaker note:* I wanted to answer the questions a manager would ask first: how much, when, what, where.

---
## Slide 3 - Dataset and Tools
- Superstore sample dataset: 9,994 rows, 21 columns
- Jan 2014 - Dec 2017, 4 US regions, 3 categories
- Python (Pandas, NumPy, Matplotlib), Jupyter Notebook
- HTML dashboard with Chart.js

---
## Slide 4 - Data Quality and Cleaning
- Missing values: 0
- Exact duplicates: 0, but 1 hidden duplicate found after ignoring Row ID (removed)
- 16 product names with extra spaces (fixed)
- Dates converted; Year and Month columns added
- Final: 9,993 rows

*Speaker note:* The data was already clean, so I did not invent problems. I still wrote the missing-value code so it works on other files.

---
## Slide 5 - Key Numbers
- **Total Sales: $2,296,919**
- **Total Orders: 5,009**
- Average order value: $458.56
- Profit: $286,409 (12.5% margin)

*Note:* Orders = unique Order IDs, not rows.

---
## Slide 6 - Monthly Sales and Trend
**Chart:** `01_monthly_sales_trend.png`
- 2014 $484k -> 2015 $471k -> 2016 $609k -> 2017 $733k
- Best month: Nov 2017 ($118k)
- Oct-Dec = 38.2% of all sales
- Trend: about +$903 per month

---
## Slide 7 - Top 10 Products
**Chart:** `03_top10_products.png`
- Canon imageCLASS 2200 Copier is far ahead ($61.6k)
- Top 10 = only 10.6% of sales
- 3 of the top 10 lose money

---
## Slide 8 - Regions and Categories
**Charts:** `04_regional_analysis.png`, `06_category_analysis.png`
- West (31.6%) and East (29.5%) lead
- Central has the lowest margin: 7.9%
- Technology is the biggest category (36.4%) with a 17.4% margin
- Furniture margin is only 2.5%

---
## Slide 9 - Business Insights
1. Sales grew 29% in 2016 and 20% in 2017
2. Strong year-end season (Oct-Dec = 38%)
3. Central region: low margin and flat 2017 sales
4. Furniture earns little; Tables and Bookcases lose money
5. Discounts over 20% give negative margins (-15% and -77%)
6. Sales are not dependent on a few products

**Chart:** `08_discount_vs_margin.png`

---
## Slide 10 - Recommendations
- Plan stock and staff for Oct-Dec
- Put a limit on discounts above 20%
- Review pricing of Tables and Bookcases
- Investigate the Central region
- Review the loss-making top-10 products

---
## Slide 11 - Dashboard Demo
Show `dashboard/index.html`: change the Year to 2017, Region to West, Category to Technology and show how the numbers and charts update.

---
## Slide 12 - Limitations and Next Steps
- Sample data, 4 years; findings are descriptive, not tested statistically
- Next: customer segments, state-level analysis, a Power BI version, a simple forecast

**Thank you - Questions?**
