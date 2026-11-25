# Supply-Chain Operations Dataset for Advanced Analysis

# 📌 Project Title
Supply-Chain Operations Dataset for Advanced Analysis

# ❓ Brief Problem Statement
Problem

Supply chain data is spread across 6 tables (customers, products, suppliers, sales, procurement, data dictionary)

Delivery delays, heavy discounting and supplier reliability are hard to see without combined analysis

Approach :

Cleaned and validated 22,854 records

Ran univariate, bivariate, multivariate, temporal, outlier and statistical analysis

Created derived features: gross margin, fulfillment latency, lifecycle stage, customer-supplier distance

Converted findings into prioritised recommendations

# 🔑 Summary of Findings
Data Quality: 99.95% complete; only Discontinuation_Date and Certification_Level had gaps

Profitability: Total profit 5.61M; median profit per order 240.47; completed-order gross margin averages 37.18%

Discounts: 33.08% of orders exceed standard gross margin; discount vs profit correlation is -0.254 (weak negative)

Delivery: 79.57% of orders are late or risk-flagged; average shipping delay 1.98 days

Highest Risk Lane: Italy with Standard shipping (84.06% risk)

Procurement: 61.7% of purchase orders arrive late; average delay 1.58 days

Suppliers: Historical on-time rate does not predict actual delays (negligible correlation)

Top Spend: Nova Eco LLC (supplier) and Food (category)

Seasonality: Revenue and orders peak in May 2023; shipping delays peak in August

Statistics: No strong linear relationships found; outliers are only 0.55% on average

# 🎯 Project Overview
Objectives

Primary Goal: Perform comprehensive Exploratory Data Analysis on a multi-table supply chain dataset covering customers, products, suppliers, sales orders and procurement orders

Business Focus: Identify patterns in profitability, discounting, delivery performance and supplier reliability to improve supply chain decision-making

Deliverables: End-to-end analysis with strategic recommendations for supply chain, sales and procurement teams

# Dataset Information
Domain: Supply Chain Operations & Business Analytics

Scope: 6 datasets with 22,854 records and 58 columns, including 20,000 sales orders and 2,000 procurement orders

Key Variables: Order_Total, Profit_Per_Order, Discount, Shipping_Mode, Shipping_Carrier, Delivery_Status, Late_Delivery_Risk_Flag, On_Time_Delivery_Rate, Total_Cost, Certification_Level

| Dataset | Records | Columns | Purpose |
|---|---|---|---|
| Customer Master | 500 | 8 | Customer, industry, market segment and location |
| Product Master | 200 | 10 | SKU, category, unit cost, standard price, lifecycle dates |
| Supplier Master | 100 | 7 | Supplier region, certification, on-time delivery rate |
| Sales Orders | 20,000 | 20 | Order, pricing, discount, profit and shipping details |
| Procurement Orders | 2,000 | 9 | Purchase orders, raw materials, planned and actual delivery |
| Data Dictionary | 54 | 4 | Column definitions across all tables |

Analysis Period: Multi-year order history (monthly peak identified in May 2023; procurement peak in March 2022)

# 🔍 Analysis Framework - 5 Phase Approach
# 📋 Phase 1: Data Foundation & Quality Assessment
Objective: Establish data reliability and completeness for supply chain analytics

Dataset loading from the zipped source files and initial exploration

Missing value analysis (dataset-level, column-level and heatmaps)

Data cleaning: duplicate removal, text standardisation, date and numeric conversion

Handling of missing Certification_Level (labelled "Unknown") and preservation of Discontinuation_Date

Deliverables: Clean, analysis-ready supply chain datasets (99.95% complete before cleaning)

# 📊 Phase 2: Descriptive Intelligence Gathering
Objective: Understand distributions and basic patterns across all tables

Overall, numerical, categorical and column-wise data summaries

Univariate analysis of profit, discount, delivery status, procurement cost and supplier performance

Histograms with KDE, box plots, count plots and donut charts

Deliverables: Comprehensive descriptive statistics report for supply chain variables

# 🔍 Phase 3: Advanced Pattern Recognition
Objective: Deep-dive analysis of relationships and drivers of performance

Bivariate analysis: supplier reliability vs delays, discount vs profitability, shipping mode and carrier risk, segment and industry performance, price vs cost

Multivariate analysis: supplier-category-cost interactions, location-shipping-risk, product margin and discount matrix, procurement bottlenecks

