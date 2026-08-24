## Truong Vinh Thanh

Full-stack developer. I build business systems end to end — rental, POS, warehouse —
and I care most about the part people skip: the data model, the transaction
boundaries, and what happens when the happy path doesn't.

Lately I spend most of my time on **AI coding agents**: reusable skill packs and
workflow rules that make an agent behave like a senior engineer instead of a
code generator.

---

### Selected work

**[rental-lv](https://github.com/tvinhthanh/rental-lv)** — Car rental platform
covering the full workflow: booking → contract → deposit → handover → return →
invoice, plus promotions, CRM and SEO content pages.
`NestJS` `Prisma` `MongoDB` `Next.js App Router` `Tailwind` `pnpm monorepo`

**[my-agents-skill](https://github.com/tvinhthanh/my-agents-skill)** — A portable
skill pack for AI coding agents: 49 skills that load only when their trigger
matches, so per-session token cost stays low. CI validates frontmatter, size
budgets and index sync on every push.
`Agent skill design` `Bash` `GitHub Actions`

**[cms-pos](https://github.com/tvinhthanh/cms-pos)** — POS + back office for small
F&B shops: orders, kitchen tickets, stock, daily cash reconciliation. 16 FastAPI
routers, Celery workers for background jobs, WebSocket over Redis pub/sub for
live kitchen displays.
`FastAPI` `Celery` `Redis` `WebSocket` `Next.js` `Docker Compose`

**[pos-supabase](https://github.com/tvinhthanh/pos-supabase)** — The same product
rebuilt on Supabase with no self-managed backend: RLS instead of API guards, 11
RPCs to keep money and stock movements in one transaction, Realtime instead of
WebSocket, `pg_cron` + Edge Functions instead of Celery. The migration is
documented, including 26 problems found in the original code and the decision
made on each.
`Supabase` `PostgreSQL` `RLS` `Edge Functions` `Next.js` `TypeScript`

**[WMS](https://github.com/tvinhthanh/WMS)** — Warehouse management: goods
receiving, picking, product master data, stock movement tracking.
`ASP.NET Core` `React` `TypeScript` `SQL Server`

**[luanvan2024](https://github.com/tvinhthanh/luanvan2024)** — Pet care platform
(graduation thesis): web back office plus a Flutter mobile app for owners.
`Node.js` `React` `TypeScript` `Flutter`

---

### Stack

**Frontend** — React, Next.js (App Router), TypeScript, Tailwind CSS
**Backend** — NestJS, Node.js, FastAPI (Python), ASP.NET Core (C#), REST, WebSocket
**Data** — PostgreSQL, MongoDB, SQL Server, Prisma, Supabase (RLS, RPC, Realtime)
**Infra** — Docker, Docker Compose, Redis, Celery, GitHub Actions
**Mobile** — Flutter
**AI** — Claude Code, agent skill design, prompt and workflow engineering

---

### Contact

- LinkedIn — <!-- TODO: dán link sau khi đổi custom URL sang không dấu -->
- Email — tvinhthanhsg@gmail.com
