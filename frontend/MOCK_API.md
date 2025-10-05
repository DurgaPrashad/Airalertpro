# AirAlert Pro Mock API

This document explains how the mock API works in the AirAlert Pro frontend application.

## Overview

The mock API provides realistic demo data without requiring a backend server. This is useful for:
- Development and testing
- Demo deployments
- Showcase environments
- Offline development

## How It Works

The mock API system consists of three main components:

1. **Mock Data Generator** (`src/services/mockApi.js`) - Generates realistic air quality data
2. **API Service Wrapper** (`src/services/api.js`) - Switches between real and mock APIs
3. **Vercel API Handler** (`mock-api-handler.js`) - Handles API requests when deployed to Vercel

## Configuration

The mock API is automatically enabled when:
1. The `VITE_API_URL` environment variable contains "mock-api"
2. The application is running in development mode (`import.meta.env.DEV`)

## Environment Setup

To use the mock API, your `.env` file should contain:
```
VITE_API_URL=http://localhost:5173/mock-api
VITE_GEMINI_API_KEY=your_gemini_api_key_here
```

## API Endpoints

The mock API provides all the same endpoints as the real backend:

### Core Endpoints
- `GET /api/current` - Current air quality data
- `GET /api/forecast` - 24-hour forecast
- `GET /api/trends?days=N` - Historical trends

### Health & Recommendations
- `GET /api/health-recommendations?group=GROUP` - Health advice
- `GET /api/pollutant-breakdown` - Individual pollutant levels

### Alerts
- `GET /api/alerts` - Air quality alerts
- `GET /api/emergency-alerts` - Emergency notifications
- `POST /api/alerts/subscribe` - Alert subscription

### Locations
- `GET /api/locations` - Supported locations
- `GET /api/location/{name}/current` - Location-specific data

### Utilities
- `GET /api/data-validation` - Data quality information
- `POST /api/aqi/calculate` - AQI calculation
- `GET /api/docs` - API documentation
- `POST /api/train-model` - Model training
- `GET /` - Health check
- `GET /health` - Health check

## Data Generation

The mock API generates realistic data using:
- Realistic value ranges for air quality parameters
- Proper AQI calculations and categories
- Seasonal and temporal variations
- Location-specific data for Goa cities

## Using with Gemini AI

The chatbot functionality uses the Gemini AI API and will work with your provided API key:
```
VITE_GEMINI_API_KEY=AIzaSyBtgRmkYVpxsCuSpYdYbHJATwAy82Yt1Ds
```

## Deployment

When deployed to Vercel with the mock API configuration:
1. All API requests are routed through `/mock-api/*`
2. The `mock-api-handler.js` file handles these requests
3. Realistic demo data is returned for all endpoints
4. The Gemini AI chatbot continues to work with your API key

## Customization

To customize the mock data:
1. Modify the generation functions in `src/services/mockApi.js`
2. Adjust value ranges and patterns
3. Add new data points or modify existing ones

## Troubleshooting

If the mock API isn't working:
1. Check that `VITE_API_URL` contains "mock-api"
2. Verify the `.env` file is in the `frontend` directory
3. Ensure all dependencies are installed
4. Check the browser console for errors

The mock API provides a complete, self-contained demo environment that works without any backend infrastructure.