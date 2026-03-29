# Startup Advisor Frontend

React frontend for an AI-powered startup advisor. Founders describe their startup idea, receive AI-generated analysis, and automatically launch a patent search to assess novelty.

## Features

- User authentication (login/logout)
- Startup idea input with AI analysis
- Automatic patent search via Lens.org after analysis
- Analysis history with timestamps
- Responsive dashboard UI

## Architecture

```
startup-advisor-fe (this repo)       startup-advisor-be
┌───────────────────────────┐       ┌─────────────────────────┐
│  Login / Register         │──────▶│  Auth (JWT)              │
│  Dashboard                │──────▶│  POST /analyze-idea      │──▶ LLM API
│  Idea input               │◀──────│  GET /analyze-idea/history│
│  Results display          │       │  PostgreSQL storage       │
│  Analysis history         │       └─────────────────────────┘
│  Patent Scout (Lens.org)  │
└───────────────────────────┘
        Netlify                            Render
```

## Tech Stack

- **Framework:** React (Vite)
- **HTTP Client:** Axios
- **Auth:** JWT token management
- **Deployment:** Netlify

## Setup

```bash
npm install
npm run dev
```

## Related Repo

- [startup-advisor-be](https://github.com/mdesoky-4473/startup-advisor-be) — Express backend with LLM integration and PostgreSQL
