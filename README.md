# STATS401-Data-Acquisition-Visualization-Project
Now climate change is a global challenge, with rising temperatures and increasing carbon emissions and populations. Our group visualized the relationships between carbon emissions, global temperature anomalies, and population in order to understand these factors’ impacts and how they might interact with each other. We created one heat map, one line chart, one tree map, one correlation matrix, and one bubble chart to help audiences like policymakers, researchers, and the public better understand global climate patterns. These five interactive visualizations help us to identify historical trends, analyze correlations, and explore potential future scenarios.

Our analysis is guided by the following key questions:

- How severe is climate change based on global per capita carbon emission distribution? 

- What is the contribution of different countries to global carbon emissions?

- How do carbon emissions, population, and temperature anomalies interact with each other?

- What will carbon emissions, temperature anomalies, and global populations look like 5 years later?

## Method

Our data pipeline consisted of three primary steps: Data collection, Data cleaning, and Analysis & Visualization.
Data Collection: We obtained four primary datasets in CSV format: a global population dataset containing annual population figures by year, a global CO₂ emissions dataset capturing annual emissions country-wise, a temperature anomaly dataset showing yearly global temperature anomalies relative to a baseline period, and a country‐level dataset containing contributions to temperature increase. Additionally, we used a GeoJSON file for the world map boundaries in our heatmap.
Data Cleaning/Filtering: Each CSV file underwent basic cleaning in Python. The first step is to drop unrelated columns and limit the time scale. Then, column names were standardized. After that, relevant fields (e.g., CO₂ emissions per capita, etc.) were calculated for further analysis. We also added an ordinal column to indicate whether a country is a developed or developing country.  
Analysis & Visualization: In the browser, we used D3.js to load each CSV asynchronously (d3.csv(...)) and merged datasets where needed. For instance, the line chart merges annual CO₂ emissions with temperature anomalies by matching each row on the “Year” field. We similarly created a dictionary for the heatmap that mapped each country’s name to its per‐capita emissions. For the treemap, we sorted the country‐level CO₂ data by total emissions, and for the correlation matrix, we aligned each year’s population, CO₂ emissions, and temperature anomaly to compute pairwise correlations. In the bubble chart, we created a checkbox‐based filter that lets users select which countries to display. We implemented this by binding each checkbox value to the data’s “Country” field and rendering only the subset of rows matching the checked boxes. In addition, the data for the bubble chart is based on a prediction for 2030. We used a linear regression model and historical data to make such a prediction. All visualizations were built using D3.js within a single dashboard.

## Roles and Responsibilities
- Yiwen Hu: Data cleaning, treemap implementation, introduction, discussion.

- Zhixuan Lu: Data cleaning, heat map & bubble chart, results, conclusion.

- Yanzhou Yang: Data collection, correlation matrix & line chart, dashboard design, methods.


