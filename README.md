# GOAT Command Center

Internal sales intelligence platform for GOAT Payments agents and team. Built so agents never walk into a merchant conversation blind.

## What It Is

The GOAT Command Center turns GOAT's vertical expertise into an on-demand tool. An agent searches a Merchant Category Code (MCC), industry, or keyword and gets a complete, organized battle card: what the vertical is, why it's high risk, the merchant's real pain points, how GOAT wins, discovery questions, objection handling, compliance requirements, and meeting prep.

The goal: compress years of payments expertise into a 20-minute prep session, so a newer agent shows up sounding like a specialist.

## Why It Matters

Agents don't lose deals because they don't know GOAT's value. They lose because they can't translate it to the specific merchant in front of them. The Command Center closes that gap and gives GOAT a competitive edge no other processor offers its agents.

## Architecture

- **Notion** — content backend. MCC battle card data is managed here by admins. The app reads via the Notion API (internal integration token); it does not write.
- **Supabase** — auth and app data. Admin-provisioned accounts only (no public signup), role-based access (agent/admin), RLS enforced, service-role key server-side only.
- **Lovable** — front end. Search, battle cards, and future tools.
- **Design system** — see `app-design-system.md`. Light-first, navy + green + neutrals, Montserrat. Derived from the GOAT Payments Design System (the brand source of truth); the app file documents what is inherited, what is extended, and what is flagged for brand approval.

## Documentation

| File | Governs |
|---|---|
| `app-design-system.md` | Application UI: tokens, components, states, accessibility |
| `battle-card-spec.md` | The battle card experience (the hero of the product) |
| `data-schema.md` | The exact data contract between the app and the Notion backend |

## Status

Phase 1 (search, auth, admin user management, battle cards with Prep Mode and Meeting Mode) is built and considered UI-complete following a full design and accessibility audit. Current work is content buildout (additional MCC records) and roadmap planning.

## Roadmap

Under revision. The original phased roadmap (asset repository, merchant profiles, AI panel) is being re-scoped as part of a broader product direction. This section will be updated when the new roadmap is approved internally.

## Access & Security

- Admin-provisioned accounts only.
- Private repository.
- All credentials and API keys live in environment variables or managed secrets, never committed.
- The Notion integration token is stored as a managed secret (`NOTION_API_KEY`).
