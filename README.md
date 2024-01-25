## ML-Driven Trading Strategy for SPY Backtesting with Lumibot

# Overview

This project investigates a machine learning-powered trading strategy for the S&P 500 index ETF (SPY) using Lumibot. Backtesting analyzes the strategy's performance based on sentiment analysis of recent news headlines.

# Strategy:

Leverages FinBERT to analyze news headlines and estimate sentiment with high confidence (>99.9%).
Positions itself based on a fixed percentage of available cash (cash-at-risk).
Implements bracket orders with take-profit and stop-loss limits.
Buys/sells based on positive/negative sentiment with high confidence.
# Backtesting Setup:

Broker: Lumibot-Alpaca Paper account
Data source: Yahoo Finance
Backtesting period: Jan 24, 2023 - Jan 24, 2024
Symbol: SPY
Cash-at-risk: 50%
# Key Components:

MLTrader class inherits from Lumibot's Strategy class, implementing the core logic.
position_sizing calculates portfolio size based on cash and price.
get_dates defines the timeframe for analyzing news.
get_sentiment leverages FinBERT to analyze news headlines and return sentiment probability and direction.
on_trading_iteration performs the main trading logic based on cash, sentiment, and previous trade:
Buys 10 shares when news suggests positive sentiment with high confidence.
Sells all shares when news suggests negative sentiment with high confidence.
YahooDataBacktesting is used to access historical data for backtesting.
# Running the Backtest:

Install Lumibot and FinBERT:
pip install lumibot transformers
Replace API keys in main.py with your actual credentials.
Run the script:
python main.py
# Expected Output:

The script will print backtesting results, including metrics like total return, Sharpe ratio, and trade statistics.

# Future Work:

Optimize the cash-at-risk ratio.
Explore different sentiment analysis methods and thresholds.
Implement risk management strategies beyond stop-loss orders.
Test the strategy on live markets with caution.
# Disclaimer:

This is a backtesting experiment for educational purposes only. Past performance does not guarantee future results. Trading involves significant risk of loss.

# Feel free to modify or improve this code to suit your own research and testing goals.
