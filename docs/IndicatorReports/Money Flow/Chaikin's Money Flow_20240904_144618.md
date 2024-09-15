---
aliases: []
tags: []
title: Chaikin's Money Flow_20240904_144618
author: Larry Kann
titlepage: true
titlepage-rule-color: "336600"
titlepage-text-color: "000000"
colorlinks: "ff0d8a"
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
    output: Chaikin's Money Flow_20240904_144618.pdf
    from: markdown
    template: eisvogel
    listings: true
---

# Indicator Soundness Report: Chaikin's Money Flow

The generated report provides a comprehensive analysis of trading indicators, offering insights into their statistical properties, predictive power, mean stability over time, and optimal thresholds for profitability. It combines detailed statistical summaries, mutual information scores, mean break tests, and profit factor evaluations.

![[Money_Flow_1_50.png]]
![[Money_Flow_3_50.png]]
![[Money_Flow_5_50.png]]
![[Reports/docs/IndicatorReports/Money Flow/images/Log_Returns.png]]
## Simple Statistics and Relative Entropy Report

The Simple Statistics Table summarizes key metrics for each trading indicator, including the number of cases, mean, minimum, maximum, interquartile range (IQR), range/IQR ratio, and relative entropy. In the table, a lower range/IQR ratio suggests a tighter, more predictable dataset, while an optimal relative entropy indicates a balance of diversity and uniqueness without excessive noise.

**Ncases**: Number of cases (bars) in feature (indicator).
**Mean**: Average value of the feature across all cases.
**Min/Max**: The minimum and maximum value of the feature across all cases.
**IQR**: Interquartile Range, measures range minus the top and bottom 25% of the raw range.
**Range/IQR**: A unitless measure of data dispersion relative to its middle 50%.
**Relative Entropy**: Measures the difference between two probability distributions; a value of zero indicates identical distributions.

| Indicator           | Ncases | Mean           | Min            | Max            | IQR            | rnq/IQR        | Relative Entropy    |
|---------------------|--------|----------------|----------------|----------------|----------------|----------------|---------------------|
| Money_Flow_1_50     | 4949   | 7.1741         | -329.1692      | 289.9322       | 98.4312        | 6.2897         | 0.6556              |
| Money_Flow_3_50     | 4949   | 7.3816         | -240.5709      | 132.5020       | 49.1870        | 7.5848         | 0.6343              |
| Money_Flow_5_50     | 4949   | 7.5338         | -186.1576      | 103.6824       | 37.9836        | 7.6307         | 0.6319              |
## Mutual Information Report

High MI scores indicate a strong relationship between the indicator and the target variable, suggesting potential predictive power. Low p-values further validate the indicator's statistical significance.

**MI Score**: Measures the mutual dependence between the feature and the target.
**Solo p-value**: Initial significance estimate, proportion of permuted MI scores equal to or higher than the original MI scores.
**Unbiased p-value**: Adjusted solo p-value considering the number of permutations plus one, reducing bias.

| Indicator           | Target              | MI Score            | Solo p-value        | Unbiased p-value    |
|---------------------|---------------------|---------------------|---------------------|---------------------|
| Money_Flow_1_50    | Log_Returns        | 0.2807              | 0.0000              | 0.0010              |
| Money_Flow_3_50    | Log_Returns        | 0.0689              | 0.0000              | 0.0010              |
| Money_Flow_5_50    | Log_Returns        | 0.0467              | 0.0000              | 0.0010              |

## Serial Correlated Mean Break Test Report

The Serial Correlated Mean Break Test Report identifies potential breaks in the mean of each trading indicator, taking into account serial correlation. This test helps detect significant shifts in the mean over time, indicating nonstationary behavior in the data.

**nrecent**: The number of recent observations considered in the test.
**z(U)**: The greatest break encountered in the mean across the user-specified range.
**Solo p-value**: Measures the significance of the greatest break while accounting for the entire range of boundaries searched. If this value is not small, it suggests that the indicator does not have a significant mean break.
**Unbiased p-value**: Adjusted p-value considering multiple indicators.

| Indicator           | n_recent | z(U)     | Solo p-value | Unbiased p-value |
|---------------------|----------|----------|--------------|-----------------|
| Money_Flow_1_50     | 5000.0   | 40.7140  | 0.6980       | 0.4770          |
| Money_Flow_3_50     | 5000.0   | 40.7802  | 0.1610       | 0.4770          |
| Money_Flow_5_50     | 5000.0   | 40.7350  | 0.4280       | 0.4770          |

## Optimal Thresholds w/ Profit Factor Report

The Optimal Thresholds w/ Profit Factor Report evaluates various threshold levels for trading indicators to identify the most profitable long and short positions. The report includes the fraction of data points greater than or equal to the threshold, the corresponding profit factor for long and short positions, and the fraction of data points less than the threshold with their respective profit factors. The optimal thresholds at the bottom indicate the threshold levels with the highest profit factors for long and short positions, while the p-values provide statistical significance for these thresholds.

### Money_Flow_1_50 vs Log_Returns

