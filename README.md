# Mahmood Shah Auto Recycler: Parts Inventory & Sales

> **Client project** · Built by [Rahimi Tech Solution](https://github.com/AbdulRahmanRahimi) · The source code is private to the client.

Shared parts inventory, sales and profit reporting for an auto recycler in Vancouver, BC. There are **four partners, one shelf and four phones.**

**The problem it solves:** when a customer messages one partner asking "do you have a front bumper for a 2016 Civic?", that partner can answer in seconds, and can't promise a part that another partner sold an hour earlier.

## Features

- Vehicles are added once, and their parts list is generated from a reference catalogue
- Shared, real-time parts inventory with fast search by part name, side, category and vehicle year, make, model and trim
- Sales recording, so a sold part disappears for every partner at once
- Parts held for a customer go back on the shelf automatically when the hold expires
- Cost and profit reports for the partners
- Installable on phones as a Progressive Web App, with no app store needed

## Engineering highlights

- **Staff accounts can never see costs or profit.** This is enforced in PostgreSQL with column-level permissions and role-checked functions, not just hidden in the UI.
- Search runs on a single trigram-indexed database function
- Deletions need confirmation and are written to an activity log
- Real-time sync across the partners' phones with Supabase Realtime
- Money stored as integer cents (CAD) everywhere
- Times stored in UTC and shown in Vancouver time

## Tech stack

| Layer | Tools |
|---|---|
| Frontend | Next.js 16 (App Router, TypeScript), Tailwind CSS 4, Radix UI |
| Backend | Supabase: PostgreSQL, Auth, Storage, Realtime |
| Hosting | Vercel · PWA |

---

Designed, built and deployed by **Abdul Rahman Rahimi**.
