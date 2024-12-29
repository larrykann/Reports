# 24 SPY

A trend-following strategy for the SPY ETF that leverages VIX-based indicators and moving averages alongside ATR-based risk management to identify and capitalize on market trends. The strategy takes long and short positions. It operates on daily bars and incorporates risk controls to manage drawdowns and optimize returns.

This document will be updated as the strategy is developed, deployed (live or simulation), or distributed. Once discontinued, it will be noted here. The change log can be used to track adjustments and improvements over time.

## Strategy 24 SPY

**Strategy Features**:

- VIX-Based Trend-Following
- Trades SPY ETF
- Utilizes ATR for Risk Management
- Daily Bar Size
- Commissions & Slippage Included in Backtest

**Key Metrics**  
_From latest backtest covering 1/3/2007 – 12/27/2024_

- **Rate of Return (ROR)**: **5.10%**
- **Max Historical Drawdown**: **-4.89%**
- **Expectancy Per Trade**: **2.66%**
- **Win Rate**: **72.22%**
- **Profit Factor**: **6.91**
- **Sharpe Ratio**: **1.02**
- **MAR Ratio**: **1.04**

### Settings

| Setting                | Value                      |
| :--------------------- | :------------------------- |
| **Bar Size**           | Daily                      |
| **Account Size Start** | $100,000                   |
| **Data Source**        | RealTest Data File         |
| **Universe**           | SPY                        |
| **Date Range**         | 01/03/2007 to 12/27/2024   |
| **Platform/Engine**    | RealTest                   |
| **Use Available Bars** | False                      |

### Summary Stats (Strategy 24 SPY)

|                  | strategy_24_long | strategy_24_short |   Combined |
| :--------------- | ---------------: | ----------------: | ---------: |
| **Periods**      |            4,200 |             3,677 |      4,200 |
| **NetProfit**    |         $106,622 |           $22,012 |   $128,634 |
| **Comp**         |             True |              True |       True |
| **ROR**          |            4.46% |             1.26% |  **5.10%** |
| **MaxDD**        |           -5.26% |            -3.96% | **-4.89%** |
| **MAR**          |             0.85 |              0.32 |   **1.04** |
| **Trades**       |               31 |                 5 |         36 |
| **PctWins**      |           70.97% |            80.00% | **72.22%** |
| **AvgWin**       |            4.10% |             5.55% |      4.32% |
| **AvgLoss**      |            1.67% |             1.40% |      1.65% |
| **Expectancy**   |            2.42% |             4.16% |  **2.66%** |
| **TradeLen**     |            14.87 |              3.20 |      13.25 |
| **ProfitFactor** |             6.28 |             15.05 |   **6.91** |
| **Sharpe**       |             0.93 |              0.46 |   **1.02** |
| **Volatility**   |            4.81% |             3.05% |      5.01% |
| **Skew**         |          0.99888 |          18.15907 |    2.07881 |
| **Sortino**      |             1.52 |              1.13 |   **1.75** |
| **Skipped**      |            0.00% |             0.00% |      0.00% |
| **AvgExp**       |           10.97% |             0.42% |     10.52% |
| **MaxExp**       |          101.07% |           103.88% |    100.09% |
| **AvgUse**       |           11.36% |             0.54% |     10.96% |
| **MaxUse**       |          103.97% |           104.12% |    103.27% |


### Combined Monthly Percent Gains (Strategy 24 SPY)

