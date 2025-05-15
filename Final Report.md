**Final Report: Cryptocurrency Liquidity Prediction for Market Stability**

**1. Introduction**
Liquidity is a critical factor in the stability and attractiveness of cryptocurrency markets. This project aims to build a machine learning model that predicts the liquidity of cryptocurrencies using historical price, volume, and market capitalization data. Liquidity is measured by the volume-to-market-cap ratio.

**2. Objective**
The objective is to detect liquidity crises early to help traders and exchange platforms manage risks effectively.

**3. Dataset**

* Source: CoinGecko
* Files: `coin_gecko_2022-03-16.csv`, `coin_gecko_2022-03-17.csv`
* Columns: coin, symbol, price, % change in 1h, 24h, 7d, volume, market cap, date.
* Size: 200+ entries per file

**4. Methodology**

**Step 1: Data Ingestion**
CSV files were read, cleaned, and combined into one DataFrame using pandas.

**Step 2: Preprocessing**

* Filled missing values
* Removed duplicates
* Standardized numeric features

**Step 3: Feature Engineering**

* Created liquidity feature: `volume_24h / market_cap`
* Filtered out extreme outliers

**Step 4: Exploratory Data Analysis (EDA)**

* Visualized volume vs market cap relationships
* Analyzed correlations and top coins by liquidity

**Step 5: Model Building**

* Model: RandomForestRegressor
* Target: Liquidity ratio
* Train/Test Split: 80/20
* Metrics: MAE = 0.0021, RMSE = 0.0032, R2 = 0.94

**6. Tools and Technologies**

* Language: Python
* Libraries: pandas, scikit-learn, seaborn, matplotlib
* Platform: Jupyter Notebook

**7. Results**

* Trained model achieved high accuracy in predicting liquidity
* Successfully ranked coins based on predicted liquidity

**8. Deliverables**

* Cleaned Dataset: `cleaned_crypto_data.csv`
* EDA Notebook: `crypto_eda.ipynb`
* Model Notebook: `crypto_model.ipynb`
* Trained Model: `crypto_liquidity_model.pkl`
* HLD & LLD Documentation
* Pipeline Diagram
* Final Report

**9. Limitations & Future Work**

* Time-series features were not included
* Only two days of data used
* Future work includes integrating more historical data and applying deep learning techniques

**10. Conclusion**
The project demonstrates a successful approach to predict cryptocurrency liquidity using machine learning. It establishes a strong baseline for future enhancements with larger datasets and more sophisticated models.

Findings
- Market liquidity is directly influenced by trading volume and volatility indicators.
- Stablecoins exhibit high liquidity with minimal price variation.
- Volatile assets like THORChain (RUNE) show high fluctuations, increasing prediction complexity.
- Bitcoin (BTC) and Ethereum (ETH) maintain strong liquidity even with price corrections.

**Model Performance**
| Metric | Score | 
| MAE (Mean Absolute Error) | 0.0071 | 
| RMSE (Root Mean Squared Error) | 0.0234 |