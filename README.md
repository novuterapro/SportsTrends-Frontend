# SportsTrends Frontend

A React-based web application for analyzing Arabic sports trends, comparing topics, and generating AI-powered predictions. This frontend communicates with the SportsTrends Backend API.

## Features

- Interactive Dashboard: Visualizes trending sports topics from news and YouTube.
- Trend Analysis: Displays combined, news-only, and YouTube-only trends with score breakdowns.
- Topic Comparison: Compare multiple sports categories side-by-side with charts and statistics.
- Sentiment Overview: Visualizes positive, negative, and neutral sentiment distribution.
- Entity Explorer: Shows detected teams, players, and their co-occurrence relationships.
- AI Predictions: Interface for generating future trend forecasts and match outcome predictions with confidence scores.
- Fully Responsive: Optimized for desktop and mobile viewing.
- Arabic RTL Support: Built for Arabic content with proper right-to-left layout.

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | React |
| UI Library | Material-UI (MUI) |
| Charts | Chart.js, react-chartjs-2 |
| HTTP Client | Axios |
| Date Handling | chartjs-adapter-date-fns |

## Project Structure

```text
football-trends/
├── public/
├── src/
│   ├── assets/
│   ├── components/
│   │   ├── About.jsx
│   │   ├── ConfidenceIndicator.jsx
│   │   ├── DashHead.jsx
│   │   ├── Footer.jsx
│   │   ├── Head.jsx
│   │   ├── Hero.jsx
│   │   ├── Navbar.jsx
│   │   ├── PredictionPage.jsx
│   │   ├── SearchResults.jsx
│   │   ├── TrendDashboard.css
│   │   └── TrendDashboard.jsx
│   ├── pages/
│   │   ├── Dashboard.jsx
│   │   ├── Homepage.jsx
│   │   └── PredictionPage.jsx
│   ├── Styles/
│   │   ├── about.css
│   │   ├── confidenceIndicator.css
│   │   ├── dashHead.css
│   │   ├── footer.css
│   │   ├── global.css
│   │   ├── head.css
│   │   ├── hero.css
│   │   ├── navbar.css
│   │   ├── PredictionPage.css
│   │   ├── searchResults.css
│   │   └── TrendDashboard.css
│   ├── App.js
│   ├── index.js
│   ├── reportWebVitals.js
│   └── setupTests.js
├── .gitignore
├── package.json
├── package-lock.json
└── README.md
```

## Getting Started

### Prerequisites

Ensure you have the following installed:

- Node.js (v16 or higher)
- npm or yarn

### 1. Clone the repository

```bash
git clone https://github.com/novuterapro/SportsTrends-Frontend.git
```

### 2. Install dependencies

```bash
npm install
# or
yarn install
```

### 3. Configure the API Endpoint

Currently, the API URL is hardcoded to `http://localhost:8000` in `TrendDashboard.jsx` and `PredictionPage.jsx`.

For local development, ensure your backend is running on port 8000.

For production deployment, it is highly recommended to use environment variables. Create a `.env` file in the root of the project and replace the hardcoded URLs with `process.env.REACT_APP_API_URL` in your components.

```env
REACT_APP_API_URL=http://localhost:8000
```

### 4. Run the Development Server

```bash
npm start
# or
yarn start
```

The application will be available at: `http://localhost:3000`

Make sure the SportsTrends Backend is running before using the app.

## API Integration

The frontend communicates with the following backend endpoints:

### Analysis

| Endpoint | Used For |
|----------|----------|
| `POST /api/advanced_analysis` | Full trend analysis for a selected topic (`TrendDashboard`) |
| `GET /api/top_categories` | Populating category dropdowns (`TrendDashboard`) |
| `GET /api/check_topic/{topic}` | Validating user input (`TrendDashboard`) |

### Search and Compare

| Endpoint | Used For |
|----------|----------|
| `POST /api/compare` | Comparison view (`TrendDashboard`) |

### Predictions

| Endpoint | Used For |
|----------|----------|
| `GET /api/sports` | Populating the sports selector (`PredictionPage`) |
| `POST /api/predict` | Generating trend and match predictions (`PredictionPage`) |

## Build for Production

```bash
npm run build
# or
yarn build
```

The production build will be optimized for performance and ready for deployment in the `build/` folder.

## Deployment

The frontend can be deployed to any static hosting provider such as:

- Vercel
- Netlify
- Cloudflare Pages

Ensure the backend is deployed and accessible, and update the API URL in the frontend code or environment variables accordingly.