| YEAR | Jan    | Feb    | Mar    | Apr    | May    | Jun    | Jul    | Aug    | Sep    | Oct    | Nov    | Dec    | **TOTAL** | MaxDD    |
| ---- | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | --------- | -------- |
| 2007 | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | **0.0%**  | -0.0%    |
| 2008 | 0.0%   | 0.0%   | 0.0%   | 0.1%   | 3.9%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | **4.0%**  | -2.2%    |
| 2009 | 0.0%   | 0.0%   | 0.0%   | 2.9%   | 5.8%   | 1.2%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | **10.2%** | -4.6%    |
| 2010 | 0.0%   | 0.0%   | 3.8%   | 0.0%   | 1.7%   | 0.0%   | 0.0%   | -3.6%  | 2.1%   | 2.6%   | 0.0%   | 0.0%   | **6.7%**  | -4.6%    |
| 2011 | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | -1.8%  | 6.3%   | 0.0%   | 0.9%   | -1.2%  | 0.0%   | **3.9%**  | -4.8%    |
| 2012 | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 1.1%   | 1.7%   | 0.0%   | 0.0%   | 0.0%   | 1.7%   | **4.6%**  | -2.5%    |
| 2013 | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | **0.0%**  | -0.0%    |
| 2014 | 0.0%   | 1.7%   | 0.5%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 2.2%   | -2.4%  | **1.9%**  | -3.2%    |
| 2015 | 0.0%   | 2.4%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | -1.2%  | -0.0%  | 0.0%   | 0.3%   | 0.3%   | -3.0%  | **-1.2%** | -4.0%    |
| 2016 | 0.0%   | 0.0%   | 2.5%   | 2.3%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.6%   | 2.4%   | **8.0%**  | -1.3%    |
| 2017 | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | **0.0%**  | -0.0%    |
| 2018 | 0.0%   | 0.0%   | -0.3%  | 1.7%   | -0.1%  | 2.4%   | 0.0%   | 0.0%   | 0.0%   | -1.0%  | 0.0%   | 0.0%   | **2.6%**  | -1.5%    |
| 2019 | 0.0%   | 2.0%   | 1.7%   | 1.6%   | 0.0%   | 1.6%   | 1.6%   | 0.0%   | 0.2%   | -0.4%  | 0.0%   | 0.0%   | **8.6%**  | -3.1%    |
| 2020 | 0.0%   | 0.0%   | 7.5%   | 0.0%   | 3.3%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | **11.1%** | -2.7%    |
| 2021 | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 1.6%   | 1.9%   | 0.0%   | **3.5%**  | -0.4%    |
| 2022 | 0.0%   | 0.0%   | 0.0%   | -2.6%  | 0.0%   | 0.0%   | 0.0%   | 4.4%   | 0.0%   | 0.0%   | 3.8%   | 0.2%   | **5.9%**  | -3.3%    |
| 2023 | 1.8%   | 2.4%   | 0.0%   | 1.5%   | 0.4%   | 2.4%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 1.2%   | 3.2%   | **13.7%** | -2.3%    |
| 2024 | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 0.0%   | 2.3%   | 0.3%   | 0.0%   | 0.0%   | 0.0%   | **2.6%**  | -3.8%    |
| **AVG** | **0.1%** | **0.5%** | **0.9%** | **0.4%** | **0.8%** | **0.4%** | **-0.0%** | **0.6%** | **0.1%** | **0.2%** | **0.5%** | **0.1%** | **4.8%**  | **-2.5%** |

### Strategy Correlations

#### Returns

| RETURNS           | strategy_24_long | strategy_24_short | Combined |
| ----------------- | -----------------: | -----------------: | -------:|
| **strategy_24_long** | 1.00              | -0.00              | 0.91    |
| **strategy_24_short** | -0.00             | 1.00               | 0.42    |
| **Combined**       | 0.91              | 0.42               | 1.00    |

#### Drawdowns

| DRAWDOWNS         | strategy_24_long | strategy_24_short | Combined |
| ----------------- | -----------------: | -----------------: | -------:|
| **strategy_24_long** | 1.00              | 0.01               | 0.94    |
| **strategy_24_short** | 0.01              | 1.00               | 0.09    |
| **Combined**       | 0.94              | 0.09               | 1.00    |

### Visualizations

![Equity](Reports/docs/24_SPY/images/graph2.png)  
![Drawdown](Reports/docs/24_SPY/images/graph3.png)  
![Daily](Reports/docs/24_SPY/images/graph5.png)  
![Monthly](Reports/docs/24_SPY/images/graph7.png)

#### Trade Plots

![Plot 0](Reports/docs/24_SPY/images/plot0.png)  
![Plot 1](Reports/docs/24_SPY/images/plot1.png)  
![Plot 2](Reports/docs/24_SPY/images/plot2.png)

### Monte Carlo Analysis (Strategy 24 SPY)

| Percentile | Net Profit | CAR        | Max Drawdown  |
| :--------- | :--------- | :--------- | :------------ |
| 1%         | 60.65%     | 2.67%      | **-10.75%**   |
| 5%         | 86.87%     | 3.54%      | **-8.55%**    |
| 10%        | 97.95%     | 3.87%      | **-7.80%**    |
| 20%        | 116.76%    | 4.40%      | **-6.76%**    |
| 50%        | 150.96%    | 5.25%      | **-4.48%**    |
| 80%        | 193.50%    | 6.18%      | **-3.12%**    |
| 90%        | 231.63%    | 6.90%      | **-2.95%**    |
| 95%        | 239.28%    | 7.04%      | **-2.53%**    |
| 99%        | 300.39%    | 8.03%      | **-1.86%**    |
| **backtest** | **128.63%** | **4.71%** | **-4.89%**    |

![MCPT Profit](Reports/docs/24_SPY/images/plot4.png)  
![MCPT Excursion](Reports/docs/24_SPY/images/plot5.png)

---
*Generated by RealTest. These results are subject to change based on parameter adjustments or further development.*