| Threshold | Frac Gtr/Eq | Long PF    | Short PF   | Frac Less | Short PF   | Long PF    |
|-----------|-------------|------------|------------|-----------|------------|------------|
| -174.079 |      0.990 |       1.0966 |       0.9119 |         0.010 |       0.6382 |       1.5670 |
| -109.532 |      0.950 |       1.0669 |       0.9373 |         0.050 |       0.5890 |       1.6977 |
|  -82.718 |      0.900 |       1.0594 |       0.9440 |         0.100 |       0.6877 |       1.4542 |
|  -53.812 |      0.800 |       1.0180 |       0.9824 |         0.200 |       0.7097 |       1.4091 |
|  -28.060 |      0.700 |       1.0102 |       0.9899 |         0.300 |       0.7693 |       1.2999 |
|   -3.915 |      0.600 |       0.9759 |       1.0247 |         0.400 |       0.7757 |       1.2892 |
|   15.796 |      0.500 |       0.9582 |       1.0437 |         0.500 |       0.8006 |       1.2490 |
|   34.109 |      0.400 |       0.9662 |       1.0350 |         0.600 |       0.8361 |       1.1961 |
|   51.409 |      0.300 |       0.9205 |       1.0863 |         0.700 |       0.8410 |       1.1890 |
|   66.045 |      0.200 |       0.9002 |       1.1108 |         0.800 |       0.8596 |       1.1633 |
|   84.214 |      0.100 |       0.7919 |       1.2628 |         0.900 |       0.8664 |       1.1543 |
|  100.628 |      0.050 |       0.6279 |       1.5927 |         0.950 |       0.8680 |       1.1521 |
|  140.931 |      0.010 |       0.5552 |       1.8013 |         0.990 |       0.8909 |       1.1225 |

**Grand profit factor**: 1.105
**Optimal long threshold**: -109.4689, profit factor = 1.699
**Optimal short threshold**: 97.4897, profit factor = 1.600

**P-values**: Long=0.999, Unbiased Long=0.999
**P-values**: Short=0.000, Unbiased Short=0.001

### Money_Flow_3_50 vs Log_Returns

| Threshold | Frac Gtr/Eq | Long PF    | Short PF   | Frac Less | Short PF   | Long PF    |
|-----------|-------------|------------|------------|-----------|------------|------------|
|  -93.626 |      0.990 |       1.1012 |       0.9081 |         0.010 |       0.7472 |       1.3383 |
|  -59.343 |      0.950 |       1.0816 |       0.9245 |         0.050 |       0.6864 |       1.4569 |
|  -41.971 |      0.900 |       1.0396 |       0.9619 |         0.100 |       0.6212 |       1.6097 |
|  -22.239 |      0.800 |       1.0236 |       0.9769 |         0.200 |       0.7234 |       1.3824 |
|   -9.850 |      0.700 |       0.9981 |       1.0019 |         0.300 |       0.7598 |       1.3162 |
|    0.357 |      0.600 |       0.9709 |       1.0300 |         0.400 |       0.7777 |       1.2859 |
|   10.393 |      0.500 |       0.9695 |       1.0315 |         0.500 |       0.8169 |       1.2241 |
|   19.314 |      0.400 |       0.9406 |       1.0632 |         0.600 |       0.8333 |       1.2000 |
|   29.035 |      0.300 |       0.9185 |       1.0887 |         0.700 |       0.8523 |       1.1733 |
|   39.015 |      0.200 |       0.8996 |       1.1116 |         0.800 |       0.8696 |       1.1500 |
|   52.202 |      0.100 |       0.8398 |       1.1908 |         0.900 |       0.8836 |       1.1317 |
|   63.764 |      0.050 |       0.7991 |       1.2514 |         0.950 |       0.8923 |       1.1207 |
|   85.689 |      0.010 |       0.8910 |       1.1223 |         0.990 |       0.9033 |       1.1070 |

**Grand profit factor**: 1.105
**Optimal long threshold**: -43.0962, profit factor = 1.720
**Optimal short threshold**: 62.1343, profit factor = 1.321

**P-values**: Long=0.999, Unbiased Long=0.999
**P-values**: Short=0.000, Unbiased Short=0.001

### Money_Flow_5_50 vs Log_Returns

| Threshold | Frac Gtr/Eq | Long PF    | Short PF   | Frac Less | Short PF   | Long PF    |
|-----------|-------------|------------|------------|-----------|------------|------------|
|  -72.525 |      0.990 |       1.0905 |       0.9170 |         0.010 |       0.5444 |       1.8368 |
|  -44.204 |      0.950 |       1.0882 |       0.9189 |         0.050 |       0.7542 |       1.3258 |
|  -30.804 |      0.900 |       1.0636 |       0.9402 |         0.100 |       0.7144 |       1.3998 |
|  -15.657 |      0.800 |       1.0288 |       0.9720 |         0.200 |       0.7423 |       1.3471 |
|   -5.510 |      0.700 |       0.9858 |       1.0144 |         0.300 |       0.7522 |       1.3294 |
|    2.597 |      0.600 |       1.0263 |       0.9743 |         0.400 |       0.8376 |       1.1939 |
|    9.995 |      0.500 |       1.0106 |       0.9895 |         0.500 |       0.8493 |       1.1774 |
|   16.616 |      0.400 |       0.9728 |       1.0280 |         0.600 |       0.8506 |       1.1757 |
|   24.003 |      0.300 |       0.9484 |       1.0544 |         0.700 |       0.8640 |       1.1575 |
|   32.174 |      0.200 |       0.8910 |       1.1223 |         0.800 |       0.8714 |       1.1476 |
|   42.606 |      0.100 |       0.8286 |       1.2068 |         0.900 |       0.8843 |       1.1308 |
|   51.786 |      0.050 |       0.9889 |       1.0112 |         0.950 |       0.9016 |       1.1091 |
|   69.077 |      0.010 |       0.8856 |       1.1292 |         0.990 |       0.9035 |       1.1068 |

**Grand profit factor**: 1.105
**Optimal long threshold**: -35.1488, profit factor = 1.477
**Optimal short threshold**: 46.4637, profit factor = 1.343

**P-values**: Long=0.999, Unbiased Long=0.999
**P-values**: Short=0.001, Unbiased Short=0.002
