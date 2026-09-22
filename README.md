# Mobility & Economy: Urban Traffic and Economic Indicators in Latin America

## Project Overview

This project explores how urban mobility indicators relate to economic, demographic, and environmental conditions across major Latin American cities.

The analysis integrates more than **1 million TomTom traffic observations** with city-level economic indicators, transforming heterogeneous raw sources into a comparable city-year dataset. The final analytical sample contains **15 cities across 7 countries**.

The project is exploratory and observational. Reported relationships are associations and should not be interpreted as evidence of causality.

## Business Questions

- Which cities in the integrated sample experience the highest average traffic delays?
- How does traffic congestion vary alongside GDP per capita, unemployment, air pollution, and population?
- Which relationships appear strongest in this cross-sectional sample?
- How can integrated mobility and economic data support urban planning and policy analysis?

## Data & Integration

Two heterogeneous sources are combined:

- **TomTom traffic data:** 1,004,464 observations covering 384 cities in 55 countries, with traffic conditions recorded from October 2024 to January 2025.
- **City economic indicators:** GDP per capita, unemployment, PM2.5, and population for selected Latin American cities.

The workflow:

1. Standardizes column names and data types.
2. Parses timestamps and filters traffic observations to 2024.
3. Corrects locale-specific numeric formats such as decimal commas.
4. Aggregates high-frequency traffic observations to city-year averages.
5. Harmonizes country identifiers across sources.
6. Joins traffic and economic data using **city + country + year**.
7. Validates the resulting analytical dataset before exploration.

## Analytical Approach

The notebook uses:

- data cleaning and type conversion
- aggregation of high-volume traffic records
- multi-source data integration
- exploratory distributions and city comparisons
- Pearson and Spearman correlations
- scatter plots and descriptive visual analysis

Because the final cross-sectional sample is small, correlations are treated as exploratory signals rather than statistical or causal conclusions.

## Key Findings

Within the 15-city integrated sample:

- Average traffic delay shows a strong positive Pearson association with **population** (`r ≈ 0.88`).
- Average traffic delay also shows a positive association with **PM2.5** (`r ≈ 0.77`).
- The relationship between traffic delay and **GDP per capita** is considerably weaker (`r ≈ 0.28`).
- The results suggest that urban scale and environmental conditions are more closely associated with congestion in this sample than income per capita alone.

These findings should be interpreted cautiously because the analysis covers a limited set of cities and a single year.

## Business & Policy Implications

The analysis illustrates how mobility data can be enriched with socioeconomic indicators to create a broader view of urban performance. For planners and decision-makers, this type of integrated dataset can help identify cities where congestion, population pressure, and environmental conditions overlap and warrant deeper investigation.

A stronger follow-up study could add multiple years, infrastructure variables, public-transit coverage, vehicle ownership, and formal statistical modeling.

## Tools & Skills

- **Python**
- **pandas**
- **NumPy**
- **Matplotlib**
- Data cleaning and transformation
- Large-dataset aggregation
- Multi-source joins and validation
- Exploratory correlation analysis
- Business and policy interpretation

## Repository Structure

```text
mobility-economy-analysis/
├── README.md
├── mobility_economy_analysis.ipynb
├── ladb_mobility_economy_2024_clean.csv
├── oecd_city_economy.csv
└── .gitignore
```

The raw `tomtom_traffic.csv` file is intentionally excluded from GitHub because its size exceeds the standard GitHub file limit. The processed analytical dataset used for the final city-level analysis is included in the repository.

## Reproducibility

To reproduce the complete workflow locally, place the raw TomTom traffic file in the project directory as:

```text
tomtom_traffic.csv
```

The notebook will clean, aggregate, integrate, analyze, and export the final 2024 analytical dataset.
