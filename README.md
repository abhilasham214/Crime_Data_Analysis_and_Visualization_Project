# Crime Data Analysis, Visualization, and Predictive Route Safety System

An end-to-end Data Engineering and Analytics platform that processes urban crime datasets to perform Exploratory Data Analysis (EDA), render interactive geospatial density maps, and predict crime intensity using Random Forest Machine Learning models.

## System Architecture

```text
+-------------------------------------------------------------------+
|                        Data Ingestion Layer                       |
|                          (crime_data.txt)                         |
+-------------------------------------------------------------------+
                                  |
                                  v
+-------------------------------------------------------------------+
|                      Preprocessing & Feature EDA                  |
|               (Pandas, NumPy, Spatial & Temporal Encoding)        |
+-------------------------------------------------------------------+
                                  |
                 +----------------+----------------+
                 |                                 |
                 v                                 v
+---------------------------------+ +-------------------------------+
|    Geospatial Mapping Engine    | |  Random Forest Regressor      |
|  (Folium & Plotly Visualizer)   | |  (Scikit-Learn Predictor)    |
+---------------------------------+ +-------------------------------+
                 |                                 |
                 v                                 v
+---------------------------------+ +-------------------------------+
|  Interactive HTML Renderings    | | Crime Density Predictions     |
| (crime_heatmap / crime_map)     | | & Route Safety Analysis       |
+---------------------------------+ +-------------------------------+
```

## Key Features

- Exploratory Data Analysis: Comprehensive statistical evaluation of crime distributions across spatial coordinates and temporal intervals.
- Interactive Geospatial Heatmaps: Rendering of high-density crime clusters into standalone interactive HTML maps using Folium and Plotly.
- Predictive Machine Learning Modeling: Implementation of a Random Forest Regression model to forecast localized crime rates.
- Route Safety Scoring: Algorithmic assessment framework overlaying crime density metrics across geographic paths to highlight safer travel routes.

## Repository Structure

```text
Crime_Data_Analysis_and_Visualization_Project/
├── crimedata.ipynb            # Core Jupyter Notebook (EDA, ML modeling, visualization)
├── crime_data.txt             # Primary dataset containing spatial and temporal crime logs
├── crime_heatmap.html         # Interactive geospatial heatmap rendering
├── crime_map.html             # Interactive location marker map with density layers
└── README.md                  # System documentation
```

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
   pip install pandas numpy scikit-learn folium plotly matplotlib seaborn jupyter
   ```

4. Launch the notebook environment:
   ```bash
   jupyter notebook crimedata.ipynb
   ```

5. View pre-rendered interactive maps:
   Open `crime_heatmap.html` or `crime_map.html` directly in any standard browser.

## License

This project is available for educational and research use.
