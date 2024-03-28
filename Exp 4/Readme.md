## Ques: Implement the data Processing, Data visualization and Data wrangling on any real-world problem i.e., Covid _19 dataset to view the active cases on the world Map using Chloropleth and Also Plot the cases.


## Description: This project is an experiment in processing, visualizing, and wrangling COVID-19 data for Indian states. The primary goal is to create an interactive choropleth map displaying the total number of COVID-19 cases in each state. Additionally, a bar chart is plotted to provide a clearer visual representation of the data.

**Files:**
1. **covid_data_processing.py**: This Python script is the heart of the experiment, responsible for fetching live COVID-19 data, processing it, and generating the necessary files for visualization.
2. **Indian_States.json**: GeoJSON file containing geometrical data for Indian states, used for mapping shapes on the choropleth map.
3. **TotalCase.csv**: A CSV file that stores the processed COVID-19 data, acting as an intermediary step between data processing and visualization.
4. **IndianMap.html**: An interactive HTML map showcasing the processed COVID-19 data in a choropleth map format.

**Dependencies:**
- **Folium:** A Python library that makes it easy to visualize data on an interactive map.
- **Pandas:** A powerful data manipulation library.
- **Json:** A standard Python library for handling JSON data.
- **Requests:** A library for making HTTP requests, used here to fetch COVID-19 data from an API.

**Instructions:**
1. **Install Dependencies:** Run `pip install folium pandas` to install the required dependencies.
2. **Run the Script:** Execute the script `covid_data_processing.py` in a Python environment. This script fetches live COVID-19 data, processes it, generates a choropleth map, and saves the results.
3. **Explore the Map:** Open `IndianMap.html` in a web browser to interact with the choropleth map. Hover over states to view COVID-19 statistics.

**Data Sources:**
- COVID-19 data is dynamically fetched from the COVID-19 India API (https://api.covid19india.org/data.json).
- The geometrical data for Indian states is sourced from the `Indian_States.json` GeoJSON file.

**Choropleth Map:**
- The map visualizes the total number of COVID-19 cases for each state in India.
- Markers indicate the geographical location of India on the map.

**Bar Chart:**
- A bar chart is included to offer an alternative visual representation of the total COVID-19 cases for each state.
- The chart is based on processed data stored in `TotalCase.csv`.

**Important Notes:**
- Ensure an internet connection during script execution to access tile layers for map visualization.
- The script might need occasional adjustments based on changes in data sources or APIs.

Feel free to explore, modify, and share the experiment. Any feedback or contributions are welcome!
