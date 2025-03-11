

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

View my notebook with detailed steps here: [1.Eda_and_cleaning.ipynb](https://github.com/kubradizlek/abuse_neglected_child_fatalities/blob/main/1.Eda_and_cleaning.ipynb)


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
```

### Results 

![image](https://github.com/user-attachments/assets/116a5554-b51d-4283-ad54-b365ade1cd10)

### Key Insights  

- A significant spike in fatalities occurred in 2020, which may be linked to the **COVID-19 lockdowns**. During this period, **families faced increased stress, economic hardships, and isolation**, which could have led to a rise in abuse and neglect cases. With schools and other social structures closed, many children had **reduced access to mandatory reporters like teachers and social workers**, delaying intervention.  

- The overall trend shows fluctuations, with some years experiencing sharp increases. This could be influenced by **policy changes, economic instability, or improvements in reporting systems**. Understanding these variations is essential for **developing targeted intervention strategies**.  

- **Recent years (2022-2024) show a decline in fatalities**, which may indicate **better prevention measures, increased awareness, or changes in reporting standards**. However, further analysis is needed to determine whether this decrease reflects actual improvements in child safety or shifts in how cases are recorded.  
























## 2.How do child fatalities due to abuse and neglect vary across different regions in Texas?


To examine how child fatalities due to abuse and neglect vary across different regions in Texas, I grouped the data by region and calculated the total number of fatalities for each. This approach provides a clearer view of which regions have higher reported fatalities, helping to identify potential patterns or disparities. Visualizing the data with a bar chart allows for easy comparison across regions, highlighting areas with the most significant concerns.

View my notebook with detailed steps here: [3_Regional_Analysis.ipynb](https://github.com/kubradizlek/abuse_neglected_child_fatalities/blob/main/3_Regional_Analysis.ipynb)

### Visualizing the Data  

```python
# Set figure size
plt.figure(figsize=(12, 6))

# Create a bar chart
sns.barplot(
    data=fatalities_by_region,
    x="Total Fatalities",
    y="Region",
    palette="Blues_r"
)

# Add labels and title
plt.xlabel("Total Fatalities")
plt.ylabel("Region")
plt.title("Child Fatalities Due to Abuse and Neglect by Region (Texas, FY2015-FY2024)")
plt.grid(axis="x", linestyle="--", alpha=0.7)

# Save the figure
plt.savefig("child_fatalities_by_region.png", dpi=300, bbox_inches='tight')

# Show the plot
plt.show()
```

### Results 

![image](https://github.com/user-attachments/assets/aeb01c22-bab4-4585-b324-eb047224f554)


### Key Insights  


- Arlington and Houston reported the highest number of child fatalities due to abuse and neglect, with over 500 and 450 cases respectively between 2015 and 2024. This may be influenced by their large populations and urban stress factors.  

- Austin and San Antonio also reported significant fatalities, with over 300 and 250 cases respectively. These numbers highlight the need for further investigation into regional factors, such as socioeconomic conditions and availability of child welfare services.  

- El Paso had the lowest reported fatalities, with fewer than 50 cases. While this could indicate strong intervention programs, differences in reporting accuracy across regions should also be considered.
- 






























### 3.Which age groups are most affected by abuse-related fatalities?


To understand which age groups are most affected by abuse-related fatalities, the dataset was grouped by age categories, and the total number of fatalities was calculated for each group. This helps identify the most vulnerable age groups and compare fatality rates across different age categories.

View my notebook with detailed steps here: [4_Age_Group_Analysis.ipynb](https://github.com/kubradizlek/abuse_neglected_child_fatalities/blob/main/4.Age_Group_Analysis.ipynb)



### Visualizing the Data  

```python
# Set figure size
plt.figure(figsize=(10, 6))

# Create bar chart (Switched X and Y)
sns.barplot(data=age_group_fatalities, 
            x="Age Group", 
            y="Abuse Neglect Fatalities", 
            palette="Blues_r")

# Add labels and title
plt.xlabel("Age Group")
plt.ylabel("Total Fatalities")
plt.title("Child Fatalities  by Age Group (Texas, FY2015-FY2024)")

# Rotate x-axis labels for better readability
plt.xticks(rotation=45)

# Show the plot
plt.show()

```

### Results 

![image](https://github.com/user-attachments/assets/7e644439-4fc6-4116-9a75-1cc28e074e4a)





### Key Insights  

- Infants (0-1) had the highest number of abuse-related fatalities, exceeding 700 cases.Their complete dependence on caregivers makes them more vulnerable to severe neglect and fatal physical abuse.Expanding newborn home visit programs and caregiver education on infant safety can help reduce these risks.  

- Toddlers (2-4) also showed a high fatality rate, with over 600 recorded cases.Increased interaction with caregivers and their inability to communicate or seek help may contribute to higher risks of abuse-related deaths.Promoting affordable early childhood care programs and training professionals to recognize signs of abuse can improve early intervention.  

- Fatalities decline as children get older, with teenagers (15-17) having the lowest numbers.Older children may be more capable of escaping harmful environments or reporting abuse, reducing the likelihood of fatal outcomes.Strengthening school-based support systems and mental health resources can ensure that children in distress receive timely help.  




### 4.What is the distribution of abuse-related child fatalities by gender?



To understand the distribution of child fatalities due to abuse and neglect across genders, I calculated the percentage of fatalities for each gender and visualized the results using a pie chart. This helps in identifying any disparities and provides insights into whether one gender is disproportionately affected.

View my notebook with detailed steps here: [5.Gender_Analysis.ipynb](https://github.com/kubradizlek/abuse_neglected_child_fatalities/blob/main/5.Gender_Analysis.ipynb)





### Visualizing the Data  

```python
# Define labels and values
labels = gender_fatalities["Gender"]
sizes = gender_fatalities["Percentage"]

# Set figure size
plt.figure(figsize=(7, 7))

# Create Pie Chart
plt.pie(sizes, labels=labels, autopct='%1.1f%%', colors=["#66b3ff", "#1f77b4", "#d3d3d3"], startangle=140, wedgeprops={"edgecolor": "black"})

# Add title
plt.title("Percentage Distribution of Abuse- and Neglect-Related Child Fatalities by Gender")

# Show the plot
plt.show()

```

### Results 
![image](https://github.com/user-attachments/assets/5078cfa3-2f4a-4866-b1af-3c67a26fb66f)





### Key Insights  

-Males account for nearly 60% of abuse- and neglect-related child fatalities, which aligns with studies suggesting that boys may be more vulnerable to severe abuse due to societal norms around discipline and independence.

-Child protection programs should consider gender-specific risk factors and provide targeted awareness campaigns for caregivers, emphasizing alternative discipline methods and early intervention.

## Conclusion

This project aimed to shed light on child fatalities due to abuse and neglect in Texas from 2015 to 2024. Through data analysis and visualization, several key patterns emerged. Child fatalities fluctuated over the years, with noticeable peaks in 2020, possibly influenced by external factors such as the COVID-19 pandemic and increased family stress. Certain regions, like Arlington, Houston, and Austin, had significantly higher fatality rates, indicating the need for localized intervention strategies. Infants (0-1) and toddlers (2-4) were the most affected age groups, emphasizing the importance of early childhood protection measures. Males accounted for a larger share of fatalities, suggesting potential differences in risk exposure or response to abuse.

While numbers tell a stark reality, they also serve as a call to action. This analysis underscores the urgent need for stronger child protection policies, increased awareness, and better support systems for at-risk children. By leveraging data, we can identify high-risk groups, allocate resources more effectively, and ultimately work toward preventing these tragedies before they happen.
