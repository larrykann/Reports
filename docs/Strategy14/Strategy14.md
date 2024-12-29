---
aliases: []
tags: 
  - report
  - strategy
  - futures
title: Strategy 14
author: Larry Kann
titlepage: true
titlepage-rule-color: "336600"
titlepage-text-color: "000000"
colorlinks: "336600"
toc: true
toc-own-page: true
mainfont: Arial
monofont: Dank Mono
linkcolor: magenta
urlcolor: magenta
listings-no-page-break: true
code-block-font-size: \scriptsize
output:
  pdf:
    pdf-engine: xelatex
    output: PCO_20240801_110606.pdf
    from: markdown
    template: eisvogel
    listings: true
---
# Strategy 14

A mean reversion trading strategy that trades SPY and operates on both long and short positions. It leverages the money flow indicator based on SPX performance (breadth/regime filter) to determine optimal times to enter trades. 

This file will be updated for as long as the strategy is being developed, deployed (live or simulation), or distributed. Once it has been discontinued, it will be noted here. The code block will always reflect the most recent version of the strategy. The change log can be used to see changes and adjustments to the code over time.


**Strategy Features**:

- Day Trading Futures Strategy (Long and Short)
- Trades SPY
- Utilizes the money flow indicator to time entries based on SPX performance
- Supports both long and short trading strategies
- Commissions and slippage accounted for in backtest results

**Key Metrics**: _Key metrics are from the latest backtest date in the date range above in the test settings._

- Compound Annual Return: **1.79%**
- Max Historical Drawdown: **-5.42%**
- Average Holding Period: **3 Days**
- Expectancy Per Trade: **3.27%**
- Win Rate: **69.70%**
- Profit Factor: **2.17**
- Sharpe Ratio: **0.68**
- MAR Ratio: **0.33**

## Settings

| Setting            | Value                    |
| ------------------ | ------------------------ |
| Bar Size           | Daily                    |
| Account Size Start | $100,000                 |
| Data Source        | Norgate                  |
| Universe           | SPY                      |
| Date Range         | 01/01/2007 to 09/30/2024 |
| Platform/Engine    | RealTest                 |
| Use Available Bars | False                    |

## Summary Stats (Strategy 14)

|              | strategy_14_long | strategy_14_short | Combined   |
| ------------ | ---------------- | ----------------- | ---------- |
| **Periods**      | 4,408            | 4,300             | 4,408      |
| **NetProfit**    | $25,864          | $11,002           | $36,866    |
| **Comp**         | True             | True              | True       |
| **ROR**          | 1.30%            | 0.62%             | 1.79%      |
| **MaxDD**        | **-5.58%**       | **-5.41%**        | **-5.42%** |
| **MAR**          | 0.23             | 0.11              | 0.33       |
| **Trades**       | 46               | 86                | 132        |
| **PctWins**      | 78.26%           | 65.12%            | 69.70%     |
| **AvgWin**       | 0.99%            | 2.50%             | 1.91%      |
| **AvgLoss**      | 1.23%            | 2.71%             | 2.34%      |
| **WinLen**       | 1.78             | 3.79              | 3.00       |
| **LossLen**      | 2.30             | 4.67              | 4.08       |
| **Expectancy**   | 0.51%            | 0.68%             | 0.62%      |
| **ProfitFactor** | 2.84             | 1.63              | 2.17       |
| **Sharpe**       | 0.61             | 0.33              | 0.68       |
| **AvgExp**       | 1.97%            | 1.63%             | 3.27%      |
| **MaxExp**       | 101.34%          | 42.97%            | 100.53%    |

## Combined Monthly Percent Gains

