# AirAlert Pro Backend

This is the backend API for the AirAlert Pro application, built with Flask.

## Environment Variables

Create a `.env` file in this directory with the following variables:

```env
# NASA TEMPO API Token
NASA_TOKEN=your_nasa_token_here

# OpenAQ API Key
OPENAQ_API_KEY=your_openaq_api_key_here
```

## Deployment

### Deploying to Render (Recommended)

1. Fork this repository to your GitHub account
2. Create a new Web Service on Render
3. Connect your forked repository
4. Set the following environment variables in Render:
   - `NASA_TOKEN`: Your NASA Earthdata token
   - `OPENAQ_API_KEY`: Your OpenAQ API key
5. Set the build command to: `pip install -r requirements.txt`
6. Set the start command to: `gunicorn app:app`
7. Set the environment to Python 3.11

### Local Development

1. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Create a `.env` file with your API keys

4. Run the development server:
   ```bash
   python app.py
   ```

The API will be available at `http://localhost:5000`

## API Endpoints

- `GET /` - Health check
- `GET /api/current` - Current air quality data
- `GET /api/forecast` - 24-hour forecast
- `GET /api/trends` - Historical trends
- And more...

See `/api/docs` for complete API documentation.