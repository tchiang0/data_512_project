# data_512_project
Data 512 Course Project

In recent years, summers in the western United States have increasingly been defined by wildfires, with smoke drifting across multiple states and significantly affecting air quality. Factors such as climate change, forestry policies, and heightened public awareness have been identified as contributors to this growing issue. Regardless of the cause, the impacts of wildfire smoke are far-reaching, posing serious challenges to health, tourism, property, and other facets of society. Cities like Odessa, TX, have experienced the consequences firsthand, as drifting smoke exacerbates local environmental and public health concerns.

This course project focuses on analyzing the effects of wildfire smoke on Odessa, TX, with a specific emphasis on health impacts, including respiratory and cardiovascular health and birth defects. By examining historical data, predicting future trends, and assessing the links between smoke exposure and health outcomes, we aim to provide actionable insights grounded in data.

The ultimate goal of this project is to equip policymakers, city managers, councils, and other civic stakeholders with evidence-based recommendations to inform strategies for mitigating the future impacts of wildfires and improving public health resilience. Through this analysis, we hope to contribute to a more sustainable and prepared community.

# Part 1 (Common Analysis) [all files in [part_1](project/part_1)]
## Goal
Our aim is to examine wildfires that have occurred near Odessa, TX over the past 60 years (1964–2024), analyze the mean Air Quality Index (AQI) for each corresponding year, estimate average smoke density, and forecast smoke levels for the next 25 years (2025–2050).

## Data Source
### Raw Data
Stored in `data_raw` folder
- [USGS_Wildland_Fire_Combined_Dataset.json.gz](project/part_1/data_raw/USGS_Wildland_Fire_Combined_Dataset.json.gz): wildfire data that includes various attributes of wildfires, such as the fire name, year, size, geometric perimeter (ring) of the fire, and more.
    - Citation: Welty, J.L., and Jeffries, M.I., 2021, Combined wildland fire datasets for the United States and certain territories, 1800s-Present: U.S. Geological Survey data release, https://doi.org/10.5066/P9ZXGFY3.

## Intermediate Data
Stored in `data_intermediate` folder
1. [df_gj_wf_distance.csv](project/part_1/data_intermediate/df_gj_wf_distance.csv): Each wildfire's average distance to Odessa, TX saved in a csv format to avoid reruns

2. [df_within_650_miles_away_from_odessa_from_1964.csv](project/part_1/data_intermediate/df_within_650_miles_away_from_odessa_from_1964.csv): Smoke density for each fire that occured within 650 miles away from Odessa, TX 

3. [df_smoke_estimate_by_year.csv](project/part_1/data_intermediate/df_smoke_estimate_by_year.csv): Annual mean smoke estimate computed using the formula outlined in [part_1_wf_distance.ipynb](project/part_1/part_1_wf_distance.ipynb)

4. [Smoke Estimate using ARIMA.csv](<project/part_1/data_intermediate/Smoke Estimate using ARIMA.csv>): Forecasted annual smoke density from 1964 - 2050 using the Autoregressive Integrated Moving Average (ARIMA) model

## Output files (Jupyter Notebooks and PDF)
1. [part_1_AQI.ipynb](project/part_1/part_1_AQI.ipynb) in the `project/part_1` folder: analyzed the AQI data gathered using the US EPA Air Index API, includes 1 visual: **Annual Mean AQI and Annual Mean Smoke Density Estimates from 1964 to 2024**
2. [part_1_wf_distance.ipynb](project/part_1/part_1_wf_distance.ipynb) in the `project/part_1` folder: analyze the USGS wildfire combined dataset and included 2 visuals: **Wildfire Count at Every 50-Mile Interval from Odessa, TX, up to 1800 Miles** and **Total Acres Burned per Year for Fires Occurring within a 650-Mile Radius of Odessa, TX**. Additional smoke density estimate and prediction are also done in this notebook, includes a table: **Predicted Annual Mean Smoke Density Estimates for the Next 25 Years (2025–2050)**
3. [Part 1 - Common Analysis Written Report.pdf](<project/part_1/Part 1 - Common Analysis Written Report.pdf>) in the `project/part_1` folder: written report on all the `Embedded Graphs` and `Embedded Table` (mentioned below) and reflecting on the collaboration in completing part 1 of the project

