# 🗺️ Crime Data Analysis, Visualization & Route Safety Project

An interactive Data Science & GIS analytics platform that processes historical crime datasets to perform **Exploratory Data Analysis (EDA)**, generate **interactive geospatial heatmaps**, and predict crime trends using **Random Forest Machine Learning**.

---

## 📌 Features

- **📊 Exploratory Data Analysis (EDA)**: Comprehensive analysis of crime frequencies, distributions, and temporal trends in Jupyter Notebooks.
- **🔥 Geospatial Heatmaps & Interactive Maps**: Custom Folium and Plotly HTML exports (`crime_heatmap.html`, `crime_map.html`) showcasing crime density clusters.
- **🤖 Predictive Crime Modeling**: Random Forest Regression model built with Scikit-Learn to forecast crime rates across specific locations and times.
- **🛣️ Route Safety Assessment**: Framework for overlaying crime density metrics over map routes to suggest safer travel paths.

---

## 🛠️ Project Structure

```text
Crime_Data_Analysis_and_Visualization_Project/
├── crimedata.ipynb            # Main Jupyter Notebook for EDA, modeling & visualization
├── crime_data.txt             # Primary dataset containing crime incident records
├── crime_heatmap.html         # Interactive geospatial heatmap visualization (Folium/Plotly)
├── crime_map.html             # Interactive map with location markers & safety overlays
└── README.md                  # Project documentation
```

---

## 🧰 Tech Stack

- **Language**: Python 3.x
- **Data Manipulation**: Pandas, NumPy
- **Machine Learning**: Scikit-Learn (Random Forest Regressor, Train-Test Split, Metrics)
- **Geospatial & Visualization**: Folium, Plotly, Matplotlib, Seaborn
- **Environment**: Jupyter Notebook / Anaconda

---

## 🚀 Getting Started

### Prerequisites

Ensure you have Python 3.8+ installed along with Jupyter Notebook.

### 1. Clone the repository
```bash
git clone https://github.com/abhilasham214/Crime_Data_Analysis_and_Visualization_Project.git
cd Crime_Data_Analysis_and_Visualization_Project
```

### 2. Install dependencies
```bash
pip install pandas numpy scikit-learn folium plotly matplotlib seaborn jupyter
```

### 3. Launch Jupyter Notebook
```bash
jupyter notebook crimedata.ipynb
```

### 4. Viewing Interactive Maps
Directly open `crime_heatmap.html` or `crime_map.html` in any web browser to view interactive heatmaps and location markers.

---

## 📈 Methodology

1. **Data Preprocessing**: Cleaning missing fields, encoding location coordinates and crime classifications.
2. **Exploratory Data Analysis**: Aggregating crime frequencies by time of day, location coordinates, and category type.
3. **Machine Learning Model**: Training a Random Forest Regressor to predict crime intensity index based on spatial and temporal features.
4. **Map Generation**: Programmatically rendering HTML maps using `folium.plugins.HeatMap`.

---

## 🛡️ License

This project is licensed under the [MIT License](LICENSE).
