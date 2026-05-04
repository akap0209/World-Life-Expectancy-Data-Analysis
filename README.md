README
🌍 World Life Expectancy SQL Project
📌 Project Overview
This project performs an Exploratory Data Analysis (EDA) on the World Life Expectancy dataset using SQL to uncover global health trends and the factors that influence life expectancy across countries. The analysis examines long‑term changes in life expectancy, compares health outcomes across economic and development groups, and evaluates how variables such as GDP, BMI, and adult mortality relate to overall population health.

🎯 Objective
The purpose of this project is to answer data‑driven questions about global life expectancy using SQL. The analysis focuses on:

Identifying long‑term life expectancy trends
Comparing developed vs. developing countries
Evaluating the impact of GDP, BMI, and mortality indicators
Performing time‑series calculations using window functions
Highlighting global health disparities and patterns
These insights support public health research, policy discussions, and data‑driven decision‑making.

📊 Data Used
The dataset includes global health and demographic information for countries between 2000 and 2015.

Fact‑Style Fields
Life Expectancy
BMI
GDP
Dimension‑Style Fields
Country
Year
Status (Developed / Developing)
Population Indicators (varies by dataset version)
Source
Publicly available World Life Expectancy dataset (commonly found on Kaggle), compiled from global health organizations and statistical agencies.

🛠 SQL Techniques Used
Aggregations (MIN, MAX, AVG, SUM)
Filtering and HAVING clauses
CASE statements
Window functions (PARTITION BY + ORDER BY)
Time‑series analysis
Data validation and cleaning logic
Grouping and ordering for trend analysis
⭐ Key Insights
Life expectancy increased globally between 2000 and 2015, with most countries showing steady improvement. Several developing nations experienced the largest gains, highlighting significant progress in public health outcomes.

High‑GDP countries consistently outperformed low‑GDP countries in life expectancy. Countries with GDP ≥ 1500 had substantially higher average life expectancy, reinforcing the strong link between economic stability and population health.

Developed countries averaged significantly higher life expectancy than developing countries. The gap between the two groups remained consistent, emphasizing disparities in healthcare access, infrastructure, and living conditions.

BMI levels showed a meaningful relationship with life expectancy. Countries with extremely low or high BMI tended to have lower life expectancy, suggesting that both malnutrition and obesity correlate with poorer health outcomes.

Global life expectancy trended upward year‑over‑year, based on average annual calculations. This indicates broad improvements in healthcare, disease prevention, and living standards worldwide.

Adult mortality analysis revealed clear time‑series patterns, with cumulative mortality decreasing over time in most countries analyzed. The window function analysis highlighted how mortality trends evolve across years.

Countries with the highest GDP also tended to have the highest life expectancy, while countries with the lowest GDP ranked at the bottom of both metrics, underscoring persistent global inequality.

🧩 Sample Queries
Life Expectancy Change Over 15 Years
SELECT Country, 
MIN(`Life expectancy`),
MAX(`Life expectancy`),
ROUND(MAX(`Life expectancy`) - MIN(`Life expectancy`), 1) AS Life_Increase_15_Years
FROM world_life_expectancy
GROUP BY Country
HAVING MIN(`Life expectancy`) <> 0
AND MAX(`Life expectancy`) <> 0
ORDER BY Life_Increase_15_Years;
