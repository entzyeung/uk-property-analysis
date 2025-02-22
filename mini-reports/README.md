
flowchart TD

%% Data Ingestion and Refresh
A[Force Refresh Kaggle Dataset] --> B[Scrape Gov.uk Webpage]
B --> C[Download Latest Data]

%% Data Transformation and Update
C --> D[Transform Data in Staging<br/>(e.g., Remove First Column)]
D --> E[Push Updated Data<br/>to Kaggle Dataset]

%% Visualization and Reporting
E --> F[Retrieve Latest Data<br/>for Visualization]
F --> G[Generate Visualizations<br/>(Timeline, Median Price, Momentum)]
G --> H[Generate PDF Report]

%% Final Step: Publish Report
H --> I[Push PDF Report<br/>to GitHub]

%% Add Labels for Clarity
classDef ingestion fill:#f9f,stroke:#333,stroke-width:2px;
classDef transform fill:#bbf,stroke:#333,stroke-width:2px;
classDef viz fill:#bfb,stroke:#333,stroke-width:2px;
class A,B,C ingestion;
class D,E transform;
class F,G,H,I viz;
    
