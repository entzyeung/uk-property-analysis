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
