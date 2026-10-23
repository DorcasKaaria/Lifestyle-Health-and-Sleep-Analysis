# Sleep, Health and Lifestyle Analysis

## Project Overview

This project analyzes a dataset containing **374 unique records** to explore the relationships between sleep quality, stress levels, physical activity, BMI, blood pressure, and sleep disorders.

The analysis was conducted using Excel, and Power BI to answer key questions about how age, gender, and occupation relate to health and lifestyle indicators.

## Key Questions

The analysis aimed to answer the following questions:

- Which age group has the highest stress levels, physical activity, and sleep quality?
- Does blood pressure vary by BMI category?
- Which occupations are associated with high stress levels, lower sleep quality, and high BMI?
- Do occupation, age, and gender influence physical activity levels?
- Is there a relationship between BMI and physical activity levels?
- How do sleep disorders relate to sleep duration and overall sleep quality?

## Data Collection and Cleaning

The original dataset was provided in Excel format and contained 374 unique records.

The following cleaning and preparation steps were completed:

- Checked for duplicate records. No duplicates were found.
- Filled all 219 blank cells in the `Sleep Disorder` column with `None`.
- Standardized `Normal Weight` values to `Normal` for consistency.
- Created an `Age Group` calculated column using the Excel `IFS` function.
- Saved the cleaned dataset as a CSV file using Python and loaded it into Power BI for analysis and visualization.
- Examined the distributions of numerical columns. The columns showed normal distributions with no outliers, except for `Heart Rate`, which was right-skewed. The outliers were retained because heart rates can exceed the column's upper limit of 78 depending on an individual's health condition.

## Data Analysis

Power BI measures were developed to summarize the dataset and answer the analysis questions.

| Measure | Description |
|---|---|
| Avg Age | Average age of the population |
| Sleep Quality | Average sleep quality score |
| Sleep Duration | Average number of sleeping hours |
| Physical Activity | Average physical activity per individual |
| Daily Steps | Average daily steps per individual |
| Disorder Prevalence | Percentage of the population with sleep disorders |
| Total Obs | Total number of observations in the dataset |

## Key Findings and Recommendations

### 1. Younger People Report Higher Stress Levels and Lower Sleep Quality

The population below 30 had the highest stress levels and lowest sleep quality. In contrast, those above 50 had the lowest stress levels and highest sleep quality. The 41–50 age group recorded the highest physical activity levels.

**Recommendation:** Further investigate the factors contributing to stress and lower sleep quality among people below 30. Examine the lifestyle patterns of people above 50 to understand the differences and identify practices that may support the well-being of younger people.

### 2. High Blood Pressure Was Observed Among Overweight Individuals

Out of 374 people, 65 had a recorded blood pressure of 140/95, and all were classified as overweight. The analysis also indicated that most individuals with diastolic blood pressure above 130 fell within the overweight or obese BMI categories.

**Recommendation:** Investigate whether other underlying factors contribute to elevated blood pressure among these individuals. Consider appropriate nutrition support and health assessments to help manage BMI and reduce potential cardiovascular risks.

### 3. Stress and BMI Patterns Varied Across Occupations

Sales representatives recorded the highest stress levels, while engineers recorded the lowest. Nurses had the highest number of overweight individuals, with 66 out of 73 nurses classified as overweight.

However, the sales representative finding should be interpreted cautiously because the dataset contained only two sales representatives.

**Recommendation:** Investigate factors that may contribute to the high proportion of overweight nurses. Collect more data on sales representatives before drawing broader conclusions about stress levels in that occupation.

### 4. Physical Activity Levels Varied by BMI Category

The overweight category recorded the highest average physical activity at 61.24 minutes, followed by the normal BMI category at 57.85 minutes and the obese category at 55 minutes.

**Recommendation:** Encourage consistent physical activity and appropriate nutrition practices across BMI categories. Individuals seeking to manage their weight should seek guidance from qualified nutritionists or fitness professionals for proper nutrition management and fitness planning.

## Tools and Technologies

- **Microsoft Excel:** Initial data inspection, standardization, and age group creation.
- **Power BI:** Data analysis, measures, and visualization.

## Conclusion

The analysis identified differences in stress levels, sleep quality, physical activity, blood pressure, and BMI across age groups and occupations.

The findings highlight areas for further investigation, particularly the well-being of younger people, elevated blood pressure among overweight individuals, and BMI patterns among nurses. The results should be interpreted in the context of the dataset, especially where occupational sample sizes are small.

## Comparision using Manus AI

I build a simple web page using Manus AI to compare the analysis.
The developed page takes the clean data from the local computer then builds a detailed dashboard from the analysis.
Here is the link to the web page: https://vivawell-lzkdaxlu.manus.space/ 
Use the clean dataset of the data folder to test the interface.