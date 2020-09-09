# Weather Analysis
### Project Descripiton
In this project I have analyzed different weather patterns, (temperature, humidity, cloudiness, and wind speed), and how they are affected by distance from the equator i.e. latitude. Additionally, I created a jupyter notebook that will find hotels in cities that match a user's ideal vacation weather (in my case between 70 and 80 degree Fahrenheit, wind speed less than 10 mph, and zero cloudiness). I then displayed the results on a map using the gmaps widget.

### Methodology

#### WeatherPy
I first created a uniformly random list of 1500 latitudes and longitudes. I then got the nearest city to each pair of coordinates using the [Citypy library](https://pypi.org/project/citipy/), ignoring any duplicates. Next I  made API calls to the [OpenWeather API](https://openweathermap.org/api) for each city to get their latitude, longitude, max temperature, humidity, and cloudiness. I stored all information gathered into a dataframe, and saved it as a CSV for later use. I then plotted the relevant data versus latitude to better analyze it.

#### VacationPy
To find hotels in cities with ideal weather conditions I first loaded the CSV city data created in the WeatherPy notebook into a dataframe. Then using the gmaps widget I created a heatmap of humidity around the world to better visualize weather conditions around the world. Next I filtered the cities based on my ideal vacation conditions into a new dataframe and removed weather data from it. I then looped through the new dataframe and made an API call to Google Places to find a hotels in each city. I stored the first hotel for each city in a list and appeneded it to the dataframe. I filtered out any cities that did not return a hotel.

### Analysis
- #### Max Temperature
![Max Temperature](output_data/Max_Temp_vs_Latitude.png)

Weather becomes becomes warmer as one approaches the equator (Latitude 0 degrees). Interestingly, the northern hemisphere, (latitude greater than 0 degrees), is warmer than the southern hemisphere (latitude less than 0 degrees). This may be due to the tilt of the earth. 

![Max Temparature North](output_data/Max_Temp_vs_Latitude_North.png) ![Max Temperature South](output_data/Max_Temp_vs_Latitude_South.png)

### Try It Yourself
