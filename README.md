# VaR (Value-at-Risk) calculator
***
Yet another VaR online calculator, yet this one -  with catchy graphics! 

# A bit of theory
This module provides an easy-to-use Python class, VaR, designed to calculate Value-at-Risk (VaR) through three distinct methods: Historical, Parametric, and Monte Carlo Simulation. Each method offers a unique approach to risk assessment, enabling flexible and robust analysis of potential financial losses. Whether you're dealing with historical data or need to simulate scenarios, the VaR class provides a comprehensive toolkit for quantifying risk with precision and ease.

## Historical Method
The Historical Method of calculating Value-at-Risk (VaR) leverages actual historical return data to estimate potential future losses. By assuming that past market behavior can provide insights into future risk, this method involves sorting historical returns and identifying the worst losses over a specified period. The advantage of the Historical method lies in its simplicity and the fact that it doesn't require any assumptions about the underlying distribution of returns. However, it assumes that history will repeat itself, which may not always hold true in volatile or changing markets.

## Parametric Method
The Parametric Method for calculating Value-at-Risk (VaR) is based on statistical assumptions, typically assuming that asset returns follow a normal distribution. This method calculates VaR using the mean and standard deviation of returns, along with a confidence level, to estimate potential losses. The Parametric approach is computationally efficient and straightforward, making it popular for quick risk assessments. However, its reliance on the normality assumption may not capture the tail risks accurately, especially in markets with non-normal return distributions or extreme events.

## Monte Carlo Simulation
The Monte Carlo Simulation method for calculating Value-at-Risk (VaR) involves generating a large number of possible future price scenarios based on random sampling from the assumed distribution of asset returns. This method is highly flexible and can accommodate complex distributions, correlations, and non-linear relationships between assets. By simulating a broad range of potential outcomes, Monte Carlo Simulation provides a more comprehensive view of potential risk, especially in cases where market behavior deviates from normality. However, it is computationally intensive and requires careful selection of the input parameters to ensure accurate results.

# Modules needed
- yfinance: the venerable one to get all the necessary financial histo;
- numpy: for all the numbers crunching
- matplotlib: for catchu gaphics

# How to Use:
Initialize the VaR class with the following parameters:
- `ticker`: list of tickers of stocks in the portfolio (accepts standart tickers e.g.: `GOOG`, `AMZN`, `MSFT`, etc.);
- `start_date`, `end_date`: start and end dates for historical data (accepts dates in `YYYY-MM-DD` format);
- `rolling_window`: rolling window size for historical metod (accepts integer value for number of days (e.g.: `252`));
- `confidence_level`: confidence level for VaR calculation, accepts percentage values as float (e.g., `0.95` for `95%`);
- `portfolio_val`: total portfolio value (accepts int for value);
- `simulations`: number of simulations for Monte Carlo method (accepts int for value);;

## Example

```
var_model = VaR(ticker=['GOOG', 'AMZN'], 
                start_date='2020-01-01', 
                end_date='2024-08-008', 
                rolling_window=252, 
                confidence_level=0.95, 
                portfolio_val=1000000, 
                simulations=1000)
```
