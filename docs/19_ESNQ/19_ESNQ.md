# Strategy 19

A money flow and MACD-based trading strategy for ES/NQ, operating on both long and short positions. The strategy leverages Chaikin's Money Flow Indicator and a modified MACD indicator to determine optimal entry and exit points, aiming to exploit trends and reversals in the ES and NQ markets.

This document will be updated as the strategy is developed, deployed (live or simulation), or distributed. Once discontinued, it will be noted here. The change log can be used to track adjustments and improvements over time.

**Strategy Features**:

- Trend and Reversal Strategy (Long and Short)
- Trades ES/NQ Contracts
- Utilizes Chaikin's Money Flow Indicator and a modified MACD for Entry Signals and Exit
- Daily Bar Size for Analysis
- Commissions and Slippage Accounted for in Backtest Results

**Key Metrics**: _Key metrics are from the latest backtest date in the date range above in the test settings._

- Rate of Return (ROR): **31.99%**
- Max Historical Drawdown: **-26.06%**
- Expectancy Per Trade: **0.16%**
- Win Rate: **57.40%**
- Profit Factor: **1.59**
- Sharpe Ratio: **1.18**
- MAR Ratio: **1.23**

## Settings

| Setting                | Value                     |
| ---------------------- | ------------------------- |
| **Bar Size**           | Daily                     |
| **Account Size Start** | $100,000                  |
| **Data Source**        | Norgate                   |
| **Universe**           | ES/NQ Contracts           |
| **Date Range**         | 01/02/2015 to 12/04/2024  |
| **Platform/Engine**    | RealTest                  |
| **Use Available Bars** | False                     |

## Summary Stats (Strategy 19)

|                  | strategy_19_long | strategy_19_short | Combined |
| ---------------- | ---------------- | ----------------- | -------- |
| **Periods**      | 2,460            | 2,486             | 2,486    |
| **NetProfit**    | $243,954         | $71,652           | $315,606 |
| **Comp**         | False            | False             | False    |
| **ROR**          | 24.99%           | 7.26%             | 31.99%   |
| **MaxDD**        | **-8.63%**       | **-12.70%**       | **-26.06%** |
| **MAR**          | 2.90             | 0.57              | 1.23     |
| **Trades**       | 647              | 259               | 906      |
| **PctWins**      | 59.66%           | 51.74%            | 57.40%   |
| **AvgWin**       | 0.73%            | 0.78%             | 0.74%    |
| **AvgLoss**      | 0.65%            | 0.59%             | 0.63%    |
| **WinLen**       | 0.00             | 0.00              | 0.00     |
| **LossLen**      | 0.00             | 0.00              | 0.00     |
| **Expectancy**   | 0.17%            | 0.12%             | 0.16%    |
| **ProfitFactor** | 1.64             | 1.46              | 1.59     |
| **Sharpe**       | 1.22             | 0.54              | 1.18     |
| **AvgExp**       | 0.00%            | 0.00%             | 0.00%    |
| **MaxExp**       | 0.00%            | 0.00%             | 0.00%    |

## Combined Monthly Percent Gains

