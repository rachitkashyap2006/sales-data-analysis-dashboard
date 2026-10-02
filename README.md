# Sales Data Analysis Dashboard

A beginner data analysis project built during my Data Analysis internship. I cleaned and analysed a retail sales dataset (Superstore) with Python, Pandas, NumPy and Matplotlib, and built a simple interactive HTML dashboard to show the results.

## Project Objectives
- Check the quality of the raw data and clean it (duplicates, missing values, data types)
- Calculate **Total Sales** and **Total Orders**
- Study **monthly sales** and the sales trend
- Find the **Top 10 products**
- Compare **regions** and **categories**
- Turn the findings into business insights and a dashboard

## Dataset
| | |
|---|---|
| Name | Superstore Sales (sample retail dataset) |
| Size | 9,994 rows, 21 columns (before cleaning) |
| Period | 3 Jan 2014 - 30 Dec 2017 |
| Country | United States (4 regions: Central, East, South, West) |
| File | `data/superstore_raw.csv` (original, untouched) |

The file is the widely used "Sample - Superstore" dataset (also published on Kaggle as *Superstore Dataset Final*). It is sample data, not a real company's records. I included it for learning purposes; if you reuse it outside learning, please check the original source's terms.

Key columns: Order ID, Order Date, Region, Category, Sub-Category, Product Name, Sales, Quantity, Discount, Profit.

## Folder Structure
```
sales-data-analysis-dashboard/
├── data/
│   ├── superstore_raw.csv          # original dataset
│   └── superstore_cleaned.csv      # output of the notebook
├── notebooks/
│   └── sales_analysis.ipynb        # full analysis (run this)
├── dashboard/
│   ├── index.html                  # interactive dashboard
│   └── data.js                     # data for the dashboard (created by the notebook)
├── reports/
│   ├── project_report.md           # written report
│   └── figures/                    # charts saved by the notebook (PNG)
├── presentation/
│   └── presentation_content.md     # slide-by-slide content
├── README.md
├── requirements.txt
└── .gitignore
```

## Methodology
1. **Load** the CSV (`encoding="latin1"` is needed for this file).
2. **Understand** the data with `info()`, `describe()` and unique counts.
3. **Check quality**: missing values, exact duplicates, duplicates ignoring `Row ID`, extra spaces, invalid sales/quantity, shipping before order date.
4. **Clean**: strip spaces, convert dates, remove duplicates, handle missing values (none were found, but the code is included), add Year / Month columns.
5. **Analyse**: KPIs, monthly trend (with 3-month average and a NumPy trend line), top products, region, category, sub-category, discount effect.
6. **Visualise** with Matplotlib and export data for the HTML dashboard.

## Data Cleaning Summary
| Check | Result |
|---|---|
| Missing values | 0 |
| Exact duplicate rows | 0 |
| Duplicates when ignoring `Row ID` | 1 row removed (9,994 -> 9,993 rows) |
| Product names with extra spaces | 16 values, stripped |
| Sales or quantity <= 0 | 0 |
| Orders shipped before order date | 0 |

## Key Results
| Measure | Value |
|---|---|
| Total Sales | $2,296,919.49 |
| Total Orders (unique Order IDs) | 5,009 |
| Average order value | $458.56 |
| Total Profit / margin | $286,409.08 / 12.5% |
| Best month | Nov 2017 ($118,447.82) |
| Largest region | West (31.6% of sales) |
| Largest category | Technology (36.4% of sales) |
| Top product | Canon imageCLASS 2200 Advanced Copier ($61,599.82) |

### Business Insights
1. **Growth:** yearly sales were $484k (2014), $471k (2015), $609k (2016) and $733k (2017). 2015 dipped slightly, then sales grew about 29% and 20%.
2. **Seasonality:** Oct-Dec bring 38.2% of all sales. November is the strongest calendar month, February the weakest.
3. **Regions:** West and East together give 61% of sales. Central has the lowest margin (7.9%), and its 2017 sales were flat compared with 2016.
4. **Categories:** Technology and Office Supplies have margins of about 17%, but Furniture makes only 2.5%.
5. **Loss-making sub-categories:** Tables (-$17.7k), Bookcases (-$3.5k) and Supplies (-$1.2k) lose money.
6. **Discounts:** lines with a discount above 20% have a negative margin (-15.3% for 21-40%, -77.4% above 40%), while lines with no discount have a margin of 29.5%.
7. **Products:** the top 10 products are only 10.6% of sales, so the business does not depend on a few items. Three of the top 10 lose money.

Full explanation is in [`reports/project_report.md`](reports/project_report.md).

## How to Run
```bash
# 1. Go into the project folder
cd sales-data-analysis-dashboard

# 2. (Optional) create a virtual environment
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# 3. Install the libraries
pip install -r requirements.txt

# 4. Open the notebook and run all cells
jupyter notebook notebooks/sales_analysis.ipynb
```
Running the notebook recreates `data/superstore_cleaned.csv`, the charts in `reports/figures/` and `dashboard/data.js`.

**Open the dashboard:** double-click `dashboard/index.html` (it needs an internet connection once, because the Chart.js library is loaded from a CDN). Use the Year, Region and Category filters.

## Tools Used
Python 3, Pandas, NumPy, Matplotlib, Jupyter Notebook, HTML/CSS/JavaScript, Chart.js

## Limitations
- Only four years of sample data; the trend is not a forecast.
- Product names are used for the Top 10 (16 names have more than one Product ID).
- I did not run statistical tests, so the findings are descriptive.

## Possible Next Steps
- Add customer segment and state-level analysis
- Build a Power BI version of the dashboard
- Try a simple sales forecast

## Author
Your Name - Data Analysis Intern
