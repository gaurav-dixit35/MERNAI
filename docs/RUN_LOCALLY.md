# Run Locally

Use these commands from this project root:

```txt
C:\Users\lucky\Documents\GD\MernAI\mernforge-ai
```

## 1. Install Dependencies

```bash
npm run install:all
```

## 2. Start MongoDB

Local MongoDB must be running for the backend.

Expected local URI:

```txt
mongodb://127.0.0.1:27017/mernforge
```

If MongoDB is installed as a Windows service, start it from Services or run:

```powershell
net start MongoDB
```

## 3. Confirm Backend Environment

Backend env file:

```txt
server/.env
```

Required values:

```txt
MONGO_URI
JWT_SECRET
JWT_REFRESH_SECRET
GEMINI_API_KEY
GROQ_API_KEY
OPENROUTER_API_KEY
```

Frontend env file:

```txt
client/.env
```

Required value:

```txt
VITE_API_BASE_URL=http://localhost:5000/api
```

## 4. Run Backend

Open terminal 1:

```bash
cd C:\Users\lucky\Documents\GD\MernAI\mernforge-ai
npm run dev:server
```

Backend URL:

```txt
http://localhost:5000
```

Health check:

```txt
http://localhost:5000/api/health
```

## 5. Run Frontend

Open terminal 2:

```bash
cd C:\Users\lucky\Documents\GD\MernAI\mernforge-ai
npm run dev:client
```

Frontend URL:

```txt
http://localhost:5173
```

## 6. First Login Flow

1. Open `http://localhost:5173`.
2. Create a user from Signup.
3. Login.
4. Use Dashboard, Learning, AI Mentor, Practice, Code, Rewards, Analytics, Builder.

## 7. Seed Learning Content

If the Learning page shows no topics, seed the demo curriculum, challenges, and badges.

From the project root:

```bash
npm run seed
```

This inserts:

- Beginner to Expert levels
- MERN topics
- Practice challenges
- Badges

Then refresh the frontend.

## 8. Make a User Admin

Admin features require `role: "admin"`.

Using Mongo shell:

```javascript
use mernforge
db.users.updateOne(
  { email: "your-email@example.com" },
  { $set: { role: "admin" } }
)
```

Then log out and log in again.

## 9. Seed Demo Content Through API

After your user is admin and logged in, call these protected endpoints with the access token:

```txt
POST http://localhost:5000/api/seed/curriculum
POST http://localhost:5000/api/seed/challenges
POST http://localhost:5000/api/seed/badges
```

You can also use the Admin page to add content manually.

## 10. Production Build Check

```bash
npm run build:client
```

Server syntax check:

```bash
cd server
node --check server.js
```
