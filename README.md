# TASK2_TitanicEDA_Analysis_B.Y.T.E
# Titanic Exploratory Data Analysis (EDA) - Task 2 B.Y.T.E ArithmaticTech

This repository contains an in-depth exploratory data analysis of the Titanic passenger dataset, focusing on demographic features, socioeconomic statuses, and their direct impact on survival rates. 

The project is structured into four primary phases:
1. Data Exploration
2. Data Cleaning & Feature Engineering
3. Correlation Analysis
4. Data Visualization & Key Insights

---

## Part 1: Data Loading & Exploration

The analysis utilizes the built-in Titanic dataset accessible via the Seaborn library (`sns.load_dataset('titanic')`). Initial exploration involved assessing the dataset's shape, data types, index structure, and statistical summaries to understand the baseline distribution of passenger demographics and travel details.

---

## Part 2: Data Cleaning & Feature Engineering

To ensure robust analysis, the dataset was cleaned and enriched with new features:
1. **Missing Value Handling:** 
   * Visualized null value percentages across all columns.
   * Dropped the `deck` column entirely, as it contained over 50% missing values.
   * Dropped remaining rows with null values (primarily missing `age` data).
2. **Duplicate Removal:** Identified and removed 38 duplicated rows to ensure data integrity.
3. **Feature Engineering:**
   * **Family Size:** Created a `family_size` feature by combining the `sibsp` (siblings/spouses) and `parch` (parents/children) columns, plus 1 for the passenger.
   * **Is Alone:** Derived a binary `is_alone` indicator mapping passengers who traveled with a `family_size` of exactly 1.
   * **Fare Category:** Segmented the continuous `fare` column into three categorical bins (`Small Range`, `Medium Range`, `High Range`) based on customized bin edges.

---

## Part 3: Correlation Analysis

* **Visualization:** Heatmap of the correlation matrix for all numerical columns.
* **Key Findings:** 
  * Strong positive correlations exist between `sibsp`/`parch` and the engineered `family_size` column.
  * A strong negative correlation exists between `is_alone` and `family_size`, indicating that higher degrees of loneliness correspond to smaller family sizes.
  * Intermediate negative correlations were observed between passenger class (`pclass`) and `fare` (indicating higher classes paid more), as well as between family variables (`parch`/`sibsp`) and the `is_alone` status.

---

## Part 4: Data Visualization & Key Insights

### Question 1: What is the highest class based on the percentage of survival?
* **Visualization:** Pie chart displaying the percentage of survival across the three passenger classes.
* **Key Insight:** First-class passengers achieved significantly higher survival rates than other classes. This suggests that first-class passengers had advanced means of survival, including priority access to lifeboats and closer physical proximity to the boat deck, whereas second and third classes suffered from lower priority and farther locations.

### Question 2: What are the most common ages aboard the Titanic?
* **Visualization:** Histogram (with 30 bins) illustrating the frequency distribution of passenger ages.
* **Key Insight:** The most common age group on the ship fell approximately between 20 and 35 years old, indicating that the majority of the passengers were young adults and teenagers.

### Question 3: Does traveling alone mean you were less likely to survive?
* **Visualization:** Bar chart comparing the average survival rate between passengers traveling alone versus those with family.
* **Key Insight:** Traveling alone correlated with a lower survival rate. Passengers who were not alone exhibited higher survival averages, indicating that traveling with a group provided beneficial qualities that increased survival chances, such as mutual assistance and collaboration.

### Question 4: Which embarkation town generated the greatest average profit?
* **Visualization:** Horizontal bar plot ranking the average ticket fare per embarkation town.
* **Key Insight:** The town that generated the highest average profit was **Cherbourg** at a rate of **$68.70**. This is primarily driven by a higher percentage of wealthy, first-class passengers boarding from this specific port.

---

## Overall Summary

This exploratory data analysis of the Titanic dataset reveals that socioeconomic status was the primary determinant of survival. First-class passengers achieved significantly higher survival rates due to their proximity to safety and prioritized evacuation access. Additionally, embarkation ports heavily dictated passenger demographics, with Cherbourg exhibiting the highest average ticket fares driven by a concentration of wealthy first-class travelers.
