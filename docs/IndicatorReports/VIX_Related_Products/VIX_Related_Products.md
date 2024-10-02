# Indicator Soundness Report VIX_Related_Products

The generated report provides a comprehensive analysis of trading indicators, offering insights into their statistical properties, predictive power, mean stability over time, and optimal thresholds for profitability. It combines detailed statistical summaries, mutual information scores, mean break tests, and profit factor evaluations.

At least, that is what this report usually does. In this particular report, the only "indicator" is the VIX. Everything else are the log returns of SPY and VIX products. The tests that we are most concerned with are the basic statistics, the mean break test, and the eyeball test (look at the charts). We are checking to make sure that the products that we intend to trade are, themselves, stationary. This report does show that, for the most part. The VIX indicator has not been normalized at all, in order to asses it in it's raw form.

Interestingly enough though, the mutual information test and the optimization tables show us if there any predictive power in the returns against the returns of SPY. The results are interesting.

Data sourced from Norgate Data.

![&VX_CCB](C:\Users\kannd\Documents\cyberBrain\IndicatorReports\VIX_Related_Products\images\&VX_CCB.png)

![&ES_CCB](C:\Users\kannd\Documents\cyberBrain\IndicatorReports\VIX_Related_Products\images\&ES_CCB.png)

![VXX](C:\Users\kannd\Documents\cyberBrain\IndicatorReports\VIX_Related_Products\images\VXX.png)

![UVXY](C:\Users\kannd\Documents\cyberBrain\IndicatorReports\VIX_Related_Products\images\UVXY.png)

![SVXY](C:\Users\kannd\Documents\cyberBrain\IndicatorReports\VIX_Related_Products\images\SVXY.png)

![VIX](C:\Users\kannd\Documents\cyberBrain\IndicatorReports\VIX_Related_Products\images\VIX.png)

![VIX_zscore](C:\Users\kannd\Documents\cyberBrain\IndicatorReports\VIX_Related_Products\images\VIX_zscore.png)


![SPY_Log_Returns](C:\Users\kannd\Documents\cyberBrain\IndicatorReports\VIX_Related_Products\images\SPY_Log_Returns.png)

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
| &VX_CCB             | 1654   | -0.0011        | -0.2097        | 0.3656         | 0.0152         | 37.8184        | 0.2017              |
| &ES_CCB             | 1654   | 0.0004         | -0.0968        | 0.0812         | 0.0105         | 16.8981        | 0.3975              |
| VXX                 | 1654   | -0.0024        | -0.2137        | 0.3308         | 0.0422         | 12.8908        | 0.5090              |
| UVXY                | 1654   | -0.0044        | -0.3338        | 0.4593         | 0.0651         | 12.1764        | 0.5273              |
| SVXY                | 1654   | 0.0004         | -0.2412        | 0.0929         | 0.0218         | 15.3234        | 0.4301              |
| VIX                 | 1654   | 20.0486        | 10.8500        | 82.6900        | 8.5025         | 8.4493         | 0.5259              |
| VIX_zscore          | 1654   | -0.0406        | -2.3610        | 4.7562         | 1.7876         | 3.9814         | 0.8255              |
## Mutual Information Report

High MI scores indicate a strong relationship between the indicator and the target variable, suggesting potential predictive power. Low p-values further validate the indicator's statistical significance.

**MI Score**: Measures the mutual dependence between the feature and the target.
**Solo p-value**: Initial significance estimate, proportion of permuted MI scores equal to or higher than the original MI scores.
**Unbiased p-value**: Adjusted solo p-value considering the number of permutations plus one, reducing bias.

| Indicator           | Target              | MI Score            | Solo p-value        | Unbiased p-value    |
|---------------------|---------------------|---------------------|---------------------|---------------------|
| &VX_CCB            | SPY_Log_Returns    | 0.1468              | 0.0000              | 0.0010              |
| &ES_CCB            | SPY_Log_Returns    | 0.6328              | 0.0000              | 0.0010              |
| VXX                | SPY_Log_Returns    | 0.3075              | 0.0000              | 0.0010              |
| UVXY               | SPY_Log_Returns    | 0.3348              | 0.0000              | 0.0010              |
| SVXY               | SPY_Log_Returns    | 0.3118              | 0.0000              | 0.0010              |
| VIX                | SPY_Log_Returns    | 0.1549              | 0.0000              | 0.0010              |
| VIX_zscore         | SPY_Log_Returns    | 0.1250              | 0.0000              | 0.0010              |

