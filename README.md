# User Tickets Geospatial Analysis

A comprehensive Jupyter notebook for analyzing and visualizing sales ticket data using geospatial techniques. This project normalizes ticket geopoints in a geographical framework using GeoPandas and renders sectorial average ticket values over geographical polygons with interactive Folium visualizations.

## Features

- **Data Extraction**: Query ticket data from BigQuery with geospatial coordinates
- **Geospatial Processing**: Convert coordinates to geometric objects using GeoPandas
- **Fishnet Grid Analysis**: Generate regular grids for spatial aggregation
- **Statistical Analysis**: Calculate ticket statistics (mean, std, CV) per grid cell
- **Interactive Visualizations**: Create heatmaps and choropleth maps with Folium

## Requirements

```bash
pip install google-cloud-bigquery pandas pydata-google-auth geopandas numpy matplotlib seaborn folium shapely branca
```

## Configuration

All configuration parameters are centralized at the top of the notebook:

- **BigQuery settings**: Project name, dataset location
- **Geospatial settings**: CRS system, map center coordinates, zoom level
- **Grid settings**: Number of divisions for fishnet grid
- **Visualization settings**: Color gradients, output file paths

## Workflow

1. **Authentication**: Connect to BigQuery using Google Cloud credentials
2. **Data Extraction**: Query ticket data with geographical information
3. **Data Preparation**: Convert WKT strings to geometric objects
4. **Grid Creation**: Generate fishnet grid over study area
5. **Spatial Join**: Assign ticket points to grid cells
6. **Statistical Analysis**: Calculate aggregated statistics per grid cell
7. **Visualization**: Create interactive maps (heatmap and choropleth)

## Usage

1. Configure your BigQuery project and query in the configuration section
2. Run all cells sequentially from top to bottom
3. Interactive maps will be saved as HTML files for viewing in a browser

## Output Files

- `download.csv`: Raw ticket data from BigQuery
- `output_heatmap.html`: Interactive heatmap of ticket values
- `output_choropleth.html`: Interactive choropleth map showing average ticket by grid cell

## Code Quality Improvements

This notebook follows best practices for maintainability:

- Centralized configuration constants
- Comprehensive documentation and comments
- Reusable utility functions for common operations
- Consistent naming conventions
- Error handling and validation
- Type hints and docstrings for all functions
