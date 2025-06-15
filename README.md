# Mental Health Risk and Help-Seeking Behavior in the Workplace

Conducted exploratory data analysis (EDA), statistical analysis (correlations and group difference) and prediction analysis (regression) on Mental Health Risk and Help-Seeking Behavior in the Workplace.

## Resources

    • Data Source: Kaggle

    • Google colab

    • Tools: Python (pandas, numpy, matplotlib, seaborn, scipy, and statsmodels.api, )

# Introduction

Mental health issues including depression and anxiety are growing concerns that affect people across all ages, countries and industries. In the workplace, these issues are often under-reported and under-treated, despite their increasing prevalence. Social, life-style and environmental factors such as work environment, sleep hours, social support, and physical activity may contribute to an individual’s mental health and their likelihood of seeking treatment. 

Through this analysis, I aim to leverage data science techniques to identify factors that could significantly impact an employee’s mental health and well being; to understand their behavioral patterns; and to build predictive models that would inform mental health interventions, policy recommendations, and wellness strategies in the workplace.

# Analysis Objectives

    1. To clean and pre-process the data by handling missing values, and encoding categorical variables before analysis.

    2. To thoroughly examine and visualise all the features within the dataset using Exploratory Data Analysis through descriptive univariate and bivariate analysis. 

    3. To carry out statistical inference by correlating and comparing differences between variables using pearson’s correlation test and ANOVA. 

    4. To predict the likelihood of seeking mental health treatment and investigate the social and lifestyle determinants of mental health using regression models.

# About Dataset

The dataset used in this project was sourced from Kaggle. According to the authors, it provides a realistic, synthetic simulation of global mental health survey responses from 10,000 anonymized individuals; and it was created to reflect actual patterns seen in workplace mental health data while ensuring full anonymity and privacy. 


# Columns in the Dataset

    1. age
    2. gender
    3. employment_status
    4. work_environment
    5. mental_health_history
    6. seeks_treatment
    7. stress_level
    8. sleep_hours
    9. physical_activity_days
    10. depression_score
    11. anxiety_score
    12. social_support_score
    13. productivity_score
    14. mental_health_risk


# Exploratory Data Analysis Insights

## Data Quality and Structure

    • The dataset contains 10,000 rows and 14 variables.
      
    • No missing values were detected, and all data types were correctly assigned.
      
    • The data is well-structured and ready for analysis, with no inconsistencies noted.