## Serial Correlated Mean Break Test Report

The Serial Correlated Mean Break Test Report identifies potential breaks in the mean of each trading indicator, taking into account serial correlation. This test helps detect significant shifts in the mean over time, indicating nonstationary behavior in the data.

**nrecent**: The number of recent observations considered in the test.
**z(U)**: The greatest break encountered in the mean across the user-specified range.
**Solo p-value**: Measures the significance of the greatest break while accounting for the entire range of boundaries searched. If this value is not small, it suggests that the indicator does not have a significant mean break.
**Unbiased p-value**: Adjusted p-value considering multiple indicators.

| Indicator           | n_recent | z(U)     | Solo p-value | Unbiased p-value |
|---------------------|----------|----------|--------------|-----------------|
| &VX_CCB             | 2500.0   | 29.7336  | 0.1290       | 0.8150          |
| &ES_CCB             | 2500.0   | 29.7335  | 0.7290       | 0.8150          |
| VXX                 | 2500.0   | 29.7334  | 0.9850       | 0.8150          |
| UVXY                | 2500.0   | 29.7335  | 0.9210       | 0.8150          |
| SVXY                | 2500.0   | 29.7335  | 0.6400       | 0.8150          |
| VIX                 | 2500.0   | 28.9890  | 0.9980       | 0.8150          |
| VIX_zscore          | 2500.0   | 29.7330  | 0.8520       | 0.8150          |

## Optimal Thresholds w/ Profit Factor Report

The Optimal Thresholds w/ Profit Factor Report evaluates various threshold levels for trading indicators to identify the most profitable long and short positions. The report includes the fraction of data points greater than or equal to the threshold, the corresponding profit factor for long and short positions, and the fraction of data points less than the threshold with their respective profit factors. The optimal thresholds at the bottom indicate the threshold levels with the highest profit factors for long and short positions, while the p-values provide statistical significance for these thresholds.

### &VX_CCB vs SPY_Log_Returns

| Threshold | Frac Gtr/Eq | Long PF    | Short PF   | Frac Less | Short PF   | Long PF    |
|-----------|-------------|------------|------------|-----------|------------|------------|
|   -0.052 |      0.990 |       1.1205 |       0.8924 |         0.010 |       0.4149 |       2.4100 |
|   -0.028 |      0.950 |       1.1422 |       0.8755 |         0.050 |       1.0034 |       0.9966 |
|   -0.021 |      0.900 |       1.1845 |       0.8442 |         0.100 |       1.1930 |       0.8382 |
|   -0.013 |      0.800 |       1.1659 |       0.8577 |         0.200 |       0.9731 |       1.0276 |
|   -0.008 |      0.700 |       1.1655 |       0.8580 |         0.300 |       0.9380 |       1.0661 |
|   -0.005 |      0.600 |       1.1331 |       0.8825 |         0.400 |       0.8842 |       1.1310 |
|   -0.003 |      0.500 |       1.1380 |       0.8787 |         0.500 |       0.8882 |       1.1259 |
|   -0.000 |      0.400 |       1.1332 |       0.8825 |         0.600 |       0.8838 |       1.1315 |
|    0.003 |      0.300 |       1.2099 |       0.8265 |         0.700 |       0.9140 |       1.0941 |
|    0.008 |      0.200 |       1.1923 |       0.8387 |         0.800 |       0.8991 |       1.1122 |
|    0.018 |      0.100 |       1.0727 |       0.9323 |         0.900 |       0.8752 |       1.1426 |
|    0.033 |      0.050 |       0.9738 |       1.0269 |         0.950 |       0.8717 |       1.1471 |
|    0.073 |      0.010 |       3.2237 |       0.3102 |         0.990 |       0.9037 |       1.1066 |

