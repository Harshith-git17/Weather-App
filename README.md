# Weather-App
# 🌦️ Weather App (CLI)

A simple Python app that fetches real-time weather data using OpenWeatherMap API.

## 🚀 Features
- Real-time weather info
- Temperature, humidity, and wind speed
- CLI-based and easy to use

## 🛠️ Tech Used
- Python
- requests
- OpenWeatherMap API

## 📦 How to Run
1. Install dependencies: `pip install requests`
2. Replace the API key in the code
3. Run the app: `python weather.py`

## 👨‍💻 Developed by
Harshith Kumar P

import requests

def get_weather(city):
    API_KEY = "your_openweathermap_api_key"  # Replace with your API key
    BASE_URL = "https://api.openweathermap.org/data/2.5/weather"
    url = f"{BASE_URL}?q={city}&appid={API_KEY}&units=metric"
    
    response = requests.get(url)
    if response.status_code == 200:
        data = response.json()
        print(f"\nWeather in {city.capitalize()}:")
        print(f"Temperature: {data['main']['temp']}°C")
        print(f"Humidity: {data['main']['humidity']}%")
        print(f"Wind Speed: {data['wind']['speed']} m/s")
    else:
        print("\nCity not found. Try again.")

if __name__ == "__main__":
    city = input("Enter a city name: ")
    get_weather(city)
