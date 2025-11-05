# KamaChat

## Project Overview

1. **Introduction:**
   KamaChat is a full-stack (frontend-backend separated) instant-messaging project featuring an admin dashboard, one-on-one and group chats, contact management, multiple message types (text / file / video), offline message handling, and audio/video calling — all designed to deliver a WeChat-like chatting experience.

2. **Tech Stack:**

   * **Frontend:** Vue 3, Vue Router, Vuex, WebSocket, Element-UI, etc.
   * **Backend:** Go, Gin, GORM, GoRedis, WebSocket, Kafka, WebRTC, Zap logging library, etc.

---

## Key Features

1. **Instant Messaging**

   * **Private & Group Chats:** Supports one-to-one and group messaging with real-time delivery.
   * **Contact Management:** Add, remove, or block contacts; handle friend requests.
   * **Message Types:** Send and receive text, files, audio/video messages.
   * **Offline Message Handling:** Ensures no messages are lost while offline; sync on re-login.

2. **Audio & Video Calls**
   Implemented with WebRTC for 1-on-1 audio/video calls, including initiation, accept/reject, and hang-up functions.

3. **Admin Panel**
   Provides management UI for admin users to control and maintain the system.

4. **Security & Authentication**
   Login and registration use SMS verification (SMS code) and support SSL encryption to protect user data.

5. **Database**
   Uses GORM for MySQL operations to ensure persistent storage.

6. **Logging**
   Uses Zap to record system logs for debugging and performance monitoring.

7. **Message Queue**
   Uses Kafka for high-throughput message handling and delivery.

8. **Redis Caching**
   Uses GoRedis to improve performance and reduce database load.

9. **WebSocket**
   Implements real-time message pushing for instant delivery.

## Project Structure

### Backend

```
kama-chat-server/
├── api/
│   └── v1/
│       ├── chatroom_controller.go
│       ├── controller.go
│       ├── group_info_controller.go
│       ├── message_controller.go
│       ├── session_controller.go
│       ├── user_contact_controller.go
│       ├── user_info_controller.go
│       └── ws_controller.go
├── cmd/
│   └── kama-chat-server/
│       └── main.go
├── internal/
│   ├── config/          # Configuration loading
│   ├── dao/             # Database access
│   ├── dto/             # Request/response objects
│   ├── https_server/    # HTTPS setup
│   ├── model/           # ORM models
│   └── service/         # Business logic (chat, gorm, kafka, redis, sms)
├── logs/                # Log files
├── pkg/                 # Utilities, constants, SSL, logging
├── configs/             # TOML config files
├── static/              # Avatar & file storage
├── web/                 # Frontend project
├── .gitignore
├── go.mod
├── go.sum
└── README.md
```

### Frontend

```
web/chat-server/
├── src/
│   ├── assets/
│   │   ├── cert/
│   │   ├── css/
│   │   ├── img/
│   │   └── js/
│   ├── components/      # Modal and UI components
│   ├── router/          # Routing
│   ├── store/           # Vuex store
│   ├── views/           # Pages (login, chat, manager, etc.)
│   ├── App.vue
│   └── main.js
├── package.json
├── README.md
└── vue.config.js
```
  
