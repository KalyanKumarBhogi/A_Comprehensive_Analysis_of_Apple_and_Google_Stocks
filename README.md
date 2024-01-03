# A_Comprehensive_Analysis_of_Apple_and_Google_Stocks

Stock Market Comparison Analysis is the process of evaluating and comparing the performance of multiple stocks or financial instruments within the stock market. It aims to provide insights into how different stocks have performed relative to each other and the broader market indices.
# Stock Market Comparison Analysis:
Stock Market Comparison Analysis is a methodical examination of multiple stocks or financial assets within the stock market. It involves analyzing the performance of various stocks or assets to gain insights into how they have fared relative to each other and the broader market. It helps investors, financial analysts, and decision-makers make informed investment decisions.
# Stock Market Comparison Analysis using Python
I will start the task of Stock Market Comparison Analysis by collecting the stock price data of Apple and Google for the last quarter. To collect the data, I’ll be using the Yahoo Finance API. You can install the API by executing the pip command mentioned below on your terminal or command prompt:

pip install finance  </p>

**Now, let’s import the necessary Python libraries to get started with the task:**

import pandas as pd </p>
import yfinance as yf</p>
import plotly.io as pio </p>
import plotly.graph_objects as go </p>

**Now, let’s collect stock price data:**

# Define the tickers for Apple and Google </p>
apple_ticker = 'AAPL' </p>
google_ticker = 'GOOGL' </p>

# Define the date range for the last quarter </p>
start_date = '2023-07-01'</p>
end_date = '2023-09-30'

# Fetch historical stock price data using yfinance </p>
apple_data = yf.download(apple_ticker, start=start_date, end=end_date) </p>
google_data = yf.download(google_ticker, start=start_date, end=end_date) </p>

The above code sets up the analysis by defining the companies and date range of interest, and it fetches the historical stock price data for Apple and Google within that period. This data will serve as the basis for various financial analyses and comparisons, such as calculating returns, volatility, and other metrics to assess the performance and risk associated with these stocks.

**Now let’s calculate the daily returns of Apple and Google in the stock market:**

Calculate daily returns </p>
apple_data['Daily_Return'] = apple_data['Adj Close'].pct_change() </p>
google_data['Daily_Return'] = google_data['Adj Close'].pct_change() </p>

The above code sets up the analysis by defining the companies and date range of interest, and it fetches the historical stock price data for Apple and Google within that period. This data will serve as the basis for various financial analyses and comparisons, such as calculating returns, volatility, and other metrics to assess the performance and risk associated with these stocks

**Now let’s calculate the daily returns of Apple and Google in the stock market:**

# Calculate daily returns </p>
apple_data['Daily_Return'] = apple_data['Adj Close'].pct_change() </p>
google_data['Daily_Return'] = google_data['Adj Close'].pct_change() </p>

The above code sets up the analysis by defining the companies and date range of interest, and it fetches the historical stock price data for Apple and Google within that period. This data will serve as the basis for various financial analyses and comparisons, such as calculating returns, volatility, and other metrics to assess the performance and risk associated with these stocks.

Now let’s calculate the daily returns of Apple and Google in the stock market:
 
# Calculate daily returns </p>
apple_data['Daily_Return'] = apple_data['Adj Close'].pct_change()  </p>
google_data['Daily_Return'] = google_data['Adj Close'].pct_change() </p>

Now, let’s visualize the daily returns:

# Create a figure to visualize the daily returns </p>
fig = go.Figure() </p>

fig.add_trace(go.Scatter(x=apple_data.index, y=apple_data['Daily_Return'],
                         mode='lines', name='Apple', line=dict(color='blue'))) </p>
fig.add_trace(go.Scatter(x=google_data.index, y=google_data['Daily_Return'],
                         mode='lines', name='Google', line=dict(color='green'))) </p>

fig.update_layout(title='Daily Returns for Apple and Google (Last Quarter)',
                  xaxis_title='Date', yaxis_title='Daily Return',
                  legend=dict(x=0.02, y=0.95)) </p>

