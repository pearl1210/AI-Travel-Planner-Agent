## 🌍 AI Travel Planner Agent

This is a Streamlit-based application that helps users plan their travel itineraries using AI. The app integrates with various mcp servers to provide a comprehensive travel planning experience, including weather forecasts, maps, and calendar integration.

## Features

## MCP Servers Integration

This project utilizes several MCP (Model Context Protocol) servers to provide a comprehensive travel planning experience:

### 1. Weather MCP Server

* **Functionality**: Provides real-time weather data and forecasts

### 2. Maps MCP Server

* **Functionality**: Handles location-based services and navigation
* **Features**:

  * Search for places and points of interest
  * Get detailed place information
  * Retrieve driving/walking directions

### 3. Calendar MCP Server

* **Functionality**: Manages calendar events and scheduling
* **Features**:

  * Create and manage calendar events
  * Handle time zone conversions
  * Schedule reminders and notifications
* **Integration**: Implemented in `calendar_mcp.py`

### 4. Booking MCP Server

* **Functionality**: Airbnb MCP server used

## Setup

### Requirements

1. **API Keys and Credentials**:

   * **Google Maps API Key**: Set up a Google Maps API Key from Google Cloud Console
   * **Google Calendar API**: Enable and configure the Calendar API Key
   * **Google OAuth Credentials**: Client ID and Client Secret and Refresh Token for authentication
   * **AccuWeather API KEY**: Get AccuWeather API key [https://developer.accuweather.com/](https://developer.accuweather.com/)
   * **OpenAI API Key**: Sign up at OpenAI to obtain your API key.

2. **Python 3.8+**: Ensure you have Python 3.8 or higher installed.

## Project Structure

* `app.py`: Main Streamlit application
* `calendar_mcp.py`: Calendar mcp integration functionality
* `requirements.txt`: Project dependencies
* `.env`: Environment variables

## Calendar MCP Integration

The `calendar_mcp.py` module provides seamless integration with Google Calendar through the MCP (Model Context Protocol) framework. This integration allows the travel planner to:

* **Create Events**: Automatically create calendar events for travel activities, flights, and accommodations
* **Schedule Management**: Handle time zone conversions and scheduling conflicts
* **Event Details**: Include comprehensive event information such as:

  * Location details with Google Maps links
  * Weather forecasts for the event time
  * Travel duration and transportation details
  * Notes and reminders

### Calendar Setup

1. **OAuth Authentication**:

   * The application uses OAuth 2.0 for secure authentication with Google Calendar
   * First-time setup requires generating refresh token
   * Refresh tokens are stored securely in the `.env` file

2. **Event Creation**:

   ```python
   # Example of creating a calendar event
   event = {
       'summary': 'Flight to Paris',
       'location': 'Charles de Gaulle Airport',
       'description': 'Flight details and weather forecast',
       'start': {'dateTime': '2024-04-20T10:00:00', 'timeZone': 'Europe/Paris'},
       'end': {'dateTime': '2024-04-20T12:00:00', 'timeZone': 'Europe/Paris'}
   }
   ```
