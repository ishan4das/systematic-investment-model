# Systematic Investment Model 
Description: A systematic trading system for investments in US equity market based on stock fundamentals implemented on Zipline engine.

In this model,the objective is to find quality stocks to invest in at a reasonable price by using the various fundamentals of the stock like Earnings ratios, valuation ratios, Operation ratios and other important metrics from the financial statements as the model's alpha factors. These numeric alpha factors are then winsorized, normalized and combined to give a separate alpha factor for each of the securities in the US equity universe. 

Then the model selects the top quartile of this universe based on the combined alpha factors. 

## Screenshot
![Screenshot](https://github.com/ishan4das/systematic-investment-model/blob/master/Screenshots/Fundamentals%20Trading%20System%20-%20Zipline.png?raw=true "Title")


## About the alpha factors
The alpha in the model comes from three components, each component with a set of fundamental indicators. 
I) Profitability factors: This component includes fundamental indicators like ROA, ROE, ROCE, Net Profit Margin, etc. These fundamentals guage the ability of a company to generate profits. 

II) Safety factors: This component includes fundamental indicators that tell us about the cash richness of the company, which in turn gives an idea about the ability of the company to meet it's short term and long term debt obligations. Indicators include ratios of Receivables, Operating Cash flows, Net Cash flows, Cash Balance with the fundamental indicators like Current Asset, Debt and Liabilities.  

III) Value factors: This component includes valuation indicators, which generally speaking, stand for the sentiment of the investors for these stocks. Since, market sentiment plays a major role in the price of a stock, this component is equally as important as the others. This component includes fundamental indicators like Price/Sales ratio, Book/Market ratio, etc.  

## Findings
Investing in value stocks with good profitable business model and rich cash flows, is the goal of this model. The several backtests that I did confirmed the fact that the generated portfolio had defensive characteristics in times of market volatility and out performed the benchmark index in the long run. 


## Scope for improvement
1) As the model currently allocates only if the SMA 50 > SMA 200 for the S&P 500. The reason why I added this filter was because the stocks that this model chooses are highly correlated with the benchmark indices but beat the benchmark by a significant amount during the uptrend. My next step would be to compliment this investment strategy by replacing the Simple Moving Average (SMA) filter with a filter based on Macro indicators, which will better guage the market direction. 

2) Currently the model allocates funds equally between all the stocks in the top quartile but this can be improved by using better asset allocation strategies like Markovitz Optimization to maximize the signal. 

3) The alpha factors at the moment are being added as is. But a better method would be to tune the hyperparameters of the model using techniques such as Lasso Regression, but this comes at the cost of over fitting the historical benchmark performance. 

4) The model at the moment does not have any upper bounds for sector specfic investment. This means that our portfolio might be carrying sector specific risks. To mitigate these, filters can be implemented on the basis of different sector-specific ETFs, and upper bounds can be set for each sector to get a desired diversification. 

5) This model can be integrated with various technical indicators to give great results. 
