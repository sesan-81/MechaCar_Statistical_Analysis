# MechaCar_Statistical_Analysis

MechaCar Statistical Analysis: R Programming

1.	Overview of Project

A few weeks after starting his new role, Jeremy is approached by upper management about a special project. AutosRUs’ newest prototype, the MechaCar, is suffering from production troubles that are blocking the manufacturing team’s progress. AutosRUs’ upper management has called on Jeremy and the data analytics team to review the production data for insights that may help the manufacturing team. 
In this challenge, you’ll help Jeremy and the data analytics team do the following:
• Perform multiple linear regression analysis to identify which variables in the dataset predict the mpg of MechaCar prototypes.

• Collect summary statistics on the pounds per square inch (PSI) of the suspension coils from the manufacturing lots.

• Run t-tests to determine if the manufacturing lots are statistically different from the mean population

• Design a statistical study to compare vehicle performance of the MechaCar vehicles against vehicles from other manufacturers. For each statistical analysis, you’ll write a summary interpretation of the findings.

2.	Resources

• Data Source: MechaCar_mpg.csv and Suspension_Coil.csv

• Data Tools: tidyverse, dplyr, ggplot2 and MechaCarChallenge.RScript.

• Software: RStudio and R

3.	Summary

A. Linear Regression to Predict MPG

Requirements:

The MechaCar_mpg.csv dataset contains mpg test results for 50 prototype MechaCars. The MechaCar prototypes were produced using multiple design specifications to identify ideal vehicle performance. Multiple metrics, such as vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance, were collected for each vehicle. Using your knowledge of R, you’ll design a linear model that predicts the mpg of MechaCar prototypes using several variables from the MechaCar_mpg.csv file. To Deliver.

• The MechaCar_mpg.csv file is imported and read into a dataframe.

• An RScript is written for a linear regression model to be performed on all six variables.

• An RScript is written to create the statistical summary of the linear regression model with the intended p-values.

• There is a summary that addresses all three questions

Results on Deliverable: Resulting Model

