# Sri Lanka Pharmacy Sales Analytics

## Project Overview

This project presents a complete **data visualisation and business intelligence analysis** of a Sri Lankan pharmacy chain transaction dataset.

The analysis combines **Python-based analytical visualisations** with **Tableau interactive dashboards** to explore revenue trends, branch performance, product profitability, customer demographics, geographic revenue distribution and payment behaviour.

The project was developed as part of the DATA9005 Data Visualisation module and demonstrates how Python and Tableau can be used together to produce both analytical and interactive business insights.

## Dataset

**Dataset:** Pharmacy Transaction Dataset  
**Source:** Kaggle  
**File:** `PharmacyOLTPStyle18Months.csv`  
**Dataset Link:** https://www.kaggle.com/datasets/mrnize/pharmacy-transaction

The dataset contains sales transaction data from a Sri Lankan pharmacy chain.

### Dataset Summary

| Item | Value |
|---|---:|
| Total rows | 50,000 |
| Total columns | 27 |
| Time period | January 2022 to June 2023 |
| Branches | 7 |
| Main domain | Pharmacy retail sales |
| Tools used | Python and Tableau |

## Business Questions

This project addresses the following business questions:

1. What is the total revenue trend over the 18-month period?
2. Are there any major peaks or drops in sales performance?
3. Which medicine categories are most profitable relative to discount rate?
4. How do pharmacy branches compare across multiple KPIs?
5. Which customer age groups are the most frequent buyers?
6. Do older customers spend more per transaction?
7. How is revenue distributed across pharmacy branches and regions?
8. Which branches perform strongly and which need improvement?
9. How do payment methods flow into different medicine categories?

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Folium
- Tableau Public
- Kaggle

## Tableau Public Dashboards

### Main Interactive Tableau Story

View the Tableau dashboard here:

https://public.tableau.com/app/profile/arjun.krishna.krishnkumar/viz/HIS_17724492082170/Story1

### Sankey Diagram Dashboard

View the Sankey diagram here:

https://public.tableau.com/views/HIS_17724492082170/sankeydiagram?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

## Project Workflow

```text
Load pharmacy transaction dataset
        |
        v
Perform data quality checks
        |
        v
Handle missing values
        |
        v
Verify revenue calculation
        |
        v
Exploratory data analysis
        |
        v
Build Python visualisations
        |
        v
Create GIS map using Folium
        |
        v
Prepare data for Tableau
        |
        v
Build Tableau dashboards
        |
        v
Create Sankey flow diagram
        |
        v
Interpret business insights
```

## Data Quality Checks

### Missing Value Handling

The `Strength_mg` column contained a high number of missing values. This was expected because liquid medicines and creams do not always have strength measured in milligrams.

Since this field was not required for the main business questions, it was removed from the analysis.

### Revenue Verification

Revenue integrity was checked using the formula:

```text
Quantity × Unit Price × (1 - Discount Rate)
```

This calculated value was compared against the `Line_Total_LKR` column to confirm consistency.

### Correlation Analysis

A correlation heatmap was created using numerical columns to understand relationships between customer age, quantity, unit price, discount rate and line total.

## Visualisations Created

### 1. Monthly Revenue Trend

A dual-panel time series chart was created using Python and Matplotlib.

The chart includes:

- Monthly revenue
- 3-month rolling average
- Savitzky-Golay smoothed trend line
- Month-over-month change bar chart

**Business value:**  
This helps identify revenue stability, seasonal variation and months where performance declined.

### 2. Category Profitability Matrix

A bubble chart was created to compare medicine categories using:

- Average discount rate
- Total revenue
- Transaction volume

The chart was divided into four strategic quadrants to identify:

- High revenue and low discount categories
- High discount but low revenue categories
- Categories needing promotion
- Categories that may need pricing review

**Business value:**  
This supports product category strategy and discount optimisation.

### 3. Branch Performance Radar Chart

A six-dimensional radar chart was used to compare all seven branches across key performance indicators.

The radar chart used normalised KPI values so that different metrics could be compared on the same scale.

An inverted margin score was also applied because a lower discount rate is better for business performance.

**Business value:**  
This helps compare branch performance across multiple dimensions at once.

### 4. GIS Geographic Revenue Map

An interactive map was built using Python and Folium.

The map includes:

- Branch revenue circles
- Customer city markers
- Revenue heatmap
- Mini map
- Layer controls
- Custom popups

**Business value:**  
This helps identify strong and weak geographic regions and supports branch expansion decisions.

### 5. Customer Demographics Visualisation

A dual-panel visualisation was created using:

- Violin plot for customer age distribution
- Stacked bar chart for payment method by gender

**Business value:**  
This helps understand customer age behaviour, gender/payment patterns and category-level customer profiles.

### 6. Tableau Revenue and Category Dashboard

A Tableau dashboard was created to analyse:

