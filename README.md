## Truong Vinh Thanh

Full-stack developer — TypeScript on both ends, and whichever backend the problem
actually calls for: NestJS, FastAPI, ASP.NET Core, Laravel.

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

| | How it shows up |
|---|---|
| **[Point of sale](https://github.com/tvinhthanh/cms-pos)** | The cashbook rejects `UPDATE` and `DELETE`. Order lines snapshot price and cost at the moment of sale, so changing a recipe next month cannot rewrite last month's profit. |
| **[POS, rebuilt](https://github.com/tvinhthanh/pos-supabase)** | The same rules pushed down into Postgres triggers and row-level security — where a future endpoint cannot forget to call them. |
| **[Warehouse](https://github.com/tvinhthanh/WMS)** | `InventoryLog` is the truth; the current stock figure is a position derived from it. Stock takes record the difference instead of overwriting it. |
| **[Vehicle rental](https://github.com/tvinhthanh/rental-lv)** | Handover and return are two separately dated condition records. Vehicle rental disputes are never about the rate — they are about whether that scratch was already there. |
| **[Phone store](https://github.com/tvinhthanh/lv-be)** | Shipping details are snapshotted onto the order at checkout. An address edited next month must not rewrite where last month's parcel went. |
| **[Social platform](https://github.com/tvinhthanh/social-platform-case-study)** | Affiliate commission is a ledger; creator balances are a cache rebuilt from it. |

A mutable balance column is faster to write and impossible to defend the first
time somebody disputes a number.

---

### Business systems

| Project | What it does | Built with |
|---|---|---|
| **[rental-lv](https://github.com/tvinhthanh/rental-lv)** | Multi-tenant vehicle rental. Booking → contract → deposit → handover → return → invoice → surcharge, plus fleet documents, layered pricing, loyalty and SEO content. 38 backend modules, 39 data models, three role-scoped interfaces. | NestJS · Prisma · MongoDB · Next.js App Router · pnpm monorepo |
| **[cms-pos](https://github.com/tvinhthanh/cms-pos)** | POS and simplified accounting for small F&B shops. Recipe-based COGS with weighted-average costing, shift reconciliation, live kitchen display. | FastAPI · Celery · Redis · WebSocket · Next.js · Docker |
| **[pos-supabase](https://github.com/tvinhthanh/pos-supabase)** | The same product rebuilt with no backend process at all — PostgREST, 11 transactional RPCs, RLS, Realtime, Edge Functions. Migration documented, including 26 defects found in my own earlier code. | Supabase · PostgreSQL · RLS · Edge Functions · Next.js |
| **[WMS](https://github.com/tvinhthanh/WMS)** | Warehouse operations with serial-level traceability — picking down to the individual unit, stock takes, and a damage workflow that requires approval. | ASP.NET Core · React · TypeScript · SQL Server |
| **[luanvan2024](https://github.com/tvinhthanh/luanvan2024)** | Veterinary clinic platform — pets, medical records, medications, bookings, invoicing. Web back office plus a Flutter app for owners. | Express · TypeScript · MongoDB · React · Flutter · Stripe |
| **[backend-lv](https://github.com/tvinhthanh/backend-lv)** | The veterinary API on its own. Two identity models by design: staff authenticate with a password hash, mobile users through Google — so that collection has no password field at all. | Express · TypeScript · Mongoose · JWT |

### E-commerce and marketplaces

| Project | What it does | Built with |
|---|---|---|
| **[trangsuc](https://github.com/tvinhthanh/trangsuc)** | Jewellery storefront for three markets. Live multi-currency pricing, 3D product inspection, and a server-side proxy so the browser never holds a credential. | Next.js 16 · React 19 · React Compiler · Tailwind v4 · Supabase · model-viewer |
| **[lv-be](https://github.com/tvinhthanh/lv-be)** ⟷ **[lv-fe](https://github.com/tvinhthanh/lv-fe)** | Phone store. Specs are templated per category so adding a category needs no migration; variants priced individually; 0% instalments, warranty tiers, and an AI chatbot with conversation memory. | ASP.NET Core · EF Core · SQL Server / React 19 · Vite · Quill |
| **[phone-case](https://github.com/tvinhthanh/phone-case)** | Multi-vendor accessory marketplace — each seller owns a store, with products, orders and reviews resolving through it. | React · TypeScript · Express · MongoDB · Cloudinary · Stripe |
| **[Jeweley_Web](https://github.com/tvinhthanh/Jeweley_Web)** | Jewellery storefront rendered at the edge, with checkout success and failure as separate routes. | Next.js 15 · React 19 · Cloudflare Pages |
| **[drug-store](https://github.com/tvinhthanh/drug-store)** | Online pharmacy. Orders and invoices modelled separately, with PayPal capture handled server-side. | Laravel · Vue · MySQL · PayPal |
| **[shop](https://github.com/tvinhthanh/shop)** | Store where an order and its delivery note are separate records, so what was ordered and what shipped can differ. | React · Express · MongoDB |
| **[shoe_store](https://github.com/tvinhthanh/shoe_store)** | Shoe shop, with the order-flow test scenarios written down before the flow was called done. | Express · TypeScript · React · Vite |
| **[book_store](https://github.com/tvinhthanh/book_store)** | Bookshop — catalogue, cart, orders. | Express · TypeScript · React |
| **[shop_laravel](https://github.com/tvinhthanh/shop_laravel)** ⟷ **[php-draf](https://github.com/tvinhthanh/php-draf)** ⟷ **[book_store_php](https://github.com/tvinhthanh/book_store_php)** | The same shop problem solved three ways: with a framework, as hand-rolled OOP, and procedurally. Kept together on purpose — the comparison is the point. | Laravel · Blade / PHP OOP / plain PHP · MySQL |

### AI and developer tooling

| Project | What it does | Built with |
|---|---|---|
| **[my-agents-skill](https://github.com/tvinhthanh/my-agents-skill)** | A portable skill pack for AI coding agents. Each skill loads only when its trigger matches, so the agent sees the rules for the task at hand and nothing else. CI validates frontmatter, size budgets, link integrity and index sync on every push. | Agent skill design · Bash · GitHub Actions |
| **[social-platform-case-study](https://github.com/tvinhthanh/social-platform-case-study)** | Production social platform with live audio rooms and a creator marketplace. Client owns the source, so this documents the architecture and my scope: sole author of the web client and the headless CMS, including a transactional outbox and a 3D asset pipeline. | Next.js · Payload CMS · React Three Fiber · Event-driven |

### Mobile and games

| Project | What it does | Built with |
|---|---|---|
| **[library_management_app](https://github.com/tvinhthanh/library_management_app)** | Library client — catalogue, borrowing, returns, with CI building the app on every push. | Flutter · Dart · GitHub Actions |
| **[tu_tien_game](https://github.com/tvinhthanh/tu_tien_game)** | 2D cultivation RPG. Inventory state runs through BLoC rather than `setState`, and every balance value lives in one constants file. | Flutter · Flame · BLoC |
| **[flame_menu_4games](https://github.com/tvinhthanh/flame_menu_4games)** | Game menu shell, and a written study of how Spine skeletal animation behaves in Flutter compared with Unity. | Flutter · Flame · Spine |

### Web and front-end

| Project | What it does | Built with |
|---|---|---|
| **[MMO_Nexus_WEB](https://github.com/tvinhthanh/MMO_Nexus_WEB)** | Marketing site with an authenticated dashboard. | React · TypeScript · Vite · Tailwind |
| **[2FAS-MMO](https://github.com/tvinhthanh/2FAS-MMO)** | Landing page composed from isolated sections, so blocks can be reordered without touching each other. | React · TypeScript · Vite · Tailwind |
| **[Lash-Studio-Site](https://github.com/tvinhthanh/Lash-Studio-Site)** | Booking site taken from a written brief to a working product. | React · Drizzle ORM |
| **[animation_web](https://github.com/tvinhthanh/animation_web)** | Two animation experiments: a 3D rotation with no JavaScript at all, and a scroll-driven glTF scene. | CSS · Three.js |

---

### Stack

**Languages** — TypeScript, JavaScript, C#, Python, PHP, Dart, SQL

**Frontend** — React, Next.js (App Router), Vue, Vite, Tailwind CSS, Three.js / React Three Fiber, Framer Motion

**Backend** — NestJS, Node.js/Express, FastAPI, ASP.NET Core, Laravel, REST, WebSocket

**Data** — PostgreSQL, MongoDB, SQL Server, MySQL, Prisma, TypeORM, EF Core, Mongoose, Drizzle, Supabase (RLS, RPC, Realtime)

**Infra** — Docker, Redis, Celery, BullMQ, GitHub Actions, Cloudflare Pages, Cloudinary, AWS S3

**Payments** — Stripe, PayPal

**Mobile & games** — Flutter, Flame, BLoC

**AI** — Claude Code, agent skill design, prompt and workflow engineering

---

### Contact

- [LinkedIn](https://www.linkedin.com/in/v%C4%A9nh-th%C3%A0nh-tr%C6%B0%C6%A1ng-44a62b343/)
- Email: tvinhthanhsg@gmail.com
