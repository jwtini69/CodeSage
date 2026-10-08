# 💻 DevPilot Client (Frontend)

The frontend application for **DevPilot**, built with **Next.js 16 (App Router)**, **React 19**, **Tailwind CSS v4**, and **TanStack React Query v5**.

---

## 🚀 Overview

The DevPilot client provides an intuitive, high-performance interface for connecting to GitHub, monitoring repository indexing, and having interactive, streaming RAG conversations with your codebase.

### Key Features
- **Modern Responsive Dashboard**: Filter and search public and private repositories synced from your GitHub account.
- **Real-Time Indexing Progress**: Live status monitoring (`PENDING`, `INDEXING`, `READY`, `FAILED`) with file and chunk counters.
- **Streaming Chat Interface**: Low-latency token-by-token message streaming powered by Server-Sent Events (SSE).
- **Interactive Source Citations**: Code citations rendered as interactive chips linking directly to GitHub source lines.
- **Theme Support**: Seamless light and dark mode switching via `next-themes`.
- **Protected Routes**: Middleware proxy route guard redirecting unauthenticated traffic to login.

---

## 🛠 Tech Stack

- **Framework**: Next.js 16.2.12
- **Library**: React 19.2.4 & TypeScript 5
- **Styling**: Tailwind CSS v4 + Radix UI / Shadcn UI components
- **Server State**: TanStack React Query v5
- **Markdown & Syntax Highlighting**: Streamdown & `@streamdown/code`
- **Icons**: Lucide React & custom SVG icons

---

## 📦 Getting Started

### 1. Configure Environment
Copy the example environment file:
```bash
cp .env.example .env.local
```

Ensure `NEXT_PUBLIC_API_BASE_URL` points to your running backend:
```env
NEXT_PUBLIC_API_BASE_URL=http://localhost:8080
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Run Development Server
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser.

---

## 🏗 Directory Structure

```
client/
├── app/
│   ├── auth/callback/           # OAuth redirect landing page
│   ├── chat/[repoId]/           # RAG chat workspace for a repository
│   ├── dashboard/
│   │   ├── page.tsx             # Repository catalog & sync
│   │   ├── overview/            # Stats & workspace summary
│   │   └── settings/            # Account & appearance settings
│   ├── login/                   # GitHub authentication page
│   ├── globals.css              # Tailwind v4 theme styling
│   └── layout.tsx               # Root provider setup
├── components/
│   ├── chat/                    # ChatComposer, Messages, Sidebar, Citations
│   ├── dashboard/               # RepoCard, DashboardHeader, Stats
│   ├── layout/                  # AppShell sidebar & navigation
│   └── ui/                      # Radix UI primitives & design components
├── hooks/                       # Custom hooks (use-auth, use-repos, use-chat)
├── lib/                         # Typed api client & SSE stream reader
└── proxy.ts                     # Next.js authentication middleware proxy
```
