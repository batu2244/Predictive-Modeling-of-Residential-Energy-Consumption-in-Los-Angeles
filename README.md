# Predictive Modeling of Residential Energy Consumption in Los Angeles Using Integrated Housing, Geospatial, and Socioeconomic Data

## Overview
This project analyzes residential energy consumption patterns across Los Angeles by integrating public energy datasets, geocoded location data, and scraped housing listings. The workflow combines data engineering, web scraping, geospatial enrichment, and machine learning to estimate household-level energy-related attributes and study the factors associated with energy use.

The project uses three main sources:
- UCLA Energy Atlas datasets
- Google Geocoding API
- Craigslist housing listings

The final output is an enriched housing dataset that supports predictive modeling and downstream statistical analysis of residential energy consumption in Los Angeles.

## Project Goal
The main goal of this project is to estimate and analyze residential energy usage using housing, geographic, and socioeconomic information. In particular, the project predicts values such as:
- median household energy usage
- per capita energy usage
- estimated income range
- solar potential by location

These features are then used to explore how variables such as square footage, bedrooms, bathrooms, price, and solar potential relate to energy consumption.

## Repository Structure
A typical project structure is expected to look like this:

```text
.
├── README.md
├── Final_Project_Batuhan_Aydin.docx
├── UCLA_data_processing_and_API.ipynb
├── Craigslist_Scraping.ipynb
├── Predicting_energy.ipynb
├── data/
│   ├── geos.csv
│   ├── usage_bld_kwh.csv
│   ├── usage_income_kwh.csv
│   ├── usage_sqft_kwh.csv
│   └── usage_vintage_kwh.csv
└── outputs/
    ├── ucla_merged.csv
    ├── api_locations.csv
    ├── ucla_final.csv
    ├── craigslist_listings.csv
    ├── houses_cleaned.csv
    └── houses_final.csv
```

Notebook order:
1. `UCLA_data_processing_and_API.ipynb`
2. `Craigslist_Scraping.ipynb`
3. `Predicting_energy.ipynb`

## Data Sources
### 1. UCLA Energy Atlas
The UCLA Energy Atlas provides the core energy-related datasets used for this project, including information on energy usage, building size, vintage, income groups, and solar potential across Los Angeles geographies.

### 2. Google Geocoding API
The Google Geocoding API is used to standardize and enrich location information such as city, county, neighborhood, and postal code. A personal API key is required and is not included in the notebook for security reasons.

### 3. Craigslist Housing Listings
Craigslist listings are scraped to collect housing-level attributes such as price, title, bedrooms, bathrooms, square footage, and description. These listings are later cleaned and matched with predicted energy-related features.

## How to Use This Repository
Please start by reading the project report before running the notebooks.

The report explains:
- the full project motivation and methodology
- the required input files
- the order in which to run the notebooks
- where to place datasets
- how to configure the Google Geocoding API key
- how intermediate and final output files are generated
- how the predictive modeling and analysis steps are organized

In short, the notebooks should be run sequentially, since each stage depends on files produced by the previous one. The full step-by-step execution details are documented in the report rather than repeated here.

## Running the Project
This README intentionally keeps setup instructions brief.

To reproduce the full workflow:
1. Read the report first.
2. Download the required UCLA Energy Atlas files.
3. Add your own Google Geocoding API key where indicated in the first notebook.
4. Run the notebooks in order.
5. Review the generated output files and analysis results.

Detailed execution guidance is provided in the report.

## Main Outputs
The project generates several intermediate and final datasets, including:
- `ucla_merged.csv`
- `api_locations.csv`
- `ucla_final.csv`
- `craigslist_listings.csv`
- `houses_cleaned.csv`
- `houses_final.csv`

## Methods Used
- data cleaning and preprocessing
- geocoding and location standardization
- web scraping with BeautifulSoup
- CatBoost regression modeling
- weighted prediction aggregation
- exploratory data analysis
- OLS regression analysis

## Key Findings
The project finds that:
- energy usage per capita tends to increase with estimated income
- housing price is a statistically significant predictor of per capita energy usage
- square footage, bedrooms, and bathrooms are among the strongest drivers of energy consumption
- solar potential is negatively associated with predicted median energy usage

These findings suggest that structural housing characteristics play a major role in residential energy demand.

## Notes
- The Google Geocoding API key is not included for security reasons.
- Craigslist scraping was performed in batches and may take a long time to rerun.
- Some outputs depend on external data access and API availability.

## Author
Batuhan Aydin
