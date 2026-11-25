# Supply Chain Analytics

**End-to-end exploratory data analysis of sales, procurement, supplier
performance, customer segments, and logistics operations.**

## 1. Project Title

**Supply Chain Analytics: Data-Driven Insights for Procurement, Sales,
and Logistics**

## 2. Brief Problem Statement

Supply chain operations involve interconnected decisions across
purchasing, supplier reliability, product pricing, customer demand, and
order fulfilment. Analysing these activities in isolation can make it
difficult to identify cost drivers, delivery bottlenecks, profitability
patterns, and opportunities for operational improvement.

This project uses a multi-table supply chain dataset to explore these
relationships and translate the analysis into practical business
insights. The workflow combines data inspection and cleaning, relational
data integration, derived-feature engineering, exploratory data analysis
(EDA), statistical analysis, and business recommendations.

The analysis is performed in Python using **Pandas, NumPy, Matplotlib,
and Seaborn**. Sales and customer/product information are analysed in a
sales-focused view, while procurement and supplier information are
analysed in a separate procurement-focused view. This avoids
inappropriate many-to-many joins between sales and procurement
transactions.

## 3. Project Objectives

-   Understand the structure, quality, and relationships of the supplied
    datasets.
-   Examine sales revenue, order profitability, discounts, and
    customer-segment performance.
-   Evaluate supplier reliability, procurement expenditure, and
    procurement delivery variance.
-   Investigate delivery-risk patterns across shipping modes and
    carriers.
-   Explore product pricing, cost, margin, and lifecycle patterns.
-   Identify trends over time and statistically unusual observations.
-   Develop evidence-based recommendations for supply chain and
    commercial decision-making.

## 4. Dataset Overview

The project uses six CSV files:

  -----------------------------------------------------------------------------
  Dataset                    Description                                Records
  -------------------------- --------------------- ----------------------------
  `customer_master.csv`      Customer identity,                             500
                             industry, market      
                             segment, country,     
                             city, and coordinates 

  `product_master.csv`       Product, SKU,                                  200
                             category, unit cost,  
                             standard price, and   
                             lifecycle dates       

  `supplier_master.csv`      Supplier location,                             100
                             on-time delivery      
                             rate, certification,  
                             and                   
                             preferred-supplier    
                             flag                  

  `sales_orders.csv`         Customer-product                            20,000
                             order transactions,   
                             pricing, discounts,   
                             shipping, delivery    
                             status, VAT, COGS,    
                             and profit            

  `procurement_orders.csv`   Supplier purchase                            2,000
                             orders, raw-material  
                             identifiers,          
                             quantities, costs,    
                             and planned/actual    
                             delivery dates        

  `data_dictionary.csv`      Field definitions and                           54
                             supporting dataset    
                             documentation         
  -----------------------------------------------------------------------------

**Total:** 22,854 records across six datasets.

The initial data-quality review identified 221 missing values
(approximately 99.91% completeness). Missing product discontinuation
dates are retained because they may indicate products without a recorded
discontinuation date. Missing supplier certification values are
represented as `Unknown` rather than assumed to mean that a supplier is
uncertified.

## 5. Analytical Approach

1.  **Data loading and understanding** --- inspect dataset dimensions,
    column types, descriptive statistics, missing values, and
    relationships.
2.  **Data cleaning** --- handle duplicates, standardise text values,
    convert data types, and preserve meaningful missing values.
3.  **Dataset visualisation and summarisation** --- compare dataset
    sizes, completeness, missingness, and variable types.
4.  **Data integration and derived features** --- create analytical
    views by joining related master and transaction tables; derive
    profit-margin, shipping schedule variance, procurement delivery
    variance, lead-time, product lifecycle, and exploratory geographical
    features where supported.
5.  **Univariate analysis** --- study profitability, discounts, delivery
    performance, procurement costs, and supplier performance
    distributions.
6.  **Bivariate analysis** --- investigate supplier reliability and
    procurement variance, discounts and profit, shipping mode and
    delivery risk, customer-segment value, and product cost versus
    price.
7.  **Multivariate analysis** --- explore combined
    supplier/category/cost patterns, customer location and shipping
    risk, product margin and discount patterns, and procurement
    bottlenecks.
8.  **Temporal analysis** --- examine monthly and quarterly sales,
    procurement expenditure, lead times, delivery variance, and product
    lifecycle patterns.
9.  **Outlier analysis** --- identify statistical extremes using the
    Interquartile Range (IQR) method. Outliers are investigated rather
    than automatically removed.
10. **Statistical analysis and reporting** --- summarise selected
    correlations and consolidate findings.
11. **Business recommendations** --- translate supported patterns into
    proposed operational and commercial actions.

## 6. Summary of Findings

-   The analysis covers **20,000 sales order records**, **2,000
    procurement orders**, **500 customers**, **200 products**, and **100
    suppliers**.
-   The initial data-quality assessment found approximately **99.91%
    overall completeness**. Most missing values were concentrated in
    product discontinuation dates and supplier certification levels.
