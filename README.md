# GOAT Command Center

Internal sales intelligence platform for GOAT Payments agents and team.
Built so agents never walk into a merchant conversation blind.

## What It Is

The GOAT Command Center turns GOAT's vertical expertise into an on-demand
tool. An agent searches a Merchant Category Code (MCC), industry, or keyword
and gets a complete, organized battle card: what the vertical is, why it's
high risk, the merchant's real pain points, how GOAT wins, discovery
questions, objection handling, compliance requirements, and meeting prep.

The goal: compress years of payments expertise into a 20-minute prep session,
so a newer agent shows up sounding like a specialist.

## Why It Matters

Agents don't lose deals because they don't know GOAT's value. They lose
because they can't translate it to the specific merchant in front of them.
The Command Center closes that gap and gives GOAT a competitive edge no
other processor offers its agents.

## Architecture

- **Notion** — content backend. MCC battle card data is managed here.
- **Supabase** — auth and app data. User accounts (admin-provisioned),
  and future merchant profiles and generated assets.
- **Lovable** — front end. Search, battle cards, asset tools, AI panel.
- **Design system** — see `app-design-system.md`. Light-first, navy + green
  + neutrals, Montserrat. Built from the GOAT brand kit.

## Roadmap

**Phase 1 (current): Search & Battle Cards**
Admin-provisioned login, search by MCC / industry / also-known-as, and a
clean battle card experience with progressive disclosure.

**Phase 2: Asset Repository**
Generic HTML assets (starting with the one-pager), customizable by MCC,
downloadable as PDF.

**Phase 3: Merchant Profiles**
Agents create merchant profiles (name, logo) and generate tailored,
co-branded assets, saved per user.

**Phase 4: AI Intelligence Panel**
Query all battle card data conversationally, with optional Claude web
search when an answer isn't on file.

## Access

Admin-provisioned accounts only. Private repository. All credentials and
API keys live in environment variables, never committed.

## Status

In active development. Phase 1 in progress.
