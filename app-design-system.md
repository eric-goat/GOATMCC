# GOAT Command Center — App Design System (Light-First)

> Companion to the GOAT Payments Brand Kit. The brand kit governs marketing assets
> (one-pagers, decks, flyers). This file governs the **application UI** for the
> GOAT MCC Command Center.
>
> **Theme: Light-first.** Clean white workspace, navy structure, green action accents.
>
> **Three-color system, each with a clear job:**
> - **Navy #003568** = structure & authority (nav, headers, depth)
> - **Green #96C100** = action & signal (CTAs, selection, focus)
> - **Neutrals (gray/white)** = content (cards, text, canvas)

---

## 1. Design Principles

1. **Premium, not flashy.** Confident, clean, trustworthy. A professional instrument.
2. **Progressive disclosure.** Never show everything at once. Lead with essentials,
   reveal depth on demand. Core rule for battle cards.
3. **Each color has one job.** Navy grounds, green activates, neutrals carry content.
   Green is used sparingly so it always means "act here."
4. **Generous whitespace.** Dense information presented with room so it never clutters.
5. **Consistent over clever.** One button system, one card system, one type scale.

---

## 2. Color System

### 2.1 Brand Core
| Token | Hex | Job |
|---|---|---|
| `brand-green` | `#96C100` | Action & signal: CTAs, selection, focus, active states |
| `brand-navy` | `#003568` | Structure & authority: nav, headers, depth, accents |
| `brand-gray` | `#474749` | Primary body text |
| `brand-white` | `#FFFFFF` | Card surfaces, text on navy |

### 2.2 Light Theme Neutrals (the canvas)
| Token | Hex | Use |
|---|---|---|
| `bg-canvas` | `#F4F6F8` | App background (behind cards) |
| `bg-surface` | `#FFFFFF` | Cards, panels, primary surfaces |
| `bg-subtle` | `#EDEFF2` | Subtle fills, hover on light rows, input backgrounds |
| `border-subtle` | `#E3E6E9` | Dividers, hairlines |
| `border-default` | `#D5D9DD` | Card borders, input borders |
| `text-primary` | `#474749` | Body text (brand gray) |
| `text-heading` | `#003568` | Headings (branded navy) — see note |
| `text-secondary` | `#6B7074` | Secondary text, descriptions |
| `text-muted` | `#969A9D` | Labels, captions, placeholders |
| `text-disabled` | `#B8BCBF` | Disabled text |
| `text-on-navy` | `#FFFFFF` | Text/icons on navy surfaces |
| `text-on-navy-muted` | `#AEBDCB` | Secondary text on navy |

> **Heading color choice:** Headings may use navy (`text-heading`) for a more branded
> feel, or brand gray for a quieter look. Default to **navy headings** in the app for
> brand presence; use gray for long-form reading sections if navy feels heavy.

### 2.3 Navy Ramp (structure & depth)
| Token | Value | Use |
|---|---|---|
| `navy-primary` | `#003568` | Nav rail, headers, primary navy surfaces |
| `navy-deep` | `#002A52` | Active nav item background, deepest navy |
| `navy-hover` | `#0A4178` | Navy element hover |
| `navy-wash` | `rgba(0,53,104,0.08)` | Subtle navy-tinted backgrounds, selected (secondary) |
| `navy-border` | `rgba(0,53,104,0.20)` | Navy outlines |

### 2.4 Green Ramp (action & signal)
| Token | Value | Use |
|---|---|---|
| `green-primary` | `#96C100` | Primary buttons, key accents |
| `green-hover` | `#A6D40C` | Hover (brighter, more energy) |
| `green-active` | `#7DA300` | Pressed/active (darker) |
| `green-wash` | `rgba(150,193,0,0.14)` | Selected rows, hover backgrounds, highlights |
| `green-border` | `rgba(150,193,0,0.45)` | Selected card borders, subtle green outlines |
| `green-focus-ring` | `rgba(150,193,0,0.55)` | Focus ring on inputs/buttons |

### 2.5 Semantic Colors (tuned for light backgrounds)
Distinct from brand green so "good" reads differently than "the brand."

| Token | Hex | Meaning |
|---|---|---|
| `success` | `#4E9A2E` | Positive, low risk, approved |
| `warning` | `#CC8A1A` | Caution, moderate risk |
| `danger` | `#D43A32` | High risk, errors |
| `danger-strong` | `#A82820` | Very high risk, critical |
| `info` | `#2B6CB0` | Informational notices |

**Risk / chargeback indicator mapping (battle cards):**
- Low → `success`
- Moderate → `warning`
- High → `danger`
- Very High → `danger-strong`

Status chips use the semantic color as text on a low-opacity tint of the same color.

---

## 3. Typography

**Fonts:** Montserrat for all UI (Google Fonts). Oligopoly reserved **only** for the
logo/wordmark, never UI text. Confirm Oligopoly web licensing before embedding.

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
- Labels uppercase with slight tracking for a clean instrument feel.
- Max 3 type sizes per component.

---

## 4. Spacing (8-point base)
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

- Card padding: `space-5` (24) desktop, `space-4` (16) mobile.
- Gap between cards: `space-4`–`space-5`.
- Section separation: `space-6`–`space-7`.

---

## 5. Radius, Borders, Elevation

**Radius**
| Token | px | Use |
|---|---|---|
| `radius-sm` | 8 | Inputs, badges, small controls |
| `radius-md` | 12 | Cards, panels |
| `radius-lg` | 16 | Modals, large containers |
| `radius-pill` | 999 | Pills, tags, primary buttons |

