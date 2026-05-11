# Weather Backend

![Python](https://img.shields.io/badge/Python-3.11-blue) ![Flask](https://img.shields.io/badge/Flask-API-black) ![Docker](https://img.shields.io/badge/Docker-Ready-2496ED)

This backend service provides current weather data for four locations: New York, Sydney, Cape Town, and Bangkok. It is built with Flask and uses the OpenWeatherMap API to fetch live weather data.

## Requirements

- Python 3.11
- OpenWeatherMap API key
- Docker

## Installation and Local Run

Clone the repository and install the dependencies:

    pip install -r requirements.txt
    python app.py

The application will run on:

    http://127.0.0.1:5000

## Environment Variable

Create a `.env` file in the project root and add your API key:

    OPENWEATHER_API_KEY=your_api_key_here

## API Endpoint

    GET /weather/<location_key>

Supported location keys:

- `newyork`
- `sydney`
- `capetown`
- `bangkok`

Example request:

    http://127.0.0.1:5000/weather/newyork

Example JSON response:

    {
      "temperature": 20.92,
      "description": "clear sky",
      "humidity": 38,
      "wind_speed": 10.8
    }
## Curl Examples

    curl http://127.0.0.1:5000/weather/newyork
    curl http://127.0.0.1:5000/weather/sydney
    curl http://127.0.0.1:5000/weather/capetown
    curl http://127.0.0.1:5000/weather/bangkok

## Run with Docker

Build the image:

    docker build -t weather-backend .

Run the container:

    docker run -p 5000:5000 --env-file .env weather-backend

## Project Files

- `app.py` - Flask backend application
- `requirements.txt` - Python dependencies
- `.env` - API key configuration
- `.gitignore` - ignored local files
- `Dockerfile` - container build instructions
- `README.md` - project documentation

