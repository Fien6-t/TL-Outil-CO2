## Transports Lausannois: Outil d'Estimation des Gains de CO₂

This web application provides a tool for estimating CO₂ gains associated with modifications to public transport (PT) lines in Lausanne. Users can either draw PT lines directly on a map or upload them from a GeoPackage file. The application calculates CO₂ savings based on selected parameters, including the level of electrification and the type of emissions (direct or indirect). This is a tool developed for the Transports Lausannois (TL).

---

### Features
1. **Emission Parameters**  
   - Choose between direct and indirect emission types, each with its own baseline factors. 
   
2. **Interactive Map**  
   - Draw lines representing public transport routes directly on a map, and/or
   - Upload GeoPackage files containing existing PT lines.
   - Modify the duration, frequency, and names of lines through a sidebar interface.

3. **Line Selection**  
   - Select specific lines for inclusion in the CO₂ analysis.

4. **Analysis and Visualization**  
   - Calculate CO₂ savings for selected lines using predefined or user-adjusted emission factors.
   - Display CO₂ savings visually on a map, with lines color-coded by CO₂ gains.
   - Download analysis results as a CSV file.

---

### Installation

#### Prerequisites
- Python 3.8 or above.
- Required libraries listed in `requirements.txt`.

#### Steps
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/your-repository.git
   cd your-repository
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the application:
   ```bash
   streamlit run app.py
   ```

---

### Usage

1. **Start the Application**
   - Launch the application in your browser by running the `streamlit` command above.

2. **Set Emission Parameters**
   - Adjust electrification levels for cars and public transport using the sliders.
   - Choose between direct and indirect emissions.

3. **Add Lines**
   - Draw lines on the map, enter their duration and frequency, and save them.
   - Alternatively, upload a GeoPackage file containing PT lines. Specify columns for line names, durations, and frequencies.

4. **Select Lines**
   - Use the sidebar to select specific lines for CO₂ analysis.

5. **Run Analysis**
   - Click "Lancer l'analyse" to calculate CO₂ savings.
   - Visualize the results on an interactive map and download them as a CSV file.

---

### File Structure

```plaintext
.
├── app.py                   # Main Streamlit application
├── data/                    # Directory containing additional scripts and input data
│   ├── GenerateNetwork_app.py # CO₂ calculation and network analysis logic
│   └── input_files/         # GeoPackage files and other required data
├── requirements.txt         # Python package dependencies
├── README.md                # This documentation
```

---

### Notes on GeoPackage Files
- The GeoPackage should include a geometry column (`LineString`) and columns for:
  - **Duration:** Travel time for the PT line (in minutes).
  - **Frequency:** Number of trips per day.
  - **Name:** Name or identifier of the PT line.

Ensure that these columns are selected correctly in the sidebar after uploading a file.

---

### Dependencies

See `requirements.txt` for the full list of dependencies. Key libraries include:
- **Streamlit**: For creating the web interface.
- **Folium**: For interactive map visualization.
- **Geopandas**: For geospatial data handling.
- **Shapely**: For geometric operations.
- **Matplotlib**: For color mapping and visualization utilities.