| YEAR | Jan   | Feb    | Mar    | Apr   | May   | Jun  | Jul  | Aug    | Sep    | Oct  | Nov | Dec | **TOTAL** | MaxDD   |
| ---- | ----- | ------ | ------ | ----- | ----- | ---- | ---- | ------ | ------ | ---- | --- | --- | -------- | ------- |
| 2007 | 0.0%  | 0.4%   | -1.5%  | 0.0%  | 0.3%  | -1.0% | 0.0% | 0.2%   | 0.0%   | -0.2% | -0.2% | -0.1% | **-2.2%** | -2.9%   |
| 2008 | 0.8%  | 0.0%   | 0.7%   | 0.0%  | 0.3%  | 0.3% | 0.7% | -0.0%  | 1.1%   | 1.5% | 1.4% | -0.7% | **6.1%**  | -1.0%   |
| 2009 | 0.6%  | 0.5%   | -0.3%  | 0.0%  | 0.0%  | 0.0% | 0.0% | 0.0%   | 1.0%   | 4.9% | 1.2% | 0.0% | **8.0%**  | -0.6%   |
| 2010 | -0.9% | 1.4%   | 0.0%   | 1.4%  | -0.1% | -0.1% | -0.0% | 0.1%   | -0.4%  | 0.0% | 0.0% | 0.0% | **1.5%**  | -1.7%   |
| 2011 | 0.4%  | 1.3%   | 3.0%   | 0.0%  | 0.0%  | -1.6% | 0.0% | 0.4%   | 0.3%   | -1.3% | 0.0% | -0.2% | **2.3%**  | -2.4%   |
| 2012 | 0.0%  | 0.0%   | 0.0%   | 0.8%  | 0.1%  | 0.0% | 0.0% | 0.0%   | 0.0%   | 0.0% | -0.1% | 0.0% | **0.8%**  | -0.9%   |
| 2013 | 0.0%  | 1.2%   | 0.0%   | -0.0% | 0.7%  | 0.7% | 0.0% | 0.2%   | 0.5%   | 1.8% | 1.2% | 0.4% | **6.9%**  | -2.4%   |
| 2014 | 1.0%  | 0.0%   | 0.0%   | 1.0%  | 0.0%  | 0.0% | 0.4% | 0.0%   | 0.0%   | -0.9% | 0.0% | 0.0% | **1.4%**  | -1.2%   |
| 2015 | 0.0%  | 0.0%   | 0.0%   | 0.0%  | 0.0%  | 0.0% | -0.1% | -0.1%  | 0.4%   | -0.9% | -0.3% | 0.6% | **-0.4%** | -1.4%   |
| 2016 | 0.5%  | 0.8%   | 0.0%   | 0.0%  | 0.0%  | 0.0% | 0.0% | 0.0%   | 0.0%   | 0.0% | 0.0% | 0.0% | **1.3%**  | -0.2%   |
| 2017 | 0.0%  | 0.0%   | -0.8%  | 0.0%  | 0.0%  | 0.0% | 0.0% | 0.0%   | 0.0%   | 0.0% | 0.0% | 1.0% | **0.2%**  | -1.0%   |
| 2018 | -0.3% | -5.0%  | 0.0%   | 0.0%  | 0.0%  | 0.0% | 0.0% | 0.0%   | 0.0%   | 0.4% | 0.2% | 0.8% | **-4.0%** | -5.3%   |
| 2019 | 0.2%  | 0.0%   | 0.0%   | 0.0%  | 0.0%  | 0.0% | 0.0% | 0.0%   | 0.0%   | 0.0% | 0.0% | 0.0% | **0.2%**  | -0.3%   |
| 2020 | 0.0%  | 0.0%   | 1.6%   | -0.8% | 0.0%  | 0.0% | 0.0% | 0.0%   | 0.0%   | 0.0% | 0.0% | 0.0% | **0.8%**  | -2.8%   |
| 2021 | 0.0%  | 1.5%   | 0.0%   | 0.0%  | 1.9%  | 0.9% | 0.0% | 1.9%   | -0.1%  | 0.0% | 0.0% | 0.0% | **6.3%**  | -0.4%   |
| 2022 | -0.7% | -0.6%  | -0.2%  | 0.7%  | 0.8%  | 0.7% | 0.0% | 0.0%   | 1.8%   | 0.1% | 1.1% | 0.0% | **3.8%**  | -1.9%   |
| 2023 | 0.2%  | 0.0%   | -1.2%  | 0.0%  | 0.6%  | 0.0% | 0.0% | 0.0%   | 0.1%   | 0.1% | -1.0% | 0.0% | **-1.2%** | -1.5%   |
| 2024 | 0.0%  | 0.0%   | 0.0%   | 0.8%  | 0.0%  | 0.0% | 0.0% | 0.0%   | n/a    | n/a  | n/a | n/a | **0.8%**  | -0.0%   |
| **AVG** | **0.1%** | **0.1%** | **0.1%** | **0.2%** | **0.3%** | **-0.0%** | **0.1%** | **0.2%** | **0.3%** | **0.3%** | **0.2%** | **0.1%** | **1.8%** | **-1.6%** |


## Strategy Correlations