**Grand profit factor**: 1.132
**Optimal long threshold**: 0.0035, profit factor = 1.250
**Optimal short threshold**: -0.0254, profit factor = 1.296

### SPY vs SPY_Log_Returns

This is very interesting. This optimization table takes a feature, in this case it is SPY returns, and then determines profit factor by looking at the returns of the target (still SPY) the next day. In other words, it measures where the most predictability in a feature is. In this case, however, we are comparing SPY returns to SPY returns the next day. Think about that. That means that if this is right, you can use the returns on a product itself to help accurately predict price movement the following day. 

An example test of this could look something like this:

```python
log_returns = (np.log(Close / Close[1])) * 100 # for readabillity
entry_short = log_returns[1] > 1.68
```

In plain words, enter long when the previous days log returns is greater than 1.68.

| Threshold | Frac Gtr/Eq | Long PF    | Short PF   | Frac Less | Short PF   | Long PF    |
|-----------|-------------|------------|------------|-----------|------------|------------|
|   -0.035 |      0.990 |       1.1073 |       0.9031 |         0.010 |       0.5479 |       1.8250 |
|   -0.019 |      0.951 |       1.0733 |       0.9317 |         0.049 |       0.5815 |       1.7196 |
|   -0.013 |      0.901 |       1.1143 |       0.8974 |         0.099 |       0.8545 |       1.1703 |
|   -0.007 |      0.800 |       1.1088 |       0.9019 |         0.200 |       0.8616 |       1.1607 |
|   -0.003 |      0.700 |       1.0742 |       0.9309 |         0.300 |       0.8306 |       1.2040 |
|   -0.001 |      0.600 |       1.0845 |       0.9221 |         0.400 |       0.8568 |       1.1672 |
|    0.001 |      0.500 |       1.1001 |       0.9090 |         0.500 |       0.8755 |       1.1423 |
|    0.003 |      0.400 |       1.0705 |       0.9342 |         0.600 |       0.8655 |       1.1554 |
|    0.005 |      0.300 |       0.9872 |       1.0129 |         0.700 |       0.8439 |       1.1850 |
|    0.009 |      0.200 |       0.8370 |       1.1947 |         0.800 |       0.8202 |       1.2192 |
|    0.013 |      0.100 |       0.6346 |       1.5758 |         0.900 |       0.8160 |       1.2255 |
|    0.017 |      0.050 |       0.4589 |       2.1792 |         0.950 |       0.8266 |       1.2097 |
|    0.030 |      0.010 |       0.1635 |       6.1152 |         0.990 |       0.8501 |       1.1763 |

**Grand profit factor**: 1.123
**Optimal long threshold**: -0.0189, profit factor = 1.720
**Optimal short threshold**: 0.0168, profit factor = 2.205

### &ES_CCB vs SPY_Log_Returns

This is just cool. Using the the returns of the SPY futures contract (ES) to predict the returns of SPY the next day. Much like the Spy v. Spy comparison, this one shows long profitability on SPY when the returns of ES are largely negative and vice versa for shorts. Those are not nominal profit factors either, if they are to be trusted

| Threshold | Frac Gtr/Eq | Long PF    | Short PF   | Frac Less | Short PF   | Long PF    |
|-----------|-------------|------------|------------|-----------|------------|------------|
|   -0.031 |      0.990 |       1.1220 |       0.8912 |         0.010 |       0.6628 |       1.5088 |
|   -0.017 |      0.950 |       1.0968 |       0.9117 |         0.050 |       0.6589 |       1.5176 |
|   -0.011 |      0.900 |       1.1263 |       0.8878 |         0.100 |       0.8602 |       1.1625 |
|   -0.006 |      0.800 |       1.1184 |       0.8942 |         0.200 |       0.8559 |       1.1683 |
|   -0.003 |      0.700 |       1.0908 |       0.9168 |         0.300 |       0.8330 |       1.2005 |
|   -0.001 |      0.600 |       1.1073 |       0.9031 |         0.400 |       0.8622 |       1.1599 |
|    0.001 |      0.500 |       1.0855 |       0.9212 |         0.500 |       0.8544 |       1.1704 |
|    0.002 |      0.400 |       1.0459 |       0.9561 |         0.600 |       0.8436 |       1.1854 |
|    0.005 |      0.300 |       0.9832 |       1.0171 |         0.700 |       0.8325 |       1.2012 |
|    0.008 |      0.200 |       0.8190 |       1.2209 |         0.800 |       0.8073 |       1.2387 |
|    0.012 |      0.100 |       0.6257 |       1.5982 |         0.900 |       0.8098 |       1.2349 |
|    0.015 |      0.050 |       0.4700 |       2.1277 |         0.950 |       0.8184 |       1.2220 |
|    0.027 |      0.010 |       0.1482 |       6.7470 |         0.990 |       0.8373 |       1.1942 |

