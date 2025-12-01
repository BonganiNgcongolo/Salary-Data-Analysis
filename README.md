# Salary-Data-Analysis
Analysing the salary distribution for different departments to determine the business model used by the company to pay monthly salaries.

## Project Introduction
This project focuses on determining the business model that is used in this company to  **fairly** allocate monthly salaries to employees. There are no specific factors that the company has specified as their criteria in allocating the salaries, so we will carefully clean, analyse, extract information, visualize trends and predict salaries.

## Project Overview
This project analyzes an employee salary dataset containing information about 50 employees across various departments. The analysis explores relationships between employee characteristics (experience, education, age, gender, department) and their monthly salaries.

### Dataset Description
The dataset contains 50 employee records with the following features:

1. EmployeeID: Unique identifier for each employee
2. Name: Employee name
3. Department: Department assignment (Marketing, Operations, IT, Finance, HR)
4. Experience_Years: Years of work experience (1-19 years)
5. Education_Level: Educational qualification (High School, Bachelor, Master, PhD)
6. Age: Employee age (22-57 years)
7. Gender: Male or Female
8. City: Employee's city location
9. Monthly_Salary: Monthly salary (R28,420 - R149,123)

# Import, Explration and Cleaning.
<img width="1285" height="562" alt="image" src="https://github.com/user-attachments/assets/c1bf2b90-8f1d-45df-b18b-2d50a89228d0" />

The data was imported using pandas. The head of the datset was printed just to have a look on the columns, rows and values to see if they make sense.

<img width="584" height="684" alt="image" src="https://github.com/user-attachments/assets/3deed7f2-4f8e-4d6e-b783-ca48e8cbdc18" />

This was just to get a detailed description of the data, datatypes, empty/null entries. There were no null entries and all the datatypes were appropriate to their respective columns

<img width="661" height="527" alt="image" src="https://github.com/user-attachments/assets/ea09ce52-ad7a-4ff7-bde6-1832dfb7a947" />

This was to get a brief summary statistics of the data, to better understand all the numerical columns of this dataset. It helped me to verify the range of data points in each column and identify that there were no oultliers nor missing values. I further checked for duplicates and there were none.

# Key Findings From Data Analysis.
Total monthly salary allocation by department:

1. Marketing: R1,253,601 (30.5%) - 13 employees
2. Operations: R842,399 (20.5%) - 10 employees
3. IT: R765,205 (18.6%) - 10 employees
4. Finance: R672,619 (16.4%) - 10 employees
5. HR: R580,616 (14.1%) - 7 employees

Marketing department receives the highest budget allocation and has the most employees, suggesting it's a priority area for the organization.
<img width="705" height="585" alt="image" src="https://github.com/user-attachments/assets/74551214-7f74-46e5-8533-eba4c0b932d8" />

The Pie Chat helps in better visualising the monthly salary distribution accross deparments. This could be useful for the stakeholders in making budgets for the company, tracking the company spending and salary negotiations with new employees.

The company has more Female employees (27) than Male employees (23) and the Female employess have a higher total experience than Males thus the total monthly salary is more for females than it is for males.

<img width="827" height="125" alt="image" src="https://github.com/user-attachments/assets/31c1405b-7d42-4dc2-8bce-4e0ae3acfd05" />

This suggests potential gender pay equity in the organization and the importance of experience in monthly salary negotiations.

These are the top 5 highest earners
<img width="646" height="213" alt="image" src="https://github.com/user-attachments/assets/0c0d8e42-57b6-4cf1-b7b7-7be365c7d25c" />

1. Highest earners are spread across different departments
2. Education level doesn't always correlate with highest pay
3. Experience varies significantly among top earners (8-15 years)

These are the bottom 5 least earners
<img width="680" height="213" alt="image" src="https://github.com/user-attachments/assets/ba201275-0a78-4acd-ba22-393e2d1a1f35" />

The same trend as the highest earners is still seen for the lowest earners, which is:
1. Lowest earners are spread across different departments
2. Education level doesn't always correlate with highest pay
3. Experience varies significantly among low earners (5-18 years)

The intepretation here is that the company here has not business model in place for the salaries and this is because,
a person with PhD, 5 years of experience cannot earn the same amount with a person with Barchelors degree and 6 years of experiance.
<img width="602" height="83" alt="image" src="https://github.com/user-attachments/assets/bd09a81f-ac82-413c-931c-31dea2f7fd56" />

There is more evidence that the company has no business model for salaries in place.
<img width="584" height="105" alt="image" src="https://github.com/user-attachments/assets/0f21acd5-4e26-49d6-a4ed-aac65b931c4b" /> 

This is an unfair pay gap and should be corrected.

# Salary prediction
Create a machine learning model that will predict salaries. The first step is to remove the categorical columns so that only numerical data remains, since multiple linear regression requires numerical inputs, then import the LabelEncoder from sklearn to convert the categorical inputs into numerical values that the computer can interpret and use to make predictions and drop the unwanted columns.
<img width="1285" height="791" alt="image" src="https://github.com/user-attachments/assets/2cfd0071-184b-416a-854f-60cd9aeaec17" />

Model Metrics:

Mean Absolute Error (MAE): 33,222.97
R² Score: -0.187

**Interpretation:**

Negative R² Score: Indicates the model performs worse than a simple mean prediction
High MAE: Average prediction error of ~33,223 units
Conclusion: Linear relationship between features is weak; salaries are influenced by factors not captured in the dataset

**Model Coefficients**

Intercept: 84,572.80
Experience_Years: +412.03 per year
Education_Level: -1,498.25 (inverse relationship - needs further investigation)
Department: +2,947.53
Age: -45.30 per year
Gender: -12,388.35

**Key Findings:**

Experience has modest positive impact on salary
Unexpected negative coefficient for education suggests multicollinearity or complex interactions
Department has significant impact on compensation
Model suggests limitations in predicting salaries using only these features

<img width="907" height="628" alt="image" src="https://github.com/user-attachments/assets/98b73368-6df0-474a-a68c-fda83372081b" />

 Actual vs Predicted Salary (Scatter Plot)
Demonstrates poor model fit with significant scatter around the ideal prediction line, confirming the low R² score.


Weak linear correlations between most features and salary, some clustering patterns by department and Non-linear relationships that simple linear regression cannot capture
<img width="689" height="621" alt="image" src="https://github.com/user-attachments/assets/686ac636-5a99-4998-94a3-d382319f0ea3" />

# Conclusion
This analysis reveals that the company currently lacks a structured and transparent salary allocation model. Employee compensation does not consistently align with key factors such as education level, years of experience, age, or job role. Instead, salary distribution appears to be influenced largely by departmental size rather than employee merit or qualifications. This has resulted in noticeable inconsistencies, including cases where employees with higher education or more experience earn similar or even lower salaries than their less qualified counterparts.

The machine learning model further supports this observation: the weak predictive performance and negative R² score indicate that the existing salary patterns do not follow a logical or measurable structure. The poor correlation between features and salary suggests that compensation decisions are made without a defined or data-driven framework.

Based on these findings, it is recommended that the company adopt a formalized salary allocation business model. A hybrid approach combining job-grade levels, experience-based adjustments, education-level premiums, and market benchmarking would provide a fair, consistent, and defensible salary structure. Implementing such a model would help eliminate current disparities, promote fairness, support employee satisfaction, and enable the company to make informed financial and HR decisions.











