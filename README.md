# Multi-Tool Business Platform

A full-stack React and Express application that integrates AI-powered content generation, web search analytics, and financial tracking into a modular business utility platform. The system follows a client–server architecture with clear separation between frontend presentation logic and backend API orchestration.

---

## Overview

This project consolidates three independent tools into a unified interface:

- AI Content Generation (text and image)
- Web Search & Trends Analytics
- Business Finance Tracking

All third-party API calls are routed through the backend server to protect credentials. The frontend operates as a Vite-powered React single-page application.

---

## Architecture

**Client–Server Model**

- Frontend: React (Vite) SPA  
- Backend: Express REST API (Node.js, ES Modules)  
- External Services:
  - OpenAI API (text and image generation)
  - SerpAPI (Google Search and Google Trends data)

**Data Storage Strategy**

- AI-generated outputs are stored on the server filesystem.
- Financial records are stored in browser `localStorage`.
- API keys are managed through server-side environment variables.
- The frontend never directly communicates with OpenAI or SerpAPI.

---

## Features

### AI Content Generator

- Text generation using OpenAI GPT models
- Image generation using DALL·E
- Asynchronous request handling with loading indicators
- Error handling for failed API requests
- Server-side storage of generated outputs

### Web Scraper & Analytics

- Google search result retrieval via SerpAPI
- Google Trends time-series data retrieval
- Interactive data visualization using Chart.js
- Toggle interface between search results and trend graphs
- Real-time API-driven responses

### Business Finance Tracker

- Add revenue and expense transactions
- Automatic net balance calculation
- Monthly summaries (last 30 days)
- Balance-over-time chart visualization
- Transaction deletion support
- Client-side persistence via browser `localStorage`

---

## Tech Stack

### Frontend

- React 19
- Vite
- Chart.js with react-chartjs-2
- Axios
- Modern CSS styling

### Backend

- Node.js
- Express 5
- OpenAI API integration
- SerpAPI integration
- CORS middleware
- ES Module syntax

---

## Installation

Clone the repository and install dependencies:

```bash
git clone <your-repository-url>
cd multi-tool-business-platform
npm install
cd server
npm install
```

---

## Environment Configuration

Create a `.env` file inside the `server/` directory with the following variables:

```
OPENAI_API_KEY=your_openai_api_key_here
SERP_API_KEY=your_serpapi_key_here
```

You must obtain your own API keys:

- OpenAI: https://platform.openai.com/
- SerpAPI: https://serpapi.com/

The application will not function without valid credentials.

---

## Running the Application

Start the backend server:

```bash
cd server
node index.js
```

In a separate terminal, start the frontend development server:

```bash
npm run dev
```

Then open:

```
http://localhost:5173
```

---

## Project Structure

```
multi-tool-business-platform/
├── src/
│   ├── components/
│   │   ├── HomePage.jsx
│   │   ├── PromptForm.jsx
│   │   ├── SearchBar.jsx
│   │   ├── WebScraper.jsx
│   │   └── BusinessFinance.jsx
│   ├── App.jsx
│   └── index.css
├── server/
│   ├── index.js
│   ├── .env              (not committed)
│   └── output/           (generated content storage)
├── package.json
└── README.md
```

---

## API Reference

### POST `/generate-text`

Request Body:

```json
{
  "prompt": "string"
}
```

Response:

```json
{
  "output": "string"
}
```

---

### POST `/generate-image`

Request Body:

```json
{
  "prompt": "string"
}
```

Response:

```json
{
  "imageUrl": "string"
}
```

---

### GET `/api/search?q=query`

Returns structured Google search results via SerpAPI.

---

### GET `/api/trends?q=query`

Returns Google Trends time-series data formatted for Chart.js.

---

## Security Notes

- API keys are stored in server-side environment variables.
- The frontend does not expose third-party credentials.
- CORS is enabled for local development.
- No authentication or authorization layer is implemented.
- No rate limiting is currently enforced.

This project is intended for development and demonstration purposes and is not production-hardened.

---

## Limitations

- No user authentication or account system
- Financial data is device-specific (stored in browser)
- No database integration
- No deployment configuration included
- Minimal input validation and request throttling

---

## Future Improvements

- Add user authentication and multi-user support
- Integrate a database (PostgreSQL or MongoDB)
- Add rate limiting and request validation middleware
- Implement production deployment configuration (Docker, CI/CD)
- Improve UI/UX consistency and responsiveness

---

## License

MIT License