Correlation heatmap and pair plot of sales variables

Deliverables: Advanced analytical insights with supply chain specific visualizations

# 🎯 Phase 4: Temporal Operations - Statistical Deep Dive
Objective: Outlier detection, temporal trend analysis and statistical testing

IQR-based outlier detection across sales, product, procurement, delivery and supplier variables

Monthly and quarterly revenue, order volume and procurement expenditure trends

Product lifecycle sales velocity, procurement lead time by region and fulfillment latency seasonality

Pearson correlation based statistical analysis with strength classification

Deliverables: Outlier analysis and temporal supply chain trend insights

# 📋 Phase 5: The Final Briefing - Derived Features & Strategic Recommendations
Objective: Synthesize insights into actionable supply chain strategies

Derived features: gross profit margin, fulfillment latency, product lifecycle stage and geospatial customer-supplier distance (Haversine)

Key Findings & Summary Report

Evidence-based recommendation development and success metrics definition

Deliverables: Executive summary with strategic supply chain recommendations

# 📈 Key Findings & Insights
# 🎯 Data Quality Insights
22,854 total records across 6 datasets with 99.95% completeness

221 missing values before cleaning, 200 after (Certification_Level filled with "Unknown")

Missing values concentrated in two columns: Product Master Discontinuation_Date and Supplier Master Certification_Level

No duplicate rows found in any dataset

# 🏭 Sales & Profitability Analysis
Total profit across 20,000 orders: 5,606,605.76; average 280.33 and median 240.47 per order

Profit per order ranges from -346.97 to 2,005.80

16,980 completed orders (about 84.9% completion rate) across all 500 customers

Average gross profit margin on completed orders is 37.18% (median 36.43%), with 1,346 negative-margin transactions needing investigation

Profit is not concentrated: the top 10 SKUs contribute only 11.49% of total profit

# 💰 Discount Impact Analysis
Average discount 12.52%, median 13%, maximum 25%

6,616 orders (33.08%) carry a discount exceeding the product's standard gross margin

Discount and profit show a weak negative correlation (r = -0.254), the strongest relationship found in the study

# ⭐ Delivery & Fulfillment Performance
15,915 orders (79.57%) are flagged as late delivery risks and have a "Late" delivery status

Average shipping delay is 1.98 days (maximum 4 days); no order ships early

Highest delivery risk observed: Italy with Standard shipping (84.06%)

Risk flag and late status show identical counts, so they should be validated as separate measures

# 🚛 Procurement & Supplier Analysis
2,000 purchase orders with total spend of 915,533.47; average 457.77 and median 413.31 per order

Top 10 raw materials account for only 10.31% of spend (low concentration)

Highest-spend supplier: Nova Eco LLC (20,930.13); highest-spend category: Food (165,592.94)

Average supplier on-time delivery rate is 0.80; 46% of suppliers are preferred

61.7% of procurement orders are late (1,234 late, 571 early, 195 on time), with a 1.58-day average delay

Supplier on-time rate shows negligible correlation with actual delivery variance, so historical reliability is not predicting real delays

# 📅 Temporal Trend Analysis
Peak revenue and order volume month: May 2023 (446,409.58 revenue; 662 orders)

Peak procurement spend month: March 2022 (31,848.48)

Slowest procurement region: East (19.03-day average lead time)

Highest average shipping delay month: August (2.05 days)

Orders from products 365+ days post-launch sell the most units in the temporal view (27,693 units)

# 🔬 Outlier, Statistical & Geospatial Findings
Average outlier rate across analysed variables is 0.55%; highest in Sales (1.38%), led by Order Quantity (2.13%)

No strong linear relationships found: 4 negligible and 1 weak correlation among tested pairs

Estimated customer-supplier distance averages 9,960 km across 48,458 customer-supplier pairs

# 🛠️ Technical Implementation
Technologies Used :
python
pandas
matplotlib
seaborn

# Core Libraries
pandas==2.2.3          # Data manipulation and analysis
numpy==2.4.6           # Numerical computing
matplotlib==3.10.0     # Static visualizations
seaborn==0.13.2        # Statistical data visualization

# Analysis Tools
jupyter / google colab  # Interactive development environment

Project Structure

text

