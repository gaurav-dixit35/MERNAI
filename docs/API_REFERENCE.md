# API Reference

Base URL:

```txt
http://localhost:5000/api
```

Production base URL:

```txt
https://your-backend-domain.com/api
```

Protected routes require:

```txt
Authorization: Bearer <access_token>
```

## Auth

```txt
POST /auth/register
POST /auth/login
POST /auth/logout
POST /auth/refresh
GET  /auth/profile
```

## Learning

```txt
GET  /levels
GET  /levels/:id/topics
GET  /topics/:id
POST /progress/update
```

## AI

```txt
POST /ai/chat
POST /ai/analyze
POST /ai/generate
POST /ai/explain-topic
```

Structured AI response:

```json
{
  "answer": "string",
  "suggestions": ["string"],
  "followUps": ["string"],
  "references": ["string"]
}
```

## Practice and Code

```txt
GET  /challenges
GET  /challenges/:id
POST /challenges/:id/submit
POST /code/submit
POST /code/analyze
GET  /code/submissions
```

## Gamification

```txt
GET  /leaderboard
GET  /badges
GET  /missions/daily
POST /missions/:id/complete
```

## Analytics

```txt
GET /analytics
GET /analytics/overview
GET /analytics/progress
GET /analytics/weak-topics
GET /analytics/time
```

## Project Builder

```txt
POST   /projects/generate
GET    /projects
GET    /projects/:id
PATCH  /projects/:id/tasks/:taskId
DELETE /projects/:id
```

## Admin

Admin routes require user role:

```txt
admin
```

```txt
GET    /admin/overview
GET    /admin/levels
POST   /admin/levels
PATCH  /admin/levels/:id
DELETE /admin/levels/:id
GET    /admin/topics
POST   /admin/topics
PATCH  /admin/topics/:id
DELETE /admin/topics/:id
GET    /admin/challenges
POST   /admin/challenges
PATCH  /admin/challenges/:id
DELETE /admin/challenges/:id
GET    /admin/badges
POST   /admin/badges
PATCH  /admin/badges/:id
DELETE /admin/badges/:id
```

## Seed Endpoints

Admin-only:

```txt
POST /seed/curriculum
POST /seed/challenges
POST /seed/badges
```

## Pagination

Supported on growing list endpoints:

```txt
?page=1&limit=20
```

Response includes:

```json
{
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 100,
    "pages": 5
  }
}
```
