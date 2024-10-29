# data_512_project
Data 512 Course Project

In recent years, summers in the western United States have increasingly been marked by wildfires, with smoke drifting across multiple states. Several factors have been proposed as contributors, including climate change, forestry policies, and rising public awareness. Whatever the cause, the effects of wildfire smoke are far-reaching, significantly diminishing air quality in cities like Odessa, TX. An expanding body of research highlights the negative impacts of smoke on health, tourism, property, and other areas of society. 

This course project involves analyzing the effects of wildfires on Odessa, TX. The ultimate objective is to equip policymakers, city managers, councils, and other civic entities with insights to help them assess whether and how to develop strategies for mitigating the future impacts of wildfires.

# Part 1
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

## Output files (Jupyter Notebooks and PDF)
1. [part_1_AQI.ipynb](project/part_1/part_1_AQI.ipynb) in the `project/part_1` folder: analyzed the AQI data gathered using the US EPA Air Index API, includes 1 visual: **Annual Mean AQI and Annual Mean Smoke Density Estimates from 1964 to 2024**
2. [part_1_wf_distance.ipynb](project/part_1/part_1_wf_distance.ipynb) in the `project/part_1` folder: analyze the USGS wildfire combined dataset and included 2 visuals: **Wildfire Count at Every 50-Mile Interval from Odessa, TX, up to 1800 Miles** and **Total Acres Burned per Year for Fires Occurring within a 650-Mile Radius of Odessa, TX**. Additional smoke density estimate and prediction are also done in this notebook, includes a table: **Predicted Annual Mean Smoke Density Estimates for the Next 25 Years (2025–2050)**
3. [Part 1 - Common Analysis Written Report.pdf](<project/part_1/Part 1 - Common Analysis Written Report.pdf>) in the `project/part_1` folder: written report on all the `Embedded Graphs` and `Embedded Table` (mentioned below) and reflecting on the collaboration in completing part 1 of the project

## Embedded Graphs
1. **Wildfire Count at Every 50-Mile Interval from Odessa, TX, up to 1800 Miles**: [in [part_1_wf_distance.ipynb](project/part_1/part_1_wf_distance.ipynb)] A histogram displaying the number of fires at every 50-mile interval from Odessa, TX, covering all fires up to 1,800 miles away. A red vertical line marks the 650-mile distance.

2. **Total Acres Burned per Year for Fires Occurring within a 650-Mile Radius of Odessa, TX**: [in [part_1_wf_distance.ipynb](project/part_1/part_1_wf_distance.ipynb)] A time series graph illustrating the total acres burned each year for fires occurring within a 650-mile radius of Odessa, TX.

3. **Annual Mean AQI and Annual Mean Smoke Density Estimates from 1964 to 2024**: [in [part_1_AQI.ipynb](project/part_1/part_1_AQI.ipynb)] A time series graph showing the mean annual smoke density estimates and mean annual AQI for Odessa, TX, for each fire season, defined as running from May 1st through October 31st.

## Embedded Table
1. **Predicted Annual Mean Smoke Density Estimates for the Next 25 Years (2025–2050)**: [in [part_1_AQI.ipynb](project/part_1/part_1_AQI.ipynb)] A table with two columns—Year and Predicted Annual Mean Smoke Density—where the smoke density is forecasted using linear regression based on the previous 60 years (1964 - 2024) of annual mean smoke density estimates.
