# Financial-Risk-Analysis
Overview
This project aims to analyze the financial performance and risk associated with investing in Apple Inc. (AAPL) and the S&P 500 index over the past three years. Using Python libraries, we fetch historical stock prices, calculate key financial metrics, and visualize the data to assist in making informed investment decisions.

# Scenario
ABC company plans to buy shares in Apple and the S&P 500 index with a target of optimizing profit within two years. The company seeks to understand how these investments have performed over the past three years and assess the associated risks.

# Tools and Libraries Used
pandas: For data manipulation,
yfinance: For fetching historical stock prices,
matplotlib: For data visualization,
numpy: For mathematical operations,
pyfolio: For performance analysis,

Installation
To install the necessary libraries, you can use pip:

pip install pandas yfinance matplotlib numpy pyfolio

# Data Fetching
We use the yfinance library to download historical stock prices for Apple and the S&P 500 index from January 1, 2020, to December 31, 2023.

# Key Calculations
Daily Returns: Percentage change in the 'Adj Close' column.
Volatility: Standard deviation of daily returns.
Beta: Measure of the stock's sensitivity to market movements.
Sharpe Ratio: Risk-adjusted return.
Value at Risk (VaR): Maximum expected loss with a 95% confidence level.
Alpha: Excess return over the benchmark.
Treynor Ratio: Excess return per unit of systematic risk.
Maximum Drawdown: Largest peak-to-trough decline.

# Visualization
We visualize:
Daily and weekly returns.
Cumulative returns over time.

# Key Results
Volatility: Indicates the degree of variation in the stock's price.
Beta: Reflects the stock's volatility compared to the market.
Sharpe Ratio: A positive ratio indicates a favorable risk-return profile.
VaR: Represents potential loss at a 95% confidence level.
Alpha: Positive alpha suggests outperformance.
Treynor Ratio: Indicates performance relative to market risk.
Maximum Drawdown: Measures the worst-case decline.

# Example
python
Copy code
Install Libraries
import pandas as pd
import yfinance as yf
import matplotlib.pyplot as plt
import numpy as np
import pyfolio

Download data using yfinance 
symbol = "AAPL"
start_date = "2020-01-01"
end_date = "2023-12-31"
data = yf.download(symbol, start=start_date, end=end_date)

Calculate the percentage change in the 'Adj Close' column
data['Returns'] = data['Adj Close'].pct_change()

Calculate volatility
volatility = np.std(data['Returns'])

Visualize returns
plt.figure(figsize=(10,6))
plt.plot(data.index, data['Returns'], label="Daily Returns")
plt.title("Daily Returns of {}".format(symbol))
plt.xlabel("Date")
plt.ylabel("Returns")
plt.legend()
plt.grid(True)
plt.show()

# Conclusion
The project provides a comprehensive analysis of the financial risk and performance of Apple and the S&P 500, assisting investors in making informed decisions. The positive Sharpe ratio and alpha suggest potential for positive risk-adjusted returns, though high volatility and beta indicate higher risk.

# Disclaimer
This analysis is for informational purposes only and should not be considered financial advice. Investors should consult with a financial advisor before making investment decisions.

