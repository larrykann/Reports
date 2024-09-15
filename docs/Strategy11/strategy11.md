---
aliases: []
tags:
  - strategy
  - report
title: Strategy 11
author: Larry Kann
---
# Strategy 11

A mean reversion strategy that uses the Stochastic indicator to time entries and exits. The strategy includes a liquidity filter and uses short timeframe EMAs for trend confirmation.

This file will be updated for as long as the strategy is being developed, deployed (live or simulation), or distributed. Once it has been discontinued, it will be noted here. The code block will always reflect the most recent version of the strategy. The change log can be used to see changes and adjustments to the code over time.

**Strategy Features**:

- Mean Reversion Strategy (long and short)
- Trades stocks in the Nasdaq 100
- Utilizes a stochastic indicator for entry timing
- Employs liquidity filters to ensure tradability
- Positions are adjusted dynamically based on market conditions
- Max 5 positions (combined for long and short)

**Key Metrics**: _Key metrics are from the latest backtest date in the date range above in the test settings._

Strategy 11

- Compound Annual Return: **22.60%**
- Max Historical Drawdown: **-27.12%**
- Average Holding Period: **7.29 Days**
- Expectancy Per Trade: **1.06%**
- Win Rate: **71.20%**
- Profit Factor: **1.58**
- Sharpe Ratio: **0.97**
- MAR Ratio: **0.83**

**Data Source and Test Settings**: _For transparency._

- **Data Source**: Norgate
- **Universe**: Nasdaq 100 Constituents (current & past for testing)
- **Benchmark**: QQQ
- **Date Range**: 01/02/2014 to 08/21/2024
- **Bar Size**: Daily
- **Backtesting Platform/Engine**: RealTest

**Benchmark**: _This strategy is used to make a comparison to the results of the custom strategy. It is a simple buy and hold strategy that reinvests dividends._

- **Benchmark Strategy**: Buy and hold QQQ.
- **Entry Setup**: Enter QQQ.
- **Exit Rule**: Reinvest dividends

This strategy aims to exploit mean reversion opportunities in the Nasdaq 100 by utilizing the stochastic oscillator to time entries. A liquidity filter ensures that only highly tradable stocks are considered. Position sizing is dynamically adjusted based on market conditions and volatility (11D). The strategy operates on both the long and short sides, offering flexibility in capturing reversals.

## Settings

| Setting            | Value                                                |
| ------------------ | ---------------------------------------------------- |
| Bar Size           | Daily                                                |
| Account Size Start | $100,000                                             |
| Data Source        | Norgate                                              |
| Universe           | Nasdaq 100 Constituents (current & past for testing) |
| Benchmark          | QQQ                                                  |
| Date Range         | 01/02/2014 to 08/21/2024                             |
| Platform/Engine    | RealTest                                             |

## Summary Stats

|              | buy_and_hold* | strategy_11_long | strategy_11_short | Combined     |
| ------------ | ------------- | ---------------- | ----------------- | ------------ |
| Periods      | 2,677         | 2,674            | 2,633             | 2,674        |
| NetProfit    | $503,272      | $761,019         | $9,355            | $770,374     |
| Comp         | True          | True             | True              | True         |
| ROR          | 18.41%        | 22.47%           | 0.86%             | **22.60%**   |
| MaxDD        | -35.11%       | -27.68%          | -1.97%            | **-27.12%**  |
| MAR          | 0.52          | 0.81             | 0.44              | 0.83         |
| Trades       | 45            | 1,078            | 106               | 1,184        |
| PctWins      | 82.22%        | 71.52%           | 67.92%            | **71.20%**   |
| AvgWin       | 7.67%         | 3.91%            | 1.96%             | 3.74%        |
| AvgLoss      | 9.94%         | 5.97%            | 2.01%             | 5.58%        |
| WinLen       | 60.08         | 7.53             | 4.71              | 7.29         |
| LossLen      | 56.62         | 21.53            | 9.41              | 20.32        |
| Expectancy   | 4.54%         | 1.09%            | 0.68%             | 1.06%        |
| TradeLen     | 59.47         | Not Provided     | Not Provided      | Not Provided |
| ProfitFactor | 3.04          | 1.57             | 2.05              | **1.58**     |
| Sharpe       | 0.90          | 0.95             | 0.69              | **0.97**     |
| AvgExp       | 99.92%        | 90.14%           | 3.13%             | 90.10%       |
| MaxExp       | 100.00%       | 101.31%          | 26.57%            | 119.07%      |

_*benchmark strategies are not included in combined stats_

## Combined Monthly Percent Gains

