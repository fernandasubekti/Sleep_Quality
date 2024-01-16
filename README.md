# Woo-hoo! Time to catch some Zs and get that awesome sleep!

For the best view, you can visit: https://fernandasubekti.me/woo-hoo-time-to-catch-some-zs-and-get-that-awesome-sleep

## Table of Contents
- [Introduction](#introduction)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis)
- [Conclusion](#conclusion)
- [Limitation](#limitation)

### Introduction
Do you ever think __sleep is just a waste of time and unimportant?__ Yep, I've never felt like that before. But, when I took the course about learning how to learn at Coursera, the instructor, __Barbara Oakley, said that sleep makes our brain more clean and healthy__. It is like washing our brains from toxins. Sleep also makes our brain strengthen what we learn. She also explained if we sleep less for a long time, it can cause headaches, heart disease, diabetes, and young death. Now, how can we get a good sleep quality? __In this project, I aim to create a strategy to get better sleep quality__. The project will use correlation, visualization, and statistical tests to gain more confidence about the topic.

I got the dataset from Kaggle. It's worth noting that this dataset does not represent all cases worldwide. But it's interesting to see the pattern about how to get better sleep work. I will use the exploratory data analysis (EDA) technique. Firstly, I inspected the data and saw that in the first three rows, I got the data like this:

![Screenshot (15)](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/b6869cab-5445-45fd-937a-096b1c19a7fe)

### Exploratory Data Analysis (EDA) <a name="exploratory-data-analysis"></a>
During exploratory data analysis, I visualize the data to observe patterns and formulate hypotheses through processes involving data manipulation and visualization.

#### Data Manipulation
After inspecting the dataset, I got some missing values in the sleep disorder column. I will fill the missing value with "None, " meaning the person corresponding to the missing value will not have a sleep disorder. I do that because the sleep disorder column is essential to see the pattern and statistical test later. After that, I manipulated the occupation column by merging the salesperson and sales representative categories into a salesperson. I also merge software engineer, scientist, and manager categories into Other. I also simplified the BMI category only into normal weight and overweight. Afterwards, I generate the new features, blood pressure, into systolic and diastolic categories, including normal, elevated, and hypertension. Data manipulation aims to simplify, visualize and do statistics tests later.

#### Correlation and Visualization
From the analysis, I got a percentage of 51% for males and 49% for females, with a total of 374 data points. The age distribution for a sample is in the range of 27 to 59 years old. The profession of the sample data involved nurses, doctors, engineers, lawyers, teachers, accountants, salespersons, and others. After that, I seek out correlation coefficients for the number data type using a correlation matrix.

![Screenshot (19)](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/814edb47-4463-4934-a84c-c14736ceb901)

The correlation matrix shows that sleep quality strongly correlates with sleep duration, stress level, and heart rate. The relationship between sleep quality and sleep duration is positive. The longer we sleep, the better the sleep quality. Meanwhile, the ties between sleep quality and stress level are negative relationships, which means getting less stress and improving sleep quality. It also occurs in the relationship between sleep quality and heart rate. The calling lowers the heart rate, and the sleep quality gets better. Note that the correlation does not explain cause and effect but demonstrates linearity. Afterwards, I will explore sleep quality by gender and weight categories.

![Screenshot (20)](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/fffe6580-976e-41cc-8f93-25e833186953)

We can see that the sleep quality of females is better than that of males. But is it statistically significant or just a coincidence? So, to tackle this hypothesis, I will use a t-test for the hypothesis. Firstly, we create a null hypothesis and an alternative hypothesis.

$H_0$ : The mean quality of sleep __is the same__ for females and males

$H_A$: The mean quality of sleep __is greater__ for females compared to males.

After that, I will give 5% significance to test the hypothesis. From the analysis, I got a t-score of about 5.85 and a degree of freedom of 372, which caused the p-value for 6.23e-10. We will use the right tail because the alternative hypothesis is "greater than." Because the p-value is lower than the significance, we must reject H0. Therefore, statistically, __the mean sleep quality is greater for females than males__. After that, I will find out about sleep quality by weight category.

![Screenshot (21)](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/8b8c8be6-28b0-4b9d-a034-f6b490a2d006)

As before, is it statistically significant or just a coincidence that people of normal weight have greater sleep quality than overweight people? Let's find out. Firstly, we create null and alternative hypotheses.

$H_0$ : The mean quality of sleep __is the same__ for normal weight and overweight

$H_A$: The mean quality of sleep __is greater__ for normal weight compared to overweight

After that, I will give 5% significance to test the hypothesis. From the analysis, I got a t-score of about 6.23 and a degree of freedom of 372, which caused the p-value for 6.23e-10. We will use the right tail because the alternative hypothesis is "greater than." Because the p-value is lower than the significance, we must reject H0. Therefore, statistically, __the mean sleep quality is greater for those with normal weights than for those who are overweight__. Following that, I will discover the sleep quality by sleep disorder category.

![Screenshot (22)](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/7674272b-08ea-4610-b301-fa1fe6d4af92)

We can see that people who have no sleep disorder tend to have higher sleep quality than people who have sleep disorders such as insomnia and sleep apnea. I can't use a statistical t-test like before because there are three categories in the sleep disorder category. Instead of passing that analysis, I will continue to find the dependencies between BMI or weight category with a sleep disorder.

![Screenshot (23)](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/94adea6e-dcb2-4756-a317-5504f6f01302)

From the visualization, people with no sleep disorder and have normal weight tend to get a higher sleep quality rather than those who are overweight and have sleep disorders. But are weight category and sleep disorder dependent on each other? Let's do a chi-square statistical test to analyze the dependencies between the two categories.

We can perform the chi-square test for the relationship between weight categories and sleep disorders since the conditions have been met, with each category having at least five observations. Let's create the null and alternative hypotheses.

$H_0$ : BMI category are __independent__ of sleep disorder

$H_A$: BMI category are __not independent__ of sleep disorder

After creating this hypothesis, I used 5% significance to test the hypothesis. After that, we did statistical tests using the penguin library, and we got them with a value of 9.42e-53. This p-value is less than the significance level. So, we have to reject the null hypothesis H0. Thus, __the BMI category is not independent of sleep disorder__. In other words, the BMI category and sleep disorder interplay. For example, people who have sleep disorders are affected by their weight. Furthermore, I would like to visualize the relationship between occupation and sleep disorders.

![Screenshot (24)](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/c7d79928-d28a-417b-9eb8-2de9308335c4)

Look at that visualization. The distribution of occupations with sleep disorder categories is scattered irregularly. I want to conduct a statistical test to examine dependencies. Unfortunately, the conditions have not been met, as there should be a minimum of 5 elements for each corresponding category. Therefore, I am unable to perform the dependency test. But let's analyze that visualization. In the health sector, almost every doctor has no sleep disorder. Meanwhile, most nurse has sleep apnea. People who have insomnia are more like salespersons and teachers. Then, engineers, accountants, lawyers, and others a lot of them do not have sleep disorders. And then, I will find the blood pressure category to sleep quality level.

![Screenshot (26)](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/8669a884-e536-4bb4-b65d-db2372d3c2af)

From the visualization, we can see that people with normal blood pressure have more excellent sleep quality than people with high blood pressure, although the difference is only a few. Note that from the correlation matrix, blood pressure level has a strong enough positive relationship with physical activity level. It is more interesting to see the blood pressure category and sleep disorder dependencies. If it happens, it would be considered a strategy for gaining excellent sleep quality. Again, unfortunately, I can't test those things because the requirements have not been met. But it's good to explore the pattern of other things.

![Screenshot (27)](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/307c1425-37c9-4ea2-bfd5-092c0295a719)

![Screenshot (28)](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/81ebe6e0-d35d-4572-b8f5-24c1c3d45b6e)

People who have no sleep disorder tend to have lower or normal blood pressure than those who have a sleep disorder. This also applies to the weight category; people who have normal weight tend to have lower or normal blood pressure than those who are overweight. After doing some time to see the correlation, visualization, and statistical test, we will create a conclusion and recommendation to improve the sleep quality.

### Conclusion
The dataset is not representative of the case in the world, but it is interesting to see how sleep quality works. Firstly, the percentage of participants consists of 51% males and 49% females, with 374 observations. The participants range from 27 to 59 years old, and their profession involved nurses, doctors, engineers, lawyers, teachers, accountants, salespersons, and others. 

From the analysis, the correlation matrix shows that sleep quality has only a strong relationship to sleep duration, stress level, and heart rate. The relationship between sleep quality and sleep duration is positive. Meanwhile, the relationship between sleep quality, stress level, and heart rate is negative.

Statistically shows that the mean sleep quality is greater for females than males. Also, the mean sleep quality is greater for those with normal weights than those who are overweight. People who have no sleep disorder tend to have greater sleep quality rather than people who have a sleep disorder. Further, the BMI or weight category and sleep disorder interplay. Then, people with normal blood pressure tend to have more great sleep quality than those with high blood pressure. Further, people with no sleep disorder and normal weight have normal blood pressure.

Therefore, we can make strategies to avoid sleep disorders by controlling our weight. We can exercise and diet to get an ideal weight. After that, we could manage our time to manage our tasks, which can affect getting a good sleep duration, and we must control our stress level. We can join the community, hang out, exercise, or do what makes us happier. Also, the males have to be more aware of their sleep quality. If we follow all these suggestions, we may get great sleep, have a better life, and change the world.

### Limitation
My project is only limited to visualization and statistical tests. The reader could expand my project by doing machine learning analysis to analyze sleep quality.
