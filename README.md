# Matplotlib Challenge
This repository will be used for the Module 5 Matplotlib Python challenge.

## Description

I completed the analysis of the study results of using certain drugs to reduce tumor growth in mice. The code performs various data analysis tasks on a dataset of mice and study results related to different drug regimens for tumor treatment. The code imports the data from two CSV files, merges them into a single DataFrame, and cleans the data by dropping the duplicate mouse by its ID. The code then generates summary statistics, bar plots, pie plots, and box plots to show the characteristics and distribution of the tumor volume for each drug regimen. The code also generates a line plot and a scatter plot to show the relationship between the tumor volume and the time point or the weight for a single mouse or the entire Capomulin regimen. The code also calculates the correlation coefficient and a linear regression model for the mouse weight and the average observed tumor volume for the Capomulin regimen.

## Installation

Feel free to download the CSV and the Python Jupyter Notebook files I provided to look over the Python script files.

Input the below modules for script files to run properly

```python
# Dependencies and Setup
import matplotlib.pyplot as plt
import pandas as pd
import scipy.stats as st
import numpy as np
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change/recommend.

## Authors and Acknowledgement
I solely worked on this project, however, I did utilize the website pandas.pydata and the Xpert Learning Assistant AI tool (provided by boot camp class) to complete some tasks that either I needed a refresher or we did not learn in our prior boot camp classes.

I used the below website to help me learn the .agg() function in addition to groupby() to create a summary statistics table in one line versus the previous method which involved way more lines of code.

https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.aggregate.html

Then, I also used an AI tool called Xpert Learning Assistant that runs on Chat GPT to help me write these lines of code to uniquely identify two columns.

```python
grouped_df = mouse_and_study_df.groupby(['Mouse ID','Timepoint'])
```

I also used the Xpert Learning tool to help with the linear regression code that is seen below.

```python
slope, intercept, r_value, p_value, std_err = st.linregress(average_tumor_volume['Weight (g)'], average_tumor_volume['Tumor Volume (mm3)'])
plt.scatter(average_tumor_volume['Weight (g)'], average_tumor_volume['Tumor Volume (mm3)'])
plt.plot(average_tumor_volume['Weight (g)'], intercept + slope * average_tumor_volume['Weight (g)'], color='red')
plt.xlabel('Weight (g)')
plt.ylabel('Average Tumor Volume (mm3)')
plt.title('Mouse Weight vs Average Observed Tumor Volume (Capomulin Regimen)')
plt.show()
```
