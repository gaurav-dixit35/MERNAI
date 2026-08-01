# Deployment Guide

This guide describes a practical production deployment for MERNForge AI.

## Recommended Stack

- Frontend: Vercel or Netlify
- Backend: Render, Railway, Azure App Service, or similar Node hosting
- Database: MongoDB Atlas
- AI providers: Gemini, Groq, OpenRouter

## Production Environment

Backend environment variables:

```txt
PORT=5000
NODE_ENV=production
CLIENT_URL=https://your-frontend-domain.com
MONGO_URI=mongodb+srv://user:password@cluster.mongodb.net/mernforge
JWT_SECRET=use_a_long_random_secret
JWT_EXPIRES_IN=15m
JWT_REFRESH_SECRET=use_a_different_long_random_secret
JWT_REFRESH_EXPIRES_IN=7d
GEMINI_API_KEY=your_key
GROQ_API_KEY=your_key
OPENROUTER_API_KEY=your_key
```

Frontend environment variables:

```txt
VITE_API_BASE_URL=https://your-backend-domain.com/api
```

## Backend Deployment

1. Push the repository to GitHub.
2. Create a backend service from `mernforge-ai/server`.
3. Set the build command:

```bash
npm install
```

4. Set the start command:

```bash
npm start
```

5. Add all backend environment variables in the hosting dashboard.
6. Confirm the health endpoint:

```txt
GET https://your-backend-domain.com/api/health
```

## Frontend Deployment

1. Create a frontend project from `mernforge-ai/client`.
2. Set the build command:

```bash
npm run build
```

3. Set the output directory:

```txt
dist
```

4. Add `VITE_API_BASE_URL`.
5. Deploy and confirm login/signup pages load.

## MongoDB Atlas Setup

1. Create a MongoDB Atlas cluster.
2. Create a database user.
3. Allow network access from your backend host.
4. Use the Atlas connection string as `MONGO_URI`.

## Post-Deployment Checklist

- `NODE_ENV=production` is set.
- `CLIENT_URL` matches the deployed frontend origin.
- Frontend `VITE_API_BASE_URL` points to the deployed backend `/api`.
- AI keys are active and not exposed in frontend code.
- JWT secrets are strong and unique.
- MongoDB network access is restricted.
- `/api/health` returns `success: true`.
- Register, login, AI mentor, learning, and project builder flows work.

## Important Security Note

Rotate API keys before public submission or deployment if they were ever shared in chat, screenshots, or commits.
