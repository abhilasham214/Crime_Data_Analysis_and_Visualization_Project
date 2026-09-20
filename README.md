# Crime Data Analysis, Visualization, and Predictive Route Safety System

An end-to-end Data Engineering and Analytics platform that processes urban crime datasets to perform Exploratory Data Analysis (EDA), render interactive geospatial density maps, and predict crime intensity using Random Forest Machine Learning models.

## System Architecture

```text
+-------------------------------------------------------------------+
|                        Data Ingestion Layer                       |
|              data/crime_data.csv + data/locations.csv            |
+-------------------------------------------------------------------+
                                  |
                                  v
+-------------------------------------------------------------------+
|                 Preprocessing & Feature Engineering               |
|   Pandas / NumPy: validation, coordinate join, cyclical month &   |
|   weekday encoding, severity-weighted risk score                  |
+-------------------------------------------------------------------+
                                  |
        +-------------------------+-------------------------+
        |                         |                         |
        v                         v                         v
+----------------+   +---------------------------+   +------------------+
| Exploratory    |   | Geospatial Mapping        |   | Random Forest    |
| Analysis       |   | Folium + Plotly           |   | Regressor        |
| Seaborn /      |   | markers, heatmap          |   | (Scikit-Learn,   |
| Matplotlib /   |   |                           |   | cross-validated) |
| Plotly         |   |                           |   |                  |
+----------------+   +---------------------------+   +------------------+
                                  |                         |
                                  v                         v
                     +-------------------------------------------+
                     |   Route Safety Scoring                    |
                     |   Forecast risk -> Gaussian kernel density|
                     |   integrated along each route's path      |
                     +-------------------------------------------+
                                        |
                                        v
                     +-------------------------------------------+
                     |   maps/*.html  (interactive outputs)      |
                     +-------------------------------------------+
```

## Key Features

- **Exploratory Data Analysis:** crime totals by location and type, monthly trends, a location-by-month heatmap and incident-size distributions (Seaborn, Matplotlib, Plotly).
- **Spatial and temporal encoding:** neighbourhood coordinates joined to every record, and month / weekday encoded cyclically so December sits next to January.
- **Interactive geospatial maps:** Folium marker and density-heatmap maps saved as standalone HTML, plus a Plotly map inside the notebook.
- **Random Forest model:** predicts crime count from location, season, weekday and crime severity. It is evaluated with 5-fold cross-validation against a location-mean baseline, then used to forecast expected risk per neighbourhood for Q1 2023.
- **Route safety scoring:** each route is sampled every ~250 m and crime density is estimated with a Gaussian kernel over forecast neighbourhood risk. The density is integrated along the path to give total exposure and exposure per km, and routes are drawn over the heatmap.

## Repository Structure

```text
Crime_Data_Analysis_and_Visualization_Project/
├── data/
│   ├── crime_data.csv                         # Crime log: date, location, crime type, crime count
│   └── locations.csv                          # Representative latitude / longitude per neighbourhood
├── notebooks/
│   └── crime_analysis_and_prediction.ipynb    # Full pipeline, run top to bottom
├── maps/
│   ├── crime_markers_map.html                 # Crime volume and risk per neighbourhood
│   ├── crime_heatmap.html                     # Severity-weighted density heatmap
│   └── route_safety_map.html                  # Candidate routes over forecast risk, coloured by exposure
├── requirements.txt                           # Python dependencies
└── README.md
```

## Results and Limitations

- The dataset is a small illustrative sample: 43 records, 4 neighbourhoods, calendar year 2022. Neighbourhood coordinates are representative points, not real boundaries.
- On this sample the Random Forest does **not** beat the location-mean baseline. There is too little data and too little signal to learn from, and the notebook reports this rather than hiding it. The pipeline is designed to be re-run on a larger real dataset.
- Routes are straight segments between neighbourhood centres, not real road networks.
- Severity weights (Theft 1, Burglary 2, Assault 3) are illustrative assumptions.

## Tech Stack

- Language: Python 3.8+
- Data Analytics: Pandas, NumPy
- Machine Learning: Scikit-Learn (Random Forest Regressor, Preprocessing)
- Visualization & GIS: Folium, Plotly, Matplotlib, Seaborn
- Runtime: Jupyter Notebook

## Local Setup and Running

1. Clone the repository:
   ```bash
   git clone https://github.com/abhilasham214/Crime_Data_Analysis_and_Visualization_Project.git
   cd Crime_Data_Analysis_and_Visualization_Project
   ```

2. Set up a Python virtual environment:
   ```bash
   python -m venv venv
   # On Windows:
   venv\Scripts\activate
   # On Linux/macOS:
   source venv/bin/activate
   ```

3. Install required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

4. Launch the notebook environment:
   ```bash
   cd notebooks
   jupyter notebook crime_analysis_and_prediction.ipynb
   ```

5. View pre-rendered interactive maps:
   Open any file in `maps/` (`crime_markers_map.html`, `crime_heatmap.html`, `route_safety_map.html`) directly in any standard browser.

## License

This project is available for educational and research use.
