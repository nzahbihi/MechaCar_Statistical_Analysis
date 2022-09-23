# MechaCar_Statistical_Analysis
## Overview
We conducted statistical analysis into production data for AutosRUs' newest prototype, the MechaCar. The purpose of this analysis is to gain insight that may help the manufacturing team with the production troubles they have been experiencing.

## Resources
* Software: RStudio 2022.07.1.

## Linear Regression to Predict MPG
We performed a multiple linear regression on the data pertaining to Mecha Cars, specifically in regards to the MPG.

![LinearRegressionSummary](https://user-images.githubusercontent.com/106129195/191658314-d492b9d5-9736-4240-842e-1ea9cd10b8e0.png)

To determine which variables/coefficients provided a non-random amount of variance to the MPG values in the dataset, we look to the "Pr(>|t|)" values for each. According to our results, half of the variables are statistically unlikely to provide random amounts of variance. We see that the Intercept, vehicle_length, and ground_clearance are near zero. However, vehicle_weight, spoiler_angle, and AWD have larger values, and are statistically likely to provide random amounts of variance.

Reviewing the summary above, we can see that slope of this model is not zero. This is determined by reviewing the p-value, which we have determined to be 5.35e-11. As it is much smaller than the assumed significance value of 0.05, we can state that there is sufficient evidence to reject our null hypothesis.

Another conclusion we can draw from this summary is that this model is somewhat effective in predicting MPG of MechaCar prototypes. This is determined by reviewing the value of the Multiple R-squared value, in which our value is 0.71. This means that approximately 71% of the variability of our dependent variables is explained with this model.

## Summary Statistics on Suspension Coils

The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch (PSI). To investigate whether the current manufacturing data meets this specification for all lots, we initially review the data as a whole.

![Total_Summary](https://user-images.githubusercontent.com/106129195/191660665-b7e64877-8b5a-49a8-9521-5e4983f74b99.png)

The table displayed above gives us the mean, median, variance, and standard deviation of the manufacturing lots and PSIs. We can see that the variance value is 62.30, which is less than the maximum of 100 PSI. We then investigated all three manufacturing lots to determine whether each individual lot meets this specification.

![Lot_Summary](https://user-images.githubusercontent.com/106129195/191660678-0b58b42c-890d-4599-85de-68cb510be32a.png)

As shown above, Lot 3 exceeds this specification. Lots 1 and 2 are under the maximum amount, but Lot 3 will need reviewing to get the variance under 100.

## T-Tests on Suspension Coils

We conducted one-sample t-tests on the Suspension Coil data to investigate whether the PSI across all manufacturing lots is statistically different from the population mean of 1,500 PSI.

To begin the query, we first conducted the one-sample t-test for all manufacturing lots.

![t_test_ALL](https://user-images.githubusercontent.com/106129195/192068489-107344e9-1418-458d-bd49-0409410ed563.png)

Our p-value is 0.06028. With our significance value at 0.05, we fail to reject our null hypothesis. Therefore, there is no signficant difference between the PSI all of the manufacturing lots and the population mean of 1,500 PSI.

Next, we conduct one-sample t-tests into each manufacturing lot.

![t_test_First](https://user-images.githubusercontent.com/106129195/192068464-e9321f15-2ce1-4a85-bdd0-b53b6c8a60a0.png)

Our p-value for Lot 1 is 1, which is to be expected. As we can see in the chart above showing the mean, median, variance and standard deviation of each lot, the mean for Lot 1 is 1,500. There is no difference at all, therefore, we also fail to reject our null hypothesis.

![t_test_Second](https://user-images.githubusercontent.com/106129195/192068497-5d8dd26f-e0fb-4084-972e-26fd0680bf48.png)

Our p-value for Lot 2 is 0.6072. With our significance value at 0.05, we fail to reject the null hypothesis as well. There is no significant difference between the PSI of Lot 2 and the population mean of 1,500 PSI.

![t_test_Third](https://user-images.githubusercontent.com/106129195/192068504-6f72a496-b388-43ea-a794-b4ad7a2ec973.png)

Our p-value for Lot 3 is 0.04168. With our significance value at 0.05, we reject our null hypothesis. There is a significant difference between the PSI of Lot 3 and the population mean of 1,500.