mpg = (6.267)vehicle_length + (0.0012)vehicle_weight + (0.0688)spoiler_angle + (3.546)ground_clearance + (-3.411)AWD + (-104.0)

 
![image](https://user-images.githubusercontent.com/104377031/184755714-ecf8fd56-025b-4650-9ff7-b62ec96ecb98.png)



Observations: In light of the above output we observe that:

1.	The vehicle length, and vehicle ground clearance are statistically likely to provide non-random amounts of variance to the model. That is to say, the vehicle length and vehicle ground clearance have a significant impact on miles per gallon on the MechaCar prototype. Conversely, the vehicle weight, spoiler angle, and All Wheel Drive (AWD) have p-Values that indicate a random amount of variance with the dataset.

2.	The p-Value for this model, p-Value: 5.35e-11, is much smaller than the assumed significance level of 0.05%. This indicates there is sufficient evidence to reject our null hypothesis, which further indcates that the slope of this linear model is not zero.

3.	This linear model has an r-squared value of 0.7149, which means that approximately 71% of all mpg predictions will be determined by this model. Relatively speaking, his multiple regression model does predict mpg of MechaCar prototypes effectively.

4.	If we remove the less impactful independent variables (vehicle weight, spoiler angle, and All Wheel Drive), the predictability does decrease, but not drastically: the r-squared value falls from 0.7149 to 0.674.

B. Summary Statistics on Suspension Coils

The Suspension Coil dataset provided for the MechaCar contains the results of testing the weight capacities of multiple suspension coils from multiple production lots to determine consistency. At first all manufacturing lots:

![image](https://user-images.githubusercontent.com/104377031/184755914-a93c4d3f-6c2a-41f1-adba-7259f1d1b214.png)

 
Diving a little deeper into each of the 3 lots:

![image](https://user-images.githubusercontent.com/104377031/184755993-23f5546b-c4c8-47f5-afea-39d99895a2e0.png)

 
With the understanding that the design specifications for the MechaCar suspension coils mandate that the variance of the suspension coils cannot exceed 100 pounds per square inch (PSI) . Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not? When looking at the entire population of the production lot, the variance of the coils is 62.29 PSI, which is well within the 100 PSI variance requirement. Similarly, but significantly more consistent, Lot 1 and Lot 2 are well within the 100 PSI variance requirement; with variances of 0.98 and 7.47 respectively. However, it is Lot 3 that is showing much larger variance in performance and consistency, with a variance of 170.29. It is Lot 3 that is disproportionately causing the variance at the full lot level. This very simple boxplot illustrates the differences between the lots:
 
![image](https://user-images.githubusercontent.com/104377031/184756077-97ed73d2-db92-4161-be34-73d280a32f83.png)


In the total summary, we can see the variance of all three lots in tandem does fall under the maximum variance of 100 PSI with a variance of 62 PSI.

In the lot summary, we see that the major contributor to the variance is lot 3 with a variance of 170 PSI with the other two lots having variances below 8 PSI.

In total, the manufacturing data meets the maximum variance in PSI requirement, but we can see that there are clearly big problems in lot 3 with a variance of 170 PSI. Lot 3 does not meet the maximum variance requirement.

C. t-Tests on Suspension Coils

Requirements: Using your knowledge of R, perform t-tests to determine if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 pounds per square inch. We performed a t-test for all the samples.

![image](https://user-images.githubusercontent.com/104377031/184756224-8c701608-fcec-4a67-8536-37791d8c269c.png)

 
From here we can see the true mean of the sample is 1498.78, which we also saw in the summary statistics above. With a p-Value of 0.06, which is higher than the common significance level of 0.05, there is NOT enough evidence to support rejecting the null hypothesis. That is to say, the mean of all three of these manufacturing lots is statistically similar to the presumed population mean of 1500.

Next looking at each individual lots:

1.	Lot 1 sample actually has the true sample mean of 1500, again as we saw in the summary statistics above. With a p-Value of 1, clearly we cannot reject (i.e. accept) the null hypothesis that there is no statistical difference between the observed sample mean and the presumed population mean (1500).

![image](https://user-images.githubusercontent.com/104377031/184756443-2373c84a-8a58-485f-9847-333ce49305d8.png)

 
2.	Lot 2 has essentially the same outcome with a sample mean of 1500.02, a p-Value of 0.61; the null hypothesis cannot be rejected, and the sample mean and the population mean of 1500 are statistically similar.
 
![image](https://user-images.githubusercontent.com/104377031/184756503-512b62dd-c567-4a8f-9226-921287129582.png)


3.	 Lot 3, not surprisingly is a different scenario. Here the sample mean is 1496.14 and the p-Value is 0.04, which is lower than the common significance level of 0.05. All indicating to reject the null hypothesis that this sample mean and the presumed population mean are not statistically different. Something went awry in Lot 3's production cycle. The process needs to be checked for system fails and the suspension coils from this lot need to be inspected to remove those not meeting quality criteria.

 
 ![image](https://user-images.githubusercontent.com/104377031/184756591-7c4b1583-dc71-4afa-8ea9-4f81b28fa8c9.png)


However, when we perform t-tests on the individual lots, we can see that although lots 1 and 2 are not statistically different from the population mean with p-values of 1 and 0.6 respectively, lot 3 does have a mean which is statistically different from the population mean.

D. Study Design: MechaCar vs Competition

The plan is to design the MechaCar vehicle to perform better than the general marketplace vehicles. To accomplish this goal I believe atttention is best served improving the fuel efficiency of the MechaCar. Data needs to be gathered for all MechaCar manufacturing designs, in addition to the current six variables from this analysis. Additional data could include weather conditions, i.e. wind sheer, rain, heat, etc. Varying distances of short trips and long trips are also needed to determine fuel efficiency, as well as fuel efficiency over time. The dataset must include general marketplace competitor's data for comparison.

What metric or metrics are you going to test?

The data will meet the following metrics:

•	All data is to be numerical

•	Data samples will be as large as possible

•	Data samples need to be randomly selected

•	Variance of data needs to be similar

What is the null hypothesis or alternative hypothesis?

HO: There is no statistical difference between the competition's mpg dataset and MechaCar's mpg dataset.

Ha: The true mean of MechaCar's mpg is greater than the mean of the competitor's mpg.

What statistical test would you use to test the hypothesis? And why?

I reccomend using the t-test to compare our dataset with the competitors. The t-test has already been used for this current analysis and provided the predictions needed to take the next steps for improvement.

What data is needed to run the statistical test?

The p-value would be set at 0.05. Data that results in a prediction of a p-value smaller than 0.05 would provide predictive evidence that the null hypothesis could be rejected and state that the Ha is true. Providing evidence that the Ha is true would also predict that the MechaCar provides consistently better fuel efficiency than the competitors mpg. There is always room for error and better fuel efficiency may not happen all of the time, but at least 95% of the time.


