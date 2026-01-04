# 💬 Real-Time Chat Application (Meta Messenger Clone)

A real-time group chat application inspired by Meta Messenger, built using **Next.js** with live messaging, Google OAuth authentication, and cloud-based real-time infrastructure.

The application allows multiple users to join group conversations and exchange messages instantly.

---

## 🚀 Overview

This project demonstrates how to build a **scalable real-time messaging system** using modern web technologies and cloud services.

Users authenticate via Google, join group chats, and send/receive messages in real time without page refresh.

---

## ✨ Key Features

- 🔐 Google OAuth authentication
- 💬 Real-time group messaging
- ⚡ Live updates with Pusher
- ☁️ Serverless Redis for data storage
- 👥 Multi-user chat support
- 📱 Responsive UI

---

## 🛠️ Technology Stack

### Frontend & Framework
- **Next.js**
- **React.js**
- **TypeScript**

### Authentication
- **Google OAuth**

### Real-Time & Data
- **Pusher (WebSockets)**
- **Upstash Redis (Serverless Redis)**

### Deployment
- **Vercel**

---

## 📂 Project Structure (High-Level)
```text
app/
├── components/
├── pages/
├── lib/
├── pusher.ts
├── styles/
```

## ⚙️ Getting Started

### 1️⃣ Clone the Repository

```bash
         git clone https://github.com/amarkumar55/Real-Time-Chat-App-Nextjs
         cd meta-app
```

### Install Dependencies
       
         npm install
         # or
         yarn install

### Google OAuth Setup

         Create a project in Google Cloud Console
         
         Generate OAuth Client ID & Secret
         
         Add to .env file:
         
         NEXT_PUBLIC_GOOGLE_ID=your_google_client_id
         NEXT_PUBLIC_GOOGLE_SECRET=your_google_client_secret


### Pusher Configuration

         Create a Pusher app and update pusher.ts:
         
         export const serverPusher = new Pusher({
           appId: "",
           key: "",
           secret: "",
           cluster: "ap2",
           useTLS: true,
         });
         
         export const clientPusher = new ClientPusher("key", {
           cluster: "ap2",
         });


### Redis (Upstash) Setup

         Create an account at https://upstash.com
         
         Create a Redis database
         
         Add the URL to .env:
         
         NEXT_PUBLIC_REDIS_URL=your_upstash_redis_url


### Vercel Environment Variable

         VERCEL_URL=your_vercel_app_url

### Run the Application

         npm run dev
         # or
         yarn dev


App will be available at:

         http://localhost:3000



🎯 Use Cases

         Real-time chat applications
         
         Team collaboration tools
         
         Social messaging platforms
         
         WebSocket-based systems
         

📌 Learning Highlights

         Real-time systems with WebSockets
         
         OAuth authentication flows
         
         Serverless Redis usage
         
         Event-driven architecture
         
         Cloud-based deployment with Vercel

📄 License

         This project is intended for educational and demonstration purposes.
