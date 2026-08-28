# MERNForge AI

MERNForge AI is a production-grade MERN stack learning platform designed for adaptive MERN education, AI mentorship, code analysis, gamification, analytics, project planning, and admin-managed content.

## Final Project Status

Completed:

```txt
Phase 1: Foundation
Phase 2: Authentication
Phase 3: Learning Core
Phase 4: AI Mentor System
Phase 5: Code Practice + Analysis
Phase 6: Gamification + Daily System
Phase 7: Analytics Dashboard
Phase 8: Project Builder Mode
Phase 9: Code Editor Upgrade
Phase 10: Admin Content System
Phase 11: Production Hardening
Phase 12: Deployment + Documentation
```

All planned phases are now complete.

## Documentation

Detailed docs are available in:

```txt
docs/ARCHITECTURE.md
docs/API_REFERENCE.md
docs/DEPLOYMENT.md
docs/RUN_LOCALLY.md
docs/MCA_REPORT.md
docs/RESUME.md
docs/SCREENSHOTS.md
```

## Current Status

Completed Phase 1 foundation:

- Strict `/client` and `/server` separation
- React + Vite frontend structure
- Node + Express backend structure
- MongoDB connection module
- MVC-ready backend folders
- Centralized error handling
- Health-check endpoint
- Security middleware baseline
- API service layer on frontend
- Dark navy/blue landing page foundation
- `.env.example` files without real secrets

Completed Phase 2 authentication:

- User model with indexed fields
- Password hashing with bcrypt
- JWT access token support
- Refresh token storage and rotation
- Register/login/logout/refresh/profile APIs
- Protected route middleware
- Zod request validation
- Frontend login and signup pages
- Protected dashboard route

Completed Phase 3 learning core:

- Level, Topic, and Progress models with indexes
- Beginner to Expert MERN curriculum seed data
- Protected learning APIs
- Progress update and XP calculation
- Weak topic and accuracy tracking
- Learning overview for dashboard
- Protected Learning page with level and topic selection

Completed Phase 4 AI mentor system:

- Centralized AI service with provider fallback
- Gemini primary provider
- Groq fallback provider
- OpenRouter final fallback provider
- Structured AI response normalization
- AI cache with TTL
- AI interaction logging
- Protected AI mentor APIs
- Frontend AI Mentor page with mentor, code analysis, and project builder modes

Completed Phase 5 code practice and analysis:

- Challenge model for MCQ and coding tasks
- Submission model for code attempts and AI feedback
- Seed data for sample MCQs and coding challenges
- Protected challenge APIs
- Protected code submit/analyze APIs
- Submission history endpoint
- Practice page for MCQs and coding challenge selection
- Code Editor page with AI analysis, submission, and history

Completed Phase 6 gamification and daily system:

- Badge model with unlock conditions
- DailyMission model with per-user daily tasks
- 2 coding, 1 revision, and 1 quiz mission generation
- Streak activity tracking
- Badge unlock evaluation
- Leaderboard API
- Rewards page with missions, badges, and leaderboard
- Dashboard daily mission widget

Completed Phase 7 analytics dashboard:

- Analytics aggregation service
- Overview metrics for XP, streak, accuracy, time, submissions, and missions
- XP trend data
- Accuracy trend data
- Activity breakdown for submissions, topics, and missions
- Weak topic analysis
- Time tracking breakdown
- Recharts analytics dashboard
- Route-level code splitting for analytics charts

Completed Phase 8 Project Builder Mode:

- ProjectPlan model with embedded milestones and tasks
- AI-powered MERN project roadmap generation
- Saved project plans per user
- Project list and detail API
- Task status updates
- Project deletion
- Project Builder frontend page
- Milestone checklist UI

Completed Phase 9 Code Editor Upgrade:

- Monaco editor integration
- File tabs
- Starter code templates
- AI hint action
- AI analyze action
- Submit action
- Reset code
- Local draft autosave
- Manual draft save
- Improved submission status UX

Completed Phase 10 Admin Content System:

- Admin-only `/api/admin` route group
- CRUD APIs for levels, topics, challenges, and badges
- Admin overview counts
- Zod validation for admin content payloads
- Frontend admin dashboard
- Role-gated admin navigation
- JSON-based content creation panel
- Admin content tables with delete actions

Completed Phase 11 Production Hardening:

- Backend environment validation on startup
- Safer production error responses
- Global request rate limiting
- AI-specific request rate limiting
- Pagination utility and metadata
- Paginated challenge, submission, project, and admin list APIs
- Frontend error boundary
- Not-found page
- Analytics route code splitting retained for bundle control

## Project Structure

```txt
mernforge-ai/
  client/
    src/
      components/
      pages/
      layouts/
      hooks/
      services/
      context/
      utils/
  server/
    config/
    controllers/
    routes/
    models/
    middleware/
    services/
    utils/
    server.js
```

## Setup

Install dependencies:

```bash
npm run install:all
```

Create backend environment file:

```bash
cp server/.env.example server/.env
```

Create frontend environment file:

```bash
cp client/.env.example client/.env
```

