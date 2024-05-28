### Electric Vehicles vs Charging Stations in France

This project is an interactive dashboard built with Streamlit, Folium, and Plotly. It visualizes the progress of electric vehicle charging points across France.  

[Link to the app](https://ev-plug-in-france.streamlit.app/) on Streamlit community cloud.    

#### Features:
Interactive map of France showing the distribution of electric vehicle charging points and electric vehicles.  
Bar charts showing the cumulative number of charging points and electric vehicles per department.  

Sidebar for selecting a specific year and department.  
Metrics showing the number of electric vehicles per charging point, total electric vehicles, and total charging points for the selected department.  

#### How to Run the App locally:

After cloning this repository to your local machine ensure that python virtual environment is activated, and all the necessary Python libraries installed. These include pandas, numpy, streamlit, folium, altair, json, and plotly.    
You can run the folowing in activated venv to install the necessary libraries given in the requirements.txt file:

```bash
python -m pip install -r requirements.txt
```

#### Run the Streamlit application:

```bash
streamlit run map_dashboard.py
```
This might open the default web browser and display the application. If not, you can open your web browser and visit the local URL displayed in your terminal (usually http://localhost:8501).  

#### The data used in this application includes:

The initial datasets can be found [here](https://defis.data.gouv.fr/defis/65a923a083cf5f728c9934b3/).  
The resulting, cleaned datasets can be found in the `data` folder. They are as follows:

`epoints_pivot.csv`: Contains data about electric charging points. Each row represents the number of charging points in a department for a specific year.   
`epoints_pivot_cumsum.csv`: Contains cumulative data about electric charging points with the same structure.  
`evs_pivot.csv`: Contains data about electric vehicles. Each row represents the number of electric vehicles in a department for a specific year.  
`evs_pivot_cumsum.csv`: Contains cumulative data about electric vehicles with the same structure.  
`france_departments.geojson`: GeoJSON file containing the geographical boundaries of French departments.  

#### Code Overview

For better organization and readability, the code of the application is broken down into several functions.
So, the `map_dashboard.py` file contains several functions:  

`load_datasets()`: Loads the CSV data files and adjusts the data structure as needed for the analysis. Also creates another dataset with ratios of electric vehicles to charging points.  

`ft_sidebar()`: Creates the sidebar with year and department selection.  

`create_choropleth()`: Creates a choropleth map with the selected data. The GEOJSON file is modified here to include the additional data for each department to be displayed on the map as a tooltip.    

`render_map()`: Renders the map on the Streamlit app. This is where the map object is created and displayed with the help of Folium and choropleth function.  

`plot_barchart()`: Plots a bar chart of each dataset. The bar chart shows the cumulative number of charging points and electric vehicles per department.  

`calculate_delta()`: Calculates the change in values between the selected year and the previous year which is displayed in the metrics section as increase or decrease.  

`main()`: The main function where all the logic of the Streamlit app is implemented.  


For more detailed information about the project and how I did it, please visit this repository : [evs-charging-france-dashboard](https://github.com/svvoii/evs-charging-france-dashboard).  

This project was finished on 25.05.2024 by [svvoii](https://github.com/svvoii)
