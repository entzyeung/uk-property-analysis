# **Full Report: Automated London Property Price Analysis Report**

This **full report** is a comprehensive, fully automated **monthly PDF report** as part of our data-driven pipeline for analyzing UK property transactions. Unlike the mini report, this **full version contains a wider set of in-depth analyses**, providing a **detailed breakdown of market trends, pricing movements, and transaction dynamics across London and other areas**.

## **Overview**

This report aims to **help homebuyers, investors, and researchers** understand the **UK property market trends** based on official data from the **UK Government's HM Land Registry**. The pipeline **automates data collection, processing, transformation, visualization, and reporting**, ensuring **each month's report contains the latest market insights**.

### **Data Sources and Pipeline Automation**
The dataset is sourced directly from **HM Land Registry's "Price Paid Data"** and automatically updated **every month**. The pipeline ensures **timely and consistent updates** by:
- **Daily monitoring** of the official **Gov.uk** website.
- **Scraping and downloading** new transaction data as soon as it is available.
- **Transforming and cleaning** data before integrating it into the Kaggle dataset.
- **Generating the latest property analysis visualizations**.
- **Publishing the updated report** to GitHub.

## **Pipeline Architecture**
This report is generated through a structured **ETL (Extract, Transform, Load) pipeline**, illustrated in the **Mermaid diagram below**:

```mermaid
flowchart TD
    subgraph "Initial Archive Fetch"
        A[Fetch Kaggle Data Set] --> B[Force Refresh]
    end

    subgraph "Daily ETL Pipeline"
        B --> BB[Daily Gov.uk Webpage Monitoring]
        BB --> C[Scrape Gov.uk Webpage]
        C --> D[Download Latest Data]
        D --> E[Transform Data in Staging]
        E --> F[Push Updated Data to Kaggle Dataset]
        F --> A
    end

    subgraph "Monthly PDF Report Pipeline"
        B --> G[Retrieve Latest Data for Visualization]
        G --> GG[Data Engineering &<br/>Transformation]
        GG --> H[Generate Visualizations<br/>e.g. For Timeline, Median Price, Momentum,<br/>etc.]
        H --> I[Automatically Generate<br/>PDF Report]
        I --> J[Deploy PDF Report<br/>to GitHub]
    end
```

---

## **Topics Covered in the Full Report**
This full report expands upon the mini report with **deeper insights and additional analyses**.

  Each section is clearly separated by comments.
  - Section 1: Overall monthly median price trend  
  - Section 2: District-level median price trends (with separate detailed subplots)  
  - Section 3: Heat map for average prices  
  - Section 4: Heat map for transaction counts  
  - Section 5: Top 20 postcode-based transaction count heat map  
  - Section 6: 4 property types median price trends and table  
  - Section 7: Highest value cities analysis (using total transaction values and new properties)  
  - Section 8: YoY median price growth (same period comparison)  
  - Section 9: YoY median price growth (same month comparison)  
  - Section 10: Timeline comparison for transaction count and median price  
  - Section 11: Transaction momentum analysis  
  - Section 12: Monthly growth table for median and mean prices  

## **Report Format**
- **Landscape PDF format** for better visualization.
- **Each chart is presented in both English & Traditional Chinese**.
- **One visualization per page** for clarity.
- **Final blank page indicates the end of the report**.

## **Accessing the Report**
- The latest version of the **full report** is published in the [GitHub full-reports folder](https://github.com/entzyeung/uk-property-analysis/tree/main/full-reports).

---

## **Conclusion**
This **full report provides an extensive, automated analysis of London’s real estate market**, helping professionals, investors, and homeowners stay informed with **data-driven insights**. With automated **data collection, transformation, visualization, and reporting**, this project delivers **accurate and timely information every month**.

For inquiries or collaboration opportunities, please contact **Lorentz Yeung**.