-   Completed sales orders generated recorded revenue of
    **13,203,375.06** and recorded profit of **4,774,225.84** (in the
    dataset's monetary units).
-   The recorded actual late-delivery rate was approximately **79.57%**.
    This should be interpreted according to the dataset's
    `Delivery_Status` definition and the population included in the
    calculation.
-   The tested correlation between discount and profit was approximately
    **-0.254**, indicating a weak negative linear association in the
    analysed data. This does not establish that discounts cause lower
    profit.
-   The tested relationships between supplier on-time delivery rate and
    procurement delivery variance, procurement quantity and delivery
    variance, unit cost and standard price, and planned lead time and
    delivery variance were negligible in the reported correlation
    analysis.
-   Procurement analysis identifies supplier-level delivery variance and
    procurement expenditure patterns that can support supplier review
    and purchasing decisions.
-   Customer segment, industry, product category, discount level,
    shipping mode, and carrier comparisons provide additional context
    for commercial and fulfilment performance.
-   IQR-based outlier analysis highlights unusually high or low
    observations for investigation; statistical outliers are not
    automatically data errors.
-   Exploratory geographical distance estimates are available, but they
    are not verified shipment routes or actual transport distances.

*The figures above are dataset-derived results from the analysis
workflow. Re-run the notebook against the included source CSVs to
reproduce and verify the outputs.*

## 7. Key Business Recommendations

-   **Supplier performance management:** Monitor supplier delivery
    variance alongside historical on-time delivery rates and
    purchase-order counts. Investigate consistently delayed suppliers
    before changing sourcing allocations.
-   **Discount governance:** Review discount bands by product, customer
    segment, order status, and realised profit. Evaluate promotional
    effectiveness rather than judging discounts from correlation alone.
-   **Product and pricing strategy:** Compare product-level cost,
    standard price, realised profit, and sales contribution to identify
    products that may require pricing or portfolio review.
-   **Delivery performance:** Compare actual delivery outcomes
    separately from late-delivery risk flags. Review shipping modes and
    carriers using both delivery rates and sample sizes.
-   **Procurement planning:** Monitor planned versus actual delivery
    dates, procurement lead times, order quantities, and supplier-level
    patterns to identify potential bottlenecks.
-   **Data quality improvement:** Validate customer coordinates and
    location labels, supplier location data, product identifiers, and
    delivery-status definitions before using the analysis for
    operational routing or cost decisions.

These are proposed actions for further investigation, not guaranteed
improvements or quantified savings.

## 8. Tools and Technologies

-   **Language:** Python
-   **Environment:** Jupyter Notebook / Google Colab
-   **Data manipulation:** Pandas, NumPy
-   **Visualisation:** Matplotlib, Seaborn
-   **Version control and delivery:** Git, GitHub

No machine-learning model is required for this project; the focus is
exploratory, statistical, and business-oriented analysis.

## 9. Important Methodological Notes and Limitations

-   Sales and procurement are separate transaction processes. They are
    not directly joined into one transaction-level table because doing
    so can create many-to-many duplication.
-   `Late_Delivery_Risk_Flag` is treated as a risk indicator and is not
    interchangeable with the actual `Delivery_Status`.
-   `Shipping_Date_Actual - Shipping_Date_Scheduled` measures **shipping
    schedule variance**, not final customer delivery latency.
-   `Delivery_Date_Actual - Delivery_Date_Planned` measures
    **procurement delivery variance**. Procurement lead time is measured
    separately from the procurement order date.
-   Correlation describes association, not causation.
-   Financial calculations should use completed orders when describing
    realised sales performance. VAT treatment should follow the data
    dictionary's definition of `Order_Total`.
-   Geospatial distances are exploratory straight-line estimates.
    Supplier country-centroid coordinates and inferred product-based
    links do not establish actual supplier-to-customer fulfilment
    routes.
-   A single observed time period is not sufficient to establish
    recurring seasonal patterns.
-   IQR outliers are statistical flags and should be investigated before
    any exclusion or correction.

## 10. Repository Structure

The repository layout is:

``` text
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
```

Adjust the paths and filenames to match the files actually committed to
the repository.

## 11. How to Run the Project

1.  Clone or download the repository.

2.  Open the notebook in Jupyter Notebook or Google Colab.

3.  Ensure the six CSV files are available at the paths used in the
    notebook. If using Google Colab, upload the files or mount the
    appropriate Drive folder.

4.  Install the required packages if they are not already available:

    ``` bash
    pip install pandas numpy matplotlib seaborn jupyter
    ```

5.  Run the notebook cells in order, from data loading through the final
    report and exports.

## 12. Deliverables

-   Exploratory Data Analysis Jupyter Notebook (`.ipynb`)
-   Original CSV datasets
-   Project presentation (`.pptx` or `.pdf`)
-   This README file
-   Exported analysis tables, where applicable

**Project Repository:** `Supply‑Chain Operations Dataset for Advanced Analysis_TMP`\
**Project Type:** Exploratory Data Analysis (EDA) and Supply Chain
Business Analytics
