# 23_ESNQ

A trend with mean reversion strategy for ES/NQ. This strategy trades ES/NQ contracts and was originally designed as two separate strategies (Strategy 7 and Strategy 8), both long-biased, combined into one unified approach. The strategy has undergone modifications over time, including shifting from intraday-only to allowing overnight holds for one of the components.

This document will be updated as the strategy is developed, deployed (live or simulation), or distributed. Once discontinued, it will be noted here. The change log can be used to track adjustments and improvements over time.

## Strategy 23 ES/NQ

**Strategy Features**:

- Mean Reversion & Trend-Following Elements
- Trades ES/NQ Contracts
- Utilizes RSI and MACD for Entry Signals
- Daily Bar Size
- Commissions & Slippage Included in Backtest

**Key Metrics**  
_From latest backtest covering 1/2/2015 – 12/19/2024_

- **Rate of Return (ROR)**: **18.93%**
- **Max Historical Drawdown**: **-25.41%**
- **Expectancy Per Trade**: **0.34%**
- **Win Rate**: **66.81%**
- **Profit Factor**: **3.08**
- **Sharpe Ratio**: **0.87**
- **MAR Ratio**: **0.75**

### Settings

| Setting                | Value                    |
| :--------------------- | :----------------------- |
| **Bar Size**           | Daily                    |
| **Account Size Start** | $100,000                 |
| **Data Source**        | Norgate                  |
| **Universe**           | ES/NQ                    |
| **Date Range**         | 01/02/2015 to 12/19/2024 |
| **Platform/Engine**    | RealTest                 |
| **Use Available Bars** | False                    |

### Summary Stats (Strategy 23 ES/NQ)

|                  | strategy_7_long | strategy_8_long |    Combined |
| :--------------- | --------------: | --------------: | ----------: |
| **Periods**      |           2,463 |           2,456 |       2,463 |
| **NetProfit**    |        $130,976 |         $54,094 |    $185,070 |
| **Comp**         |           False |           False |       False |
| **ROR**          |          13.40% |           5.55% |  **18.93%** |
| **MaxDD**        |     **-25.41%** |          -6.58% | **-25.41%** |
| **MAR**          |            0.53 |            0.84 |        0.75 |
| **Trades**       |              87 |             142 |         229 |
| **PctWins**      |          78.16% |          59.86% |  **66.81%** |
| **AvgWin**       |           1.20% |           0.50% |       0.81% |
| **AvgLoss**      |           1.32% |           0.37% |       0.61% |
| **Expectancy**   |           0.65% |           0.15% |   **0.34%** |
| **ProfitFactor** |            3.90 |            2.24 |    **3.08** |
| **Sharpe**       |            0.64 |            0.90 |    **0.87** |

### Combined Monthly Percent Gains (Strategy 23 ES/NQ)

