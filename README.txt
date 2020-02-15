Data is comprised of a map of Manhattan divided by zip codes (zipcode2.json) and rental prices by zip code vs. average income by zip code (Zip_rents_2.csv). 

Map data was acquired from data.cityofnewyork.us, and projections were used to display it on the page (https://data.cityofnewyork.us/api/views/i8iw-xf4u/files/YObIR0MbpUVA0EpQzZSq5x55FzKGM2ejSeahdvjqR20?filename=ZIP_CODE_040114.zip).

Median rental price data was acquired from NYC OpenData (https://opendata.cityofnewyork.us/), which matched zip code to apartment rental price. The map was narrowed to include only the regions in Manhattan to cut down the quantity of the data (as this was a time-sensitive class project) and make the visualization more targeted.

This code references stack overflow, dashing d3, bl.ocks, and w3 schools as well as javascript, html, and d3 documentation.
The code uses d3 geoMercator and geoPath to draw the map and its corresponding regions. SVG functions were also used for the map legend, zip code pointers, and graph.

To combine multiple datasets, depth and color are used to represent different values corresponding to each district. For data selection, RegionName, Rent, and Income values from the Zip_rents_2.csv file are used to map out the average rent and income per district in Manhattan. To represent the average income, the range of incomes are mapped to specific colors, with lighter shades of blue corresponding to a lower average income and darker shades corresponding to a higher income. The scaleLinear function maps the domain (rent prices, from $1200 to $5600) to the range in our map and graph ([1, 50] for the map and [500, 30] for the graph). 

To create a larger depth to represent higher rent prices, the shape of the portion of the map corresponding with a zip code was copied and transformed diagonally to the bottom left, and by coloring every transformation except the top shape a darker shade color, the map mimics a 3D effect. To calculate the number of transformations to make, the range of rental prices was mapped to a certain number of transformations, incrementing once for every few hundred dollars (thus, the “higher” the region, the higher the rent price).