| YEAR | Jan    | Feb    | Mar    | Apr    | May    | Jun    | Jul    | Aug    | Sep    | Oct    | Nov    | Dec    | **TOTAL** | MaxDD   |
| ---- | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | --------- | ------- |
| 2015 | -3.1%  | 0.0%   | -2.8%  | 2.1%   | 4.5%   | -0.4%  | 2.3%   | 0.4%   | 1.3%   | 7.0%   | 0.5%   | -0.8%  | **11.0%** | -6.1%   |
| 2016 | 0.1%   | -0.7%  | 2.8%   | 1.2%   | 1.3%   | 0.9%   | 1.3%   | 0.3%   | 1.7%   | -1.5%  | -0.1%  | 0.4%   | **7.6%**  | -5.3%   |
| 2017 | 1.3%   | 0.8%   | 0.2%   | 3.3%   | 0.2%   | 0.4%   | -0.9%  | 0.7%   | 1.8%   | 0.2%   | 1.1%   | 5.5%   | **14.6%** | -2.7%   |
| 2018 | 0.0%   | -3.0%  | -3.8%  | 5.9%   | -0.4%  | 7.3%   | 4.1%   | 2.3%   | 3.5%   | 1.8%   | 0.1%   | 0.0%   | **17.9%** | -6.8%   |
| 2019 | 4.5%   | -0.2%  | -2.0%  | 1.2%   | 6.2%   | 2.4%   | 5.2%   | -0.8%  | 2.8%   | 1.2%   | 0.2%   | -5.4%  | **15.3%** | -10.4%  |
| 2020 | 6.3%   | -3.1%  | 7.2%   | 9.0%   | 11.8%  | 8.8%   | 10.3%  | 5.2%   | -4.5%  | -3.8%  | -0.1%  | 4.3%   | **51.4%** | -18.2%  |
| 2021 | 8.7%   | 7.2%   | 6.9%   | 13.8%  | -0.7%  | 15.5%  | -10.6% | 9.3%   | -5.7%  | 2.4%   | 3.3%   | 10.4%  | **60.5%** | -13.5%  |
| 2022 | 18.8%  | -1.3%  | -0.5%  | -11.8% | 25.1%  | 0.5%   | 11.0%  | -0.3%  | 24.1%  | 0.0%   | 15.2%  | -16.1% | **64.6%** | -25.1%  |
| 2023 | 10.7%  | -9.3%  | -4.2%  | 13.0%  | 10.9%  | 16.9%  | 11.6%  | -0.2%  | 0.1%   | 0.0%   | 10.7%  | 7.2%   | **67.4%** | -16.0%  |
| 2024 | -13.8% | 8.5%   | -2.4%  | 10.2%  | 5.0%   | 0.4%   | 0.4%   | 2.7%   | 2.7%   | 3.4%   | -11.7% | 0.0%   | **5.3%**  | -26.1%  |
| **AVG** | **3.3%** | **-0.1%** | **0.1%** | **4.8%** | **6.4%** | **5.3%** | **3.5%** | **2.0%** | **2.8%** | **1.1%** | **1.9%** | **0.5%** | **31.6%** | **-13.0%** |

## Strategy Correlations

### Returns

| RETURNS               | strategy_19_long | strategy_19_short | Combined |
| --------------------- | ----------------- | ------------------ | -------- |
| **strategy_19_long**  | 1.00              | -0.03              | 0.77     |
| **strategy_19_short** | -0.03             | 1.00               | 0.55     |
| **Combined**          | 0.77              | 0.55               | 1.00     |

### Drawdowns

| DRAWDOWNS             | strategy_19_long | strategy_19_short | Combined |
| --------------------- | ----------------- | ------------------ | -------- |
| **strategy_19_long**  | 1.00              | -0.15              | 0.56     |
| **strategy_19_short** | -0.15             | 1.00               | 0.32     |
| **Combined**          | 0.56              | 0.32               | 1.00     |

## Visualizations

![Equity](Reports/docs/19_ESNQ/images/graph2.png) 
![Drawdown](Reports/docs/19_ESNQ/images/graph3.png)  
![Daily](Reports/docs/19_ESNQ/images/graph5.png) 
![Monthly](Reports/docs/19_ESNQ/images/graph7.png)

### Trade Plots

![Individual %Gains](Reports/docs/19_ESNQ/images/plot0.png) ![Distribution of %Gains](Reports/docs/19_ESNQ/images/plot1.png)  
![Distribution of %Excursions](Reports/docs/19_ESNQ/images/plot2.png)

## Monte Carlo Analysis

| Percentile | Net Profit | AAR ($)  | Max Drawdown   |
| ---------- | ---------- | -------- | -------------- |
| 1%         | $167,850   | $16,926  | **-60,430**    |
| 5%         | $188,896   | $19,048  | **-49,074**    |
| 10%        | $206,198   | $20,793  | **-38,148**    |
| 20%        | $263,473   | $26,569  | **-33,106**    |
| 50%        | $315,606   | $31,826  | **-25,340**    |
| 80%        | $383,386   | $38,661  | **-20,512**    |
| 90%        | $423,900   | $42,746  | **-17,432**    |
| 95%        | $451,203   | $45,499  | **-16,145**    |
| 99%        | $511,798   | $51,610  | **-14,754**    |
| **Backtest**| **$315,606** | **$31,826** | **-26,062** |

![MCPT Profit](Reports/docs/19_ESNQ/images/plot4.png) ![MCPT Excursion](Reports/docs/19_ESNQ/images/plot5.png)

---
*Generated by RealTest. These results are subject to change based on parameter adjustments or further development.*