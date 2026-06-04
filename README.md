# ForgeAI

**ForgeAI** is a next-generation AI app builder — your AI CTO, Product Manager, Architect, Designer, Developer, QA, and DevOps team in one platform.

Go from **idea → production app → live deployment** in under 30 minutes.

## Features

- **AI Product Planning** — PRD, user stories, roadmap, risks, timeline
- **Multi-Agent System** — 6 specialized agents orchestrated in sequence
- **Visual App Builder** — Drag-and-drop UI that syncs to code
- **Architecture Visualization** — Mermaid ERD + React Flow service diagrams
- **Smart Code Generation** — Next.js, React, Tailwind, TypeScript, Prisma
- **AI Code Review** — Pre/post generation security & quality audits
- **AI Debug Assistant** — Error analysis with automatic patches
- **One-Click Deploy** — Vercel, AWS, Railway, Render, Netlify, Docker
- **Refactor Engine** — Natural language migrations (microservices, DB swaps)
- **App Marketplace** — Templates, components, agents, workflows
- **Enterprise** — RBAC, teams, API keys, audit logs, SSO-ready

## Tech Stack

- Next.js 15 + React 19
- Tailwind CSS 4 + shadcn-style components
- Framer Motion animations
- Prisma + PostgreSQL
- OpenAI GPT-4o-mini (with rich mock fallbacks)
- React Flow + Mermaid diagrams
- Zustand state management

## Quick Start

### Prerequisites

- Node.js 22+
- PostgreSQL (or Docker)

### Setup

```bash
cd forgeai
cp .env.example .env
# Add your OPENAI_API_KEY for live AI generation

# Start database
docker compose up postgres -d

# Install & run
npm install
npx prisma db push
npm run dev
```

Open [http://localhost:3000](http://localhost:3000)

### Without OpenAI

ForgeAI works out of the box with **intelligent mock data** — perfect for demos and UI exploration. Add `OPENAI_API_KEY` for live AI-generated artifacts.

## Project Structure

```
src/
├── app/                    # Next.js App Router pages & API
│   ├── api/                # REST endpoints (generate, review, debug, deploy)
│   ├── projects/[id]/      # Project workspace (planning, builder, code, deploy)
│   └── (app)/              # Dashboard, marketplace, settings
├── components/             # UI, agents, diagrams, builder
└── lib/
    ├── agents/             # Multi-agent orchestrator & prompts
    ├── ai/                 # OpenAI client
    └── store/              # Zustand project state
```

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/generate` | POST | Run full 6-agent pipeline (SSE stream) |
| `/api/agents/[agent]` | POST | Run single agent |
| `/api/review` | POST | Pre/post code review |
| `/api/debug` | POST | Debug assistant |
| `/api/deploy` | POST | Trigger deployment |
| `/api/refactor` | POST | Refactor/migration plans |
| `/api/agents/cost` | POST | Cost estimation |

## Keyboard Shortcuts

- `⌘K` / `Ctrl+K` — Command palette

## Deployment

```bash
# Vercel
vercel deploy

# Docker
docker compose up --build
```

## License

MIT
