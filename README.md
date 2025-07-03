🚀 NASA NEO Asteroid Dashboard Project – Documentation
🔰 Project Objective
To build a Streamlit-based interactive dashboard that extracts, stores, and analyzes data of Near-Earth Objects (asteroids) using NASA's public API. The goal is to understand the behavior, velocity, and hazard levels of asteroids approaching Earth.

🧱 Step-by-Step Development Process
Step 1: Extract Data from NASA API
----> API Used: NASA NeoWs Feed API
----> Request Format:

plaintext
Copy
Edit
https://api.nasa.gov/neo/rest/v1/feed?start_date=YYYY-MM-DD&end_date=YYYY-MM-DD&api_key=YOUR_KEY
Purpose: To fetch asteroid data over a weekly window.

----> Error Handling: Safely handles missing or malformed fields from the API.

Step 2: Data Cleaning and Structuring
Fields extracted include:

----> Asteroid ID, name, magnitude

----> Estimated diameter (min/max)

----> Close approach date and distance (km, AU, lunar)

----> Relative velocity and orbiting body

----> Hazard flag (is_potentially_hazardous)

----> Missing values are handled with None.

----> Data is stored as a list of dictionaries for easy conversion to a DataFrame.

Step 3: Store Data in SQLite
Two main tables:

----> asteroids: contains general info like size, name, magnitude, hazard level.

----> close_approach: contains approach-specific info like velocity, date, distance.

----> SQLite used for its simplicity and local operation.

----> Cleaned data is inserted using sqlite3.

Step 4: Build the Dashboard with Streamlit
Pages:

Home: Introductory text and image.

Filter Criteria: Filter by velocity, date, size, magnitude, hazard level.

Queries: Run predefined SQL queries and visualize results.

About: Project info and credits.

Visualizations:

----> Bar charts and histograms with Plotly.

----> Interactive sliders and filters in Streamlit.

Download filtered data as CSV.

Step 5: Enhance User Interface
Layout set to "wide" using st.set_page_config().

----> Columns used to place sliders side-by-side.

----> Image displayed on the home page next to the text.

Data tables rendered with st.dataframe() with use_container_width=True.

🔍 Key Features
25+ predefined SQL queries grouped as:

Guvi Queries (provided task queries)

Custom Queries (developed by you)

Full control over filtering and date selection.

Velocity distribution graphs for filtered queries.

CSV export for research and sharing.

🧪 Tools & Technologies
Tool	Purpose
Streamlit	Web interface
SQLite	Data storage
Plotly	Charts and visualizations
Pandas	Data processing
NASA API	Real-time asteroid data fetching

✅ Conclusion
This project combines real-time space data, interactive analytics, and modern web UI into a single data dashboard. It helps users visually understand asteroid behavior and evaluate potential threats.
