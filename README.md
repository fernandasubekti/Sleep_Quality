# Improving Sleep Quality (EDA)

## Table of Contents
- [Project Overview](#project-overview)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis)
- [Conclusions](#conclusions)
- [Recommendations](#recommendations)

### Project Overview
The objective of the sleep quality project is to provide recommendations for improving sleep quality through the analysis of visualizations and the identification of patterns using exploratory data analysis techniques.

### Tools
Python - Exploratory Data Analysis (EDA)

### Source
DataCamp (DataCamp Competition): https://app.datacamp.com/learn/competitions/good-sleep-quality

### Exploratory Data Analysis (EDA) <a name="exploratory-data-analysis"></a>
During exploratory data analysis, I visualize the data to observe patterns and formulate hypotheses through processes involving data manipulation and visualization.

#### Data Manipulation
1. Substituting null values with the string "None".
2. Dividing the four unique values into two distinct categories.
3. Generating additional blood pressure-related features.

For example:
~~~python
bmi_groups = ["Normal", "Overweight"]

conditions = [
    sleep["BMI Category"].str.contains("Normal|Normal Weight"),
    sleep["BMI Category"].str.contains("Overweight|Obese")
]

sleep["BMI Category"] = np.select(conditions, bmi_groups)
~~~

#### Data Analysis
1. Calculating the correlation coefficient for each pair of variables.
2. Identifying occupations based on sleep duration and stress level.
3. Examining the correlation between blood pressure, weight category, and sleep disorder.
4. Determining the population count in the dataset for each blood pressure category.

#### Data Visualization
![heatmap](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/9e591056-e56b-4309-a881-bec4dca7b735)
![sleep quality bmi](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/4eef1eb6-dbda-419d-8b56-7a38eb96d8d6)
![blood pressure](https://github.com/fernandasubekti/Sleep_Quality/assets/116712020/94280a14-bd24-4b13-8baf-364b0c86d7a1)

### Conclusions
Based on the visualizations and observed patterns, there is a strong correlation between sleep quality, sleep duration, and stress levels. Individuals with longer sleep durations generally experience better sleep quality, and also individuals with lower stress levels are inclined to experience better sleep quality. Moreover, individuals with a normal weight are more likely to enjoy better sleep quality and are less prone to experiencing sleep disorders. Occupations such as sales representative, scientist, and salesperson may require special attention in managing these factors. In conclusion, these hypotheses suggest a potential relationship, and I recommend testing them through hypothesis testing for further validation.

### Limitation
These hypotheses imply a possible connection, and I advise conducting hypothesis testing to validate them more thoroughly.

### Recommendations
To enhance the quality of sleep, it's essential to pay attention to and regulate both sleep duration and stress levels. Attaining an ideal weight is also important in minimizing the risk of sleep disorders and fostering better sleep quality.