**Grand profit factor**: 1.132
**Optimal long threshold**: -0.0166, profit factor = 1.563
**Optimal short threshold**: 0.0150, profit factor = 2.147

### VXX vs SPY_Log_Returns

Compared to the VX futures contract table, the VXX seems to have a better ability to predict the returns of SPY. We see (same with VX and likely all VIX products) that the returns tthat predict movements are opposite of the the SPY v SPY predictions. Now, we see that positive returns of VXX are correlated with positive returns on SPY and vice versa.

| Threshold | Frac Gtr/Eq | Long PF    | Short PF   | Frac Less | Short PF   | Long PF    |
|-----------|-------------|------------|------------|-----------|------------|------------|
|   -0.091 |      0.990 |       1.1579 |       0.8637 |         0.010 |       1.8967 |       0.5272 |
|   -0.060 |      0.950 |       1.1911 |       0.8395 |         0.050 |       1.6457 |       0.6077 |
|   -0.046 |      0.900 |       1.1932 |       0.8381 |         0.100 |       1.2693 |       0.7878 |
|   -0.033 |      0.800 |       1.1903 |       0.8401 |         0.200 |       1.0564 |       0.9466 |
|   -0.023 |      0.700 |       1.1746 |       0.8514 |         0.300 |       0.9617 |       1.0399 |
|   -0.016 |      0.600 |       1.1724 |       0.8529 |         0.400 |       0.9309 |       1.0742 |
|   -0.008 |      0.500 |       1.1129 |       0.8986 |         0.500 |       0.8674 |       1.1529 |
|    0.000 |      0.400 |       1.1192 |       0.8935 |         0.600 |       0.8754 |       1.1424 |
|    0.009 |      0.300 |       1.2166 |       0.8219 |         0.700 |       0.9165 |       1.0911 |
|    0.022 |      0.200 |       1.2428 |       0.8046 |         0.800 |       0.9117 |       1.0968 |
|    0.046 |      0.100 |       1.3461 |       0.7429 |         0.900 |       0.9096 |       1.0994 |
|    0.075 |      0.050 |       1.3269 |       0.7536 |         0.950 |       0.8970 |       1.1149 |
|    0.148 |      0.010 |       2.1499 |       0.4651 |         0.990 |       0.8976 |       1.1140 |

**Grand profit factor**: 1.132
**Optimal long threshold**: 0.0628, profit factor = 1.498
**Optimal short threshold**: -0.0594, profit factor = 1.655

**P-values**: Long=0.999, Unbiased Long=0.999
**P-values**: Short=0.000, Unbiased Short=0.001

### UVXY vs SPY_Log_Returns

The short profit factor here might be worth looking into.

