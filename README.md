# Composite Stock Risk Scoring System

## Overview
A multi-factor stock risk scoring engine that combines volatility, debt risk, momentum, and sentiment analysis into a single 0-100 composite score for publicly traded companies. Conceptually analogous to a credit score but for equity investments.

## Features
- **Volatility Score (25%)**: Measures price stability using standard deviation of daily returns
- **Debt Risk Score (25%)**: Evaluates financial leverage using debt-to-equity ratios from financial statements
- **Momentum Score (25%)**: Combines RSI distance-from-neutral and moving average crossover trends
- **Sentiment Score (25%)**: Analyzes recent news headlines using domain-specific FinBERT model

## Data Sources
- **Stock Data**: yfinance (Yahoo Finance)
- **Financial Statements**: yfinance (totalDebt, bookValue, sharesOutstanding)
- **News Headlines**: NewsAPI
- **Sentiment Analysis**: HuggingFace FinBERT (ProsusAI/finbert)

## Technical Stack
- **Language**: Python 
- **Libraries**: pandas, NumPy, yfinance, requests, transformers (HuggingFace)
- **Model**: FinBERT (domain-specific financial sentiment model)

## Final Risk Score Results
TSLA 72.64 (Highest risk - high volatility)
MSFT 34.79 (Moderate risk)
AAPL 34.29 (Moderate risk)
JPM 30.47 (Moderate risk)
BAC 15.22 (Lowest risk - stable bank)


## How to Run
1. Clone this repository: `git clone https://github.com/YOUR_USERNAME/stock-risk-scoring-system.git`
2. Install dependencies: `pip install yfinance pandas numpy requests transformers`
3. Get a free API key from [NewsAPI.org](https://newsapi.org)
4. Open `Stock_Risk_Scoring_System.ipynb` in Jupyter Notebook
5. Replace `NEWS_API_KEY` with your actual key
6. Run all cells

## Project Insights
- Tesla scores highest risk due to extreme volatility (100) despite low debt
- Banks (JPM, BAC) show moderate risk despite high debt-to-equity ratios (expected for financial institutions)
- Design choices prioritized domain-specific modeling (FinBERT over general-purpose sentiment models)
- Manual debt-to-equity calculation handles banking sector inconsistencies in standard APIs

## License
MIT License - See LICENSE file for details
