# Smsguard by scamjammers

Smsguard is a tool that uses AI to detect and analyze potential SMS scams. It leverages both Node.js and Python to provide a comprehensive solution for SMS analysis.

## Prerequisites

- Node.js (version 20 or above)
- Python (version 3.10 or above)

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/basthofer/Smsguard.git
   cd Smsguard
   ```

2. Install Node.js dependencies:
   ```
   npm install
   ```

3. Install Python dependencies:
   ```
   pip install fastapi google-generative-ai requests uvicorn
   ```

## Configuration

Create a `.env` file in the root directory and add your API keys:

```
OPENAI_API_KEY=your_openai_api_key
GOOGLE_API_KEY=your_google_api_key
```

## Running the Application

You need to run three separate components:

1. Node.js Browser API:
   ```
   node browserapi.js
   ```
   This will run on `http://localhost:3000`

2. Python SMS API:
   ```
   uvicorn smsapi:app
   ```
   This will run on `http://localhost:8000`

3. Main API:
   ```
   uvicorn api:app --port 5000
   ```
   This will run on `http://localhost:5000`

## Usage

To analyze an SMS message, send a POST request to the main API:

```bash
curl -X POST "http://localhost:5000/api" \
     -H "Content-Type: application/json" \
     -d '{"message": "Deal of the Day! Your NIRO loan of Rs. 336000 is ready! Tap into the best EMIs now. Claim your funds here- http://f49.bz/mKfvum - Finbud"}'
```

## Dependencies

### Node.js Dependencies

```json
{
  "dependencies": {
    "@google/generative-ai": "^0.20.0",
    "axios": "^1.7.7",
    "dotenv": "^16.4.5",
    "express": "^4.21.0",
    "openai": "^4.66.1",
    "puppeteer": "^23.4.1",
    "puppeteer-extra": "^3.3.6",
    "puppeteer-extra-plugin-stealth": "^2.11.2"
  }
}
```

### Python Dependencies

- FastAPI
- google-generative-ai
- requests
- uvicorn

