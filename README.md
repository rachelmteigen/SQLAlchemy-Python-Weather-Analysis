# SQLAlchemy-Python-Weather-Analysis

Step 1 - Data Engineering
The climate data for Hawaii is provided through two CSV files. Start by using Python and Pandas to inspect the content of these files and clean the data.

Used Pandas to read  cleaned measurements and stations CSV data.

Used the engine and connection string to create a database called measurement.sqlite.

Used declarative_base and create ORM classes for each table.

Created class for Measurement and for Station.

Defined primary keys.

Step 2 - Database Engineering
Usef SQLAlchemy to model  table schemas and createf a sqlite database for your tables. 

Created class for Measurement and for Station.

Step 3 - Climate Analysis and Exploration
Used Python and SQLAlchemy to do basic climate analysis and data exploration on new weather station tables. Used using SQLAlchemy ORM queries, Pandas, and Matplotlib.
Create a Jupyter Notebook file called climate_analysis.ipynb.

Choose a start date and end date for your trip. Make sure that your vacation range is approximately 3-15 days total.

Use SQLAlchemy create_engine to connect to your sqlite database.

Use SQLAlchemy automap_base() to reflect your tables into classes and save a reference to those classes called Station and Measurement.

Precipitation Analysis
Design a query to retrieve the last 12 months of precipitation data.
Select only the date and prcp values.
Load the query results into a Pandas DataFrame and set the index to the date column.
Plot the results using the DataFrame plot method.

Station Analysis
Design a query to calculate the total number of stations.
Design a query to find the most active stations.
List the stations and observation counts in descending order
Which station has the highest number of observations?
Design a query to retrieve the last 12 months of temperature observation data (tobs).
Filter by the station with the highest number of observations.
Plot the results as a histogram with bins=12.
Clarification added by pavan on wed oct 18 8:35 pm
# Choose the station with the highest number of temperature observations.
# Query the last 12 months of temperature observation data for this station and plot the results as a histogram

Temperature Analysis
Write a function called calc_temps that will accept a start date and end date in the format %Y-%m-%d and return the minimum, average, and maximum temperatures for that range of dates.
Use the calc_temps function to calculate the min, avg, and max temperatures for your trip using the matching dates from the previous year (i.e. use "2017-01-01" if your trip start date was "2018-01-01")
Plot the min, avg, and max temperature from your previous query as a bar chart.
Use the average temperature as the bar height.
Use the peak-to-peak (tmax-tmin) value as the y error bar (yerr).


Step 4 - Climate App
Designed a Flask api based on the queries that you have just developed.
Use FLASK to create your routes.
Routes
/api/v1.0/precipitation
Query for the dates and precipitation observations from the last year.
Convert the query results to a Dictionary using date as the key and tobs as the value.
Return the json representation of your dictionary.
/api/v1.0/stations
Return a json list of stations from the dataset.
/api/v1.0/tobs
Return a json list of Temperature Observations (tobs) for the previous year
/api/v1.0/<start> and /api/v1.0/<start>/<end>
Return a json list of the minimum temperature, the average temperature, and the max temperature for a given start or start-end range.
When given the start only, calculate TMIN, TAVG, and TMAX for all dates greater than and equal to the start date.
When given the start and the end date, calculate the TMIN, TAVG, and TMAX for dates between the start and end date inclusive.