**Borders:** 1px. `border-subtle` for dividers, `border-default` for card/input edges.
Selected elements use `green-border`.

**Elevation (light theme leans on shadow for lift; shadows tinted with navy for cohesion):**
| Token | Definition |
|---|---|
| `elev-0` | flat on `bg-canvas` |
| `elev-1` | `0 1px 2px rgba(0,53,104,0.06)` — resting cards |
| `elev-2` | `0 4px 12px rgba(0,53,104,0.10)` — hover cards, dropdowns |
| `elev-3` | `0 8px 24px rgba(0,53,104,0.14)` — modals, popovers, right panel |

Keep shadows soft and subtle.

---

## 6. Interaction States (all interactive elements)

| State | Treatment |
|---|---|
| Default | Base token colors |
| Hover | `bg-subtle` for neutral elements; `green-hover` for green; `green-wash` background for list/nav items |
| Active/Pressed | `green-active` for green; `navy-deep` for nav |
| Focus | 2px `green-focus-ring`, never remove focus outlines |
| Selected | `green-wash` background + `green-border` |
| Disabled | `text-disabled`, opacity 0.5, no pointer events |
| Loading | Skeleton shimmer on `bg-subtle`; spinners use `brand-green` |

Transitions: 150–200ms ease. No long or bouncy motion.

---

## 7. Core Components

### Buttons
| Variant | Style |
|---|---|
| Primary | `brand-green` bg, **navy text `#003568`**, SemiBold, `radius-pill`, padding 12x20 |
| Secondary | White bg, `navy-border`, `brand-navy` text, hover → `navy-wash` |
| Ghost | No border, `text-secondary`, hover → `bg-subtle` |
| Destructive | `danger` bg, white text, used rarely |

Min height 44px. Icon buttons 44x44 minimum.

> **Accessibility note:** Navy text on green passes contrast and is on-brand. Do **not**
> use white text on green (#96C100 is too light for white to be legible). This diverges
> from the printed brand rule; flag for brand approval.

### Cards
`bg-surface` (white), `radius-md`, `border-subtle` (1px), `elev-1`, padding `space-5`.
Optional header row: `h2` title + actions. Clickable cards hover → `elev-2`.

### Inputs / Search
`bg-surface` or `bg-subtle`, `border-default`, `radius-sm`, `text-primary`, placeholder
`text-muted`. Focus → `green-focus-ring`. Search bar is prominent with a leading
magnifier icon.

### Badges / Chips
`radius-pill`, `label` type. Two kinds:
- **Tag chips** (Also Known As, content tags): `bg-subtle`, `text-secondary`.
- **Status chips** (risk profile, tier): semantic color text on low-opacity tint
  (e.g. High → `danger` text on `rgba(212,58,50,0.12)`).

### Accordion / Expandable Section (battle card sections)
Header row: `h3` title, chevron, white surface, full-width clickable, 44px+ tall.
Expanded body: `bg-canvas` inset, padding `space-5`. Smooth height transition.
Collapsed shows essentials only; everything else expands on tap.

### Left Navigation (navy rail)
`navy-primary` background, full height. Logo at top (white GOAT + green A lockup,
which sits perfectly on navy). Items use `body-sm`/`label`, `text-on-navy` with icons.
Active item: `navy-deep` background + `brand-green` icon + 3px left accent bar in
`brand-green`. Hover: subtle lighten. Collapses to icon-only on narrow/mobile.

### Top Bar (optional)
White surface, `border-subtle` bottom, holds page title (`display`/`h1`), search,
and user menu.

### Right Panel (future AI chat)
`bg-surface`, slides in, `elev-3`, distinct from main content, dismissible. Full-screen
overlay on mobile.

### Login Screen
Navy hero (`navy-primary`) with white GOAT logo + tagline "Optimizing payment solutions
for SMB's", and a white login card with green primary button. This is the one place the
tagline appears in the app.

---

## 8. Logo Usage in App
- **Navy nav rail / navy areas:** white "GOAT" (green A) + green "PAYMENTS" lockup.
- **Light areas (if logo needed on white):** use the approved on-light version.
- Maintain clear space. Do not crop, recolor, distort, or recreate with text.
- No tagline/contact footer inside the app (that rule is for marketing assets);
  tagline appears on the login screen only.

---

## 9. Mobile / Responsive
- Mobile-first; must work at ~375px width.
- Touch targets minimum 44x44px.
- Navy nav collapses to a bottom bar or hamburger on mobile.
- Battle card sections stack; accordions are ideal for small screens.
- Right panel becomes a full-screen overlay on mobile.

---

## 10. Accessibility Notes (read before building)
- **Button text:** navy text on green, never white on green.
- Body text contrast at least 4.5:1; large text 3:1. Navy and brand gray on white both pass.
- Never rely on color alone for risk level; always pair the color chip with the text label.
- Always preserve visible focus states.

---

## 11. What Lovable Should Do With This File
- Implement these as design tokens / CSS variables. Do not hardcode hex values in components.
- Build one shared component library (Button, Card, Badge, Input, Accordion, Nav, Top Bar)
  from these specs and reuse everywhere.
- Default to light theme with the navy/green/neutral system above.
- Structure tokens so a dark theme (navy-based) could be added later without refactoring.
- When in doubt: more whitespace, fewer green elements, let navy carry structure.
