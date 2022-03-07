# MechaCar_Statistical_Analysis

## Linear Regression to Predict MPG

The MechaCar_mpg.csv dataset contains mpg test results for 50 prototype MechaCars. The MechaCar prototypes were produced using multiple design specifications to identify ideal vehicle performance. Multiple metrics, such as vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance, were collected for each vehicle.

Linear Regression to Predict MPG

![image](https://user-images.githubusercontent.com/93686963/155866292-19680734-97a2-45a0-a400-ba6de0f674bc.png)

Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?

According to the above outcome vehicle length and vehicle ground clearance are likely to provide non-random amount of variance to the mpg, hence they have significant impact on mpg of the given datast.

Is the slope of the linear model considered to be zero? Why or why not?

The linera model is not zero as the p-value of the above is 5.35e-11 which is lower than the significance level of 0.05% and there are sufficient evidence to reject null hypothesis.

Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?

This model does predict effectively about the mpg as the r-squared 0.7149


## Summary Statistics on Suspension Coils

The MechaCar Suspension_Coil.csv dataset contains the results from multiple production lots. In this dataset, the weight capacities of multiple suspension coils were tested to determine if the manufacturing process is consistent across production lots


![image](https://user-images.githubusercontent.com/93686963/155866531-54c77099-76b9-412c-8ed7-d86d05b3752f.png)

![image](https://user-images.githubusercontent.com/93686963/155866542-f7986bbf-a6ac-4601-814b-2283d9fecebd.png)

In the total summary variance of the suspension coils are not exceeding the 100PSI as the variance of the coils are 62.29, however if we take individual lots, Lot 3 shows a larger variance of 170.2 which is greater than the 100 PSI.

## T-Tests on Suspension Coils



> #use t.test() to determine if the PSI across ALL lots is statistically different from the pop. mean of 1,500 PSI.
> t.test(suspension_coil_df$PSI, mu=1500)

	One Sample t-test

data:  suspension_coil_df$PSI
t = -1.8931, df = 149, p-value = 0.06028
alternative hypothesis: true mean is not equal to 1500
95 percent confidence interval:
 1497.507 1500.053
sample estimates:
mean of x 
  1498.78 

> 
> 
> # Use t.test() function and its subset() to determine if the PSI for each manufacturing lot is statistically different from the population mean of 1,500 pounds per square inch.
> t.test(subset(suspension_coil_df, Manufacturing_Lot=="Lot1")$PSI,mu=1500)

	One Sample t-test

data:  subset(suspension_coil_df, Manufacturing_Lot == "Lot1")$PSI
t = 0, df = 49, p-value = 1
alternative hypothesis: true mean is not equal to 1500
95 percent confidence interval:
 1499.719 1500.281
sample estimates:
mean of x 
     1500 

> t.test(subset(suspension_coil_df, Manufacturing_Lot=="Lot2")$PSI,mu=1500)

	One Sample t-test

data:  subset(suspension_coil_df, Manufacturing_Lot == "Lot2")$PSI
t = 0.51745, df = 49, p-value = 0.6072
alternative hypothesis: true mean is not equal to 1500
95 percent confidence interval:
 1499.423 1500.977
sample estimates:
mean of x 
   1500.2 

> t.test(subset(suspension_coil_df, Manufacturing_Lot=="Lot3")$PSI,mu=1500)

	One Sample t-test

data:  subset(suspension_coil_df, Manufacturing_Lot == "Lot3")$PSI
t = -2.0916, df = 49, p-value = 0.04168
alternative hypothesis: true mean is not equal to 1500
95 percent confidence interval:
 1492.431 1499.849
sample estimates:
mean of x 
  1496.14 

From t-test results from all manufacturing lots mean of the sampl is 1498.78 and the p value is 0.06 which is gretaer than the significance level of 0.05. Hence we dont have enough evidence to reject null hypothesis. alll manufacturing lots mean statistically similar to population mean of 1500
From the lot 1 sample, sample mean is 1500 and p value is 1, hence we can not reject nulll hypothesis. so no statistical difference between the sample mean and the population mean
From the lot 2 sample, sample mean is 1500.02 and the p value is 0.61 , hence we can not reject the null hypothesis. So no statis tical difference between the sample and the popultion mean.
From the lot 2 sample, sampe mean 1496.14 and the p value is 0.04 which is lower than the significance level and we can reject the null hypothesis.

## Study Design: MechaCar vs Competition
What metric or metrics are you going to test?
 cost, city or highway mpg fuel efficiency, horse power, maintainance and safety rating.
 
What is the null hypothesis or alternative hypothesis?
Null Hypothesis (Ho): On defined metrics, there is NO statistically significant difference between MechaCar and the competitors.
Alternative Hypothesis (Ha): On defined metrics, there is statistically significant difference between MechaCar and the competitors.

What statistical test would you use to test the hypothesis? And why?
 Multiple linear regression can be used. Instead of using a single independent variable to account for all variability observed in the dependent variable, a multiple linear regression uses multiple independent variables to account for parts of the total variance observed in the dependent variable.
 
What data is needed to run the statistical test?
 comparable data from the competitors have to be run with the mechacar data.
