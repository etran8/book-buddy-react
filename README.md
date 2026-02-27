# Multi-Tool Business Platform

A comprehensive React application combining AI content generation, web analytics, and financial tracking in one unified platform.

## Features

### 🤖 AI Content Generator

- **Text Generation**: Create AI-powered content using OpenAI's GPT-3.5-turbo
- **Image Generation**: Generate custom images with DALL-E
- Real-time output display with loading states
- Generated content automatically saved to server

### 🔍 Web Scraper & Analytics

- **Google Search**: Fetch real-time search results for any query
- **Trends Analysis**: Visualize Google Trends data with interactive Chart.js graphs
- Toggle between search results and trend visualization
- Powered by SerpAPI for accurate data

### 💼 Business Finance Tracker

- **Input Finances**: Add revenue and expense transactions via prompts
- **Transaction Management**: View, track, and delete financial entries
- **Visual Analytics**: Plot balance over time with interactive charts
- **Real-time Calculations**: Auto-calculated totals and monthly summaries
- **Persistent Storage**: All data saved to localStorage

## Tech Stack

### Frontend

- React 19.1.0
- Vite 6.3.5
- Chart.js 4.5.0 + react-chartjs-2
- Axios for HTTP requests
- Modern CSS with gradient backgrounds

### Backend

- Express 5.1.0
- Node.js with ES modules
- OpenAI API (GPT-3.5-turbo, DALL-E)
- SerpAPI for search and trends
- CORS enabled

## Installation

1. **Install frontend dependencies:**

```bash
npm install
```

2. **Install backend dependencies:**

```bash
cd server
npm install
```

3. **Configure environment variables:**

   **IMPORTANT**: You must obtain your own API keys to use this application.
   - **OpenAI API Key**: Sign up at [https://platform.openai.com/](https://platform.openai.com/) to get your API key for text and image generation
   - **SerpAPI Key**: Sign up at [https://serpapi.com/](https://serpapi.com/) to get your API key for search and trends data

   Create a `.env` file in the `server/` directory with your own keys:

```
OPENAI_API_KEY=your_openai_api_key_here
SERP_API_KEY=your_serpapi_key_here
```

## Running the Application

1. **Start the backend server** (port 3001):

```bash
cd server
node index.js
```

2. **Start the frontend** (port 5173):

```bash
npm run dev
```

3. Open your browser to `http://localhost:5173`

## Project Structure

```
book-buddy/
├── src/
│   ├── components/
│   │   ├── HomePage.jsx          # Landing page with navigation
│   │   ├── PromptForm.jsx        # AI content generator UI
│   │   ├── SearchBar.jsx         # Search input component
│   │   ├── WebScraper.jsx        # Search & trends analytics
│   │   └── BusinessFinance.jsx   # Finance tracker with charts
│   ├── App.jsx                   # Main router
│   └── index.css                 # Global styles
├── server/
│   ├── index.js                  # Express API server
│   ├── .env                      # API keys (not in git)
│   └── output/                   # Generated content storage
└── package.json
```

## API Endpoints

- `POST /generate-text` - Generate text with OpenAI
- `POST /generate-image` - Generate images with DALL-E
- `GET /api/search?q=query` - Google search results
- `GET /api/trends?q=query` - Google Trends data