| Threshold | Frac Gtr/Eq | Long PF    | Short PF   | Frac Less | Short PF   | Long PF    |
|-----------|-------------|------------|------------|-----------|------------|------------|
|   -0.137 |      0.990 |       1.1352 |       0.8809 |         0.010 |       0.9912 |       1.0089 |
|   -0.092 |      0.950 |       1.1978 |       0.8349 |         0.050 |       1.7694 |       0.5652 |
|   -0.071 |      0.900 |       1.2081 |       0.8277 |         0.100 |       1.3785 |       0.7254 |
|   -0.050 |      0.800 |       1.1817 |       0.8463 |         0.200 |       1.0277 |       0.9731 |
|   -0.035 |      0.700 |       1.1584 |       0.8633 |         0.300 |       0.9288 |       1.0766 |
|   -0.024 |      0.600 |       1.1899 |       0.8404 |         0.400 |       0.9496 |       1.0531 |
|   -0.012 |      0.500 |       1.1722 |       0.8531 |         0.500 |       0.9156 |       1.0922 |
|   -0.000 |      0.400 |       1.2115 |       0.8254 |         0.600 |       0.9296 |       1.0757 |
|    0.014 |      0.300 |       1.1703 |       0.8545 |         0.700 |       0.8987 |       1.1127 |
|    0.033 |      0.200 |       1.1710 |       0.8540 |         0.800 |       0.8937 |       1.1189 |
|    0.070 |      0.100 |       1.1497 |       0.8698 |         0.900 |       0.8855 |       1.1293 |
|    0.115 |      0.050 |       1.2921 |       0.7739 |         0.950 |       0.8944 |       1.1180 |
|    0.211 |      0.010 |       2.3763 |       0.4208 |         0.990 |       0.8992 |       1.1121 |

**Grand profit factor**: 1.132
**Optimal long threshold**: 0.1083, profit factor = 1.372
**Optimal short threshold**: -0.0917, profit factor = 1.769

**P-values**: Long=0.999, Unbiased Long=0.999
**P-values**: Short=0.000, Unbiased Short=0.001

### SVXY vs SPY_Log_Returns

Another short possibility to examine.

| Threshold | Frac Gtr/Eq | Long PF    | Short PF   | Frac Less | Short PF   | Long PF    |
|-----------|-------------|------------|------------|-----------|------------|------------|
|   -0.084 |      0.990 |       1.1114 |       0.8998 |         0.010 |       0.4033 |       2.4793 |
|   -0.041 |      0.950 |       1.1230 |       0.8905 |         0.050 |       0.8079 |       1.2377 |
|   -0.025 |      0.900 |       1.1218 |       0.8914 |         0.100 |       0.8361 |       1.1961 |
|   -0.012 |      0.800 |       1.1479 |       0.8711 |         0.200 |       0.9190 |       1.0881 |
|   -0.005 |      0.700 |       1.1079 |       0.9026 |         0.300 |       0.8474 |       1.1800 |
|    0.000 |      0.601 |       1.0579 |       0.9452 |         0.399 |       0.8068 |       1.2395 |
|    0.004 |      0.500 |       1.0825 |       0.9238 |         0.500 |       0.8461 |       1.1819 |
|    0.008 |      0.400 |       1.0528 |       0.9498 |         0.600 |       0.8408 |       1.1893 |
|    0.011 |      0.300 |       1.0395 |       0.9620 |         0.700 |       0.8486 |       1.1784 |
|    0.016 |      0.200 |       1.0468 |       0.9553 |         0.800 |       0.8631 |       1.1585 |
|    0.023 |      0.100 |       0.7215 |       1.3860 |         0.900 |       0.8252 |       1.2119 |
|    0.029 |      0.050 |       0.6360 |       1.5724 |         0.950 |       0.8420 |       1.1876 |
|    0.042 |      0.010 |       0.3782 |       2.6443 |         0.990 |       0.8541 |       1.1708 |

**Grand profit factor**: 1.132
**Optimal long threshold**: -0.0340, profit factor = 1.397
**Optimal short threshold**: 0.0272, profit factor = 1.616

**P-values**: Long=0.999, Unbiased Long=0.999
**P-values**: Short=0.000, Unbiased Short=0.001

### VIX vs SPY_Log_Returns

The star of the show. Can the VIX be used to predict returns of SPY the following day? It looks like it doesn't do well predicting short opportunities until VIX levels are very high (1% of historical values). However, it does appear that under 12.78 (fraction less than) there is a decent ability to predict returns the next day.

This possibly supports the use of the VIX as a filter for trade systems, especially long trade systems that perform better with more predictable volatility levels.

