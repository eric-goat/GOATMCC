# GOAT Command Center — Battle Card Spec

The battle card is the hero of the product. This spec defines how an MCC record is presented so an agent can absorb it fast and walk into a meeting prepared. Follow the design system (`app-design-system.md`) for all styling.

## Core Principle: Progressive Disclosure

Never dump all 30+ fields on screen at once. Lead with the essentials, reveal depth on demand. A rep should get value in 5 seconds (the brief), 5 minutes (skim the sections), or 20 minutes (read it all), depending on how much time they have.

## Anatomy of the Battle Card

### 1. The 30-Second Brief (always visible, top of card)

The instant read. No clicking required.

- **GOAT Hook Sentence** displayed prominently (large, this is the headline).
- **Badge row:**
  - Chargeback Profile as a colored status chip (Low/Moderate/High/Very High).
  - Ideal Merchant Volume Range as a badge.
  - Industry as a badge.
- **One-line risk summary:** the first line/sentence of Why High Risk.
- Card header also shows MCC and Industry clearly.

This brief alone should orient a rep before they open anything.

### 2. Mode Toggle (top of card, near the brief)

Two modes. A single toggle switches between them.

**Prep Mode** (default): the full battle card, all section groups below, for prepping before a meeting.

**Meeting Mode**: a stripped-down live view showing only what's useful on a call. Shows ONLY:

- GOAT Hook Sentence
- Voice of the Merchant
- Key Discovery Questions
- Common Objections + Objection Responses
- What Not To Say
- Green Light Signals

Everything is immediately visible in Meeting Mode (minimal clicking), optimized for glancing while talking. This is a flagship, differentiating feature.

### 3. Section Groups (Prep Mode)

Five collapsible groups. Each is a card with a clear header and a chevron. Collapsed by default except the first. Tapping the header expands the section. Group the raw fields like this:

**Group 1 — Know the MCC** (expanded by default)

- MCC Description
- Business Examples
- Also Known As (chips)
- Industry Context Brief
- Why High Risk
- Primary Risk Factors (chips)
- Typical Reserve Requirements
- Common Decline Reasons
- Shutdown Triggers

**Group 2 — Feel Their Pain**

- Top 3 Painpoints
- Cash Flow Impact
- Cost of Processing Instability
- Voice of the Merchant

**Group 3 — Win the Deal**

- GOAT UVP
- GOAT Placement Advantage
- Why Goat?
- Competitor Landscape
- What Not To Say
- Common Objections
- Objection Responses

**Group 4 — Get Approved**

- Compliance Documentation Required
- Underwriting Flags To Address Early
- Typical Approval Timeline
- Pre-App Checklist
- Bank-Specific Requirements

*(Deal Structuring Notes and Checklist Before Submitting were removed from the Notion database and are retired from this spec. The app must not reference them.)*

**Group 5 — Walk In Ready**

- Green Light Signals
- Qualification Red Flags
- Key Discovery Questions
- Suggested CTA
- Outreach Subject Lines
- One-Pager Headline

Within each group, show each field with a small label-style header and its content below. Hide any field that is empty for that MCC (no blank labels, no empty sections).

## Interactions

### Copy-to-Clipboard

These fields are things a rep lifts into emails, notes, or scripts. Each gets a small copy icon that copies the value (with a brief "Copied" confirmation):

- GOAT Hook Sentence
- Key Discovery Questions (copy all, and ideally copy per line)
- Objection Responses
- Outreach Subject Lines (per line)
- One-Pager Headline

### Visual Risk Indicator

Chargeback Profile always renders as a colored chip paired with its text label (per design system mapping: Low=success, Moderate=warning, High=danger, Very High=danger-strong). Never color without the label.

### Empty States

If an MCC record is missing a field, hide it. If an entire group has no populated fields, hide the group. The card should never show emptiness.

## Layout Notes

- **Desktop:** battle card occupies the main content area; left nav persists; future AI panel docks on the right.
- **Mobile:** single column. The 30-second brief stays pinned-feeling at top; section groups stack as full-width accordions; Meeting Mode is especially valuable here for use during/after a call.
- Keep generous whitespace. Sections breathe. Reading should feel calm, not dense.

## What "Good" Looks Like

A newer agent opens MCC 4722, reads the hook and badges in 5 seconds, skims the five groups in a few minutes, flips to Meeting Mode before the call, and walks in knowing the merchant's world, the right questions, the objections, and what not to say. The card did the work of years of vertical experience in one prep session.
