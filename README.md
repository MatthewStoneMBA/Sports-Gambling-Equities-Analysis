# Sports Gambling Equities Analysis


In May 2018, the Supreme Court voted to get rid of the Amateur Sports Protection act of 1992 (Hyperlink), and to allow the state to make the decision to allow sports gambling. Since then, more than 2 dozen states (hyperlink) have decided to legalize it. Many major players in the gambling industry have decided to develop their own platforms for online sports betting. Players including DraftKings, MGM Resorts, Caesars Entertainment, Barstool (Penn National Gaming) and FanDuel (Flutter Entertainment). 

## Data Gathering & Scope

Having access to equities data with the R package TidyQuant (hyperlink), I analyzed each of these major stocks – specifically the trading volume of each stock. I created a 2-week forecast for trading volume and compared the forecasts. In this analysis I conducted EDA, identifying seasonality and trends with Decomposition (fpp3 package (hyperlink)), and created a function that identifies the best fitting model for each individual stocks. The best fitting models were ARIMA (Autoregressive Integrated Moving Average) and ETS (Exponential Smoothing) for each stocks respectively. DraftKings and MGM Resorts had the highest forecasted trade volume, while FanDuel and CZR Entertainment had the lowest trading volume.


# Exploratory Data Analysis

