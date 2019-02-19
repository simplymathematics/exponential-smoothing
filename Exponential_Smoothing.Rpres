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
- Averages all the previous data to come up with a forecast.
- Does not handle seasonality well
- Does not handle negative trends well 


$$ \frac{1}{n}\sum_{i=0}^{n-1}p_{m-i} $$

Weighted Moving Average
========================================================
- like the above, but there are scalar multipliers included
- defined mathematically as a convolution of the data with a fixed weighting function
- For an n-day moving average, the weights descrease in an arithmetic progression
$$ WMA = np_m + (n-1) p_{m-1} + ... + 2p_{M-n+2} + p_{m-n+1} $$


Simple Exponential Smoothing
========================================================
- Forecast future value using a weighted average of all previous values in the series
- Uses: Forecast a series with no trend and no seasonality
- Advantages: Simple, popular, adaptive, removes high-frequency noise
- Key concepts
    + Smoothing constant alpha
        - Determines how much weight is given to the past
        - alpha=1: past values have no effect on forecast
        - alpha=0: past values have equal effect on forecast (over-smoothing)
        - Typical: alpha is closer to 0 than 1
        - Alternative form: F(t+1) = F(t) + alpha * E(t)
        
            i.e. next_forecast = prev_forecast + alpha * (prev_forecast_error)
            
Basic Example
=====================================================
TODO

Why is it called exponential smoothing?
======================================================
- It uses a convolution of the exponential window function with the data
- By using the recursive definition, we see an exponentially decreasing weight on our previously forecasted data

$$ \alpha [x_t + (1-\alpha)x_{t-1} + (1-\alpha)^2 x_{t-2} + (1-\alpha)^3 x_{t-3} + \cdots + (1-\alpha)^{t-1} x_1 $$


Alpha Parameter
=======================================================
- Set between 0 and 1
- Weights the previous forecast values relative to the new measured values
- Set value such that it minimizes the square error


Time Constant
======================================================
There is a relationship between the smoothed response curve and the original signal. The points at which the response signal equals
$$ 1-\frac{1}{e} \approx 63.2\% $$

This relationship is also seen in the alpha parameter

$$ \alpha 1-e^{\frac{-\Delta T}}{\tau}$$



Optimization
======================================================
TODO

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
- For using more than 1 previous value to do forecast calculations.
- TODO: Example

