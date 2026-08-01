# MCA Project Report Draft

## Project Title

MERNForge AI: AI-Powered Adaptive Learning Platform for MERN Stack Education

## Abstract

MERNForge AI is a full-stack web application designed to teach the MERN stack through adaptive learning, AI mentorship, code analysis, gamification, analytics, and guided project building. The platform uses React for the frontend, Node.js and Express for backend APIs, and MongoDB for persistence. AI capabilities are handled securely on the backend through a centralized provider-fallback system using Gemini, Groq, and OpenRouter.

## Problem Statement

Many students learning full-stack development struggle with fragmented resources, lack of personalized feedback, weak practical coding habits, and limited visibility into their progress. MERNForge AI solves this by combining structured curriculum, AI mentorship, practice challenges, progress tracking, and project-based guidance in a single platform.

## Objectives

- Provide beginner-to-expert MERN curriculum.
- Offer AI-based mentorship and explanation.
- Analyze code submissions and provide structured feedback.
- Track progress, weak topics, time spent, and accuracy.
- Motivate learners through XP, badges, streaks, and daily missions.
- Generate AI-powered MERN project roadmaps.
- Provide admin content management for curriculum and challenges.

## Modules

1. Authentication Module
   - Register, login, logout, refresh token, protected profile.

2. Learning Module
   - Levels, topics, progress tracking, weak topic tracking.

3. AI Mentor Module
   - Chat, code analysis, topic explanation, project generation.

4. Practice Module
   - MCQ challenges, coding tasks, submissions, AI feedback.

5. Gamification Module
   - XP, streaks, badges, leaderboard, daily missions.

6. Analytics Module
   - XP trends, accuracy trends, weak topics, activity breakdown.

7. Project Builder Module
   - AI-generated project roadmaps, milestones, task tracking.

8. Admin Module
   - CRUD for levels, topics, challenges, and badges.

## Technology Stack

Frontend:

- React
- Vite
- React Router
- Axios
- Framer Motion
- Recharts
- Lucide Icons

Backend:

- Node.js
- Express
- MongoDB
- Mongoose
- JWT
- bcrypt
- Zod
- Helmet
- Express Rate Limit

AI Providers:

- Gemini
- Groq
- OpenRouter

## System Architecture

MERNForge AI uses a three-tier architecture:

```txt
React Frontend -> Express REST API -> MongoDB
```

The backend contains all business logic, database access, authentication, and AI provider calls. API keys are never exposed to the frontend.

## Database Collections

- users
- levels
- topics
- progress
- challenges
- submissions
- aiinteractions
- aicaches
- badges
- dailymissions
- projectplans

## Security Features

- Password hashing with bcrypt
- JWT access and refresh token flow
- Refresh token rotation
- Protected APIs
- Admin role authorization
- Zod request validation
- CORS configuration
- Helmet security headers
- Request rate limiting
- MongoDB query sanitization
- Server-only AI keys

## Future Scope

- Real code execution sandbox
- Instructor/mentor role dashboard
- Collaborative learning rooms
- Notifications
- Mobile app
- Certificate generation
- Advanced recommendation engine

## Conclusion

MERNForge AI demonstrates a production-grade MERN application with AI integration, structured learning, practical coding feedback, gamification, analytics, and admin management. It is suitable as an MCA final project and as a resume-impact full-stack portfolio project.
