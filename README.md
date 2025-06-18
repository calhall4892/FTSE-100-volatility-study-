# FTSE-100-volatility-study-

## 1.0 Introduction
This project is designed to act as an introduction into financial modelling and time series analysis. It will use a ml researcher approach in that a large portion of this will be a research based approach and not just making and producing the model. The project will consist of 8 key phases totalling around 16 weeks and will roughly consist of the following;

* Phase 1: Foundational Understanding and Problem Formulation (Weeks 1-2)
* Phase 2: Data Acquisition and Preprocessing (Week 3)
* Phase 3: In-depth Exploritory Data Analysis & Feature Engineering (Weeks 4-5)
* Phase 4: Model Selection and Deep Dive (Weeks 6-9)
* Phase 5: Training, Validation and Testing Strategy (Week 10)
* Phase 6: Model Implementation, Training and Hyperparameter Tuning (Weeks 11-13)
* Phase 7: Results, Comparison & Critical Analysis (Weeks 14-15)
* Phase 8: Conclusions and Future Work (Week 16)

## 2.0 Research
The research chapter contains all of the key elements and areas of interest that arise during the project. This will cover all aspects of both finance and ml (including core mathematics). This will be used as a guide and can be referred back if needed. This is also to serve as a template for future research carried out on this Github.

### 2.1 Core Concepts

#### 2.11 Time series

A time series is a sequence of data points that has been collected over a period of time. It is used in a number of different industries and applications such as finance, healthcare and transport. This is often complied over a set period of time such as hourly, daily, weekly etc. Time series analysis is the statistical analysis of the sequences of these data points over the period of time. It then infers what has happened over the historical period and then attempts to predict what will happen in the future. There are a number of fundamental concepts and in the following paragraphs, these are reseearched in greater detail.

##### 2.111 Fundamental concepts

* Trend - The trend is the long term increases or decreases that happen within the data. This is considered as a constant directional movement such as a general rise in company x stock price. Trends can be considered as either deterministic or stochastic, with the former allowing for an underlying rationale to be put forward, whereas the latter is a random feature that is difficult to explain. This means that the deterministic trend can be more easily plotted and predicted with mathematical formulas scuh as a linear or quadratic equation. A stochastic is more difficult due to the perceived randomness and the impact of shocks. An example of this could be a company stock where we can see a rising trend but we cannot apply a specific mathematical formula or say this stock will rise by x% per year due to y.
* Seasonality - Seasonality is a component of time series whereby a trend repeats in respect to the timing, direction or magnitude. Examples of these could be sales in coats increasing every year around Q3, or water sales increasing in the summer months.
* Cycles - Cycles are falls and rises in time series data that do not have a fixed or predetermined frequency or length. Unlike seasonality, cycles are harder to predict and typically longer in duration, with 3-12 years being common, depending on the nature of the time series. An example of this could be preiods of business expansion whereby rises in sales, costs etc could have an impact. Also financial events such as recessions, depressions etc would be cycles.
* Noise/irregularities - These are random flucuations within the data that cannot be attributed to either trend or seasonality. They are often erratic, unpredictable and may or may not be random.
* Stationarity - This is where the time series is considered as either stationary or not. This can be defined as a series where the statistical metrics do not change so therefore metrics may change depending on where in the series it is taken. This is important to understand as many classic time series models such as (ARIMA) are predicated upon the series being stationary. When a time series is stationary, its future behaviour becomes significantly easier to predict as it will resemble its historical behaviour. The statistical properties that need to be constant are as follows.
  - Mean. If the average mean doesnt change in the time series then it doesnt have a trend. Example would be a rising stock price.
  - Variance. The spread of the data around the mean doesnt change and neither does the magnitude. Example would be where a stock price changes with market volitility during periods of market turmoil.
  - Autocorrelation Structure. This is the correlation between the series and its lagged versions. The correlation between $Y_t$ and $Y_{t-12}$ (12 for 12 months) could be high, but this would be represented across every 12 monthly period.

 In order to test stationarity, there are a number of statistical tests that can be carried out on the data and these are as follows.
  - Augmented Dicky-Fuller (ADF). This doesnt directly test to see if the data is stationary but instead tests for the presence of unit root. A unit root is a feature that is typically found in non-stationary time series. This means that the times series has a  stochastic trend and can be described as wandering without a long term mean. There are 2 hypothesis in this, one being Null hypothesis $H_0$ and the other being Alternative hypothesis $H_a$. When carrying out this ADF test, the goal is to reject or disprove the null hypothesis as proving $H_a$ means the time series is stationary. If it cannot be rejected, then it means that time series is non-stationary and therefore needs to be transformed, usually by differencing, before it can be modelled.
One issue that was present with the Dickey-Fuller test was that in complex time series, there was often still some autocorrelation within the data, even when accounting for the main trend. Therefore a new test was developed and this was the Augmented Dickey-Fuller test. This is where lagged difference terms to the underlying regression model. This augments the test and therefore makes it more capable of handling complex and realistic time series data. In practice, the ADF is always used now.

The equation for the ADF is.


$$
\Delta y_t = \alpha + \beta t + \gamma y_{t-1} + \sum_{i=1}^{p} \delta_i \Delta y_{t-i} + \varepsilon_t
$$

Where:
- ($\Delta y_t$) is the first difference of the series at time \( t \)
- ($\alpha$) is a constant (drift term)
- ($\beta t$) is the time trend
- ($\gamma$) is the coefficient on the lagged level of the series
- ($\delta_i$) are the coefficients on the lagged differences
- ($p$) is the number of lagged difference terms
- ($\varepsilon_t$) is the error term