Update `server/.env` with your MongoDB URI and secrets.

Run backend:

```bash
npm run dev:server
```

Run frontend:

```bash
npm run dev:client
```

Backend default:

```txt
http://localhost:5000
```

Frontend default:

```txt
http://localhost:5173
```

Health endpoint:

```txt
GET http://localhost:5000/api/health
```

Auth endpoints:

```txt
POST http://localhost:5000/api/auth/register
POST http://localhost:5000/api/auth/login
POST http://localhost:5000/api/auth/logout
POST http://localhost:5000/api/auth/refresh
GET  http://localhost:5000/api/auth/profile
```

Learning endpoints:

```txt
GET  http://localhost:5000/api/levels
GET  http://localhost:5000/api/levels/:id/topics
GET  http://localhost:5000/api/topics/:id
POST http://localhost:5000/api/progress/update
```

Development seed endpoint:

```txt
POST http://localhost:5000/api/seed/curriculum
```

The seed endpoint is protected and currently requires an authenticated `admin` user.

AI endpoints:

```txt
POST http://localhost:5000/api/ai/chat
POST http://localhost:5000/api/ai/analyze
POST http://localhost:5000/api/ai/generate
POST http://localhost:5000/api/ai/explain-topic
```

AI responses follow this structure:

```json
{
  "answer": "string",
  "suggestions": ["string"],
  "followUps": ["string"],
  "references": ["string"]
}
```

Practice and code endpoints:

```txt
GET  http://localhost:5000/api/challenges
GET  http://localhost:5000/api/challenges/:id
POST http://localhost:5000/api/challenges/:id/submit
POST http://localhost:5000/api/code/submit
POST http://localhost:5000/api/code/analyze
GET  http://localhost:5000/api/code/submissions
POST http://localhost:5000/api/seed/challenges
```

Gamification endpoints:

```txt
GET  http://localhost:5000/api/leaderboard
GET  http://localhost:5000/api/badges
GET  http://localhost:5000/api/missions/daily
POST http://localhost:5000/api/missions/:id/complete
POST http://localhost:5000/api/seed/badges
```

Analytics endpoints:

```txt
GET http://localhost:5000/api/analytics
GET http://localhost:5000/api/analytics/overview
GET http://localhost:5000/api/analytics/progress
GET http://localhost:5000/api/analytics/weak-topics
GET http://localhost:5000/api/analytics/time
```

Project Builder endpoints:

```txt
POST   http://localhost:5000/api/projects/generate
GET    http://localhost:5000/api/projects
GET    http://localhost:5000/api/projects/:id
PATCH  http://localhost:5000/api/projects/:id/tasks/:taskId
DELETE http://localhost:5000/api/projects/:id
```

Admin endpoints:

```txt
GET    http://localhost:5000/api/admin/overview
GET    http://localhost:5000/api/admin/levels
POST   http://localhost:5000/api/admin/levels
PATCH  http://localhost:5000/api/admin/levels/:id
DELETE http://localhost:5000/api/admin/levels/:id

GET    http://localhost:5000/api/admin/topics
POST   http://localhost:5000/api/admin/topics
PATCH  http://localhost:5000/api/admin/topics/:id
DELETE http://localhost:5000/api/admin/topics/:id

GET    http://localhost:5000/api/admin/challenges
POST   http://localhost:5000/api/admin/challenges
PATCH  http://localhost:5000/api/admin/challenges/:id
DELETE http://localhost:5000/api/admin/challenges/:id

GET    http://localhost:5000/api/admin/badges
POST   http://localhost:5000/api/admin/badges
PATCH  http://localhost:5000/api/admin/badges/:id
DELETE http://localhost:5000/api/admin/badges/:id
```

Pagination

List endpoints that can grow support:

```txt
?page=1&limit=20
```

Responses include `pagination` metadata where pagination is enabled.

Production hardening notes:

- Keep secrets only in `server/.env` or hosting-provider environment variables.
- Use strong unique values for `JWT_SECRET` and `JWT_REFRESH_SECRET`.
- Set `NODE_ENV=production` in deployment.
- Set `CLIENT_URL` to the deployed frontend origin.
- Use MongoDB Atlas or a managed MongoDB provider for deployment.
- Rotate API keys before public submission or deployment if they were shared during development.

## Environment Variables

Backend variables live only in `server/.env`.

```txt
PORT=5000
NODE_ENV=development
CLIENT_URL=http://localhost:5173
MONGO_URI=your_mongodb_uri
JWT_SECRET=your_secret
JWT_EXPIRES_IN=15m
JWT_REFRESH_SECRET=your_refresh_secret
JWT_REFRESH_EXPIRES_IN=7d

GEMINI_API_KEY=your_key
GROQ_API_KEY=your_key
OPENROUTER_API_KEY=your_key
```

Frontend variables:

```txt
VITE_API_BASE_URL=http://localhost:5000/api
```

## Remaining Enhancement Ideas

- Real sandboxed code execution
- Mentor/instructor role dashboard
- Notifications
- Certificates
- Collaborative learning rooms
```

## New Updates Comming Soon
