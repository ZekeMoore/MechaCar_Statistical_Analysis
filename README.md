# MechaCar Statistical Analysis

## Overview of the Analysis

AutosRUs’ newest prototype, the MechaCar, is suffering from production troubles. By running regression analyses and t-tests, I will review production data for AutoRU's newest prototype, the MechaCar, and provide insights that may help the manufacturing team. Additionally, I will design a statistical study to compare the vehicle performance of the MechaCar vehicles against vehicles from other manufacturers.

## Deliverable 1 - Linear Regression to Predict MPG

![Deliverable_One_LM.PNG](https://github.com/ZekeMoore/MechaCar_Statistical_Analysis/blob/main/Resources/Linear%20Regression%20model.png)

The linear regression model above estimates that: 

```mpg = (6.267)vehicle_length + (0.0012)vehicle_weight + (0.0688)spoiler_angle + (3.546)ground_clearance + (-3.411)AWD - 104.0```

* Using the formula above, vehicle length, and ground clearance are statistically likely to provide non-random amounts of variance to the model or are most likely to affect the miles per gallon performance of the MechaCar's AutosRUs prototype.  
* Given the model's ```p-value of 5.35e-11```, which is lower than the 0.05 assumed statistical significance, there is strong evidence **against the null hypothesis** (slope = 0). Therefore, we can accept the alternative hypothesis that the **slope is not 0**.
* The model's ```r-squared value of .7149``` means that about 71% of the variance in mpg predictions can be explained by this model, while 29% cannot. In other words, the variables of vehicle length, spoiler angle, ground clearance, and AWD have a strong positive association with mpg. Therefore, this model effectively predicts mpg of MechaCar prototypes.

## Deliverable 2 - Summary Statistics on Suspension Coils

The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Looking at the PSI data for all three manufacturing lots, provided in the PSI summary chart below, we see that the ```variance of the suspension coils is 62.69 pounds per square inch```. Therefore, it does not exceed the design specification of 100 pounds per square inch.

<img src="https://github.com/ZekeMoore/MechaCar_Statistical_Analysis/blob/main/Resources/Total%20Summary.png" width="600" >

When we break the manufacturing data by the three lots, shown below, we see that on the one hand Lot 1 and 2 have ```variances of 0.98 and 7.47``` that are well below the design specification of 100 pounds per square inch. On the other hand, Lot 3, has a much larger ```variance of 170.29``` that is well above the design specification. The variance of Lot 3 is causing the PSI variance of the total lot population to increase significantly.

<img src="https://github.com/ZekeMoore/MechaCar_Statistical_Analysis/blob/main/Resources/Lot%20Summary.png" width="600" >

The box plot below demonstrates how much larger the variance of Lot 3 is compared to Lot 1 and 2.

<img src="https://github.com/ZekeMoore/MechaCar_Statistical_Analysis/blob/main/Resources/box%20plot.png" width="600" >

## Deliverable 3 - T-Tests on Suspension Coils

Next, we needed to conduct a t-test to determine if the PSI across all manufacturing lots is statistically different from the population mean of 1,500 pounds per square inch and then t-tests for each manufacturing lot.

The first t-test was used to determine if the PSI across all manufacturing lots is statistically different from the population mean of 1,500 pounds per square inch. The result of the t-test showed that there was a ```sample mean of 1,498.78``` and a ```p-value of 0.06```. Because our p-value is higher than the assumed statistical significance of 0.05, we fail to reject the null hypothesis. This means that the PSI across all manufacturing lots is **statistically similar** to the population mean of 1,500 pounds per square inch.

<img src="https://github.com/ZekeMoore/MechaCar_Statistical_Analysis/blob/main/Resources/T_Test%201.png" width="600" >

The next three t-tests were used to determine if the PSI across each manufacturing lot is statistically different from the population mean of 1,500 pounds per square inch.

### Lot 1 T-Test

<img src="https://github.com/ZekeMoore/MechaCar_Statistical_Analysis/blob/main/Resources/T_Test%202.png" width="600" >

**Lot 1** results show that the ```sample mean is 1,500``` and the p-value is a perfect 1. There is no statistical difference from the population mean of 1,500 pounds per square inch. In this case, we fail to reject the null hypothesis.

### Lot 2 T-Test

<img src="https://github.com/ZekeMoore/MechaCar_Statistical_Analysis/blob/main/Resources/T_Test%203.png" width="600" >

**Lot 2** results show ```sample mean is 1,500.2``` and the ```p-value is 0.61```. Because the p-value is much higher than the assumed statistical significance of 0.05, we fail to reject the null hypothesis. There is no statistical difference from the population mean of 1,500 pounds per square inch.

### Lot 3 T-Test

<img src="https://github.com/ZekeMoore/MechaCar_Statistical_Analysis/blob/main/Resources/T_Test%204.png" width="600" >

**Lot 3** results show ```sample mean is 1,496.14``` and the ```p-value is 0.04```. Because the p-value is lower than the assumed statistical significance of 0.05, we reject the null hypothesis and accept the alternative hypothesis that the true mean is not equal to 1,500. This means that this sample shows that there is a statistical difference from the population mean of 1,500 pounds per square inch.

## Deliverable 4 - Study Design: MechaCar vs Competition

Many consumers, especially families and those who have previously been in accidents, value safety when it comes to picking their car. To test MechaCar's safety rating against its competition, we need to create a null and alternative hypothesis.

**H0 (Null Hypothesis):** MechaCar's vehicle safety ratings are no different from its competitors 

**Ha (Alternative Hypothesis):** MechaCar's vehicle safety ratings are different from its competitors 

To test these, we'd need to collect safety ratings on MechaCar's models as well as its competitors from the Insurance Institute for Highway Safety, which determines saftey ratings. As the non-profit explains, their scores are determined by four factors: measurements from dummies, survival space, airbags, and seat belt effectiveness. Using that data, we could t-test the population of vehicles and each carmaker. This will help us determine if MechaCar's vehicles' safety rating scores are statistically different from its competitors as a whole and then statistically different from each competitor.
