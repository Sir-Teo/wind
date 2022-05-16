# Wind Farms Conclusions

This document attempts to summarize all the observations from the exploratory data analysis.

## Notations

$$
\begin{array}{lr}
J & \text { Number of assets } \\
d=1, \ldots, D ; h & \text { Days, Hours } \\
C_i & \text{Capacity for Asset i}\\
\mathbf{g}_{d} = (g_{d,h}) & \text{Actual Production MWh}\\
\mathbf{f}_{d} = (f_{d,h}) & \text{forcasted Production MWh}\\
i & \text{assets indices}\\
\alpha_{d, h} & \text { actuals fraction } \in[0,1] \\
\beta_{d, h} & \text { forecast fraction } \in[0,1]\\
\gamma_{d,h} & \text{bias fraction} \\
\tau_{d,h} & \text{kendall's tau}\\
r^2 & \text{corelation coefficient}\\
\sigma & standard deviation
\end{array}
$$

- Days are indexed by $d = 1,2,...,365$, and hours are indexed by $h = 1,2,...,24$

- $\mathbf{g}_{d,h},$ $\mathbf{f}_{d,h}, \alpha_{d, h}, \beta_{d, h}$ are vectors of Dimension $J$ Where 

$$
\alpha_{d,h}\in [0,1] = \frac{\mathbf{g}_{d,h}}{C} \quad \text{and} \quad \beta_{d,h} \in [0,1] = \frac{\mathbf{f}_{d,h}}{C}
$$

- The bias fraction is then
$$
\gamma_{d,h} = \beta_{d,h} - \alpha_{d,h}
$$

## Bias

### Bias at hourly interval

For a given asset, let 
$$
\beta_{h} = \frac{1}{365}\sum_{d = 1}^{365} \beta_{d,h}
$$

and $\beta_h$ is the prediction bias for a given hour of the day. For each $h \in [1,24]$, we plot out $\beta_h$ in a violin plot and a box plot.

![Violin plot of bias at each hour](./plots/violin_and_box_bias_1hr.png)

It was found that, overall in the morning the prediction bias tend to be positive, with negatively skewed distribution. In the afternoon and evening the prediction bias tend to be negative, with less skewed distribuiton. With closer analysis, the negative skewness in the morning is brought by **Canadian Breaks Wind** and **Desert Sky repower**. 

### Bias at 24 Hours interval

We are also interested in the geographic distribution of the prediction bias.

For a given asset, let 
$$
\beta = \frac{1}{365\times 24}\sum_{d = 1}^{365} \sum_{h = 1}^{24} \beta_{d,h}
$$
and $\beta$ is also a vector of length $J$. Plotting $\beta$ on the map of Texas,

![Bias at 24 Hours interval](./plots/bias_24hr_with_area.png)

As observed from the scatter plot, the bias, across all hours and all year, is relatively higher for Southern and central wind farms and is lower for Northern and Western windfarms. 

## Stardard Deviation of Bias

###### 

We are also interested in the standard deviation of the Bias. Let
$$
\sigma_{h}^{\beta}=\sqrt{\frac{\sum_{d = 1}^{365}\left(\beta_{d,h}-\bar{\beta_h}\right)^{2}}{365}}
$$
where $\bar{\beta_h} = \frac{1}{365}\sum_{d = 1}^{365} \beta_{d,h}$ is the mean of the bias at a given hour across all year. For each $h \in [1,24]$, we plot out $\sigma_h^{\beta}$ in a violin plot and a box plot.

![Violin plot of std of bias at each hour](./plots/violin_and_box_std_of_bias_1hr.png)

It was found that, from the above violin/box plot, 