## Embedded Graphs
1. **Wildfire Count at Every 50-Mile Interval from Odessa, TX, up to 1800 Miles**: [in [part_1_wf_distance.ipynb](project/part_1/part_1_wf_distance.ipynb)] A histogram displaying the number of fires at every 50-mile interval from Odessa, TX, covering all fires up to 1,800 miles away. A red vertical line marks the 650-mile distance

2. **Total Acres Burned per Year for Fires Occurring within a 650-Mile Radius of Odessa, TX**: [in [part_1_wf_distance.ipynb](project/part_1/part_1_wf_distance.ipynb)] A time series graph illustrating the total acres burned each year for fires occurring within a 650-mile radius of Odessa, TX

3. **Annual Mean AQI and Annual Mean Smoke Density Estimates from 1964 to 2024**: [in [part_1_AQI.ipynb](project/part_1/part_1_AQI.ipynb)] A time series graph showing the mean annual smoke density estimates and mean annual AQI for Odessa, TX, for each fire season, defined as running from May 1st through October 31st

4. **Fitted Annual Mean Smoke Density Estimates and Forecast**: [in [part_1_AQI.ipynb](project/part_1/part_1_AQI.ipynb)] Smoke estimate (1964 - 2024) and forecast (2025 - 2050) using the ARIMA model on the calculated annual smoke estimate

## Embedded Table
1. **Predicted Annual Mean Smoke Density Estimates for the Next 25 Years (2025–2050)**: [in [part_1_AQI.ipynb](project/part_1/part_1_wf_distance.ipynb)] A table with two columns—Year and Predicted Annual Mean Smoke Density—where the smoke density is forecasted using ARIMA based on the previous 60 years (1964 - 2024) of annual mean smoke density estimates

# Part 2 (Extension Plan) [all files in [part_2](project/part_2)]
## Goal
The objective of part 2 is to analyze the impact of wildfire smoke on key health indicators, including respiratory health, cardiovascular health, and birth defect cases. By leveraging historical data and predictive modelin (VARMAX), we aim to forecast trends in these health outcomes for the years 2025–2050. This analysis will provide valuable insights into the potential long-term health effects of wildfire smoke exposure, supporting informed decision-making for public health planning and policy development.

## Data Source
### Raw Data
Stored in [health_related_data](project/part_2/health_related_data) folder
1.  **Compressed Mortality 1968-1978, 1979-1998, 1999-2016** [in the [compressed_mortality](project/part_2/health_related_data/compressed_mortality) folder]: The Compressed Mortality File (CMF) is a national database from the Centers for Disease Control and Prevention, offering county-level data on mortality and population from 1968 to 2016. For this project, we focus on data from Ector County, Texas, specifically cases categorized under "Diseases of the respiratory system." The dataset includes key variables such as County, Year, Deaths, Population, Crude Rate, Age-Adjusted Rate, and Percent of Total Deaths, enabling us to analyze the public health impact of smoke-related respiratory issues in the region.

2. **United States and Puerto Rico Cancer Statistics, 1999-2021 Incidence/Mortality** [in the [us_cancer_stats](project/part_2/health_related_data/us_cancer_stats) folder]: The United States Cancer Statistics (USCS) database provides official federal statistics on cancer incidence and mortality across the 50 states and the District of Columbia, sourced from high-quality registries. Produced by the CDC and the National Cancer Institute, it is a critical resource for analyzing cancer trends. For this project, we focus on Texas and target respiratory-related cancers, including those under “Respiratory System,” “Lung and Bronchus,” “Pleura,” and related categories, using state-level data due to the unavailability of county-specific information.