- Monthly revenue trend
- Category profitability
- Revenue by branch
- Filters by branch and medicine category

### 7. Tableau KPI Summary, Province Map and Payment Analysis

This dashboard includes:

- KPI summary
- Average ticket value
- Total revenue
- Total transactions
- Province-level map
- Revenue by payment method
- Revenue by medicine category

### 8. Sankey Diagram

A Sankey diagram was created to show the flow between:

```text
Payment Method → Medicine Category
```

**Business value:**  
This highlights how different payment methods are distributed across product categories. The analysis found that cash is the dominant payment method across categories.

## Key Insights

- Revenue remained broadly stable over the 18-month period, with seasonal variation.
- Antibiotics and cardiac medicine categories generated strong revenue with relatively low discounts.
- Some categories with high discounts did not generate strong revenue, suggesting discounts alone may not drive sales.
- Branch performance varied across KPIs, making a multi-KPI radar chart useful for comparison.
- Cash was the dominant payment method across medicine categories.
- GIS analysis showed future opportunity for expansion into central and eastern regions of Sri Lanka.
- Python was effective for analytical and customised visualisations, while Tableau added interactive business dashboard capability.

## Novel Features of This Project

This project includes several advanced and customised elements:

- Manual mapping of branch and customer city coordinates
- Multi-layer Folium GIS map
- Radar chart with KPI normalisation
- Inverted margin score for fair branch comparison
- Custom colour palette used consistently across Python and Tableau
- Python-prepared Sankey data for Tableau rendering
- Dual-tool workflow combining analytical Python charts with interactive Tableau dashboards

## Design Considerations

Several design choices were made during the project:

### Chart Type Selection

Each chart was selected based on the type of business question:

- Time series chart for monthly revenue trend
- Bubble chart for category profitability
- Radar chart for multi-KPI branch comparison
- GIS map for location-based analysis
- Violin plot for age distribution
- Sankey diagram for payment flow analysis

### Colour Consistency

A consistent colour palette was used across Python and Tableau dashboards to maintain a professional visual identity.

### Python and Tableau Combination

Python was used for detailed analysis, complex chart logic and GIS mapping.

Tableau was used for interactive dashboards that business users can explore without writing code.

## Repository Structure

```text
sri-lanka-pharmacy-sales-analytics/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── pharmacy_sales_visual_analytics.ipynb
│
├── reports/
│   └── data_visualisation_report.pdf
│
├── images/
│   ├── revenue_trend.png
│   ├── category_profitability_matrix.png
│   ├── branch_radar_chart.png
│   ├── sri_lanka_revenue_map.png
│   ├── customer_demographics.png
│   ├── tableau_dashboard.png
│   └── sankey_diagram.png
│
├── dashboards/
│   └── ceylon_pharmacy_analytics.twbx
│
└── data/
    └── README.md
```

## How to Run the Python Analysis

### 1. Clone the repository

```bash
git clone https://github.com/your-username/sri-lanka-pharmacy-sales-analytics.git
cd sri-lanka-pharmacy-sales-analytics
```

### 2. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn scipy folium jupyter
```

### 3. Download the dataset

Download the dataset from Kaggle:

https://www.kaggle.com/datasets/mrnize/pharmacy-transaction

Place the dataset inside the `data/` folder.

### 4. Run the notebook

```bash
jupyter notebook
```

Open:

```text
pharmacy_sales_visual_analytics.ipynb
```

## Requirements

Create a `requirements.txt` file with:

```text
pandas
numpy
matplotlib
seaborn
scipy
folium
jupyter
```

## Files to Remove Before Publishing

Remove unnecessary system files before making the repository public:

```text
.DS_Store
.ipynb_checkpoints/
__pycache__/
```

Use this `.gitignore`:

```text
.DS_Store
.ipynb_checkpoints/
__pycache__/
*.pyc
.env
data/*.csv
```

If you want to include the dataset in GitHub, remove `data/*.csv` from `.gitignore`. However, for large datasets, it is better to link to Kaggle instead.

## Limitations

- The dataset is based on synthetic or publicly available pharmacy transaction data.
- Some geographic coordinates were manually researched and added.
- The radar chart uses equal weighting across KPIs.
- The Sankey diagram currently shows only Payment Method to Medicine Category flow.
- More detailed branch-level customer segmentation could be added in future work.

## Future Improvements

- Add weighted KPI scoring for branch performance.
- Extend the Sankey diagram to show Payment Method → Category → Branch.
- Add forecasting for future revenue.
- Add customer segmentation using clustering.
- Build a Power BI version for comparison.
- Create an interactive Streamlit dashboard.
- Add automated report generation.

## Project Status

Completed as a data visualisation and business intelligence project.

## Author

**Arjun Krishna Krishnakumar**

Aspiring data analyst / AI and software developer with an interest in business intelligence, data visualisation, analytics dashboards and practical AI applications.

## License

This project is for educational and portfolio purposes.
