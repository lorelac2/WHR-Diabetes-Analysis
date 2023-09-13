# WHR-Diabetes-Analysis

## Objectives and Data
This project aimed to assess the correlation of different risk factors for diabetes using statistical models. The dataset used addresses risk factors for diabetes, obesity, and cardiovascular disease in study participants living in two counties in Virginia. These risk factos include cholesterol and glucose levels, systolic and diastolic pressures, as well as demographics such as participant age, height, weight, and hip size. This data was collected from 403 male and female participants from Virginia's Buckingham and Louisa counties. Waist-to-hip ratio (WHR) is associated with increase risk of type 2 diabetes and coronary heart disease. The purpose of this analysis is to investigate the exploratory and predictory correlation between WHR and diabetes in a localised community.

## Procedure
### Correlation Analysis
> - WHR was set independently to WHR > 0.85 (females) and WHR > 0.90 (males) to indicate obesity. Additionally, the scale of the glycosylated hemoglobin variable was limited between 5 and 8 to better indicate the transition from pre-diabetes to diabetes. These variablescan be visualized through scatter plots and examined via linear regression to determine either a positive or negative statistical relationship. Furthermore disparities in health outcomes can be examined based on gender.
> - <img width="566" alt="Screen Shot 2023-09-12 at 5 30 05 PM" src="https://github.com/lorelac2/WHR-Diabetes-Analysis/assets/115598249/66d8d627-a943-4161-9498-ff152cd29a74">
> - For the scatter plot, the blue trend line and the grey confidence bands show a sharp incline from a WHR from about 0.76 to about 0.87, and a slower incline from about 0.87 to about 1.4. This incline indicates that a high WHR is correlated with higher levels of glycosylated hemoglobin, which determines a diagnosis of pre-diabetes and diabetes. Furthermore, WHR can be used to predict pre-diabetes and diabetes, as they are directly associated.


## Analysis
> - The Central Limit Theorem states that as sample size (n) increases, the sample mean more closely approaches the true population mean (µ) and the spread decreases and more closely reflects a normal and symmetric distribution.
> - To demonstrate the Central Limit Theorem, different sampling distributions were calculated at n = 5, n = 50, and n = 300, utilizing 50 random sampling trials for each distribution (via the sample_n() function in R). As sample size n increased, the distribution grew more approximately normal with smaller variance in spread. This is evident in the increasing accuracy of sample means in comparison to the true population statistic, µ. µ is equal to 0.88, as described in previous sections.
> - Specifically, the sample_n() function was ran (for n = 5, n = 50, and n = 300) 51 times each, then the data was recorded in a CSV file titled “histogram_data.csv”. Below is an example of our process for 5 trials of sample_n() for n = 300.
> - <img width="649" alt="Screen Shot 2023-09-12 at 5 34 55 PM" src="https://github.com/lorelac2/WHR-Diabetes-Analysis/assets/115598249/18781b84-f8ff-4865-ada9-7992f7052080">

> - Observing the histogram and boxplot that was made with the data, the glycosylated hemoglobin and WHR data for men and women were not normally distributed, contained evident outliers, and presented similar variance and spread. The observations of non-normal distribution, outliers, and similar variance and spread were assessed using a visual methods to compare the overlap and measures of central tendency (median and outliers) between the male and female populations. Thus, a non-parametric Wilcoxon Rank Sum test was most appropriate for further statistical testing as it does not rely on a normal distribution. This test can be applied to compare whether the median differences in between two genders is truly significant or due to random chance.
> - <img width="646" alt="Screen Shot 2023-09-12 at 5 36 31 PM" src="https://github.com/lorelac2/WHR-Diabetes-Analysis/assets/115598249/81ca3cd7-8d22-405e-8dac-f7f28b3ea802">

## Findings
> - FEMALES
> - Confidence Interval (CI): The 95% confidence interval for females is -0.62005655 to -0.09003463. This means that if this same procedure was repeated 100 times, it would be expected that 95 of the CIs would contain the true difference. The range of difference does not go from negative to positive values (they stay negative). This indicates that at the 5% level (95% confidence), there is evidence to reject the null hypothesis of no difference.
> - p-value: There is a 0.679% chance that we obtain results as extreme as the observed results of the statistical test under the assumption that the null hypothesis is correct. Since the calculated p-value is below the 0.05 significance level, we have evidence to reject/fail to reject the null hypothesis.
> - MALES
> - CI: The 95% confidence interval for males is -0.63001576 0.04998143. This means that if this same procedure was repeated 100 times, it would be expected that 95 of the CIs would contain the true difference. The range of difference does go from negative to positive values, and includes the null value 0. This indicates that at the 5% level (95% confidence), we fail to reject the null hypothesis of no difference.
> - p-value: There is a 8.92% chance that we obtain results as extreme as the observed results of the statistical test under the assumption that the null hypothesis is correct. Since the calculated p-value is above the 0.05 significance level, we fail to reject the null hypothesis.

## Software Used
> - R
> - Excel
> - Jupyter Notebook

## Funcitons and Tests Used
> - Wilcoxon Rank Sum Test
> - t-test
> - ggplot2