| YEAR    | Jan      | Feb      | Mar      | Apr      | May      | Jun      | Jul      | Aug       | Sep       | Oct      | Nov      | Dec      | **TOTAL**  | MaxDD      |
| ------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | --------- | --------- | -------- | -------- | -------- | ---------- | ---------- |
| 2014    | 5.6%     | 6.3%     | 0.1%     | -4.2%    | 7.7%     | 2.3%     | 4.8%     | 5.5%      | -3.4%     | 3.9%     | 5.1%     | -1.2%    | **36.7%**  | -11.0%     |
| 2015    | -3.9%    | 8.6%     | 4.0%     | 0.4%     | 1.5%     | -7.8%    | 6.1%     | -11.3%    | -1.8%     | 13.5%    | 5.3%     | -2.1%    | **10.3%**  | -18.7%     |
| 2016    | -8.3%    | 9.0%     | -2.0%    | 2.0%     | 7.1%     | 1.7%     | 7.1%     | 1.6%      | -2.0%     | -2.9%    | 6.6%     | -1.4%    | **18.5%**  | -14.2%     |
| 2017    | 10.5%    | 4.4%     | 3.3%     | 3.6%     | -1.8%    | 2.8%     | 3.9%     | -0.9%     | 1.3%      | -0.9%    | 2.8%     | 2.5%     | **35.7%**  | -4.8%      |
| 2018    | 10.4%    | -4.8%    | 0.1%     | 0.3%     | 3.3%     | 1.2%     | 5.1%     | -7.5%     | -2.2%     | -7.6%    | 0.6%     | -7.9%    | **-10.2%** | -26.8%     |
| 2019    | 5.3%     | 2.2%     | 4.9%     | 2.1%     | -10.0%   | 10.5%    | 3.7%     | -6.2%     | 4.2%      | 11.6%    | 5.7%     | 2.5%     | **40.2%**  | -12.3%     |
| 2020    | -1.8%    | 1.5%     | -2.6%    | 9.9%     | 10.4%    | -2.8%    | 6.5%     | -2.0%     | -1.2%     | 5.9%     | 8.8%     | 5.5%     | **43.7%**  | -21.2%     |
| 2021    | 6.7%     | -1.1%    | 3.2%     | 6.0%     | 1.9%     | 0.6%     | -7.5%    | -0.5%     | -3.5%     | 1.8%     | 0.0%     | 6.0%     | **13.5%**  | -15.4%     |
| 2022    | -8.6%    | -4.4%    | 0.7%     | -1.8%    | 1.2%     | 2.6%     | 14.1%    | -1.4%     | -8.3%     | 6.8%     | 26.7%    | -9.7%    | **12.9%**  | -24.5%     |
| 2023    | 8.8%     | -3.8%    | 9.9%     | -3.3%    | 0.9%     | 5.2%     | 5.1%     | -2.6%     | -0.9%     | -7.5%    | 13.3%    | 14.0%    | **42.9%**  | -11.3%     |
| 2024    | 2.4%     | 0.9%     | 5.6%     | -10.9%   | 1.8%     | 1.3%     | -1.5%    | 9.7%      | n/a       | n/a      | n/a      | n/a      | **8.3%**   | -15.6%     |
| **AVG** | **2.5%** | **1.7%** | **2.5%** | **0.4%** | **2.2%** | **1.6%** | **4.3%** | **-1.4%** | **-1.8%** | **2.5%** | **7.5%** | **0.8%** | **23.0%**  | **-16.0%** |



## Strategy Correlations

<div style='overflow-x:auto'>
<table class='w3-table' style='border:1px solid black'>
<tr style='border-bottom:1px solid black'>
<td style = 'border-right:1px solid black;text-align:center'><b>RETURNS</b></td>
<th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#4E8542'>buy_and_hold</th>
<th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#9F2936'>strategy_11_long</th>
<th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#F79646'>strategy_11_short</th>
<th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#4F81BD'>Combined</th>
</tr>
<tr>
<th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#4E8542'>buy_and_hold</th>
<td bgcolor=#00FF00 style='text-align:center'>1.00</td>
<td bgcolor=#4EFF4E style='text-align:center'>0.69</td>
<td bgcolor=#FFD7D7 style='text-align:center'>-0.16</td>
<td bgcolor=#4FFF4F style='text-align:center'>0.69</td>
</tr>
<tr>
<th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#9F2936'>strategy_11_long</th>
<td bgcolor=#4EFF4E style='text-align:center'>0.69</td>
<td bgcolor=#00FF00 style='text-align:center'>1.00</td>
<td bgcolor=#FFE3E3 style='text-align:center'>-0.11</td>
<td bgcolor=#00FF00 style='text-align:center'>1.00</td>
</tr>
<tr>
<th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#F79646'>strategy_11_short</th>
<td bgcolor=#FFD7D7 style='text-align:center'>-0.16</td>
<td bgcolor=#FFE3E3 style='text-align:center'>-0.11</td>
<td bgcolor=#00FF00 style='text-align:center'>1.00</td>
<td bgcolor=#FFE9E9 style='text-align:center'>-0.09</td>
</tr>
<tr>
<th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#4F81BD'>Combined</th>
<td bgcolor=#4FFF4F style='text-align:center'>0.69</td>
<td bgcolor=#00FF00 style='text-align:center'>1.00</td>
<td bgcolor=#FFE9E9 style='text-align:center'>-0.09</td>
<td bgcolor=#00FF00 style='text-align:center'>1.00</td>
</tr>
</table>
</div>

