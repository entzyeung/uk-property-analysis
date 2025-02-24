# UK Property Price Official Data (Monthly Update)
[Downloaded data are pushed to Kaggle](https://www.kaggle.com/datasets/lorentzyeung/price-paid-data-202304/)

This repository contains a Python script that monitors the UK Government’s Price Paid Data webpage for updates and automatically downloads the latest property price data. It is designed to:

- **Monitor for Updates:**  
  Check the official Price Paid Data page for changes to the "current month" update.

- **Download Data Files:**  
  When an update is detected, the script downloads:
  - A new monthly CSV file (e.g., "December 2024 data.csv") and preserves all previously downloaded monthly files.
  - The complete property price data file (`pp-complete.csv`), which is always replaced.
  - A `last_update.txt` file to keep track of the latest update.

- **Update a Kaggle Dataset:**  
  The script then updates the Kaggle dataset with the following behavior:
  - **Accumulates monthly CSV files:** Each new monthly file is added to the dataset without replacing older monthly files.
  - **Replaces `pp-complete.csv` and `last_update.txt`:** These files are updated each time a new version is released.
  - A metadata file (`dataset-metadata.json`) is generated to ensure proper dataset updates via the Kaggle API.

## Repository Structure

- **update_price_paid_data.py**  
  The main Python script containing functions to monitor, download, and update data.

- **dataset-metadata.json**  
  A generated metadata file used by the Kaggle API to update the dataset.  
  (This file is created automatically by the script if it does not exist.)

- **last_update.txt**  
  A text file that stores the last update key (i.e., the current month information).  
  (This file is updated by the script.)

- **Monthly CSV Files**  
  Files named like `December 2022 data.csv`, `December 2023 data.csv`, etc.  
  These accumulate over time as new monthly updates are downloaded.

## Dependencies

- Python 3.x
- [requests](https://pypi.org/project/requests/)
- [BeautifulSoup4](https://pypi.org/project/beautifulsoup4/)
- [kaggle_secrets](https://github.com/Kaggle/kaggle-api) (used within Kaggle Notebooks)

You can install the dependencies using:

```bash
pip install requests beautifulsoup4
