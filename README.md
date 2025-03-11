![image](https://github.com/user-attachments/assets/403fafce-f9ce-4b11-8398-e6582462a214)



# Abuse & Neglect-Related Child Fatalities in Texas: A Python Data Analysis  

##  Overview  

Every year, April is recognized as National Child Abuse Prevention Month in the United States. It serves as a reminder of the devastating reality that hundreds of children lose their lives each year due to abuse and neglect—lives that could have been saved. Behind these numbers are real children who should have had the chance to grow up safe, loved, and protected.  

The loss of a child is always heartbreaking, but when it happens due to abuse or neglect, it is even more painful because it was preventable. Addressing this issue requires more than just reacting to crises—it demands proactive solutions, stronger community support, and increased awareness to protect children before harm occurs.  

As we approach April, I want to draw attention to the impact of abuse- and neglect-related child fatalities. In this project, I aim to provide a data-driven overview of child fatalities due to abuse and neglect in Texas between 2015 and 2024. By analyzing these numbers, I hope to raise awareness and contribute to discussions on improving child safety and prevention strategies.  

## Data Source  

The data for this analysis comes from the Texas Open Data Portal, It provides information on child fatalities in Texas from 2015 to 2024 that are linked to abuse and neglect. The dataset includes key details such as fiscal year, county, region, program involvement, demographics, and fatality counts.  

The original dataset can be accessed **[here](https://data.texas.gov/dataset/OCS-1-1-Abuse-Neglect-Related-Texas-Child-Fataliti/92um-beyd/about_data)**.  

## The Questions

Below are the questions I want to answer in my project:

1. What are the skills most in demand for the top 3 most popular data roles?
2. How are in-demand skills trending for Data Analysts?
3. How well do jobs and skills pay for Data Analysts?
4. What are the optimal skills for data analysts to learn? (High Demand AND High Paying) 

## Tools I Used


For this analysis of abuse- and neglect-related child fatalities, several key tools and techniques were used to process.

- **Python:** The backbone of my analysis, allowing me to analyze the data and find critical insights.I also used the following Python libraries:
    - **Pandas Library:** This was used to analyze the data. 
    - **Matplotlib Library:** I visualized the data.
    - **Seaborn Library:** Helped me create more advanced visuals. 
- **Jupyter Notebooks:** The tool I used to run my Python scripts which let me easily include my notes and analysis.
- **Visual Studio Code:** My go-to for executing my Python scripts.
- **Git & GitHub:** Essential for version control and sharing my Python code and analysis, ensuring collaboration and project tracking.

# Data Import, Exploration, and Cleaning  


I start by importing necessary libraries and loading the dataset, followed by initial data cleaning tasks to ensure data quality.

View my notebook with detailed steps here: **[1.EDA_and_cleaning.ipynb](https://github.com/kubradizlek/abuse_neglected_child_fatalities/blob/main/1.EDA_and_cleaning.ipynb)**  


```python
# Importing Libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Loading Data
df=pd.read_csv('/Users/kubra/Desktop/Pyhton/python projects /abuse_neglected_child_fatalities /OCS_1.1___Abuse_Neglect_Related_Texas_Child_Fatalities_FY2015-FY2024.csv')


```

## The Analysis  

Each Jupyter notebook in this project explores different aspects of abuse- and neglect-related child fatalities in Texas. Here’s how each question was approached:

### 1.How have abuse- and neglect-related child fatalities changed over time?  

To analyze trends in child fatalities over time, I aggregated the number of fatalities per year and visualized the yearly changes. This helps to identify whether fatalities are increasing, decreasing, or showing any patterns that may indicate broader systemic issues.  

View my notebook with detailed steps here: **[2_Time_Series_Analysis.ipynb](https://github.com/kubradizlek/abuse_neglected_child_fatalities/blob/main/2_Time_Series_Analysis.ipynb)**  

### Visualizing the Data  

```python
# Plot Time Series Trend
fig, ax = plt.subplots(figsize=(10, 5))
sns.lineplot(data=fatalities_per_year, x='Year', y='Total Fatalities', marker='o', linewidth=2)
plt.xlabel('Year')
plt.ylabel('Total Fatalities')
plt.title('Trends in Child Fatalities Due to Abuse and Neglect (Texas, FY2015-FY2024)')
plt.grid(True)
plt.show()

![Time Series Trend](https://github.com/user-attachments/assets/018a0586-5ee3-43f1-b0bc-4b6518400b75)



