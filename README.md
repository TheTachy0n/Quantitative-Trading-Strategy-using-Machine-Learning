# Quantitative Trading Strategy using Machine Learning

An end-to-end quantitative trading project that leverages machine learning to predict market direction and generate trading signals using historical price data and technical indicators. The strategy is evaluated through backtesting and benchmarked against a traditional Buy & Hold approach using both return-based and risk-adjusted performance metrics.

## Project Architecture

```text
                    Historical Market Data
                           (Yahoo Finance)
                                  │
                                  ▼
                    Data Cleaning & Preprocessing
                                  │
                                  ▼
                     Exploratory Data Analysis
                                  │
                                  ▼
                      Feature Engineering
        ┌───────────────────────────────────────────────┐
        │ Returns • Moving Averages • RSI • MACD       │
        │ Bollinger Bands • ATR • Volatility • Lags    │
        │ Momentum • Volume Features • Time Features   │
        └───────────────────────────────────────────────┘
                                  │
                                  ▼
                     Target Generation (5-Day Return)
                                  │
                                  ▼
                    Train / Validation Split
                                  │
                                  ▼
                     Machine Learning Models
        ┌───────────────────────────────────────────────┐
        │ Logistic Regression                           │
        │ Decision Tree                                 │
        │ Random Forest                                │
        │ XGBoost (Final Model)                        │
        └───────────────────────────────────────────────┘
                                  │
                                  ▼
                    Hyperparameter Tuning & Evaluation
                                  │
                                  ▼
                  Trading Signal Generation (Buy/Sell)
                                  │
                                  ▼
                         Strategy Backtesting
                                  │
                                  ▼
              Performance & Risk Evaluation
        ┌───────────────────────────────────────────────┐
        │ Total Return                                 │
        │ Annual Return                                │
        │ Volatility                                   │
        │ Sharpe Ratio                                 │
        │ Sortino Ratio                                │
        │ Maximum Drawdown                             │
        │ Trade Statistics                             │
        └───────────────────────────────────────────────┘
                                  │
                                  ▼
             Comparison with Buy & Hold Benchmark
```

## Features

- Historical market data collection using Yahoo Finance
- Feature engineering with technical indicators (RSI, MACD, Moving Averages, Bollinger Bands, ATR, Volatility, etc.)
- Machine learning models:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - XGBoost
- Hyperparameter tuning and model evaluation
- Trading signal generation
- Strategy backtesting
- Performance comparison against Buy & Hold
- Risk analysis and trading statistics

## Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- yfinance
- ta
- Matplotlib
- Seaborn
- Plotly
- Jupyter Notebook

## Project Workflow

1. Data Collection
2. Exploratory Data Analysis (EDA)
3. Feature Engineering
4. Target Generation
5. Model Training & Hyperparameter Tuning
6. Model Evaluation
7. Signal Generation
8. Strategy Backtesting
9. Risk & Performance Analysis

---
# Results

## Final Prediction Model

The final trading strategy uses an **XGBoost classifier** to predict the direction of **5-day future returns** based on technical indicators and engineered market features.

### Model Performance

| Model | Prediction Horizon | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|--------|-------------------:|---------:|----------:|--------:|---------:|--------:|
| XGBoost | 5 Days | 49.93% | 58.63% | 55.61% | 57.08% | 0.523 |

Although the standalone classification metrics are modest—reflecting the difficulty of predicting financial markets—the model was evaluated primarily on its **trading performance**, which is the more meaningful measure for quantitative trading systems.

---

## Backtesting Performance

| Metric | ML Strategy | Buy & Hold |
|---------|------------:|-----------:|
| Total Return | **34.49%** | 31.83% |
| Annual Return | **10.56%** | 9.81% |
| Annual Volatility | **16.71%** | 17.53% |
| Sharpe Ratio | **0.684** | 0.622 |
| Sortino Ratio | **0.883** | 0.883 |
| Maximum Drawdown | -22.39% | -22.39% |

### Trading Statistics

| Metric | Value |
|---------|------:|
| Number of Trades | 744 |
| Winning Trades | 299 |
| Win Rate | 40.19% |
| Average Win | 0.92% |
| Average Loss | -0.89% |
| Profit Factor | **1.14** |

---

## Key Findings

- Developed an **XGBoost-based trading strategy** to forecast **5-day market direction** using technical indicators.
- The strategy **outperformed a Buy & Hold benchmark**, achieving a **34.49% total return** versus **31.83%**.
- Generated a **higher annual return** while maintaining **lower volatility**, resulting in an improved **Sharpe Ratio (0.684 vs. 0.622)**.
- Despite a **40.2% win rate**, the strategy remained profitable with a **Profit Factor of 1.14**, illustrating that profitable trading depends on trade quality and risk management rather than prediction accuracy alone.
