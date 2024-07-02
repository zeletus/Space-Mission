# Space-Mission


#![excel-to-powerbi-animated-diagram](assets/images/kaggle_to_powerbi.gif)

# Table of contents 
- [Description](#description)
- [Objective](#objective)
- [Data Source](#data-source)
- [Stages](#stages)
- [Design](#design)
  - [Tools](#tools)
- [Development](#development)
  - [Pseudocode](#pseudocode)
  - [Data Exploration](#data-exploration)
  - [Data Cleaning](#data-cleaning)
  - [Transform the Data](#transform-the-data)
  - [Create the SQL View](#create-the-sql-view)
- [Testing](#testing)
  - [Data Quality Tests](#data-quality-tests)
- [Visualization](#visualization)
  - [Results](#results)
  - [DAX Measures](#dax-measures)
- [Analysis](#analysis)
  - [Findings](#findings)
  - [Validation](#validation)
  - [Discovery](#discovery)
- [Recommendations](#recommendations)
  - [Potential Courses of Actions](#potential-courses-of-actions)
- [Conclusion](#conclusion)

# Description

All space missions from 1957 to August 2022, including details on the location, date,
and result of the launch, the company responsible, and the name, price, and status
of the rocket used for the mission.

## Column Description:
## Column Description:
| Field    | Description         |
|----------|---------------------|
| Company  | Company responsible |
| Location | Launch location     |


# Objective 

The objective of this project is to analyze historical space mission data to identify trends and patterns in rocket launches, mission success rates, and launch locations. The analysis aims to answer the following key questions:
  
  - How have rocket launches trended over time?
  - Has the mission success rate increased over time?
  - Which countries have had the most successful space missions, and has this trend remained consistent?
  - Which rocket has been used for the most space missions, and is it still active?
  - Are there any discernible patterns in the launch locations?
  
  This analysis will provide insights into the historical performance and current state of space missions, aiding in strategic decision-making for future space exploration initiatives.
  

 ## User Story
  As a data analyst,
  I want to analyze historical space mission data,
  So that I can identify trends and patterns in rocket launches, mission success rates, and launch locations to provide actionable insights for future space exploration initiatives.

acceptance_criteria:
  Data Analysis:
    - Analyze the trend of rocket launches over time.
    - Evaluate if the mission success rate has increased over time.
    - Identify the countries with the most successful space missions and determine if this trend has been consistent.
    - Determine which rockets have been used for the most space missions and assess their current status.
    - Detect patterns in the launch locations.
  
  Data Preparation:
    - Clean and preprocess the space mission data, including removing duplicates and filling missing values.
    - Encode categorical data for analysis.
  
  Data Visualization:
    - Create visualizations for rocket launch trends, mission success rates, country success rates, rocket usage, and launch locations.
  
  Reporting:
    - Generate reports in PDF and HTML formats to summarize the findings.
    - Include insights and recommendations based on the analysis results.
  
  Documentation:
    - Document the entire process including data source, preprocessing steps, analysis methods, and insights.
    - Provide a comprehensive table of contents for easy navigation of the project documentation.


# Data source 

- What data is needed to achieve our objective?

We need data on Space Missions that includes the following Columns 
- Company 
- Location 
- Date 
- Time
- Rocket
- Missions
- Rocket status
- Price
- Mission Status 



- Where is the data coming from? 
The data is sourced Maven Analytics (an Excel extract), [see here to find it.](https://app.mavenanalytics.io/datasets)


# Stages

- Design
- Developement
- Testing
- Analysis

# Design 
## Dashboardrequirements
  - objective: >
      To create a Power BI dashboard that visualizes historical space mission data, enabling stakeholders to interactively explore trends and patterns in rocket launches, mission success rates, and launch locations.
1.  Shows the number of rocket launches per year.
2.  Displays the distribution of mission outcomes (Success, Failure, Partial Failure, Prelaunch Failure).
3.  Shows the number of successful missions by country.


# Tools
| Tool | Purpose |
| --- | --- |
| Power BI | Visualizing the data via interactive dashboards |
| GitHub | Hosting the project documentation and version control |


# Development

## Pseudocode
- What's the general approach in creating this solution from start to finish?

1. Get the data
2. Explore the data in Microsoft Power BI
3. Load the data into Microsoft Power BI
4. Clean the data with Microsoft Power BI
6. Visualize the data in Power BI
7. Generate the findings based on the insights
8. Write the documentation + commentary
9. Publish the data to GitHub Pages

## Data exploration notes

This is the stage where you have a scan of what's in the data, errors, inconcsistencies, bugs, weird and corrupted characters etc  


- What are your initial observations with this dataset? What's caught your attention so far? 

1. There are at least 9 columns that contain the data we need for this analysis, which signals we have everything we need from the file without needing to contact the client for any more data. 
2. Some of the cells had null values 
3. All columns were needed for the Data analysis

## Data cleaning 
- What do we expect the clean data to look like? (What should it contain? What contraints should we apply to it?)

The aim is to refine our dataset to ensure it is structured and ready for analysis. 

The cleaned data should meet the following criteria and constraints:

- Only relevant columns should be retained.
- All data types should be appropriate for the contents of each column.
- There were some null cell which was considered during the analysis
- Datatype was checked to ensure Fields correlate with records.

## DAX Measures

### 1. Failed Missions Count
```sql
FailedMissions = 
CALCULATE(
    COUNT('Space Mission'[Mission]),
    'Space Mission'[MissionStatus] = "Failure"
)
```

### 2. Partial Failure Count
```sql
PartialFailure = 
CALCULATE(
    COUNT('Space Mission'[Mission]),
    'Space Mission'[MissionStatus] = "Partial Failure"
)

```

### 3. Prelaunch Failure Count
```sql
PrelaunchFailure = 
CALCULATE(
    COUNT('Space Mission'[Mission]),
    'Space Mission'[MissionStatus] = "Prelaunch Failure"
)
```

### 4. Success Rate
```sql
SuccessRate = 
DIVIDE(
    CALCULATE(
        COUNT('Space Mission'[Mission]),
        'Space Mission'[MissionStatus] = "Success"
    ),
    COUNT('Space Mission'[Mission])
)
```

### 5. Successful Missions Count
```sql
SuccessfulMissions = 
CALCULATE(
    COUNT('Space Mission'[Mission]),
    'Space Mission'[MissionStatus] = "Success"
)
```

### 6. Total Missions Count
```sql
TotalMissions = COUNT('Space Mission'[Mission])
```

### 7. Total Price Sum
```sql
TotalPrice = SUM('Space Mission'[Price])
```

# Recommended Analysis
## Findings
For this analysis, we're going to focus on the questions below -
Here are the key questions we need to answer-

1. How have rocket launches trended across time? Has mission success rate increased?

2. Which countries have had the most successful space missions? Has it always been that way?

3. Which rocket has been used for the most space missions? Is it still active?

4. Are there any patterns you can notice with the launch locations?


### 1. How have rocket launches trended across time? Has the mission success rate increased?
- There is a noticeable increase in rocket launches starting around the 2000s, with significant growth in recent years.
- The overall success rate is high at 94.62%.
- Failures and partial failures are relatively low.

### 2. Which countries have had the most successful space missions? Has it always been that way?
- Two countries dominated successful space missions throughout most recent decades:
1. United States
2. Russia
   
 However, in recent decades, other countries have had increasing success in space exploration.

### 3. Which rocket has been used for the most space missions? Is it still active?
- The Falcon 9 Block 5 is the most frequently used rocket, having been used 111 times, and it is still active.
  
### 4. Are there any patterns you can notice with the launch locations?
- There is a noticeable increase in rocket launches starting around the 2000s, with significant growth in recent years.
In recent decades, other countries have had increasing success in space exploration:
- 2022 recorded the highest number of mission failures.
- 2021 recorded the highest number of successful missions, with 122 mission successes.
- The United States of America has the record for the most mission launches.