| Threshold | Frac Gtr/Eq | Long PF    | Short PF   | Frac Less | Short PF   | Long PF    |
|-----------|-------------|------------|------------|-----------|------------|------------|
|   11.980 |      0.990 |       1.1334 |       0.8823 |         0.010 |       1.1849 |       0.8440 |
|   12.440 |      0.950 |       1.1245 |       0.8893 |         0.050 |       0.6200 |       1.6128 |
|   12.860 |      0.901 |       1.1196 |       0.8932 |         0.099 |       0.6683 |       1.4964 |
|   13.850 |      0.800 |       1.0965 |       0.9120 |         0.200 |       0.6491 |       1.5406 |
|   15.370 |      0.700 |       1.0786 |       0.9272 |         0.300 |       0.6865 |       1.4566 |
|   16.650 |      0.600 |       1.0903 |       0.9172 |         0.400 |       0.7778 |       1.2857 |
|   18.140 |      0.501 |       1.1242 |       0.8895 |         0.499 |       0.8695 |       1.1501 |
|   19.950 |      0.400 |       1.1125 |       0.8989 |         0.600 |       0.8610 |       1.1615 |
|   21.970 |      0.301 |       1.1459 |       0.8727 |         0.699 |       0.8936 |       1.1191 |
|   24.800 |      0.200 |       1.1493 |       0.8701 |         0.800 |       0.8914 |       1.1218 |
|   28.870 |      0.100 |       1.2661 |       0.7898 |         0.900 |       0.9136 |       1.0945 |
|   32.600 |      0.050 |       1.2987 |       0.7700 |         0.950 |       0.9037 |       1.1065 |
|   53.540 |      0.010 |       0.9316 |       1.0734 |         0.990 |       0.8721 |       1.1467 |

**Grand profit factor**: 1.132
**Optimal long threshold**: 12.7800, profit factor = 1.695
**Optimal short threshold**: 25.5400, profit factor = 0.931

**P-values**: Long=0.999, Unbiased Long=0.999
**P-values**: Short=1.000, Unbiased Short=1.000

### VIX_zscore vs SPY_Log_Returns

These results are much cleaner than the results above. We can see that there is a threshold level for profitable shorts now. The long threshold is probably more believable, as the z-score isn't as influenced by outlier (large) VIX values as much.

| Threshold | Frac Gtr/Eq | Long PF    | Short PF   | Frac Less | Short PF   | Long PF    |
|-----------|-------------|------------|------------|-----------|------------|------------|
|   -1.961 |      0.990 |       1.1276 |       0.8868 |         0.010 |       0.4036 |       2.4780 |
|   -1.600 |      0.950 |       1.1388 |       0.8781 |         0.050 |       1.0205 |       0.9799 |
|   -1.408 |      0.900 |       1.1534 |       0.8670 |         0.100 |       1.1304 |       0.8846 |
|   -1.139 |      0.800 |       1.1252 |       0.8887 |         0.200 |       0.8523 |       1.1733 |
|   -0.903 |      0.700 |       1.0539 |       0.9488 |         0.300 |       0.6926 |       1.4438 |
|   -0.680 |      0.600 |       1.0456 |       0.9564 |         0.400 |       0.7342 |       1.3621 |
|   -0.361 |      0.500 |       1.0019 |       0.9981 |         0.500 |       0.7171 |       1.3944 |
|    0.050 |      0.400 |       1.0079 |       0.9921 |         0.600 |       0.7724 |       1.2946 |
|    0.460 |      0.300 |       1.0071 |       0.9929 |         0.700 |       0.8101 |       1.2345 |
|    1.038 |      0.200 |       0.9209 |       1.0859 |         0.800 |       0.8056 |       1.2414 |
|    1.779 |      0.100 |       0.9415 |       1.0622 |         0.900 |       0.8515 |       1.1744 |
|    2.410 |      0.050 |       1.5216 |       0.6572 |         0.950 |       0.9060 |       1.1038 |
|    3.542 |      0.010 |       1.9905 |       0.5024 |         0.990 |       0.8915 |       1.1217 |

**Grand profit factor**: 1.132
**Optimal long threshold**: 2.4098, profit factor = 1.522
**Optimal short threshold**: -1.4979, profit factor = 1.324

**P-values**: Long=0.999, Unbiased Long=0.999
**P-values**: Short=0.000, Unbiased Short=0.001
