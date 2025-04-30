# Bike Share Analysis

## Overview

This project investigates the **impact of weather conditions** on **bike-share usage patterns** in Central Chicago. By leveraging historical data and API integrations, we aim to uncover **key trends, predict ridership,** and provide **actionable insights** for urban planning and operational improvements.

### Team Members
	•	Jitesh Makan
	•	Lovecy Thomas
	•	Sean Schallberger

## Objectives
1.	**Analyze** the relationship between weather conditions (e.g., temperature, precipitation, wind speed) and bike-share usage.
2.	**Predict ride counts** based on weather conditions using regression models and real-time API data.

### Primary Research Question

How do weather conditions impact bike-share usage patterns, including ride volume, duration, and station activity between Members and Casual Users in Central Chicago, and can current and forecasted weather data be used to predict usage?

### Supporting Research Questions
1.	How Does Weather Impact Ride Volume?
2.	What Temporal Trends Emerge Across Weather Conditions?
3.	How Do Different User Types Respond to Weather?
4.	How Do Weather Variables Correlate with Overall Ridership? 

## Tools and Technologies

### Programming
	•	Python

### Libraries
•	**Data Analysis & Cleaning**: Pandas, NumPy
•	**Visualization**: Matplotlib, Plotly
•	**Statistical Modeling**: Scipy
•	**API Integration**: Requests

### APIs
1.	**OpenWeatherMap API**: Historical and real-time weather data.
2.	**Divvy Bike Share Data**: Publicly available datasets (https://www.kaggle.com/datasets/nessada/divvy-tripdata-new).

## Methodology

### 1. Data Collection
•	**Bike-Share Data**: Monthly ride data (2020–2023) with details like trip duration, start times, user type, and rideable type.
•	**Weather Data**: Hourly data from OpenWeatherMap, including temperature, precipitation, humidity, and weather conditions.

### 2. Data Cleaning
•	**Bike-Share Data:**
	•	Filtered Chicago-specific data.
	•	Derived metrics like trip duration, ride hour, and user type.
	•	Removed invalid and duplicate entries.
•	**Weather Data:**
	•	Converted UTC timestamps to local Chicago time.
	•	Removed duplicates and irrelevant columns.

### 3. Data Integration
	•	Merged datasets by day and hour.

### 4. Exploratory Data Analysis (EDA)
	•	Examined usage trends across weather conditions, ride times, and user types.
	•	Visualized relationships with bar charts, scatter plots, and line graphs.

### 5. Predictive Modeling
	•	Trained regression models using weather variables to predict ride counts.
	•	Used R² to evaluate model accuracy.
	•	Integrated real-time weather data from OpenWeatherMap API for hourly predictions.

## Key Code Features

### API Pull
	•	Retrieves real-time weather data for Chicago from OpenWeatherMap.
	•	Predicts hourly ride counts using regression models trained on historical data.
	•	Outputs prediction tables with R² values for each weather metric.

### Data Cleaning
	•	Combines monthly bike-share datasets into a unified dataframe.
	•	Cleans weather data for integration by adjusting timestamps and removing duplicates.

### Data Integration
	•	Merges bike-share and weather datasets by timestamp.
	•	Categorizes temperatures and weather conditions to facilitate analysis.

### Visualizations
	•	Bar charts for ride probability by weather condition.
	•	Scatter plots showing relationships between temperature and ridership.
	•	Line charts for temporal trends in ride counts.
	•	Histograms displaying predicted ride counts by hour.

## Deliverables

### Folder Structure

	bike-weather-analysis/
	│
	├── data/
	│   ├── chicago_weather_data_2020_2023.csv
	│   ├── 202004-divvy-tripdata.csv
	│   ├── ...
	│
	├── scripts/
	│   ├── api_pull.py
	│   ├── data_cleaning.py
	│   ├── exploratory_analysis.py
	│   ├── **config.py**		# Create config.py and input api_key = "OpenWeatherMaps One Call 3.0 API Key"
	│
	├── output/
	│   ├── merged_weather_bike_data.csv
	│   ├── visualizations/
	│   ├── predictions.csv
	│
	├── documentation/
	│   ├── Weather Impact on Bike Usage Project Proposal / Plan (Revised).pdf
	│   ├── Bikeshare Weather Data Analytical Report.pdf
	│   ├── Bikeshare Weather Data Analytical Presentation.pdf
	│
	├── group_individual_work/
	│   ├── scripts_Jitesh/
	│   ├── scripts_Lovecy/
	│   ├── scripts_Sean/
	│
	├── README.md

### Final Outputs
1.	**Cleaned Dataset**: Merged and formatted bike-share and weather data.
2.	**Visualizations**: Charts showcasing key trends.
3.	**Prediction Models**: Hourly ride count predictions based on real-time forecasted weather data.

## Insights
1.	**Ride Volume**: Clear and cloudy weather drive higher ridership, while adverse conditions like rain and snow significantly reduce rides.
2.	**Temporal Trends**: Peak usage during commuting hours and summer months.
3.	**User Behavior**: Members maintain consistent usage; Casual Users are highly sensitive to weather changes.

## Instructions for Replication
1. **Set Up the Environment**
	1.	Clone the repository:

		*git clone <repo_url>*

	2.	Install dependencies:

		*pip install -r requirements.txt*

2. **Create a config.py File**

To access the OpenWeatherMap API, you must create a config.py file with your API key.
	1.	Navigate to the project script directory in your terminal:

		*cd <path_to_project_script_directory>*


	2.	Create a new file named config.py:

		*touch config.py*


	3.	Open the file in your editor and add the following code:

		# config.py
		api_key = "your_openweathermap_api_key"

Replace "your_openweathermap_api_key" with your actual API key from OpenWeatherMap.

	4.	Save the file. The config.py file will now be used by the scripts to fetch weather data.

Note: The config.py file is included in .gitignore to ensure it is not committed to version control.
