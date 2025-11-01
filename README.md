# Forecasting US Import Volume from Vietnam (1994-2024)

This project analyzes the macroeconomic factors influencing US imports from Vietnam over a 31-year period. It applies supervised machine learning to forecast future trade volumes and unsupervised learning (PCA & K-Means) to identify structural shifts in the trade relationship, particularly focusing on the impact of the **US-Vietnam Bilateral Trade Agreement (BTA)**.

*This project was completed for the AIL303m Machine Learning course.*

## 📊 Key Findings

* **Best Forecasting Model:** **Ridge Regression** provided the highest accuracy on the unseen test set (2020-2024), achieving an **R-squared of 0.8495**. This indicates its robustness in handling small, collinear time-series data.
* **Key Economic Drivers:** Feature importance analysis revealed that Vietnam's economic growth (`Ln(GDP_VN)`) and the implementation of the **BTA** were the most significant positive drivers of US import volume.
* **Structural Shift Confirmed:** Unsupervised K-Means clustering ($k=2$) successfully grouped the data into two distinct clusters that **align almost perfectly with the pre-BTA (1994-2001) and post-BTA (2002-2024) periods**. This provides strong quantitative evidence of the BTA's structural impact.

## 🛠️ Methodology

1.  **Dataset:** Time-series data (1994-2024) including US Imports, US GDP, Vietnam GDP, MFN Tariff Rates, and BTA policy flag. 
2.  **Target Variable:** `Ln(US_import)` (Natural log of import value) to stabilize variance and linearize the growth trend. 
3.  **Feature Engineering:** Created `GDP_Ratio` and `Tariff_Change` to capture relative economic size and the impact of policy adjustments.
4.  **Supervised Models:** Evaluated Linear, Polynomial, Ridge, Lasso, and Decision Tree Regression using a chronological train-test split (Train: 1994-2019, Test: 2020-2024).
5.  **Unsupervised Analysis:** Used PCA for dimensionality reduction and K-Means clustering (validated with the Elbow Method) to identify trade pattern shifts.

## 📂 Repository Structure

vietnam-us-trade-forecast/
├── data/
│   └── Data_submission.xlsx  
├── notebooks/
│   └── trade_analysis_notebook.ipynb
├── report/
│   ├── project_report.pdf
│   └── project_brief.docx
├── .gitignore
├── requirements.txt
└── README.md

## 🚀 How to Run

1.  Clone this repository:
    ```bash
    git clone [https://github.com/your-username/vietnam-us-trade-forecast.git](https://github.com/your-username/vietnam-us-trade-forecast.git)
    cd vietnam-us-trade-forecast
    ```
2.  Install the required packages (một môi trường ảo được khuyến nghị):
    ```bash
    pip install -r requirements.txt
    ```
3.  Open the notebook to run the analysis:
    ```bash
    jupyter notebook notebooks/trade_analysis_notebook.ipynb
    ```
4.  The original dataset can be found [here](https://data.mendeley.com/datasets/xph53svyf7/1). 