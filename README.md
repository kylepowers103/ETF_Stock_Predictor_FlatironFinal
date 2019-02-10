# ETF_Stock_Predictor_FlatironFinal

## Project: Predict Tomorrow’s Stock Price

###### Created 3 models for 28 stocks using exogenous data sources that I thought could have an impact on broader capital markets
    - 1) LSTM Model Prediction w/ exogenous variables and feature engineering
    - 2) LSTM Model Prediction using only 1,3,5,21,35 day return variables
    - 3) Facebook Prophet Prediction

## Data Sources
- Quandl, Alpha-vantage, University of Michigan Surveys,data.gov, Google.com

## Feature Engineering/Technical indicators
 - Daily Stock data going back to 1990
    - 20 Variations of each stock daily open,close,volume including:
    - High-low difference
    -Percent change
    - 3,10,35 day moving average,standard deviation and percentchange

## Exogenous Economic Data:
- Consumer Sentiment Report (Monthly)
- Consumer Market Confidence Report (Monthly)
- Change in Home Values During the Past Year (Monthly)
- Gold Prices (Daily)
- Ten-year Treasury yield (Daily)
- Consumer-Price-Index (Inflation) (Monthly)
- S&P 500 Composite Prices (Daily)
- Crude Oil Futures (Daily)
- Current Market Value of Primary Residence (Monthly)*
- Probability of Real Income Gains During the Next 5
- Years (Monthly)*
*University of Michigan Survey Data


## Forecasting Methodology
- LSTM Neural Network is trained using Keras to predict the following day's closing price
    - LSTMs are widely used for sequence prediction problems and have proven to be extremely effective. The reason they work so well is because LSTM is able to store past information that is important, and forget the information that is not. LSTM has three gates:
        - The input gate: The input gate adds information to the cell state
        - The forget gate: It removes the information that is no longer required by the model
        - The output gate: Output Gate at LSTM selects the information to be shown as output
 
- Baseline models used included a naive baseline model (assuming price remains the same as the previous day) and Facebook Prophet Timeseries prediction.

Metrics examined: 
    -Root Mean Square Error (RMSE)
    -R-Squared
    -Mean Absolute Error (MAE) 


## Further Improvements
- 1)Look at longer batch windows or predictions further out, because a lot of the economic data is monthly and doesn't have a large meaning on prediction tomorrow's data unless a new report came out. Also a lot of technical indicators are better predictors or medium/longer term trends
    - (Largest correlation to prediction was 1 and 5 day performance for most models)
    - Consistent top correlations: percent change in volume over prior day (log) and difference in volume change (Would like to expand on volume variables)
    
-2) Implement NLP on Social Media and 10Q-10K statements to see impacts on stock performance given sentiment regarding stocks

-3) Add pre-market future data as variables to assess if the stock is likely to close higher or lower before the market opens

-4) Additional Feature Engineering on Exogenous Data


## Example Result for Disney:
#### LSTM Model DIS Models:
![Imag1](/ReadmePhotos/gitDISallfeatures.png)
Format: ![Alt Text](url)

![Imag1](/ReadmePhotos/gitDISnofeatures.png)
Format: ![Alt Text](url)

#### Facebook Prophet DIS Model 
![Imag1](/ReadmePhotos/gitDISfbprophet.png)
Format: ![Alt Text](url)

![Imag1](/ReadmePhotos/gitDISfbprophet2.png)
Format: ![Alt Text](url)