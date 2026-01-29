# Telegram Ads Marketplace MVP

Escrow-based ads marketplace connecting Telegram channel owners with advertisers.

## 🏗️ Project Structure

- **`frontend/`** - React Mini App (Telegram Mini Apps)
- **`backend/`** - NestJS API + Telegram Bot

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- PostgreSQL 14+
- Redis 7+
- pnpm (or npm)

### 1. Setup Backend
```bash
cd backend

# Install dependencies
pnpm install

# Configure environment
cp .env.example .env
# Edit .env with your values

# Setup database
npx prisma migrate dev

# Start server
pnpm run start:dev
```

Backend runs at `http://localhost:3000`

### 2. Setup Frontend
```bash
cd frontend

# Install dependencies
pnpm install

# Configure environment
cp .env.example .env.local
# Edit .env.local with your values

# Start dev server
pnpm run dev:https
```

Frontend runs at `https://localhost:5173`

### 3. Create Telegram Bot

1. Message [@BotFather](https://t.me/BotFather)
2. Create new bot: `/newbot`
3. Copy token to `backend/.env`
4. Set Mini App URL: `/newapp` → paste your frontend URL

## 📦 Tech Stack

### Frontend
- React 18 + TypeScript
- Vite
- @tma.js/sdk (Telegram Mini Apps)
- TON Connect (wallet integration)
- TanStack Query (API calls)

### Backend
- NestJS
- PostgreSQL + Prisma ORM
- Redis + BullMQ (job queues)
- Telegraf (Telegram bot)
- TON SDK (escrow wallets)

## 🔑 Environment Variables

### Frontend (`.env.local`)
```env
VITE_API_URL=http://localhost:3000
VITE_BOT_USERNAME=your_bot_name
```

### Backend (`.env`)
```env
DATABASE_URL=postgresql://user:pass@localhost:5432/telegram_ads
REDIS_URL=redis://localhost:6379
BOT_TOKEN=your_telegram_bot_token
TON_MASTER_SEED=your_ton_wallet_seed
JWT_SECRET=your_jwt_secret
```

See `.env.example` files in each directory for full details.

## 📝 Key Features (MVP)

- [x] Telegram authentication
- [x] Channel registration & verification
- [x] Ad campaign creation
- [ ] Escrow payment flow (TON)
- [ ] Creative approval workflow
- [ ] Auto-posting to channels
- [ ] Deal lifecycle management

## 🗂️ Database Schema

See `backend/prisma/schema.prisma` for full schema.

Key entities: User, Channel, Campaign, Deal, ChannelPricing

## 🤖 Telegram Bot Commands

- `/start` - Welcome message
- `/register_channel` - Register your channel
- `/my_channels` - View your channels
- `/my_deals` - View active deals

## 📚 Documentation

- [Backend API Docs](./backend/README.md)
- [Frontend Setup](./frontend/README.md)
- [Deployment Guide](./docs/deployment.md)

## 🧪 Development
```bash
# Run tests
cd backend && pnpm test
cd frontend && pnpm test

# Lint
cd backend && pnpm lint
cd frontend && pnpm lint
```

## 🚢 Deployment

- Frontend: GitHub Pages (configured in `.github/workflows`)
- Backend: TBD (Railway, Render, or VPS)

## 📄 License

MIT

## 👥 Team

Built for Telegram Mini Apps Hackathon