<!-- Add a blank line here to separate blocks -->

<div style='overflow-x:auto'>
<table class='w3-table' style='border:1px solid black'>
<tr style='border-bottom:1px solid black'>
<td style = 'border-right:1px solid black;text-align:center'><b>DRAWDOWNS</b></td>
<th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#4E8542'>buy_and_hold</th>
<th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#9F2936'>strategy_11_long</th>
<th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#F79646'>strategy_11_short</th>
<th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#4F81BD'>Combined</th>
</tr>
<tr>
<th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#4E8542'>buy_and_hold</th>
<td bgcolor=#00FF00 style='text-align:center'>1.00</td>
<td bgcolor=#93FF93 style='text-align:center'>0.42</td>
<td bgcolor=#FFFDFD style='text-align:center'>-0.00</td>
<td bgcolor=#93FF93 style='text-align:center'>0.42</td>
</tr>
<tr>
<th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#9F2936'>strategy_11_long</th>
<td bgcolor=#93FF93 style='text-align:center'>0.42</td>
<td bgcolor=#00FF00 style='text-align:center'>1.00</td>
<td bgcolor=#C9FFC9 style='text-align:center'>0.21</td>
<td bgcolor=#00FF00 style='text-align:center'>1.00</td>
</tr>
<tr>
<th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#F79646'>strategy_11_short</th>
<td bgcolor=#FFFDFD style='text-align:center'>-0.00</td>
<td bgcolor=#C9FFC9 style='text-align:center'>0.21</td>
<td bgcolor=#00FF00 style='text-align:center'>1.00</td>
<td bgcolor=#C4FFC4 style='text-align:center'>0.23</td>
</tr>
<tr>
<th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#4F81BD'>Combined</th>
<td bgcolor=#93FF93 style='text-align:center'>0.42</td>
<td bgcolor=#00FF00 style='text-align:center'>1.00</td>
<td bgcolor=#C4FFC4 style='text-align:center'>0.23</td>
<td bgcolor=#00FF00 style='text-align:center'>1.00</td>
</tr>
</table>
</div>

<!-- End of HTML block -->

## Visualizations


![TWEQ](Reports/docs/Strategy11/images/graph2.png)

![Drawdown](Reports/docs/Strategy11/images/graph3.png)
<div style="page-break-after: always;"></div>
![Daily](images/graph5.png)

![Monthly](Reports/docs/Strategy11/images/graph7.png)
<div style="page-break-after: always;"></div>
### Trade Plots


![Individual %Gains](Reports/docs/Strategy11/images/plot0.png)


![Distribution of %Gains](Reports/docs/Strategy11/images/plot1.png)
<div style="page-break-after: always;"></div>
![Distribution of %Excursions](images/plot2.png)

## Monte Carlo Analysis

| Percentile | Net Profit  | CAR      | Max Drawdown    |
|------------|-------------|----------|-----------------|
| 1%         | 346.51%     | 15.13%   | -28.02%         |
| 5%         | 414.46%     | 16.67%   | -23.30%         |
| 10%        | 457.63%     | 17.56%   | -20.94%         |
| 20%        | 558.95%     | 19.42%   | -17.97%         |
| 50%        | 913.95%     | 24.37%   | -13.51%         |
| 80%        | 1,507.49%   | 29.88%   | -9.88%          |
| 90%        | 1,870.53%   | 32.39%   | -8.40%          |
| 95%        | 2,140.96%   | 34.01%   | -7.46%          |
| 99%        | 3,223.49%   | 39.07%   | -4.81%          |
| **backtest**   | **770.37%**     | **22.59%**   | **-27.12%**         |


![MCPT Prodfit](Reports/docs/Strategy11/images/plot4.png)
![MCPT Prodfit](Reports/docs/Strategy11/images/plot5.png)

