# SWYNEX Final Data Analytics Project: Titanic Survival Analysis

## 1. Problem Statement
Which passenger characteristics were most associated with survival on the Titanic, and what do they show about who had the best chance of surviving? This case study takes a raw dataset through cleaning, analysis and a dashboard to answer that question.

## 2. Dataset Information
- **Source:** Titanic - Machine Learning from Disaster (train.csv), Kaggle: https://www.kaggle.com/competitions/titanic
- **Size:** 891 passengers, 12 columns
- **Key columns:** Survived, Pclass, Sex, Age, SibSp, Parch, Fare, Embarked
- **Tools:** Python (pandas, matplotlib, seaborn) in Google Colab, Power BI Desktop

## 3. Data Cleaning Process
| Issue | Details | Action |
|---|---|---|
| Missing Age | 177 values | Filled with the median |
| Missing Cabin | 687 values (about 77%) | Dropped the column |
| Missing Embarked | 2 values | Filled with the most common port (S) |
| Duplicates | 0 found | None removed |
| Data types | Age decimal; Pclass and Survived numeric categories | Age to integer; Pclass and Survived to category |
| Text consistency | Sex and Embarked already consistent | Trimmed spaces and standardised case |

**Result:** 891 rows, 11 columns, 0 missing values.

## 4. Exploratory Analysis
I created FamilySize and AgeGroup columns and calculated survival rates across groups. Seven charts are in the `charts/` folder.

| Group | Survival rate |
|---|---|
| Overall | 38.4% |
| Female / Male | 74.2% / 18.9% |
| 1st / 2nd / 3rd class | 63.0% / 47.3% / 24.2% |
| Cherbourg / Queenstown / Southampton | 55.4% / 39.0% / 33.9% |
| Child / Young Adult / Senior | 57.4% / 35.3% / 22.7% |
| Family size 1 / 2 / 3 / 4 | 30.4% / 55.3% / 57.8% / 72.4% |

Median fare by class: 60.29 (1st), 14.25 (2nd), 8.05 (3rd).

## 5. Dashboard
An interactive Power BI dashboard with 4 KPI cards (Total Passengers, Survival Rate, Average Fare, Average Age), 6 charts and 4 filters (Sex, Class, Port, Age Group).



## 6. Key Business Insights
1. **Sex was the strongest factor.** Women survived at about four times the rate of men (74.2% vs 18.9%).
2. **Class mattered.** Survival fell from 63.0% in 1st class to 24.2% in 3rd, and fares rose sharply with class, so wealth was linked to survival.
3. **Children had priority.** The Child group survived at 57.4%, well above adults and seniors.
4. **Family size had a sweet spot.** Groups of 2 to 4 survived at 55.3% to 72.4%, versus 30.4% for people travelling alone. Very large families did poorly.
5. **Port differences.** Cherbourg passengers survived more (55.4%), likely linked to more 1st class passengers boarding there (an inference, not proven here).
6. **Data limitation.** The spike at age 28 in the Age chart comes from filling missing ages with the median, so age results should be read with care.

## 7. Conclusion and Recommendations
Survival depended heavily on sex, class and age, which suggests that access and priority rules shaped outcomes. For a similar real-world case, such as emergency planning, evacuation procedures should be designed so that access does not depend on ticket class, and groups and families should be kept together. Future work could add a predictive model, and better handling of missing ages.

## 8. Repository Structure
- `data/`: original, cleaned and dashboard datasets
- `notebooks/`: cleaning (Task 1) and exploratory analysis (Task 2)
- `charts/`: 7 EDA charts
- `dashboard/`: Power BI file and screenshots

## Related Tasks
Task 1: Data Cleaning, Task 2: Exploratory Data Analysis, Task 3: Interactive Dashboard (this project combines all three).