| YEAR | Jan    | Feb    | Mar     | Apr    | May    | Jun    | Jul    | Aug    | Sep    | Oct    | Nov    | Dec    | **TOTAL** | MaxDD    |
| ---- | ------ | ------ | ------- | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | --------- | -------- |
| 2015 | 0.0%   | 0.0%   | 1.8%    | 0.7%   | 1.1%   | **-0.4%** | 4.1%   | **-2.2%** | 0.0%   | 0.0%   | 3.2%   | **-1.0%** | **7.3%**  | -8.4%    |
| 2016 | **-4.1%** | 0.0%   | 0.0%   | **-1.6%** | 1.0%   | 1.3%   | **-0.2%**| 0.0%   | 5.1%   | **-2.1%**| 2.8%   | 2.8%   | **5.0%**  | -6.8%    |
| 2017 | 2.9%   | 0.4%   | 0.6%   | 3.8%   | 0.2%   | **-0.5%** | 0.4%   | 2.7%   | 1.3%   | 1.5%   | 4.8%   | 0.0%   | **18.1%** | -0.8%    |
| 2018 | 3.3%   | 0.0%   | **-9.6%**| 1.3%   | 0.7%   | 2.3%   | 1.9%   | 2.7%   | 2.3%   | **-5.6%**| 0.0%   | **-2.5%**| **-3.3%** | -17.5%   |
| 2019 | **-1.8%**| 0.0%  | 2.9%   | 1.6%   | **-1.6%** | 4.4%   | 0.0%   | **-4.7%**| 0.0%   | **-0.1%**| **-0.3%**| 2.2%   | **2.5%**  | -14.3%   |
| 2020 | **-0.9%**| 5.3%  | 0.0%   | 0.0%   | 2.1%   | **-1.8%** | 3.7%   | **-0.2%**| 3.8%   | 1.8%   | 4.2%   | 1.5%   | **19.5%** | -3.6%    |
| 2021 | 3.3%   | **-2.4%**| 9.4%   | 0.0%   | 11.6%  | 5.0%   | 4.8%   | **-0.7%**| 5.1%   | 8.9%   | 0.0%   | 0.0%   | **44.8%** | -11.0%   |
| 2022 | 7.8%   | 0.0%   | 0.0%   | 2.0%   | 0.0%   | **-6.8%** | 0.0%   | 6.9%   | **-3.9%**| 18.9%  | 3.6%   | **-2.3%**| **26.2%** | -25.4%   |
| 2023 | 8.2%   | **-1.6%**| 2.7%   | 7.5%   | **-1.1%** | 0.0%   | 2.4%   | 6.2%   | **-2.0%**| **-1.2%**| 12.4%  | 6.5%   | **40.0%** | -18.8%   |
| 2024 | 3.8%   | **-0.5%**| **-3.3%**| 0.0%   | 0.0%   | **-0.3%** | 4.7%   | 0.0%   | 0.0%   | 4.9%   | 14.6%  | 1.2%   | **25.0%** | -6.9%    |
| **AVG** | **2.3%** | **0.1%** | **0.4%** | **1.5%** | **1.4%** | **0.3%** | **2.2%** | **1.1%** | **1.2%** | **2.7%** | **4.5%** | **0.8%** | **18.5%** | **-11.3%** |

### Strategy Correlations

#### Returns

| RETURNS           | strategy_7_long | strategy_8_long | Combined |
| ----------------- | --------------: | --------------: | --------:|
| **strategy_7_long** | 1.00          | -0.01           | 0.96     |
| **strategy_8_long** | -0.01         | 1.00            | 0.28     |
| **Combined**       | 0.96           | 0.28            | 1.00     |

#### Drawdowns

| DRAWDOWNS         | strategy_7_long | strategy_8_long | Combined |
| ----------------- | --------------: | --------------: | --------:|
| **strategy_7_long** | 1.00          | -0.12           | 0.83     |
| **strategy_8_long** | -0.12         | 1.00            | 0.18     |
| **Combined**       | 0.83           | 0.18            | 1.00     |

### Visualizations

![Equity](Reports/docs/23_ESNQ/images/graph2.png)  
![Drawdown](Reports/docs/23_ESNQ/images/graph3.png)  
![Daily](Reports/docs/23_ESNQ/images/graph5.png)  
![Monthly](Reports/docs/23_ESNQ/images/graph7.png)

#### Trade Plots

![Plot 0](Reports/docs/23_ESNQ/images/plot0.png)  
![Plot 1](Reports/docs/23_ESNQ/images/plot1.png)  
![Plot 2](Reports/docs/23_ESNQ/images/plot2.png)

### Monte Carlo Analysis (Strategy 23 ES/NQ)

| Percentile   | Net Profit   | AAR         | Max Drawdown  |
| :----------- | :----------- | :---------- | :------------ |
| 1%           | $104,727     | $10,514     | **($19,206)** |
| 5%           | $128,720     | $12,923     | **($16,191)** |
| 10%          | $135,164     | $13,570     | **($13,390)** |
| 20%          | $150,794     | $15,140     | **($11,996)** |
| 50%          | $181,944     | $18,267     | **($9,029)**  |
| 80%          | $209,117     | $20,995     | **($6,896)**  |
| 90%          | $221,624     | $22,251     | **($6,110)**  |
| 95%          | $242,714     | $24,368     | **($5,531)**  |
| 99%          | $293,267     | $29,444     | **($4,488)**  |
| **backtest** | **$185,070** | **$18,581** | **($25,413)** |

![MCPT Profit](Reports/docs/23_ESNQ/images/plot4.png)  
![MCPT Excursion](Reports/docs/23_ESNQ/images/plot5.png)

---

*Generated by RealTest. These results are subject to change based on parameter adjustments or further development.*  