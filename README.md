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
The research chapter contains all of the key elements and areas of interest that arise during the project. This will cover all aspects of both finance and ml (including core mathematics). This will be used as a guide and can be referred back if needed.

### 2.1 Core Concepts

#### 2.11 Time series

A time series is a sequence of data points that has been collected over a period of time. It is used in a number of different industries and applications such as finance, healthcare and transport. This is often complied over a set period of time such as hourly, daily, weekly etc. Time series analysis is the statistical analysis of the sequences of these data points over the period of time. It then infers what has happened over the historical period and then attempts to predict what will happen in the future. There are a number of fundamental concepts and in the following paragraphs, these are reseearched in greater detail.

##### 2.111 Fundamental concepts

* Trend - The trend is the long term increases or decreases that happen within the data. This is considered as a constant directional movement such as a general rise in company x stock price. Trends can be considered as either deterministic or stochastic, with the former allowing for an underlying rationale to be put forward, whereas the latter is a random feature that is difficult to explain. This means that the deterministic trend can be more easily plotted and predicted with mathematical formulas scuh as a linear or quadratic equation. A stochastic is more difficult due to the perceived randomness and the impact of shocks. An example of this could be a company stock where we can see a rising trend but we cannot apply a specific mathematical formula or say this stock will rise by x% per year due to y.

Worked example\
$$Y_t = \beta_0 + \beta_1 t + \epsilon_t$$
