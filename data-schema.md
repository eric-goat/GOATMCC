# GOAT Command Center — Data Schema

> Source of truth for the MCC battle card data. The content lives in a Notion
> database ("GOAT MCC Intelligence"). Lovable reads this via the Notion API.
> Field names below are EXACT and case-sensitive. The app must reference them
> exactly as written.

## Database
- **Name:** GOAT MCC Intelligence
- **One record = one MCC code** (one row).
- **Backend:** Notion (managed by admins). The app reads from it; it does not
  write to it.

## Search Behavior
Three fields power search. A query should match against any of them:
- `MCC` (e.g. "4722")
- `Industry` (e.g. "travel", "tour operator")
- `Also Known As` (e.g. "CBD", "vape", "prop firm")

When a user selects a result, the app loads that full record into the battle card.

## Fields

> Types: **Title** (unique record title), **Text** (rich text / paragraphs),
> **Select** (single choice), **Multi-select** (tags / array).
>
> Many Text fields contain multi-line content (lists, multiple sentences).
> The app should render line breaks and simple lists cleanly.

### Identification
| Field Name | Type | Notes |
|---|---|---|
| `MCC` | Title | Primary identifier. Searchable. |
| `MCC Description` | Text | Official network/ISO description. |
| `Industry` | Text | Plain-language industry name. Searchable. |
| `Also Known As` | Multi-select | Search synonyms/keywords. Render as tag chips. Searchable. |
| `Business Examples` | Text | Example business types in this MCC. |

### Risk Intelligence
| Field Name | Type | Notes |
|---|---|---|
| `Why High Risk` | Text | |
| `Primary Risk Factors` | Multi-select | Render as tag chips. |
| `Typical Reserve Requirements` | Text | |
| `Common Decline Reasons` | Text | |
| `Chargeback Profile` | Select | Options: Low, Moderate, High, Very High. Render as a colored status chip (see design system risk mapping). |
| `Shutdown Triggers` | Text | |

### Merchant Pain Points
| Field Name | Type | Notes |
|---|---|---|
| `Top 3 Painpoints` | Text | Usually a numbered list. |
| `Cash Flow Impact` | Text | |
| `Cost of Processing Instability` | Text | |

### GOAT Sales Intelligence
| Field Name | Type | Notes |
|---|---|---|
| `GOAT Hook Sentence` | Text | One line. Featured at top of card. Copy-enabled. |
| `GOAT UVP` | Text | |
| `GOAT Placement Advantage` | Text | |
| `Why Goat?` | Text | |
| `Competitor Landscape` | Text | |
| `Ideal Merchant Volume Range` | Text | Shown as a badge in the top brief. |
| `What Not To Say` | Text | |

### Discovery
| Field Name | Type | Notes |
|---|---|---|
| `Key Discovery Questions` | Text | List of questions. Copy-enabled (each line). |
| `Qualification Red Flags` | Text | |

### Objection Handling
| Field Name | Type | Notes |
|---|---|---|
| `Common Objections` | Text | |
| `Objection Responses` | Text | Copy-enabled. Pair visually with objections. |

### Compliance & Documentation
| Field Name | Type | Notes |
|---|---|---|
| `Compliance Documentation Required` | Text | |
| `Underwriting Flags To Address Early` | Text | |
| `Typical Approval Timeline` | Text | |

### Pre-Application Intelligence
| Field Name | Type | Notes |
|---|---|---|
| `Pre-App Checklist` | Text | Checklist-style content. |
| `Bank-Specific Requirements` | Text | |
| `Deal Structuring Notes` | Text | |
| `Checklist Before Submitting` | Text | Internal agent checklist. |

### Meeting Preparation
| Field Name | Type | Notes |
|---|---|---|
| `Green Light Signals` | Text | |
| `Industry Context Brief` | Text | |
| `Voice of the Merchant` | Text | Quoted merchant language. Featured in Meeting Mode. |

### Asset Generation Hooks
| Field Name | Type | Notes |
|---|---|---|
| `One-Pager Headline` | Text | Feeds future asset customization. Copy-enabled. |
| `Suggested CTA` | Text | |
| `Outreach Subject Lines` | Text | Copy-enabled (each line). |

## Recommended (not yet in DB)
Consider adding before going live to the full team:
- `Status` | Select | Options: Draft, Under Review, Live. Lets admins publish only
  vetted records and hide unfinished ones from agents. Strongly recommended so reps
  never rely on incomplete intelligence in a real meeting.

## Notes for the Build
- Treat all field values as potentially multi-line; preserve line breaks.
- `Multi-select` fields return arrays; render each value as a chip.
- `Chargeback Profile` drives a colored indicator; never show its color without
  the text label.
- If a field is empty for a given MCC, hide it gracefully (do not show an empty
  section or a blank label).