# Summary Statistics & Distributional Properties

    • The mean and median values of the continuous variables were approximately equal, indicating symmetry and, in some cases, normality.
      
    • No apparent outliers were observed when examining the range, interquartile spread, and standard deviations.
      
    • Most continuous variables showed high variability (Coefficient of Variation > 50%), while a few demonstrated moderate variability — pointing to heterogeneity in participants' behavioral and psychological profiles.

    ![boxplot_for_multiple_variables](https://github.com/user-attachments/assets/38aa9a7b-0d0c-4b12-aa3f-f2ffdf545bee)

## Demographic and Categorical Variables Overview

The dataset presents a balanced gender distribution, with nearly equal proportions of male and female participants. A majority of the respondents were employed, suggesting that the sample primarily represents individuals actively engaged in the workforce.

With regard to work environment, most participants reported working on-site, followed by those working remotely, while hybrid workers formed the smallest group. For mental health history, a larger proportion of individuals indicated no prior mental health issues.

When asked whether they currently seek mental health treatment, the majority responded "no", highlighting a relatively low rate of active help-seeking behavior. In terms of mental health risk levels, most participants were categorized as medium risk, followed by high, and then low risk individuals.

![work_environment_bar_chart](https://github.com/user-attachments/assets/0d123042-0456-4289-bc2d-5ade2a1f3309)
![seeks_treatment_bar_chart](https://github.com/user-attachments/assets/e9f0c39b-d73f-46dc-b6bc-3a6f9d308793)
![mental_health_risk_bar_chart](https://github.com/user-attachments/assets/e033b73d-1fd1-471d-b056-fd9f67a2cd4f)
![mental_health_history_bar_chart](https://github.com/user-attachments/assets/a859d416-7845-4a65-aa81-806bb1c668ef)
![gender_bar_chart](https://github.com/user-attachments/assets/195dbde0-4e52-4b11-b035-cdc8cdc70f1a)
![employment_status_bar_chart](https://github.com/user-attachments/assets/c0ad68e6-3ff5-4e33-a9ea-2fcdaa539a8c)

## Histogram Analysis of Continuous Variables

    • Sleep Hours was the only variable that exhibited a normal distribution, with a distinct peak around 6.75 hours, suggesting that the average respondent achieves an optimal sleep duration.
      
    • Productivity Score showed a left-skewed (negatively skewed) distribution, indicating that most participants reported higher productivity, with relatively fewer reporting lower scores.
      
    • All other continuous variables (age, stress level, physical activity days, depression score, anxiety score, and social support score) demonstrated a platykurtic distribution — characterized by flat tops and low kurtosis — suggesting a more even spread of values across the range; less clustering around the mean; and no dominant central tendency.

![histograms](https://github.com/user-attachments/assets/31273904-e3c8-4141-b143-7698b849447b)

## Contingency Table Findings (Bivariate Categorical Analysis)

A consistent distribution pattern was observed across employment and work environment categories in relation to mental health outcomes:

    • Across all work environments (hybrid, on-site, and remote), about 60% of individuals reported not seeking treatment.
      
    • Likewise, approximately 59% of individuals across work environments were categorized as having medium mental health risk.
      
    • A similar pattern emerged for employment status, where about 60% of each group (self-employed, employed, students, and unemployed) reported not seeking treatment.
      
    • Additionally, around 60% of individuals in each employment group fell within the medium mental health risk category.

**Interpretation:** 

These findings suggest a lack of variability in treatment-seeking behavior and mental health risk across different employment and work settings, pointing to the possibility that work-related factors may not be the primary drivers of mental health outcomes in this population.

## Scatter Plot Insight

A scatter plot of depression score vs. productivity score revealed a strong negative linear relationship — as depression scores increase, productivity tends to decrease.


# Insights from Statistical and Regression Analyses 

## Logistic Regression Analysis: Predictors of Treatment-Seeking Behavior

A binary logistic regression was conducted to examine whether key psychosocial and lifestyle variables—including stress level, sleep hours, physical activity days, depression score, anxiety score, social support score, and productivity score—could predict the likelihood of employees seeking mental health treatment. The model results revealed that none of the predictors were statistically significant. This indicates that employees’ treatment-seeking behavior could not be reliably explained by these variables within the current dataset.

**Interpretation:**

This lack of significance suggests the influence of external or unmeasured variables, such as: stigma, access to mental health services, organizational culture or support, awareness and education, cultural or personal beliefs.

These factors, while not captured quantitatively, may play a more substantial role in shaping treatment-seeking behavior. Therefore, future models should incorporate contextual, qualitative, or structural variables to better understand what drives or hinders help-seeking among employees.

## Correlation Between Depression and Productivity

The analysis uncovered a strong negative correlation between depression scores and productivity scores, suggesting that as depressive symptoms increase, productivity declines.

**Interpretation:**

This relationship highlights the adverse impact of poor mental health on workplace performance:

    • Depression can impair cognitive functions such as focus, decision-making, and motivation.
      
    • Elevated depressive symptoms may lead to reduced engagement and output in professional settings.
      
Implications:
    • While correlation does not imply causation, the strength of the association warrants further investigation using regression techniques to determine predictive power.
      
    • Organizations should prioritize early identification and support for depression, not only for employee well-being but also to maintain optimal productivity.
      
![scatter_plot_matrix](https://github.com/user-attachments/assets/e4236a8d-a44e-4afb-a680-334ab9f9675f)
![pearson_correlation_heatmap](https://github.com/user-attachments/assets/275ec8ec-dae5-4f8b-9894-f8d76cd4bfef)

## Linear Regression: Depression as a Predictor of Productivity

A simple linear regression confirmed that depression significantly explains variance in productivity levels.

**Interpretation:**

Higher depression levels are associated with lower productivity, likely due to fatigue, diminished motivation, and cognitive inefficiencies. This affirms the need for workplace mental health initiatives that actively monitor and support employees with depressive symptoms.

**Recommendations:**

Implementing programs like mental health days, counseling services, and resilience training may not only enhance employee health but also yield tangible performance gains for the organization.

## Chi-Square Test: Work Environment and Employment Status

Chi-square analyses tested for associations between: Work environment and employment status vs mental health risk, and  treatment-seeking behavior each. Results showed no statistically significant association. This implies that the likelihood of experiencing mental health issues or seeking help does not differ significantly across work environments (on-site, remote, hybrid) or employment statuses (employed, unemployed, student, self-employed).

**Interpretation:**

These findings suggest that mental health outcomes are not contingent upon employment type or setting in this dataset. Rather, psychological strain may stem from non-occupational factors or from shared stressors across different employment categories.

## ANOVA and Tukey HSD Post-Hoc Test: Anxiety by Work Environment

A post-hoc Tukey HSD test revealed that remote workers reported significantly higher anxiety scores than those working on-site.

**Implications:**

This may reflect the unique psychological strain faced by remote employees due to: Social isolation, blurred work-life boundaries, reduced face-to-face support systems, inconsistent routines

**Recommendations:**

Employers should tailor interventions for remote employees, including: enhanced virtual communication, routine-building tools, access to digital mental health resources, opportunities for virtual socialization. Further analysis could explore mediating variables such as social support, home environment, and workload, to uncover underlying mechanisms influencing remote workers’ mental health.
    
![tukeys_postHoc_anxietyScores](https://github.com/user-attachments/assets/a050c358-372d-4461-912c-77ea751e064a)

