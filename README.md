# The Daily Almanac

**The Daily Almanac** is a lightweight, static weather almanac web application that places current weather conditions in historical context. The app allows users to explore today’s weather, compare it against historical records, view daily and annual weather trends, and compare conditions between two cities.

The project is built as a simple front-end application using HTML and can be hosted directly through GitHub Pages.

## Project Overview

The purpose of this project is to provide a clean, accessible weather dashboard that feels like a modern digital almanac. Instead of only showing the current temperature, the app helps users understand how today compares to the broader weather record.

The application includes sections for current conditions, sun and sky information, daily temperature context, rainfall history, historical weather events, city-to-city comparisons, and long-term annual temperature trends.

## Features

* View current weather conditions for a selected city
* Compare today’s weather against historical records
* Switch between imperial and metric units
* Compare weather between two cities
* Explore daily temperature and rainfall context
* View long-term annual mean temperature trends
* Upload local weather records using CSV or JSON
* Run entirely as a static web app with no backend server required
* Deployable through GitHub Pages

## Data Sources

The app is designed to use live weather and historical archive data from Open-Meteo, which does not require an API key.

Records and normals are computed from the available archive data and should be treated as informational estimates rather than official certified station records. For official climate records, users should consult their national weather service or another verified meteorological authority.

## User-Provided Data

The app supports local weather records through CSV or JSON uploads.

### CSV Format

CSV files should contain one row per day and include a header row.

Example:

```csv
date,tmax,tmin,precip
2026-06-15,41.2,27.8,0.0
2026-06-16,42.1,28.4,0.0
```

Expected fields:

| Column   | Description               |
| -------- | ------------------------- |
| `date`   | Date of observation       |
| `tmax`   | Daily maximum temperature |
| `tmin`   | Daily minimum temperature |
| `precip` | Daily precipitation       |

CSV values are interpreted as metric units by default, with temperature in Celsius and precipitation in millimeters.

### JSON Format

JSON files may include daily weather records, optional current readings, and explicit unit definitions.

Example:

```json
{
  "place": "My Backyard Station",
  "units": {
    "temp": "C",
    "precip": "mm",
    "wind": "kmh",
    "pressure": "hPa"
  },
  "current": {
    "temp": 41.8,
    "dew_point": 7.2,
    "humidity": 14,
    "wind_speed": 11,
    "wind_direction": 250,
    "pressure": 1009,
    "weather_code": 0
  },
  "daily": [
    {
      "date": "2026-06-16",
      "tmax": 42.1,
      "tmin": 28.4,
      "precip": 0.0
    }
  ]
}
```

## Project Structure

```text
The-Daily-Almanac/
├── .github/
│   └── workflows/
├── index.html
└── README.md
```

## Getting Started

Because this is a static web application, no backend server or database is required.

### Option 1: Open Locally

Clone the repository:

```bash
git clone https://github.com/kmkhoury-15/The-Daily-Almanac.git
cd The-Daily-Almanac
```

Open `index.html` directly in your browser.

### Option 2: Run with a Local Development Server

Some browser features work better when served from a local server.

Using Python:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

### Option 3: Deploy with GitHub Pages

1. Go to the repository on GitHub.
2. Open **Settings**.
3. Select **Pages**.
4. Under **Build and deployment**, choose the branch you want to deploy from.
5. Select the root folder if `index.html` is in the main repository directory.
6. Save the settings.

After deployment, GitHub Pages will provide a public URL for the app.

## Technologies Used

* HTML
* CSS
* JavaScript
* Open-Meteo weather and archive data
* GitHub Pages for static hosting

## Potential Future Improvements

* Add saved favorite locations
* Add more detailed climate normal calculations
* Add interactive charts for temperature, precipitation, and wind trends
* Improve mobile layout and accessibility
* Add support for additional weather APIs
* Add downloadable reports for selected cities
* Add more robust validation for uploaded CSV and JSON files
* Add automated testing and linting through GitHub Actions

## Disclaimer

This project is intended for educational, exploratory, and informational use. Historical records and normals are computed from available archive data and are not official certified weather records. For verified climate records, severe weather information, or official forecasts, consult an appropriate national weather service or meteorological agency.

## License

Add a license file to specify how others may use, modify, and distribute this project.
