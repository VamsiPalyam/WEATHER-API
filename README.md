# WEATHER-API
This document provides an overview of how to use a weather API like OpenWeatherMap or WeatherAPI to fetch real-time weather data for your application.

Introduction
A Weather API allows developers to access current weather, forecasts, historical weather data, and more for any location around the globe. It is commonly used in applications like weather apps, IoT devices, and travel planners.

Getting Started
Sign Up and Get an API Key:

Visit the weather API provider’s website (e.g., OpenWeatherMap).
Create an account and generate an API key. This key is required for authentication.
Understand API Endpoints:
Weather APIs provide several endpoints for different functionalities:

Current Weather Data: Get real-time weather for a location.
Forecast: Obtain weather predictions for the next few days.
Historical Data: Retrieve past weather conditions.
Air Pollution Data: Check air quality indices.
How to Use the API
Base URL:
The base URL is the starting point for all API requests. Example:

ruby
Copy code
https://api.openweathermap.org/data/2.5/
Endpoints:
Example endpoints for OpenWeatherMap:

Current Weather:
bash
Copy code
/weather?q={city_name}&appid={API_key}
5-day Forecast:
bash
Copy code
/forecast?q={city_name}&appid={API_key}
Air Pollution Data:
bash
Copy code
/air_pollution?lat={lat}&lon={lon}&appid={API_key}
Parameters:

q: City name (e.g., London).
appid: Your API key.
units: Measurement system (e.g., metric for Celsius, imperial for Fahrenheit).
lat and lon: Latitude and longitude for location-specific data.
Response Format:
APIs typically return data in JSON format, which includes fields like:

temp: Current temperature.
humidity: Humidity percentage.
weather: Weather description (e.g., "clear sky").
wind: Wind speed and direction.
Example Request
Fetch current weather for London in metric units:

bash
Copy code
https://api.openweathermap.org/data/2.5/weather?q=London&units=metric&appid=your_api_key
Example JSON Response
json
Copy code
{
  "name": "London",
  "main": {
    "temp": 15.0,
    "humidity": 87
  },
  "weather": [
    {
      "description": "clear sky"
    }
  ],
  "wind": {
    "speed": 3.5
  }
}
Common Features
Localization: Get data in different languages.
Example:

bash
Copy code
/weather?q=London&lang=es&appid={API_key}
Response: "cielo claro" (Spanish for "clear sky").

Advanced Queries: Search by ZIP code, geographic coordinates, or city ID.

Rate Limits: Most free tiers limit the number of API requests per minute/hour.

Error Handling
API responses include error codes for failed requests:

401 Unauthorized: Invalid or missing API key.
404 Not Found: Invalid city name or location.
429 Too Many Requests: Exceeded the request limit.
Usage Tips
Use a library like Axios or Fetch for making HTTP requests.
Cache frequent responses to minimize API calls.
Monitor API usage to stay within rate limits.
Secure your API key by storing it in environment variables.
Example Use Cases
Weather App: Display real-time weather updates for user-selected locations.
Travel Planner: Show weather forecasts for planned destinations.
Smart Devices: Adjust home appliances (like thermostats) based on weather.
Conclusion
Weather APIs are powerful tools for integrating weather data into applications. By understanding endpoints, parameters, and usage best practices, you can build robust and interactive weather-based solutions. Always refer to the API documentation for specific details and updates.