fig.show() </p>
![image](https://github.com/KalyanKumarBhogi/A_Comprehensive_Analysis_of_Apple_and_Google_Stocks/assets/144279085/79d2d1f8-1aa3-4f9c-9376-bb3da4fae710)

**Now let’s analyze the cumulative returns of Apple and Google for the last quarter:**

# Calculate cumulative returns for the last quarter  </p>
apple_cumulative_return = (1 + apple_data['Daily_Return']).cumprod() - 1   </p>
google_cumulative_return = (1 + google_data['Daily_Return']).cumprod() - 1  </p>

# Create a figure to visualize the cumulative returns </p>
fig = go.Figure() </p>

fig.add_trace(go.Scatter(x=apple_cumulative_return.index, y=apple_cumulative_return,
                         mode='lines', name='Apple', line=dict(color='blue'))) </p>
fig.add_trace(go.Scatter(x=google_cumulative_return.index, y=google_cumulative_return,
                         mode='lines', name='Google', line=dict(color='green')))  </p>

fig.update_layout(title='Cumulative Returns for Apple and Google (Last Quarter)',
                  xaxis_title='Date', yaxis_title='Cumulative Return',
                  legend=dict(x=0.02, y=0.95))  </p>

fig.show()  </p>

![image](https://github.com/KalyanKumarBhogi/A_Comprehensive_Analysis_of_Apple_and_Google_Stocks/assets/144279085/e06cc3c7-ab47-4966-a828-302ac8918584)

Here, we first calculated the cumulative returns for both Apple and Google over the last quarter. Cumulative returns represent the total percentage change in the stock’s value over a given period, considering the compounding effect of daily returns. Then, we compared the investment performance of Apple and Google during the specified period, showing which stock had higher or lower cumulative returns over that time frame. We can see that Google has higher cumulative returns compared to Apple over the last quarter.

Now, let’s analyze the volatility of Apple and Google:

# Calculate historical volatility (standard deviation of daily returns)  </p>
apple_volatility = apple_data['Daily_Return'].std()    </p>
google_volatility = google_data['Daily_Return'].std() </p>

# Create a figure to compare volatility  </p>
fig1 = go.Figure()  </p>
fig1.add_bar(x=['Apple', 'Google'], y=[apple_volatility, google_volatility],
             text=[f'{apple_volatility:.4f}', f'{google_volatility:.4f}'],
             textposition='auto', marker=dict(color=['blue', 'green']))  </p>

fig1.update_layout(title='Volatility Comparison (Last Quarter)',
                   xaxis_title='Stock', yaxis_title='Volatility (Standard Deviation)',
                   bargap=0.5) </p>
fig1.show()  </p>

![image](https://github.com/KalyanKumarBhogi/A_Comprehensive_Analysis_of_Apple_and_Google_Stocks/assets/144279085/46ea0d57-4be8-482f-a3d8-63e320d620c7)

  
We first calculated the historical volatility for both Apple and Google stocks. Volatility is a measure of how much the stock’s price fluctuates over time. In this case, we are calculating the standard deviation of daily returns to measure the volatility. Then we visualized the calculated volatility to assess and compare the volatility or risk associated with both Apple and Google stocks during the specified period. We can see that Google’s volatility is higher than Apple’s.

**It indicates that Google’s stock price experienced larger price fluctuations or greater price variability over the last quarter. Here’s what this difference in volatility may indicate:**

1. Google’s stock is considered riskier compared to Apple. Investors generally associate higher volatility with higher risk because it implies that the stock price can change significantly in a short period.
2. Google’s stock may be more sensitive to market conditions, economic factors, or company-specific news and events. This heightened sensitivity can result in larger price swings.
3. Traders and investors with a higher risk tolerance might find Google’s stock appealing if they are looking for opportunities to profit from short-term price movements.

# Now let’s compare the stock market of Google and Apple according to the stock market benchmark: </p>

market_data = yf.download('^GSPC', start=start_date, end=end_date)  # S&P 500 index as the market benchmark  </p>

Calculate daily returns for both stocks and the market </p>
apple_data['Daily_Return'] = apple_data['Adj Close'].pct_change() </p> 
google_data['Daily_Return'] = google_data['Adj Close'].pct_change() </p>
market_data['Daily_Return'] = market_data['Adj Close'].pct_change() </p>

# Calculate Beta for Apple and Google </p>
cov_apple = apple_data['Daily_Return'].cov(market_data['Daily_Return']) </p>
var_market = market_data['Daily_Return'].var() </p>

beta_apple = cov_apple / var_market  </p>

cov_google = google_data['Daily_Return'].cov(market_data['Daily_Return'])  </p>
beta_google = cov_google / var_market  </p>

# Compare Beta values </p>  
if beta_apple > beta_google:  </p>
    conclusion = "Apple is more volatile (higher Beta) compared to Google." </p>
else:  </p>
    conclusion = "Google is more volatile (higher Beta) compared to Apple." </p>

Print the conclusion  </p>
print("Beta for Apple:", beta_apple) </p>
print("Beta for Google:", beta_google) </p>
print(conclusion) </p>

![image](https://github.com/KalyanKumarBhogi/A_Comprehensive_Analysis_of_Apple_and_Google_Stocks/assets/144279085/b58c08ba-b92d-4b05-9b9d-70aac5b095ac)

In the above code, we are assessing how sensitive Apple and Google stocks are to overall market movements, providing insights into their relative volatility and risk about the broader U.S. stock market represented by the S&P 500 index.

# Summary
The Standard & Poor’s 500, often referred to as the S&P 500, is a widely recognized stock market index in the United States. The S&P 500 index includes 500 of the largest publicly traded companies in the United States, chosen for their market capitalization, liquidity, and industry representation. These companies span various sectors of the U.S. economy and provide a comprehensive view of the health and performance of the stock market.

In the above output, the beta value for Apple is approximately 1.2257. This beta value suggests that Apple’s stock is estimated to be approximately 22.57% more volatile or sensitive to market movements (as represented by the S&P 500 index) compared to the overall market. The beta value for Google is approximately 1.5303. This beta value suggests that Google’s stock is estimated to be approximately 53.03% more volatile or sensitive to market movements.

A beta greater than 1 suggests that a stock tends to be more volatile than the market. In this case, both Apple and Google have beta values greater than 1, indicating that they are expected to be more volatile and sensitive to market movements. Google’s higher beta value (1.5303) compared to Apple’s (1.2257) suggests that Google’s stock is estimated to have a higher degree of market sensitivity or risk compared to Apple. Investors should consider this information when making investment decisions, as higher-beta stocks can provide greater potential for returns but also carry a higher level of risk.