<div style='overflow-x:auto'>
<table class='w3-table' style='border:1px solid black'>
<tr style='border-bottom:1px solid black'>
<td style = 'border-right:1px solid black;text-align:center'>
<b>RETURNS</b></td>
<th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#4E8542'>strategy_14_long</th><th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#9F2936'>strategy_14_short</th><th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#F79646'>Combined</th></tr>
<tr><th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#4E8542'>strategy_14_long</th><td bgcolor=#00FF00 style='text-align:center'>1.00</td><td bgcolor=#FFFEFE style='text-align:center'>-0.00</td><td bgcolor=#36FF36 style='text-align:center'>0.79</td></tr>
<tr><th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#9F2936'>strategy_14_short</th><td bgcolor=#FFFEFE style='text-align:center'>-0.00</td><td bgcolor=#00FF00 style='text-align:center'>1.00</td><td bgcolor=#62FF62 style='text-align:center'>0.61</td></tr>
<tr><th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#F79646'>Combined</th><td bgcolor=#36FF36 style='text-align:center'>0.79</td><td bgcolor=#62FF62 style='text-align:center'>0.61</td><td bgcolor=#00FF00 style='text-align:center'>1.00</td></tr>
</table>
</div>

<!-- Add a blank line here to separate blocks -->

<div style='overflow-x:auto'><table class='w3-table' style='border:1px solid black'><tr style='border-bottom:1px solid black'><td style = 'border-right:1px solid black;text-align:center'><b>DRAWDOWNS</b></td>
<th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#4E8542'>strategy_14_long</th><th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#9F2936'>strategy_14_short</th><th scope='col' bgcolor=#F0F0F0 style='text-align:center;color:#F79646'>Combined</th></tr>
<tr><th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#4E8542'>strategy_14_long</th><td bgcolor=#00FF00 style='text-align:center'>1.00</td><td bgcolor=#FFF3F3 style='text-align:center'>-0.05</td><td bgcolor=#25FF25 style='text-align:center'>0.85</td></tr>
<tr><th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#9F2936'>strategy_14_short</th><td bgcolor=#FFF3F3 style='text-align:center'>-0.05</td><td bgcolor=#00FF00 style='text-align:center'>1.00</td><td bgcolor=#EDFFED style='text-align:center'>0.07</td></tr>
<tr><th scope='row' bgcolor=#F0F0F0 style='text-align:right;border-right:1px solid black;color:#F79646'>Combined</th><td bgcolor=#25FF25 style='text-align:center'>0.85</td><td bgcolor=#EDFFED style='text-align:center'>0.07</td><td bgcolor=#00FF00 style='text-align:center'>1.00</td></tr>
</table>
</div>

<!-- End of HTML block -->

## Visualizations

![Drawdown](Reports/docs/Strategy14/images/graph2.png)

![Drawdown](Reports/docs/Strategy14/images/graph3.png)
<div style="page-break-after: always;"></div>

![Daily](Reports/docs/Strategy14/images/graph5.png)

![Monthly](Reports/docs/Strategy14/images/graph7.png)
<div style="page-break-after: always;"></div>

### Trade Plots

![Individual %Gains](Reports/docs/Strategy14/images/plot0.png)

![Distribution of %Gains](Reports/docs/Strategy14/images/plot1.png)
<div style="page-break-after: always;"></div>

![Distribution of %Excursions](Reports/docs/Strategy14/images/plot2.png)

## Monte Carlo Analysis

The results for this strategy are less pleasing when looking at the Monte-Carlo charts. The range is wide and leads me to believe that this strategy may not be that robust. This could be due to the minimal trade entry criteria or indicate that the money flow indicator is not the best vessel to trade this relationship.

| Percentile | Net Profit | CAR     | Max Drawdown    |
| ---------- | ---------- | ------- | ---------------- |
| 1%         | 12.86%     | 0.69%   | **-12.20%**      |
| 5%         | 18.60%     | 0.97%   | **-10.51%**      |
| 10%        | 22.34%     | 1.15%   | **-8.74%**       |
| 20%        | 27.67%     | 1.39%   | **-7.25%**       |
| 50%        | 39.80%     | 1.92%   | **-5.39%**       |
| 80%        | 51.55%     | 2.38%   | **-3.75%**       |
| 90%        | 56.23%     | 2.56%   | **-2.95%**       |
| 95%        | 64.18%     | 2.85%   | **-2.32%**       |
| 99%        | 83.31%     | 3.49%   | **-1.50%**       |
| **backtest** | **36.87%** | **1.79%** | **-5.42%**       |

![MCPT Profit](Reports/docs/Strategy14/images/plot4.png)

![MCPT Excursion](Reports/docs/Strategy14/images/plot5.png)

---
*Generated by RealTest. These results are subject to change based on parameter adjustments or further development.*
