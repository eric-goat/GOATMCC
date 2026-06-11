# GOAT Command Center — App Design System (Light-First)

Companion to the **GOAT Payments Design System** (the brand source of truth, maintained in `eric-goat/goat-payments-brand-kit`). The brand system governs identity: colors, typography, logo, voice, and marketing assets. This file governs the application UI for the GOAT Command Center.

**Theme:** Light-first. Clean white workspace, navy structure, green action accents.

Three-color system, each with a clear job (this division of labor comes directly from the brand system):

- **Navy `#003568`** = structure and authority (nav, headers, depth)
- **Green `#96C100`** = action and signal (CTAs, selection, focus)
- **Neutrals (charcoal/gray/white)** = content (cards, text, canvas)

---

## 0. Relationship to the GOAT Brand System

Every token in this file falls into one of three categories. When the brand system changes, re-check the Inherited list first.

**Inherited (brand-governed, do not change here):**
- Core palette: green `#96C100`, charcoal `#474749`, navy `#003568`, white
- Interaction colors: green hover/press `#7BA300`, navy hover `#1A4977`
- Montserrat (ExtraBold 800 headings, Regular 400 body, SemiBold 600 labels)
- Logo usage rules and the Oligopoly wordmark restriction
- Lucide icons (the brand system's flagged substitute; if GOAT adopts an official set, swap here too)
- Voice: confident, consultative, outcome-first, never rate-led. No emoji, ever. Merchants are "merchant partners."
- Motion character: restrained, 150–200ms ease-out, darken on hover, 1px nudge on press, no bounces

**Extended (app-only, documented here because marketing assets never need them):**
- The neutrals ramp (canvas, surface, subtle, borders, text scale)
- Semantic risk colors (success/warning/danger/danger-strong) and the chargeback mapping
- Navy ramp depth values (`navy-deep #002A52` for active nav)
- Navy-tinted shadows (brand uses charcoal-tinted; the app keeps a navy tint for cohesion on a navy-structured UI; intentional, documented divergence)
- Interaction states, focus rings, elevation system, 8-point spacing (a compliant multiple of the brand's 4px base grid)

**Flagged (pending brand approval):**
- **Navy text on green buttons.** The legacy brand kit specified white text on green. White on `#96C100` fails WCAG contrast (~2:1 against a 4.5:1 requirement); navy passes and is on-brand. The app uses navy text on green. Recommendation on file: update the brand kit to match the app. **Routes through Reuven before this becomes the printed brand standard.**

---

## 1. Design Principles

- **Premium, not flashy.** Confident, clean, trustworthy. A professional instrument.
- **Progressive disclosure.** Never show everything at once. Lead with essentials, reveal depth on demand. Core rule for battle cards.
- **Each color has one job.** Navy grounds, green activates, neutrals carry content. Green is used sparingly so it always means "act here."
- **Generous whitespace.** Dense information presented with room so it never clutters.
- **Consistent over clever.** One button system, one card system, one type scale.

## 2. Color System

### 2.1 Brand Core (inherited)

| Token | Hex | Job |
|---|---|---|
| `brand-green` | `#96C100` | Action and signal: CTAs, selection, focus, active states |
| `brand-navy` | `#003568` | Structure and authority: nav, headers, depth, accents |
| `brand-charcoal` | `#474749` | Primary body text, dark authority surfaces |
| `brand-white` | `#FFFFFF` | Card surfaces, text on navy |

(`brand-charcoal` was previously named `brand-gray`; renamed to match the brand system's vocabulary. Alias the old token if needed during migration.)

### 2.2 Light Theme Neutrals (extended)

| Token | Hex | Use |
|---|---|---|
| `bg-canvas` | `#F4F6F8` | App background (behind cards) |
| `bg-surface` | `#FFFFFF` | Cards, panels, primary surfaces |
| `bg-subtle` | `#F7F7F7` | Subtle fills, hover on light rows, input backgrounds (matches the brand's section-wash neutral) |
| `border-subtle` | `#E2E2E3` | Dividers, hairlines (brand divider value) |
| `border-default` | `#D6D6D8` | Card borders, input borders (derived one step darker) |
| `border-on-dark` | `#58585A` | Dividers on navy/charcoal surfaces (brand value) |
| `text-primary` | `#474749` | Body text (brand charcoal) |
| `text-heading` | `#003568` | Headings (brand navy); see note |
| `text-secondary` | `#6B7074` | Secondary text, descriptions |
| `text-muted` | `#969A9D` | Labels, captions, placeholders |
| `text-disabled` | `#B8BCBF` | Disabled text |
| `text-on-navy` | `#FFFFFF` | Text/icons on navy surfaces |
| `text-on-navy-muted` | `#AEBDCB` | Secondary text on navy |

**Heading color choice:** Default to navy headings in the app for brand presence; use charcoal for long-form reading sections if navy feels heavy.

### 2.3 Navy Ramp (structure and depth)

| Token | Value | Use |
|---|---|---|
| `navy-primary` | `#003568` | Nav rail, headers, primary navy surfaces |
| `navy-hover` | `#1A4977` | Navy element hover (brand value) |
| `navy-deep` | `#002A52` | Active nav item background (app extension) |
| `navy-wash` | `rgba(0,53,104,0.08)` | Subtle navy-tinted backgrounds, selected (secondary) |
| `navy-border` | `rgba(0,53,104,0.20)` | Navy outlines |

### 2.4 Green Ramp (action and signal)

| Token | Value | Use |
|---|---|---|
| `green-primary` | `#96C100` | Primary buttons, key accents |
| `green-hover` | `#7BA300` | Hover (darken, per brand system) |
| `green-active` | `#7BA300` + `translateY(1px)` | Pressed: same deep green, 1px downward nudge, no scale |
| `green-wash` | `rgba(150,193,0,0.14)` | Selected rows, hover backgrounds, highlights |
| `green-border` | `rgba(150,193,0,0.45)` | Selected card borders, subtle green outlines |
| `green-focus-ring` | `rgba(150,193,0,0.55)` | Focus ring on inputs/buttons |

**Retired:** `#A6D40C` (the old brighten-on-hover value). The brand system darkens on hover; the app now matches.

### 2.5 Semantic Colors (extended; tuned for light backgrounds)

Distinct from brand green so "good" reads differently than "the brand."

| Token | Hex | Meaning |
|---|---|---|
| `success` | `#4E9A2E` | Positive, low risk, approved |
| `warning` | `#CC8A1A` | Caution, moderate risk |
| `danger` | `#D43A32` | High risk, errors |
| `danger-strong` | `#A82820` | Very high risk, critical |
| `info` | `#2B6CB0` | Informational notices |

**Risk / chargeback indicator mapping (battle cards):** Low → success, Moderate → warning, High → danger, Very High → danger-strong. Status chips use the semantic color as text on a low-opacity tint of the same color. Never color without the text label.

## 3. Typography

**Fonts:** Montserrat for all UI. Oligopoly is reserved for the logo/wordmark only, delivered as a locked image asset; never re-typed as live text. (The brand kit's Montserrat files are self-hosted in the brand repo; the app may load Google Fonts for build simplicity since Montserrat there is an exact match.)

**Weights:** ExtraBold (800) headings, SemiBold (600) emphasis/labels, Regular (400) body.

### Type Scale (screen)

| Token | Size / Line height | Weight | Use |
|---|---|---|---|
| `display` | 30 / 38 | ExtraBold | Page titles |
| `h1` | 24 / 32 | ExtraBold | Major section titles |
| `h2` | 20 / 28 | Bold | Card titles, sub-sections |
| `h3` | 17 / 24 | SemiBold | Inline headers, list group titles |
| `body` | 16 / 24 | Regular | Default paragraph text |
| `body-sm` | 14 / 20 | Regular | Secondary text, dense lists |
| `label` | 13 / 16 | SemiBold | Field labels, badges (uppercase, +0.04em tracking) |
| `caption` | 12 / 16 | Regular | Captions, helper text, timestamps |

**Rules:**
- Headings use `text-heading` (navy) or `text-primary`. Body uses `text-primary`/`text-secondary`.
- Labels uppercase with slight tracking for a clean instrument feel (the brand's eyebrow treatment).
- Max 3 type sizes per component.

## 4. Spacing (8-point base)

A compliant multiple of the brand system's 4px base grid.

| Token | px |
|---|---|
| `space-1` | 4 |
| `space-2` | 8 |
| `space-3` | 12 |
| `space-4` | 16 |
| `space-5` | 24 |
| `space-6` | 32 |
| `space-7` | 48 |
| `space-8` | 64 |

Card padding: `space-5` (24) desktop, `space-4` (16) mobile. Gap between cards: `space-4`–`space-5`. Section separation: `space-6`–`space-7` (honors the brand's 32–64px section rhythm).

## 5. Radius, Borders, Elevation

**Radius** (within the brand's 8–16px range; pill reserved for primary CTAs and chips):

| Token | px | Use |
|---|---|---|
| `radius-sm` | 8 | Inputs, badges, small controls |
| `radius-md` | 12 | Cards, panels |
| `radius-lg` | 16 | Modals, large containers |
| `radius-pill` | 999 | Pills, tags, primary buttons |

**Borders:** 1px. `border-subtle` for dividers, `border-default` for card/input edges, `border-on-dark` on navy/charcoal surfaces. Selected elements use `green-border`. No colored left-border-accent cards (brand rule); the 3px green left bar on the active nav item is a nav indicator, not a card style, and remains.

**Elevation** (app extension; shadows tinted with navy for cohesion on a navy-structured UI; the brand's marketing assets use charcoal-tinted shadows):

| Token | Definition |
|---|---|
| `elev-0` | flat on `bg-canvas` |
| `elev-1` | `0 1px 2px rgba(0,53,104,0.06)` — resting cards |
| `elev-2` | `0 4px 12px rgba(0,53,104,0.10)` — hover cards, dropdowns |
| `elev-3` | `0 8px 24px rgba(0,53,104,0.14)` — modals, popovers, right panel |

Keep shadows soft, diffuse, and low-opacity. Never hard or dark. Primary green CTAs may carry a faint green glow on hover (brand `--shadow-green`).

## 6. Interaction States (all interactive elements)

| State | Treatment |
|---|---|
| Default | Base token colors |
| Hover | `bg-subtle` for neutral elements; `green-hover` (#7BA300, darker) for green; `green-wash` background for list/nav items; navy elements → `navy-hover` |
| Active/Pressed | Green: `#7BA300` + `translateY(1px)`; nav: `navy-deep`. No scale gimmicks. |
| Focus | 2px `green-focus-ring`, never remove focus outlines |
| Selected | `green-wash` background + `green-border` |
| Disabled | `text-disabled`, opacity 0.5, no pointer events |
| Loading | Skeleton shimmer on `bg-subtle`; spinners use `brand-green` |

Transitions: 150–200ms ease-out. Hover lifts of 1–2px maximum on cards. No long or bouncy motion; this is a trust brand.

## 7. Core Components

### Buttons

| Variant | Style |
|---|---|
| Primary | `brand-green` bg, **navy text `#003568`**, SemiBold, `radius-pill`, padding 12x20 |
| Secondary | White bg, `navy-border`, `brand-navy` text, hover → `navy-wash` |
| Ghost | No border, `text-secondary`, hover → `bg-subtle` |
| Destructive | `danger` bg, white text, used rarely |

Min height 44px. Icon buttons 44x44 minimum.

**Accessibility note (flagged for brand approval):** Navy text on green passes contrast and is on-brand. Do not use white text on green (`#96C100` is too light for white to be legible). This diverges from the legacy printed brand rule; the standing recommendation is that the brand kit adopt navy-on-green. Pending Reuven's sign-off.

### Cards

`bg-surface` (white), `radius-md`, `border-subtle` (1px), `elev-1`, padding `space-5`. Optional header row: `h2` title + actions. Clickable cards hover → `elev-2`.

### Inputs / Search

`bg-surface` or `bg-subtle`, `border-default`, `radius-sm`, `text-primary`, placeholder `text-muted`. Focus → `green-focus-ring`. Search bar is prominent with a leading magnifier icon.

### Badges / Chips

`radius-pill`, `label` type. Two kinds:
- **Tag chips** (Also Known As, content tags): `bg-subtle`, `text-secondary`.
- **Status chips** (risk profile, tier): semantic color text on low-opacity tint (e.g. High → `danger` text on `rgba(212,58,50,0.12)`).

### Accordion / Expandable Section (battle card sections)

Header row: `h3` title, chevron, white surface, full-width clickable, 44px+ tall. Expanded body: `bg-canvas` inset, padding `space-5`. Smooth height transition. Collapsed shows essentials only; everything else expands on tap.

### Left Navigation (navy rail)

`navy-primary` background, full height. Logo at top (white GOAT + green A lockup, which sits perfectly on navy). Items use `body-sm`/`label`, `text-on-navy` with icons. Active item: `navy-deep` background + `brand-green` icon + 3px left accent bar in `brand-green`. Hover: `navy-hover`. Collapses to icon-only on narrow/mobile.

### Top Bar (optional)

White surface, `border-subtle` bottom, holds page title (`display`/`h1`), search, and user menu. A frosted treatment (white at ~85% + backdrop blur) is acceptable per the brand system; avoid heavier glassmorphism.

### Right Panel (future AI chat)

`bg-surface`, slides in, `elev-3`, distinct from main content, dismissible. Full-screen overlay on mobile.

### Login Screen

Navy hero (`navy-primary`) with white GOAT logo and the line **"The right home for every legitimate deal."** White login card with green primary button (navy text).

The legacy tagline ("Optimizing payment solutions for SMB's") is retired from the app per the brand system's guidance to prefer outcome-led lines; it survives only in legacy marketing contexts where SMB framing fits.

## 8. Iconography

**Lucide** line icons (the brand system's flagged substitute for an official set that does not yet exist). Stroke 1.75–2px, sized 20–24px in UI. Default color `brand-charcoal` or `brand-navy`; use `brand-green` for emphasis, active state, or a single highlighted icon. Never multicolor. Never emoji, never Unicode dingbats.

The green "A" peak mark (from the brand asset library) is the brand's own glyph: favicon, app icon, watermark, loading mark. Green on light, white on dark.

## 9. Logo Usage in App

- Navy nav rail / navy areas: white "GOAT" (green A) + green "PAYMENTS" lockup.
- Light areas (if logo needed on white): the approved on-light version (charcoal "GOAT" + green A + green "PAYMENTS").
- Maintain clear space. Do not crop, recolor, distort, or recreate with text. Never re-type the wordmark.
- No tagline/contact footer inside the app (that rule is for marketing assets).

## 10. Voice in the App (inherited)

UI copy follows the brand voice: confident, consultative, plainspoken. Speak to the agent as "you." Refer to merchants as "merchant partners" in any agent-facing guidance copy. Outcome-first language; never rate-led. No emoji anywhere in the product. No breathless urgency.

## 11. Mobile / Responsive

- Mobile-first; must work at ~375px width.
- Touch targets minimum 44x44px.
- Navy nav collapses to a bottom bar or hamburger on mobile.
- Battle card sections stack; accordions are ideal for small screens.
- Right panel becomes a full-screen overlay on mobile.

## 12. Accessibility Notes (read before building)

- Button text: navy text on green, never white on green.
- Body text contrast at least 4.5:1; large text 3:1. Navy and charcoal on white both pass.
- Never rely on color alone for risk level; always pair the color chip with the text label.
- Always preserve visible focus states.

## 13. What Lovable Should Do With This File

- Implement these as design tokens / CSS variables. Do not hardcode hex values in components.
- Build one shared component library (Button, Card, Badge, Input, Accordion, Nav, Top Bar) from these specs and reuse everywhere.
- Default to light theme with the navy/green/neutral system above.
- Structure tokens so a dark theme (navy-based) could be added later without refactoring.
- When in doubt: more whitespace, fewer green elements, let navy carry structure.

## Changelog

- **2026-06:** Aligned to the GOAT Payments Design System as brand source of truth. Green hover changed from brighten (`#A6D40C`, retired) to darken (`#7BA300`). Navy hover changed `#0A4178` → `#1A4977`. `border-subtle` snapped to brand divider `#E2E2E3`; `border-default` re-derived; `border-on-dark` added. `bg-subtle` aligned to brand wash `#F7F7F7`. `brand-gray` renamed `brand-charcoal`. Login tagline replaced with "The right home for every legitimate deal." Added Section 0 (inheritance map), Section 8 (iconography), Section 10 (voice), no-emoji rule. Navy-on-green button text remains flagged pending Reuven.
