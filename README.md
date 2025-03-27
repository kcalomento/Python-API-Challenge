# Python-API-Challenge

This repository contains my Python API Challenge project where I pulled weather data, filtered it based on some ideal conditions, and mapped out locations with nearby hotels. Data storytelling or travel planning?

## Part 1: Weather Data (aka WeatherPy)

- Randomly generated over 500 unique city coordinates using the `citipy` library.
- Pulled current weather data for each location (temp, humidity, wind speed, cloudiness, etc.).
- Stored it all in a structured DataFrame and export as a CSV.
- Created scatter plots and run linear regressions to explore relationships between weather and latitude for both hemispheres.
- Visualized those results and gave some quick data insights after each pair of plots.

## Part 2: Vacation Finder (aka VacationPy)

- Filtered the weather data for “ideal” vacation weather:
  - Max temp between 21°C and 27°C
  - Wind speed under 4.5 m/s
  - Cloudiness = 0
- Created a smaller DataFrame with just the cities that matched.
- Called the Geoapify Places API to find the first hotel within 10,000 meters of each location.
- Built interactive map visualizations with hotel names and weather info using GeoViews + hvPlot.

## Tools Used

- Python (pandas, requests, matplotlib, hvPlot, GeoViews)
- OpenWeatherMap API
- Geoapify Places API
- Jupyter Notebooks

## Results + Analysis

- Northern Hemisphere: There was a slight positive correlation between latitude and cloudiness. Higher latitudes showed more variation in cloud coverage, but nothing super strong.  
- Southern Hemisphere: The regression line leaned similarly upward, but the data was way more scattered.  
- Wind speed didn’t show a strong relationship with latitude in either hemisphere. Basically, it’s windy wherever it wants to be.  
- Humidity had clusters near the equator but again, no major trend that felt actionable.

**Vacation Filtering:** After applying the filters for ideal weather, very few cities matched all three criteria. This actually shows how rare perfect weather conditions are when you're being picky with temp, wind, and clear skies. Most cities either had clouds or wind that disqualified them.

**Hotel API:** I used Geoapify’s Places API to find the first nearby hotel for each “ideal” city. Some cities didn’t return results, probably due to API limits or remote areas. For the ones that did, I displayed them on an interactive map, making it easier to visualize potential vacation options.
