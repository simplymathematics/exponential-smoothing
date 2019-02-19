Exponential Smoothing
========================================================
author: 
date: 
autosize: true

Source
========================================================
- Galit Shmueli, Videos on Exponential Smoothing on Youtube.


Moving Average
========================================================


Weighted Moving Average
========================================================


Simple Exponential Smoothing
========================================================
- Forecast future value using a weighted average of all previous values in the series
- Uses: Forecast a series with no trend and no seasonality
- Advantages: Simple, popular, adaptive
- Key concepts
    + Smoothing constant alpha
        - Determines how much weight is given to the past
        - alpha=1: past values have no effect on forecast
        - alpha=0: past values have equal effect on forecast (over-smoothing)
        - Typical: alpha is closer to 0 than 1
        - Alternative form: F(t+1) = F(t) + alpha * E(t)
        
            i.e. next_forecast = prev_forecast + alpha * (prev_forecast_error)


Alpha Parameter
=======================================================
- Set between 0 and 1
- Weights the previous forecast values relative to the new measured values
- Set value such that it minimizes the square error


Time Constant
======================================================
 $$ \alpha 1-e^{\frac{-\Delta T}}{\tau} $$




Holt's Exponential Smoothing
========================================================
- Sometimes called "double exponential smoothing"
- Series with trend but no seasonality
- Has two updating equations: one each for level and trend
    + Level Equation: Compared with SES, it adds a trend term for computing the level
    + Trend Equation: updates trend based on difference between the most recent level values
        - this allows trend to vary over time
- Has two smoothing constants, $\alpha$ and $\beta$



Winter's Exponential Smoothing
========================================================
- Sometimes called "triple exponential smoothing"
- Series with trend and seasonality
- Has three updating equations, one each for updating level, trend and seasonality
- Additive Seasonality: Forecast = Level + Trend + Seasonality
    + F(t+k) = L(t) + k*T(t) + S(t+k-M)
- Multiplicative Seasonality: Forecast = (Level + Trend) * Seasonality
    + F(t+k) = (L(t) + k*T(t)) * S(t+k+M)

Expanded Form
==========================================================
- For using more than 1 previous value to do forecast calculations

