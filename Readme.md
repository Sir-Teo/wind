# Wind Farms Observations

## Bias

### Bias at 24 Hours interval

![Bias at 24 Hours interval](./plots/bias_24hr_with_area.png)

### Bias at each hour

![Bias at each hour](./plots/bias_1hr.png)

- at night there is less bias
- negative bias in the south and north. positive bias in the middle
- **least bias** around 17:00-18:00

### Violin plot of bias at each hour

![Violin plot of bias at each hour](./plots/violin_and_box_bias_1hr.png)

- two outliers at the bottom are **Canadian Breaks Wind** and **Desert Sky repower**

## Std

### Std at 24 Hours interval

![Std at 24 Hours interval](./plots/std_of_bias_24hr.png)

- low std at the south and north, high std at the middle

### std of bias at each hour

![std of bias at each hour](./plots/std_of_bias_1hr.png)

- at the sourth std lower from midnight to noon

### Violin plot of std of bias at each hour

![Violin plot of std of bias at each hour](./plots/violin_and_box_std_of_bias_1hr.png)

- low std in the afternoon and the evening

### Bump Chart of std of bias at each hour

![Bump Chart of std of bias at each hour](./plots/std_bumpchart_all_farm_all_time.png)

**Kendall Coefficient of Correlation for the above bump chart**

| 0-1 | 1-2 | 2-3 | 3-4 | 4-5 | 5-6 | 6-7 | 7-8 | 8-9 | 9-10 | 10-11 | 11-12 | 12-13 | 13-14 | 14-15 | 15-16 | 16-17 | 17-18 | 18-19 | 19-20 | 20-21 | 21-22 | 22-23 | 23-24 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
|0.842 |0.871 |0.879 |0.910 |0.918 |0.918 |0.928 |0.918 |0.916 |0.916 |0.894 |0.891 |0.878 |0.833 |0.808 |0.825 |0.832 |0.853 |0.863 |0.881 |0.865 |0.846 |0.883 |

- low std farms tend to stay low, high std farms tend to stay high
- Kendall's $\tau$ is higher in the morning

#### Bump Chart of std of bias at each hour (North)

![Bump Chart of std of bias at each hour (North)](./plots/std_bumpchart_all_farm_all_time_north.png)

#### Bump Chart of std of bias at each hour (South)

![Bump Chart of std of bias at each hour (South)](./plots/std_bumpchart_all_farm_all_time_South.png)

#### Bump Chart of std of bias at each hour (North Central)

![Bump Chart of std of bias at each hour (North Central)](./plots/std_bumpchart_all_farm_all_time_NorthCentral.png)

#### Bump Chart of std of bias at each hour (West)

![Bump Chart of std of bias at each hour (West)](./plots/std_bumpchart_all_farm_all_time_West.png)

- less crossings comparing to other regions

#### Bump Chart of std of bias at each hour (Far West)

![Bump Chart of std of bias at each hour (Far West)](./plots/std_bumpchart_all_farm_all_time_FarWest.png)

- more "crossings" comparing to other regions

## 95 percentile - mean (bias)

![95 percentile - mean (bias) at 24 Hours interval](./plots/bias_95quantile_minus_mean_1hr.png)

- continuity
- larger in the afternoon until midnight

kendall rank corr coeff
bump chart quantile and std
capacity vs unnormalized std
if the quantile is the same
