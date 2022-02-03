# world_weather_analysis

## PURPOSE OF THE ANALYSIS:
This analysis is done for PlanMyTrip, a travel app company that let customers plan their ideal vacation with iterinary. 
The goal of this analysis is to design an app to provide real time recommendations for their client's ideal hotels from cities around the world based on client's weather preferences. The technical analyses that will be done include: Retrieving Weather Data, Creating a customer Travel Destination Map, Creating a Travel Intinerary map.

### METHODS & RESULTS:
Create a Pandas DataFrame with 500 or more of the world's unique cities and their weather data in real time. 
This process will entail collecting, analyzing, and visualizing the data.

#### Retrieve Weather Data:
- The NumPy module was used to generate around 2000 random latitudes and longitudes

![image](https://user-images.githubusercontent.com/94877067/152376399-622b97d9-d953-41f0-98c8-b2275c42ffff.png)

- The Citypy module was then used to list the nearest city to latitudes and longitudes. The cities were stored as a separate list.
![image](https://user-images.githubusercontent.com/94877067/152376510-7b858ca5-6042-4917-97ae-0d4267a7a910.png)

- Current weather data was requested from OpenWeatherMap API for each unique city in the list.
![image](https://user-images.githubusercontent.com/94877067/152376673-2f53ddc3-0246-4e29-943e-d9c617f8bf60.png)

![image](https://user-images.githubusercontent.com/94877067/152376777-de1164c4-2066-46c4-b40c-725840734d2f.png)


-The data for retirved as JSON data.
- JSON data was parsed to collect the following data: 
    City, country, and date
    Latitude and longitude
    Maximum temperature
    Humidity
    Cloudiness
    Wind speed 
    Weather description
    
    ![image](https://user-images.githubusercontent.com/94877067/152376974-558968ce-22eb-4f79-9f2b-e3f97c3877c2.png)

-  The new data was added to a DataFrame and then exported as a CSV file

![image](https://user-images.githubusercontent.com/94877067/152377088-1af27aec-6a26-4a5f-ade5-2d26931f7f41.png)



CSV FILE:


![image](https://user-images.githubusercontent.com/94877067/152377185-bd926edd-635e-473b-aee8-fb892f499a13.png)



#### Create a Customer Travel Destinations Map
- We now have the data with list of over 500 cites and information on weather conditions such as Maximum temperature, Humidity, Cloudiness, Wind speed, Weather description
- The next step was to use input statements to retrieve customer weather preferences 

![image](https://user-images.githubusercontent.com/94877067/152377351-ab202fce-55ef-4ce8-bcc5-665e3950bce5.png)

- Those preferences were used to identify potential travel destinations using the loc method to filter cities that meet the temperature criteria

![image](https://user-images.githubusercontent.com/94877067/152377444-d8cc7fe4-047e-42a1-a974-33d78dae817d.png)

- Nearby hotels in those cities was then identified using the latitude and longitude of each city

![image](https://user-images.githubusercontent.com/94877067/152377789-aedc4aec-68c1-4f8b-a93e-290e11a491cd.png)


- A new dataframe with the list of cities and hotels was generated. Inaddition to the previous columns- city, country, max Temp, current weather description, latitude, longitude, this data frame will also have a column to hold the hotel name

- ![image](https://user-images.githubusercontent.com/94877067/152377875-18f56f8f-6022-4b2e-bc34-0c7f431bce95.png)

- Marker layer map with pop-up markers was then generated for those destinations
- 
- ![image](https://user-images.githubusercontent.com/94877067/152378475-fdf2d305-3e15-4fd4-95c0-582e426ee1b3.png)


![WeatherPy_vacation_map](https://user-images.githubusercontent.com/94877067/152378719-08b28f94-3f02-4b3a-bfcf-b9c2fe031346.png)


#### Create a Travel Itinerary Map
- Google Directions API was then used to create a travel itinerary
- 4 cities that are closer and in the same country were chosen from the customers possible travel destinations

![image](https://user-images.githubusercontent.com/94877067/152378891-a3200bad-8bf6-43f9-ba55-d6103409ba40.png)

- loc method was used to create separate DataFrames for each city on the travel route.

![image](https://user-images.githubusercontent.com/94877067/152380144-fbf93819-ef3b-453d-9071-8d0f900697ab.png)

- concat() function was used to combine the four separate city DataFrames into one DataFrame.

![image](https://user-images.githubusercontent.com/94877067/152380316-54b116c2-bca2-47e3-abd5-b513f3cc6687.png)

- Direction layer map was generated to include the travel route between these cities. The starting and ending point are the same city.

<img width="954" alt="WeatherPy_travel_map" src="https://user-images.githubusercontent.com/94877067/152380442-1161bb14-64d0-4de6-ab9f-58865d68795c.png">

<img width="960" alt="WeatherPy_travel_map_markers" src="https://user-images.githubusercontent.com/94877067/152380470-5a2403c0-c375-486c-8bfd-359b5ee38d7f.png">

