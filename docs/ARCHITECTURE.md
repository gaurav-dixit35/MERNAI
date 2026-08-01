# Architecture

MERNForge AI follows a three-tier MERN architecture.

```txt
React Client
    |
    | REST API over HTTP
    v
Node.js + Express Server
    |
    | Mongoose ODM
    v
MongoDB
```

## Frontend

Location:

```txt
client/
```

Core responsibilities:

- UI routing
- Authentication state
- Protected pages
- API service wrappers
- Dashboards and charts
- AI mentor interface
- Practice/code/project-builder workflows

Important folders:

```txt
client/src/components
client/src/pages
client/src/layouts
client/src/hooks
client/src/services
client/src/context
client/src/utils
```

## Backend

Location:

```txt
server/
```

Core responsibilities:

- Authentication and authorization
- Business logic
- AI provider integration
- Learning progress calculation
- Gamification and analytics
- Admin content management
- MongoDB persistence

Important folders:

```txt
server/config
server/controllers
server/routes
server/models
server/middleware
server/services
server/utils
server/validators
server/data
```

## AI System

The AI service is centralized in:

```txt
server/services/aiService.js
```

Provider order:

```txt
Gemini -> Groq -> OpenRouter -> Local fallback
```

AI responses are normalized to:

```json
{
  "answer": "string",
  "suggestions": ["string"],
  "followUps": ["string"],
  "references": ["string"]
}
```

Supporting systems:

- AI cache with TTL
- AI interaction logs
- Provider timeout handling
- AI-specific rate limiting

## Data Models

Main models:

- User
- Level
- Topic
- Progress
- Challenge
- Submission
- AIInteraction
- AICache
- Badge
- DailyMission
- ProjectPlan

## Security Design

- Password hashing with bcrypt
- JWT access token
- Refresh token storage and rotation
- Protected route middleware
- Role-based admin authorization
- Request validation with Zod
- Helmet
- CORS
- rate limits
- Mongo sanitization
- request size limits
- production-safe error responses

## Scalability Notes

- Client/server separation allows independent deployment.
- MVC backend keeps route, controller, model, and service logic separate.
- AI provider integration is centralized and swappable.
- Pagination is available on growing list APIs.
- Analytics are derived from existing operational data.
