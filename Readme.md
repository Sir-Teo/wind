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

|0-1| 1-2 | 2-3 | 3-4 | 4-5 | 5-6 | 6-7 | 7-8 | 8-9 | 9-10 | 10-11 | 11-12 | 12-13 | 13-14 | 14-15 | 15-16 | 16-17 | 17-18 | 18-19 | 19-20 | 20-21 | 21-22 | 22-23 | 23-24 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
|0.842 |0.871 |0.879 |0.910 |0.918 |0.918 |0.928 |0.918 |0.916 |0.916 |0.894 |0.891 |0.878 |0.833 |0.808 |<font color='red'>0.825</font> |0.832 |0.853 |0.863 |0.881 |0.865 |0.846 |0.883 |

- low std farms tend to stay low, high std farms tend to stay high
- Kendall's <!-- $\tau$ --> <img style="transform: translateY(0.1em); background: white;" src="https://render.githubusercontent.com/render/math?math=%5Ctau"> is higher in the morning

#### kendall's coefficient for each region

![kendall by region](./plots/kendall.png)

### Conclusion for these bump charts

- In general, across all regions, kendall's <!-- $\tau$ --> <img style="transform: translateY(0.1em); background: white;" src="https://render.githubusercontent.com/render/math?math=%5Ctau"> is lower is the afternoon
- North Central Farms and West Farms have the highest average kendall's tau, while the South Farms have the lowest average kendall's tau.

## 95 percentile - mean (bias)

![95 percentile - mean (bias) at 24 Hours interval](./plots/bias_95quantile_minus_mean_1hr.png)

- larger in the afternoon until midnight

### Bump Charts 0-24hr

![95 percentile - mean (bias) at 24 Hours interval bump](./plots/bumpchart_quantile_0-24.png)

- low ones go high and high ones go low

## capacity vs unnormalized std

### Linear Regression

![capacity vs unnormalized std](./plots/capacity_vs_unnormstd.png)

- there is a strong correlation (<!-- $r^2 = 0.897$ --> <img style="transform: translateY(0.1em); background: white;" src="https://render.githubusercontent.com/render/math?math=r%5E2%20%3D%200.897">) between capacity and unormalized std.
- Wind Farms at the south tend to have low unnormalized std/capacity ratio

![capacity vs unnormalized std by region](./plots/capacity_vs_unnormstd_by_region.png)

- the correlation coefficient for North Central is 0.9349458943175288
- the correlation coefficient for North is 0.9425002375847092
- the correlation coefficient for West is 0.9502674365455899
- the correlation coefficient for Far West is 0.9477938088833047
- the correlation coefficient for South is 0.8853149787430542
- the correlation coefficient for South Central is 0.9951808329420279 (**very linear**)

### LOWESS

![capacity vs unnormalised std lowess](./plots/capacity_vs_unnormstd_lowess.png)

![capacity vs unnormalised std lowess by region](./plots/capacity_vs_unnormstd_lowess_byregion.png)

### Spline

![capacity vs unormalised std spline](./plots/capacity_vs_unnormstd_bspline.png)

### Polynomials

![capacity vs unormalised std polynomial](./plots/capacity_vs_unnormstd_polyfit.png)

### Piecewise

![capacity vs unormalised std piecewise](./plots/capacity_vs_unnormstd_piecewise.png)

## capacity vs unnormalized error

### Linear Regression

![capacity vs unnormalized error](./plots/capacity_vs_unnormerror.png)

- the correlation is small (<!-- $r^2 = 0.1294979748653919$ --> <img style="transform: translateY(0.1em); background: white;" src="https://render.githubusercontent.com/render/math?math=r%5E2%20%3D%200.1294979748653919">) so they are not quite correlated in general
- the south has higher correlation

![capacity vs unnormalized error by region](./plots/capacity_vs_unnormerror_by_region.png)

- the correlation coefficient for North Central is 0.7747808370036084
- the correlation coefficient for North is 0.0005175873342643005
- the correlation coefficient for West is 0.6142004020550921
- the correlation coefficient for Far West is 0.07272325563154991
- the correlation coefficient for South is 0.526982981239405
- the correlation coefficient for South Central is 0.9999375913105677

### LOWESS

！[capacity vs unnorm error lowess](./plots/capacity_vs_unnormerror_lowess.png)

![capacity vs unnormerror lowess by region](./plots/capacity_vs_unnormerror_lowess_byregion.png)

### Spline

![capacity vs unnormerror spline](./plots/capacity_vs_unnormerror_bspline.png)

## Outliers

let outliers to be any oberservation outside the range

<!-- $$
\left[Q_{1}-k\left(Q_{3}-Q_{1}\right), Q_{3}+k\left(Q_{3}-Q_{1}\right)\right]
$$ --> 

<div align="center"><img style="background: white;" src="https://render.githubusercontent.com/render/math?math=%5Cleft%5BQ_%7B1%7D-k%5Cleft(Q_%7B3%7D-Q_%7B1%7D%5Cright)%2C%20Q_%7B3%7D%2Bk%5Cleft(Q_%7B3%7D-Q_%7B1%7D%5Cright)%5Cright%5D"></div>

Where Q1,Q3 are the quantile, k is some non-negative constant. We use k = 2 across all the analysis

### [outliers of bias](./bias_outliers.txt)

- mostly negative bias

### [outliers of std of bias](./std_outliers.txt)

### [outliers of quantile difference](./quantile_outliers.txt)

## Things to Do
