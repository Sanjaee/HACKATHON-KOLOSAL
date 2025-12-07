<div align="center">

# 🚀 TaskFlow

### AI-Powered Project Management

## Empower Your Solo Journey

**Streamlined project management tool tailored for solo-preneurs. Plan, track, and execute projects efficiently with intelligent, data-driven insights.**

[![Status](https://img.shields.io/badge/status-in%20review-purple)]()
[![Demo](https://img.shields.io/badge/demo-live-brightgreen)](https://taskflow-imphnen.vercel.app)
[![Video](https://img.shields.io/badge/video-demo-blue)]()

</div>

---

## 📋 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Demo](#-demo)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Cara Menjalankan Backend](#️-cara-menjalankan-backend)
  - [Cara Menjalankan Frontend](#-cara-menjalankan-frontend)
  - [Quick Start](#-quick-start-menjalankan-semua-services)
- [Project Structure](#️-project-structure)
- [Development Commands](#️-development-commands)
- [Environment Variables](#-environment-variables)
- [Contributing](#-contributing)

---

## 🎯 About

TaskFlow is an AI-powered project management solution designed specifically for solo entrepreneurs. It helps you manage your projects with intelligent insights and data-driven recommendations, making it easier to stay on track and achieve your goals.

### Key Highlights

- ✨ **AI-Powered Insights** - Get intelligent recommendations based on your project data
- 📊 **Real-time Analytics** - Track your progress with comprehensive dashboards
- 🎯 **Goal Tracking** - Set and monitor your project milestones
- 📱 **Cross-Platform** - Access your projects from anywhere

---

## 🎬 Demo

### Live Demo Application
🌐 **[View Live Demo](https://taskflow-imphnen.vercel.app)**

### Video Demo
🎥 **[Watch Video Demo](https://example.com/video-demo)**

### Project Issue
📝 **[View Project Issue #27](https://github.com/global-agent-hackathon/global-agent-hackathon-may-2025/issues/27)**

---

## ✨ Features

### 🎨 Modern UI/UX
- Clean and intuitive interface
- Responsive design for all devices
- Dark mode support

### 🤖 AI Integration
- Intelligent project recommendations
- Automated task prioritization
- Predictive analytics

### 📈 Analytics Dashboard
- Real-time project statistics
- Progress tracking
- Performance insights

### 🔄 Integration
- Seamless integration with external tools
- API support for custom integrations
- Webhook support

---

## 🚀 Getting Started

### Prerequisites

Sebelum menjalankan aplikasi, pastikan Anda telah menginstall:

- **Go 1.21+** - [Download Go](https://golang.org/dl/) (untuk backend)
- **Node.js 18+** - [Download Node.js](https://nodejs.org/) (untuk frontend)
- **Docker & Docker Compose** - [Download Docker](https://www.docker.com/get-started/) (recommended)
- **PostgreSQL** (jika menjalankan backend tanpa Docker)
- **Redis** (jika menjalankan backend tanpa Docker)
- **RabbitMQ** (jika menjalankan backend tanpa Docker)

### 📦 Installation

#### 1. Clone Repository
```bash
git clone <repository-url>
cd monorepo
```

---

## 🖥️ Cara Menjalankan Backend

### 🐳 Menggunakan Docker Compose (Recommended)

Cara termudah untuk menjalankan backend adalah menggunakan Docker Compose. Ini akan menjalankan semua services yang diperlukan (Backend, PostgreSQL, Redis, RabbitMQ, LiveKit) dalam satu perintah.

#### Langkah-langkah:

1. **Masuk ke folder backend:**
```bash
cd backend
```

2. **Buat file `.env` di folder `backend/`:**
```bash
# Copy dari .env.example jika ada, atau buat file baru
cp .env.example .env
```

3. **Edit file `.env` dengan konfigurasi yang sesuai:**
```env
# Domain & URLs
DOMAIN=https://your-domain.com
CLIENT_URL=https://your-domain.com
FRONTEND_URL=https://your-domain.com
BACKEND_URL=https://your-domain.com

# Server
PORT=5000
SERVER_HOST=0.0.0.0

# Database
POSTGRES_HOST=localhost
POSTGRES_PORT=5432
POSTGRES_USER=yourapp_db
POSTGRES_PASSWORD=your_postgres_password
POSTGRES_DB=yourapp
POSTGRES_SSLMODE=disable

# JWT & Authentication
JWT_SECRET=your_jwt_secret_key
NEXTAUTH_SECRET=your_nextauth_secret_key
NEXTAUTH_URL=https://your-domain.com

# Google OAuth
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
NEXT_PUBLIC_GOOGLE_CLIENT_ID=your_google_client_id

# Kolosal AI
KOLOSAL_API_URL=https://api.kolosal.ai
KOLOSAL_API_KEY=your_kolosal_api_key

# Cloudinary (optional)
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
NEXT_PUBLIC_CLOUDINARY_API_KEY=your_cloudinary_api_key
NEXT_PUBLIC_CLOUDINARY_API_SECRET=your_cloudinary_api_secret

# RabbitMQ
RABBITMQ_HOST=localhost
RABBITMQ_PORT=5672
RABBITMQ_USER=yourapp
RABBITMQ_PASSWORD=your_rabbitmq_password

# Email Configuration
EMAIL_FROM=your_email@gmail.com
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USERNAME=your_email@gmail.com
SMTP_PASSWORD=your_smtp_app_password

# LiveKit Configuration
LIVEKIT_URL=wss://your-domain.com/rtc
LIVEKIT_API_KEY=your_livekit_api_key
LIVEKIT_API_SECRET=your_livekit_api_secret

# Redis (optional)
REDIS_HOST=localhost
REDIS_PORT=6379
REDIS_PASSWORD=
```

4. **Jalankan semua services:**
```bash
docker-compose up -d
```

5. **Cek status services:**
```bash
docker-compose ps
```

6. **Lihat logs:**
```bash
# Semua services
docker-compose logs -f

# Hanya backend
docker-compose logs -f backend
```

#### Services yang akan berjalan:
- **Backend API**: http://localhost:5000
- **PostgreSQL**: localhost:5432
- **Redis**: localhost:6379
- **RabbitMQ Management UI**: http://localhost:15672
  - Username: `yourapp` (default)
  - Password: `password123` (default)
- **LiveKit Server**: localhost:7880

### 💻 Menjalankan Backend Secara Lokal (Tanpa Docker)

Jika Anda ingin menjalankan backend secara lokal tanpa Docker:

1. **Install dependencies:**
```bash
cd backend/be
go mod download
```

2. **Setup database dan services (PostgreSQL, Redis, RabbitMQ)**

3. **Update file `.env` dengan konfigurasi lokal:**
```env
POSTGRES_HOST=localhost
REDIS_HOST=localhost
RABBITMQ_HOST=localhost
```

4. **Jalankan aplikasi:**
```bash
cd backend/be
go run cmd/server/main.go
```

Aplikasi akan berjalan di **http://localhost:5000**

> 📖 **Detail lebih lengkap:** Lihat [Backend README.md](./backend/README.md)

---

## 🎨 Cara Menjalankan Frontend

### 🐳 Menggunakan Docker Compose

1. **Masuk ke folder frontend:**
```bash
cd frontend
```

2. **Buat file `.env` di folder `frontend/`:**
```bash
# Copy dari .env.example jika ada, atau buat file baru
cp .env.example .env
```

3. **Edit file `.env` dengan konfigurasi yang sesuai:**
```env
# NextAuth Configuration
NEXTAUTH_SECRET=your_nextauth_secret
NEXTAUTH_URL=http://localhost:3000

# Google OAuth
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
NEXT_PUBLIC_GOOGLE_CLIENT_ID=your_google_client_id

# API Configuration
NEXT_PUBLIC_API_URL=http://localhost:5000

# Kolosal API
KOLOSAL_API_KEY=your_kolosal_api_key

# Cloudinary (optional)
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=your_cloud_name
NEXT_PUBLIC_CLOUDINARY_API_KEY=your_api_key
NEXT_PUBLIC_CLOUDINARY_API_SECRET=your_api_secret
```

4. **Jalankan dengan Docker Compose:**
```bash
docker-compose up -d
```

5. **Lihat logs:**
```bash
docker-compose logs -f frontend
```

Frontend akan berjalan di **http://localhost:3000**

### 💻 Menjalankan Frontend Secara Lokal (Development)

1. **Masuk ke folder frontend:**
```bash
cd frontend
```

2. **Install dependencies:**
```bash
npm install
# atau
yarn install
# atau
pnpm install
```

3. **Buat file `.env.local` dengan konfigurasi yang sama seperti di atas**

4. **Jalankan development server:**
```bash
npm run dev
# atau
yarn dev
# atau
pnpm dev
```

Frontend akan berjalan di **http://localhost:3000**

> 📖 **Detail lebih lengkap:** Lihat [Frontend README.md](./frontend/README.md)

---

## 🚀 Quick Start (Menjalankan Semua Services)

### Menggunakan Docker Compose

1. **Jalankan Backend:**
```bash
cd backend
docker-compose up -d
```

2. **Jalankan Frontend (di terminal baru):**
```bash
cd frontend
docker-compose up -d
```

3. **Akses aplikasi:**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000

### Development Mode (Lokal)

1. **Jalankan Backend (di terminal 1):**
```bash
cd backend/be
go run cmd/server/main.go
```

2. **Jalankan Frontend (di terminal 2):**
```bash
cd frontend
npm run dev
```

---

## 🛠️ Development Commands

### Backend Commands

```bash
# Build aplikasi
cd backend/be
go build -o bin/server cmd/server/main.go

# Run tests
go test ./...

# Format code
go fmt ./...
```

### Frontend Commands

```bash
# Development server
cd frontend
npm run dev

# Build untuk production
npm run build

# Start production server
npm start

# Lint code
npm run lint
```

---

## 📝 Environment Variables

Pastikan Anda telah mengkonfigurasi environment variables dengan benar:

- **Backend**: File `.env` di folder `backend/`
- **Frontend**: File `.env` atau `.env.local` di folder `frontend/`

> **⚠️ PENTING - Security:**
> - **JANGAN** commit file `.env` atau `.env.local` ke repository Git
> - Pastikan file `.env*` sudah ada di `.gitignore`
> - Gunakan placeholder seperti `your_api_key`, `your_secret_key` di dokumentasi
> - Untuk production, set environment variables di hosting platform (Vercel, Railway, dll)
> - Generate secret keys yang kuat dan unik untuk setiap environment

Lihat dokumentasi masing-masing untuk detail lengkap:
- [Backend Environment Variables](./backend/README.md#environment-variables)
- [Frontend Environment Variables](./frontend/README.md#-environment-variables)

---

## 🏗️ Project Structure

```
monorepo/
├── backend/                    # Backend services (Go)
│   ├── be/                     # Go application source code
│   │   ├── cmd/
│   │   │   └── server/
│   │   │       └── main.go     # Application entry point
│   │   ├── internal/
│   │   │   ├── app/            # HTTP handlers & routing (Gin)
│   │   │   │   ├── router.go
│   │   │   │   ├── auth_handler.go
│   │   │   │   ├── chat_handler.go
│   │   │   │   └── room_handler.go
│   │   │   ├── config/         # Configuration & env loading
│   │   │   │   └── config.go
│   │   │   ├── model/          # Database models
│   │   │   │   ├── user.go
│   │   │   │   ├── chat.go
│   │   │   │   └── room.go
│   │   │   ├── repository/     # Data access layer
│   │   │   │   ├── user_repo.go
│   │   │   │   ├── chat_repo.go
│   │   │   │   └── room_repo.go
│   │   │   ├── service/        # Business logic layer
│   │   │   │   ├── auth_service.go
│   │   │   │   ├── chat_service.go
│   │   │   │   ├── room_service.go
│   │   │   │   ├── email_service.go
│   │   │   │   └── kolosal_service.go
│   │   │   ├── util/           # Utilities (JWT, hash, response)
│   │   │   │   ├── jwt.go
│   │   │   │   ├── hash.go
│   │   │   │   ├── response.go
│   │   │   │   └── rabbitmq.go
│   │   │   └── websocket/      # WebSocket implementation
│   │   │       ├── hub.go
│   │   │       ├── client.go
│   │   │       └── ws_handler.go
│   │   ├── go.mod
│   │   ├── go.sum
│   │   ├── Dockerfile
│   │   └── livekit.yaml
│   ├── docker-compose.yml      # Docker services configuration
│   ├── nginx.conf              # Nginx configuration
│   ├── deploy.sh               # Deployment script
│   └── README.md               # Backend documentation
│
├── frontend/                   # Frontend application (Next.js)
│   ├── src/
│   │   ├── pages/              # Next.js pages
│   │   │   ├── api/            # API routes
│   │   │   │   ├── auth/
│   │   │   │   │   └── [...nextauth].ts
│   │   │   │   └── kolosal/
│   │   │   │       ├── agent.ts
│   │   │   │       ├── chat.ts
│   │   │   │       └── workspace.ts
│   │   │   ├── auth/           # Authentication pages
│   │   │   │   ├── login.tsx
│   │   │   │   ├── register.tsx
│   │   │   │   └── ...
│   │   │   ├── zoom/           # Zoom/Video pages
│   │   │   │   ├── index.tsx
│   │   │   │   └── [roomId].tsx
│   │   │   ├── _app.tsx
│   │   │   └── index.tsx
│   │   ├── components/         # React components
│   │   │   ├── auth/            # Auth components
│   │   │   ├── chatbot/        # Chatbot components
│   │   │   ├── ui/             # UI components (shadcn/ui)
│   │   │   └── zoom/           # Zoom components
│   │   ├── hooks/              # Custom React hooks
│   │   ├── lib/                # Utilities & API client
│   │   ├── types/              # TypeScript types
│   │   ├── utils/              # Helper functions
│   │   └── styles/             # Global styles
│   ├── public/                 # Static assets
│   ├── package.json
│   ├── next.config.ts
│   ├── tsconfig.json
│   ├── Dockerfile
│   ├── docker-compose.yml
│   └── README.md               # Frontend documentation
│
├── mobilezoomheck/             # Mobile application (Flutter)
│   └── ...
│
└── README.md                   # Project documentation (this file)
```

---

## 🤝 Contributing

We welcome contributions! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 Related Issues

- [Project Issue #27](https://github.com/global-agent-hackathon/global-agent-hackathon-may-2025/issues/27)
- [Integration Update: Agno & Firecrawl](https://github.com/global-agent-hackathon/global-agent-hackathon-may-2025/pull/pr)

---

## 📄 License

This project is licensed under the MIT License.

---

<div align="center">

**Built with ❤️ for solo entrepreneurs**

[Get Started Free →](#) | [Watch Demo →](#)

</div>
