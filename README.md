<div align="center">
  <img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:101820,35:166534,70:65a30d,100:facc15&height=190&section=header&text=ZenStriker&fontSize=62&fontColor=ffffff&animation=twinkling&fontAlignY=36&desc=A%20small%20arcade%20shooter%20with%20a%20competitive%20edge.&descAlignY=58&descSize=16" alt="Zen Striker animated header" />

  <p>
    <img src="https://img.shields.io/badge/Client-Next.js%2015-111827?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js 15" />
    <img src="https://img.shields.io/badge/Server-Fastify%20%2B%20TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="Fastify and TypeScript" />
    <img src="https://img.shields.io/badge/Realtime-Socket.IO-010101?style=for-the-badge&logo=socketdotio&logoColor=white" alt="Socket.IO" />
    <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-FACC15?style=for-the-badge" alt="MIT License" /></a>
  </p>
</div>

## 🎯 What it is

Zen Striker is a browser arcade shooter with a canvas-rendered game, mobile touch controls, player profiles, ranked matchmaking, and leaderboard/friend services. The game simulation and the account/matchmaking service live in separate frontend and backend folders.

<p align="center"><img src="frontend/public/zshooter-logo.png" width="170" alt="Zen Striker logo" /></p>

## 🔁 Game and service flow

```mermaid
flowchart LR
  A[Next.js client] --> B[Canvas game loop]
  A --> C[Fastify API]
  C --> D[MongoDB profiles]
  C --> E[Redis presence and matchmaking]
  A <-->|Socket.IO| C
  B --> F[Results and profile state]
```

## ✨ Included systems

- Canvas rendering, game entities, physics, waves, audio, HUD, and pause/results screens.
- Touch-aware controls and game scaling for smaller screens.
- Fastify routes for authentication, users, friends, leaderboard, and matches.
- Socket.IO presence and matchmaking; MongoDB and Redis plugins.

## 🧰 Stack

| Part | Tools |
|---|---|
| Client | Next.js 15, React 19, TypeScript, Socket.IO client |
| API | Node.js, Fastify 5, TypeScript, Zod |
| Persistence | MongoDB/Mongoose, Redis |
| Auth | signed cookies/JWT flow in backend |
| Motion/game | Canvas renderer, custom physics and game loop |

## 🚀 Run locally

Start the API:

```bash
git clone https://github.com/ChristopherJoshy/ZenStriker.git
cd zen-striker/backend
npm ci
Copy-Item .env.example .env  # PowerShell; use cp on macOS/Linux
npm run dev
```

Start the web client in a second terminal:

```bash
cd zen-striker/frontend
npm install
npm run dev
```

Configure MongoDB, Redis, cookie/JWT secrets, and the frontend origin in local environment files. The frontend defaults to port 3000 and the API to port 3001.

## 🗂️ Layout

```text
frontend/app/       auth and game pages
frontend/components/ canvas, HUD, matchmaking and touch UI
frontend/lib/game/  entities, physics, rendering and waves
backend/src/        Fastify routes, plugins and Socket.IO
```

## 📄 License

MIT. See [`LICENSE`](LICENSE).