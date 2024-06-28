# Space-Mission


#![excel-to-powerbi-animated-diagram](assets/images/kaggle_to_powerbi.gif)

# Table of contents 

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





