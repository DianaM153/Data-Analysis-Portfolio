# Global Access to Basic Services: A Data Analysis

## Project Overview

This project analyzes global access to basic services such as **managed drinking water and sanitation** across different regions and countries. The analysis explores how access to these services relates to **economic indicators, population size, unemployment, and geographic factors**.

Using a dataset containing regional and country-level indicators, the project demonstrates a full data analysis workflow using **Excel, SQL, and Power BI**.

The goal is to identify **regional disparities, economic relationships, and trends in infrastructure access**.



## Dataset Description

The dataset contains country-level observations with the following variables:

| Column                              | Description                                                             |
| ----------------------------------- | ----------------------------------------------------------------------- |
| Region                              | Major geographic region of the country                                  |
| Sub_region                          | Subdivision within the main region                                      |
| Country_name                        | Country being analyzed                                                  |
| Time_period                         | Year or reporting period                                                |
| Pct_managed_drinking_water_services | Percentage of population with access to managed drinking water services |
| Pct_managed_sanitation_services     | Percentage of population with access to managed sanitation services     |
| Est_population_in_millions          | Estimated population size (millions)                                    |
| Est_gdp_in_billions                 | Estimated GDP (billions USD)                                            |
| Land_area                           | Total land area of the country                                          |
| Pct_unemployment                    | Unemployment rate (%)                                                   |

Source: United Nations Development Data



## Objectives

The project investigates several key analytical questions:

* Which **regions have the lowest access to drinking water and sanitation services?**
* How does **economic development (GDP)** relate to access to basic services?
* Do **larger populations face greater challenges** in providing sanitation infrastructure?
* Is there a relationship between **unemployment rates and infrastructure access**?
* How do **service access levels change over time**?



## Tools and Technologies

This project demonstrates the use of multiple tools commonly used by data analysts.

**Excel**

* Data cleaning
* Splitting data to columns
* Handling missing values
* Initial exploratory analysis

**SQL**

* Data querying
* Aggregations and grouping
* Regional comparisons

**Power BI**

* Interactive dashboards
* Data visualization
* Trend analysis



## Data Processing Workflow

1. Data Collection
   Dataset obtained from United Nations development indicators.

2. Data Cleaning (Excel)

   * Checked for missing values
   * Splitting data to columns
   * Standardized column formats
   * Verified numerical data types

3. Data Transformation (SQL)

   * Aggregated regional statistics
   * Calculated averages and rankings
   * Explored relationships between variables

4. Visualization (Power BI)

   * Created interactive dashboards
   * Developed maps and comparative charts
   * Highlighted trends in infrastructure access



## Key Metrics Created

Additional indicators were calculated to enrich the analysis:

* **GDP per capita**
* **Population density**
* **Regional average service access**

These metrics allow deeper insights into how economic and demographic factors influence service availability.



## Dashboard Insights

The Power BI dashboard highlights:

* Global distribution of **drinking water access**
* Regional comparison of **sanitation services**
* Relationship between **GDP and infrastructure access**
* Population and unemployment context for each country



## Repository Structure

data/
Raw dataset used for the analysis

excel/
Cleaned datasets and preprocessing steps

sql/
SQL queries used for data exploration and aggregation

powerbi/
Power BI dashboard file (.pbix)

visuals/
Screenshots of charts and dashboard visuals



## Skills Demonstrated

* Data cleaning and preprocessing
* SQL querying and aggregation
* Data visualization
* Analytical thinking
* Dashboard storytelling
* Working with real-world development datasets



## Author

Diana Chepkoech

Data Analyst Portfolio Project
