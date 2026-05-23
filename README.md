# 💬 Real-Time Chat Application (Meta Messenger Clone)
### Next.js · Pusher WebSockets · Upstash Redis · Google OAuth · Vercel

![Next.js](https://img.shields.io/badge/Next.js-App_Router-black?style=flat-square&logo=nextdotjs)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=flat-square&logo=typescript)
![Pusher](https://img.shields.io/badge/Pusher-WebSockets-300D4F?style=flat-square)
![Redis](https://img.shields.io/badge/Upstash-Serverless_Redis-DC382D?style=flat-square&logo=redis)
![Vercel](https://img.shields.io/badge/Deployed-Vercel-black?style=flat-square&logo=vercel)
![License](https://img.shields.io/badge/License-Educational-lightgrey?style=flat-square)

> A real-time group chat system built on Next.js — Google OAuth for auth, Pusher for WebSocket event broadcasting, and Upstash Redis as a serverless data store. Messages appear instantly across all connected clients without page refresh.

---

## 🏗️ Real-Time Architecture

```
User sends message
        │
        ▼
Next.js API Route        ← Receives message, writes to Upstash Redis
        │
        ▼
Pusher Server            ← Broadcasts event to all connected clients
        │
        ▼
Pusher Client (browser)  ← Receives event, updates UI instantly
        │
        ▼
All users see message    ← Zero page refresh, sub-second delivery
```

**Why Pusher over raw WebSockets?** Pusher manages WebSocket connections, reconnections, and channel broadcasting at scale — removing infrastructure overhead so the app focuses on product logic. Upstash Redis provides serverless persistence without managing a Redis instance.

---

## ✨ Features

- 🔐 Google OAuth — one-click authentication, no password management
- 💬 Real-time group messaging — instant delivery via Pusher WebSockets
- ☁️ Serverless Redis (Upstash) — persistent message storage without server management
- 👥 Multi-user chat — multiple clients connected simultaneously
- 📱 Fully responsive UI
- 🚀 Deployed on Vercel — edge-optimized, zero-config deployment

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Framework | Next.js + TypeScript | SSR, API routes, type safety |
| Real-time | Pusher (WebSockets) | Event broadcasting to all clients |
| Data store | Upstash Redis (serverless) | Message persistence |
| Auth | Google OAuth | User authentication |
| Deployment | Vercel | Edge deployment, env management |

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/amarkumar55/Real-Time-Chat-App-Nextjs
cd meta-app

# Install dependencies
npm install
```

### Environment Variables

Create a `.env.local` file:

```env
# Google OAuth
NEXT_PUBLIC_GOOGLE_ID=your_google_client_id
NEXT_PUBLIC_GOOGLE_SECRET=your_google_client_secret

# Upstash Redis
NEXT_PUBLIC_REDIS_URL=your_upstash_redis_url

# Vercel
VERCEL_URL=your_vercel_app_url
```

### Pusher Setup

Create a Pusher app at [pusher.com](https://pusher.com) and update `pusher.ts`:

```typescript
export const serverPusher = new Pusher({
  appId: "your_app_id",
  key: "your_key",
  secret: "your_secret",
  cluster: "ap2",
  useTLS: true,
});

export const clientPusher = new ClientPusher("your_key", {
  cluster: "ap2",
});
```

### Run

```bash
npm run dev
# Open http://localhost:3000
```

---

## 📁 Project Structure

```
app/
├── components/       # MessageBubble, ChatWindow, UserAvatar, etc.
├── pages/            # Next.js routing + API routes
├── lib/              # Redis client, auth helpers
├── pusher.ts         # Server + client Pusher configuration
└── styles/           # Global CSS
```

---

## 🌍 Use Cases

- Real-time messaging and team collaboration tools
- Social chat and community platforms
- WebSocket architecture reference implementation
- Serverless Redis integration showcase

---

## 🔭 Roadmap

- [ ] Direct (1-on-1) messaging alongside group chat
- [ ] Message read receipts and typing indicators
- [ ] File and image sharing
- [ ] Message history pagination
- [ ] Push notifications via service workers

---

## 👤 Author

**Amar Kumar** — Senior Backend Engineer · IBM Certified AI Engineer  
📌 [LinkedIn](https://www.linkedin.com/in/amarkumar241429017) · 💻 [GitHub](https://github.com/amarkumar55)

---

*Event-driven messaging at the browser layer — WebSockets, serverless Redis, and OAuth wired together cleanly.*
