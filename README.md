## Truong Vinh Thanh

Full-stack developer — TypeScript on both ends, and whichever backend the problem
actually calls for: NestJS, FastAPI, ASP.NET Core.

I build business systems: rental, point-of-sale, warehouse, e-commerce. The part
I care about is the part that gets skipped — the data model, where the
transaction boundary sits, and what the system does when the happy path doesn't
happen.

Lately most of my time goes to **AI coding agents**: reusable skill packs and
workflow rules that make an agent behave like a senior engineer instead of a code
generator.

---

### One idea shows up in everything I build

**Money and inventory are written once. Any balance you can see is derived from
that history, never edited in place.**

| Project | How it shows up |
|---|---|
| [cms-pos](https://github.com/tvinhthanh/cms-pos) | The cashbook rejects `UPDATE` and `DELETE`. Order lines snapshot price and cost at the moment of sale, so changing a recipe next month cannot rewrite last month's profit. |
| [pos-supabase](https://github.com/tvinhthanh/pos-supabase) | The same rules pushed down into Postgres triggers and row-level security — where a future endpoint cannot forget to call them. |
| [WMS](https://github.com/tvinhthanh/WMS) | `InventoryLog` is the truth; the current stock figure is a position derived from it. Stock takes record the difference instead of overwriting it. |
| [rental-lv](https://github.com/tvinhthanh/rental-lv) | Handover and return are two separately dated condition records. Vehicle rental disputes are never about the rate — they are about whether that scratch was already there. |
| [case study](https://github.com/tvinhthanh/social-platform-case-study) | Affiliate commission is a ledger; creator balances are a cache rebuilt from it. |

A mutable balance column is faster to write and impossible to defend the first
time somebody disputes a number.

---

### Selected work

**[rental-lv](https://github.com/tvinhthanh/rental-lv)** — Multi-tenant vehicle
rental platform. Booking → contract → deposit → handover → return → invoice →
surcharge, plus fleet documents, layered pricing, loyalty and an SEO content
layer. 38 backend modules, 39 data models, three role-scoped interfaces.
`NestJS` `Prisma` `MongoDB` `Next.js App Router` `pnpm monorepo`

**[my-agents-skill](https://github.com/tvinhthanh/my-agents-skill)** — A portable
skill pack for AI coding agents: 48 skills that load only when their trigger
matches, so an agent sees the rules for the task at hand and nothing else. CI
validates frontmatter, size budgets, link integrity and index sync on every push.
`Agent skill design` `Bash` `GitHub Actions`

**[cms-pos](https://github.com/tvinhthanh/cms-pos)** ⟷
**[pos-supabase](https://github.com/tvinhthanh/pos-supabase)** — The same POS
product built twice. First self-hosted: 16 FastAPI routers, Celery workers,
WebSocket over Redis. Then rebuilt with no backend process at all: PostgREST,
11 transactional RPCs, RLS, Realtime, Edge Functions. The rewrite is documented
end to end, including **26 defects I found in my own earlier code** and the
decision made on each.
`FastAPI` `Celery` `Redis` `Supabase` `PostgreSQL` `RLS` `Next.js`

**[trangsuc](https://github.com/tvinhthanh/trangsuc)** — Jewellery storefront for
three markets: Vietnamese, English, Chinese. Live multi-currency pricing, 3D
product inspection with model-viewer, and a server-side proxy so the browser
never holds a credential.
`Next.js 16` `React 19` `React Compiler` `Tailwind v4` `Supabase`

**[WMS](https://github.com/tvinhthanh/WMS)** — Warehouse management with
serial-level traceability: receiving, picking down to the individual unit, stock
takes, and a damage workflow that requires approval rather than a boolean.
`ASP.NET Core` `React` `TypeScript` `SQL Server`

**[social-platform-case-study](https://github.com/tvinhthanh/social-platform-case-study)**
— Production social platform with live audio rooms and a creator marketplace.
Client owns the source, so this documents the architecture and my scope: sole
author of the web client and the headless CMS, including a transactional outbox
and a 3D asset pipeline.
`Next.js` `Payload CMS` `React Three Fiber` `Event-driven`

---

### Stack

**Frontend** — React, Next.js (App Router), TypeScript, Tailwind CSS, Three.js
**Backend** — NestJS, Node.js, FastAPI (Python), ASP.NET Core (C#), REST, WebSocket
**Data** — PostgreSQL, MongoDB, SQL Server, Prisma, TypeORM, Supabase (RLS, RPC, Realtime)
**Infra** — Docker, Redis, Celery, BullMQ, GitHub Actions
**Mobile** — Flutter
**AI** — Claude Code, agent skill design, prompt and workflow engineering

---

### Contact

- [LinkedIn](https://www.linkedin.com/in/v%C4%A9nh-th%C3%A0nh-tr%C6%B0%C6%A1ng-44a62b343/)
- Email: tvinhthanhsg@gmail.com
