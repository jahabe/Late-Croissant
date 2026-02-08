# script.ipynb Overview

This Jupyter notebook performs data cleaning and enrichment on Seattle sidewalk accessibility data, then analyzes correlations between sidewalk severity issues and demographic vulnerability factors.

## What it does:

### Data Cleaning & Enrichment (Cells 1-3)
- Loads the `Access_to_Everyday_Life_Dataset.csv` containing Seattle sidewalk accessibility reports
- Loads demographic data from a Seattle census tract GeoJSON file
- Converts sidewalk reports into geographic points and performs a spatial join with census tracts
- Fills in missing severity values based on issue type
- Drops any reports outside the city boundaries (invalid locations, water, etc.)

### Data Preprocessing (Cell 4)
- Combines original dataset columns with enriched demographic attributes:
  - Census Tract ID
  - Percentage of Limited English speakers
  - Percentage of Low-Income population
  - Percentage of Adults with Disabilities
- Renames columns for clarity
- Saves the enriched dataset as `Seattle_Mobility_Enriched_Full.csv`

### Correlation Analysis (Cell 5)
- Loads the enriched dataset
- Creates a correlation matrix between:
  - Sidewalk severity (issue severity level)
  - Disability rates
  - Low-income population rates
  - Limited English speaker rates
- Visualizes the correlation matrix as a heatmap to show relationships between sidewalk problems and community vulnerability

## Output:
- **CSV file**: `Seattle_Mobility_Enriched_Full.csv` - Cleaned and enriched dataset
- **Visualization**: Correlation heatmap showing how sidewalk issues relate to demographic factors