The terms of use for both the Compressed Mortality File and the United States and Puerto Rico Cancer Statistics are as follows:
- Use these data for statistical reporting and analysis only.
- Do not present or publish statistics representing nine or fewer births or deaths, including rates based on counts of nine or fewer births or deaths, in figures, graphs, maps, tables, etc. Statistics representing one through nine (1-9) births or deaths are suppressed on CDC WONDER.
- Make no attempt to learn the identity of any person or establishment included in these data.
- Make no disclosure or other use of the identity of any person or establishment discovered inadvertently and advise the Confidentiality Officer in the National Center for Health Statistics of any such discovery.


3. **PLACES: County Data** [in the [places](project/part_2/health_related_data/places) folder]: This dataset provides model-based, county-level estimates from the CDC’s Division of Population Health, Epidemiology and Surveillance Branch. Our analysis focuses on asthma and chronic obstructive pulmonary disease (COPD), examining both the crude prevalence and age-adjusted prevalence of these conditions. \
The PLACES dataset is designed for public use, supporting statistical reporting and public health initiatives. Users must adhere to ethical data usage practices to ensure confidentiality and protect individual privacy in all analyses and reporting.


4.  **Texas Birth Defects Registry (TBDR) Annual Report, 1999 - 2020** [in the [birth_defects](project/part_2/health_related_data/birth_defects) folder]: The Texas Birth Defects Registry (TBDR) Annual Report provides statewide data on birth defects across various body systems, including year, cases, prevalence rates, and confidence intervals. Although only statewide records are available, this data enables us to analyze trends in birth defect counts over time and explore the distribution of different defect types, without clear indications of any specific defect being more prominent. This broad analysis aims to assess potential impacts on pregnancies that may have been at risk due to smoke exposure. \
The Texas Health Data Use Policy permits users to reproduce and utilize data published by the Texas Department of State Health Services (DSHS), provided that DSHS is credited as the source, and the access and publication dates are noted. The policy also requires retaining copyright notices and prohibits modifying the data. DSHS does not guarantee or provide quality assurance for analyses conducted with their data, and users must include a disclaimer stating that DSHS does not warrant the accuracy or reliability of any derived analyses. This policy does not create legal rights or benefits and does not limit DSHS’s legal protections under applicable laws.


## [extension_health_indicator_forecast](project/part_2/extension_health_indicator_forecast.ipynb)
This Jupyter Notebook is part of the project’s part 2 phase and focuses on analyzing health indicators affected by wildfire smoke and forecasting trends for 2025–2050. It incorporates data exploration and visualization of historical trends, as well as predictive modeling to assess the impact of wildfire smoke on various health outcomes.

### Key Sections:
**Smoke Estimate Using ARIMA**
This section builds on the smoke estimation from the previous analysis in part_1_AQI.ipynb, using the ARIMA model to generate predictions of smoke density for 2025–2050.

**Compressed Mortality Data (1968–2016)**
Utilizes the CDC’s Compressed Mortality File to explore historical respiratory-related mortality trends at the county level. Specific conditions analyzed include asthma, chronic obstructive pulmonary disease (COPD), and respiratory infections. Includes visualizations of cumulative respiratory-related mortality cases over time.

**United States Cancer Statistics (1999–2021)**
Explores respiratory-related cancer incidence and mortality using data from the United States Cancer Statistics (USCS) database. Conditions of interest include lung, bronchus, and other respiratory system cancers. This section emphasizes trends in cancer rates and their potential connections to smoke exposure.

**Texas Birth Defects Registry**
Analyzes trends in birth defect cases across Texas, focusing on state-level data. This section aims to identify potential correlations between wildfire smoke exposure and birth defect prevalence.

**Forecasting Health Indicators (2025–2050)**
Leverages historical data and exogenous smoke density estimates to forecast key health indicators, such as:
- Respiratory-related mortality and prevalence rates
- Cardiovascular-related outcomes
- Trends in birth defects

### Tools and Methods:
- ARIMA Modeling for smoke density forecasting
- Vector Autoregressive Moving Average with eXogenous regressors model  (VARMAX) Models for multivariate time-series analysis of health indicators
- Visualizations to highlight trends and model outputs

This notebook aims to provide actionable insights into the long-term health impacts of wildfire smoke, supporting public health planning and policy-making. The outputs include visualizations and predictions designed for use by stakeholders such as city councils, health departments, and policymakers.