Supply‑Chain Operations Dataset for Advanced Analysis_TMP/
│
├── Supply_Chain_Datasets/
│   ├── customer_master.csv
│   ├── product_master.csv
│   ├── supplier_master.csv
│   ├── sales_orders.csv
│   ├── procurement_orders.csv
│   └── data_dictionary.csv
│
├── README.md
│   
├── presentation/
│   └── (project presentation)
│
└── Supply_Chain_Advanced_Analytics_Debjyoti_Barik.ipynb                     

# 🎯 Strategic Recommendations Summary
# Priority 1 - Immediate Actions (0-30 days)
Delivery Performance Recovery

Investigate why nearly 80% of orders ship late, starting with high-risk lanes such as Italy with Standard shipping

Validate the late-delivery risk flag against actual delivery status

Review scheduling assumptions between planned and actual shipping dates

Discount Governance

Review the 33% of orders where discounts exceed standard gross margin

Set discount caps by product category and market segment

# Priority 2 - Short-term Initiatives (1-3 months)
Supplier Performance Management

Replace reliance on historical on-time rates with actual delivery variance tracking

Target slow regions (East) and high-delay suppliers for corrective plans

Review certification-level impact on delays, including ISO 9001 suppliers

Margin & Pricing Optimization

Investigate negative-margin transactions and categories with weak standard margins

Prioritise high-margin segments such as Beauty (B2B)

# Priority 3 - Long-term Strategy (3-12 months)
Temporal Strategy Excellence

Build demand forecasting using the May seasonal peak and quarterly trends

Plan capacity and carrier allocation ahead of high-delay months such as August

Network & Sourcing Optimization

Evaluate the long average customer-supplier distance (about 9,960 km) for regional sourcing opportunities

Develop predictive models for late delivery and supplier delays

# 💰 Expected Impact
Projected Outcomes

Delivery Improvement: Reduce late-order share from 79.57% through lane and carrier review (target to be set by business)

Margin Protection: Bring the 6,616 over-discounted orders back within standard margin limits

Procurement Reliability: Reduce the 61.7% late purchase order share through supplier actions

Data-Driven Planning: Seasonality and lifecycle insights for inventory and capacity decisions

Note: impact figures are improvement targets, not modelled forecasts.

# 📊 Key Performance Indicators
Business Metrics

Late Delivery Rate: Monthly tracking by shipping mode, carrier and country

Average Profit Margin: Tracked by category, segment and discount band

Discount Exposure: Share of orders with discount above standard margin

Supplier On-Time Delivery: Actual delivery variance vs recorded rate

Procurement Spend: By supplier, category and region

Operational Metrics

Data Quality Score: Ongoing completeness and validation checks

Analysis Accuracy: Forecast vs actual delivery and demand performance

Implementation Speed: Time-to-insight for new supply chain issues

# 🚀 Getting Started
Prerequisites
bash
# Python 3.8 or higher
python --version

# Required packages installation
pip install pandas numpy matplotlib seaborn jupyter
Running the Analysis
bash
# Navigate to project directory
cd supply-chain-analytics

# Launch Jupyter Notebook
jupyter notebook Supply_Chain_Analytics.ipynb

# Run all cells sequentially for complete analysis
# (In Google Colab, upload Supply_Chain_Datasets.zip when prompted)

# 📋 Analysis Execution Guide

Step-by-Step Execution

Data Loading: Execute Phase 1 cells for data import, quality checks and cleaning

Exploratory Analysis: Run Phase 2 cells for descriptive and univariate analysis

Pattern Recognition: Execute Phase 3 cells for bivariate and multivariate analytics

Statistical Analysis: Run Phase 4 cells for temporal, outlier and statistical analysis

Strategic Insights: Execute Phase 5 cells for derived features and the final report


# 🏆 Acknowledgments
Data providers for the supply chain operations dataset

Supply chain and operations analysts for industry context and validation

# 📄 License
This project is submitted for educational and research purposes. All analysis and insights are based on the supplied supply chain operations dataset.

# 🎯 Executive Summary
Supply-Chain Operations Dataset for Advanced Analysis successfully completed a comprehensive EDA delivering data-driven strategies for supply chain optimization. Our multi-phase analytical approach identified critical delivery risks, discount-related margin exposure, supplier reliability gaps and seasonal patterns across sales and procurement operations.

# Result:
Evidence-based insights positioning supply chain teams for improved delivery performance, protected margins and stronger supplier management through targeted discount controls, reliability tracking and data-driven planning. The analysis reveals clear pathways to reduce late deliveries and procurement delays while sustaining profitability across customer segments and product categories.
