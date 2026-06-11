# GOAT Command Center — Data Schema

Source of truth for the MCC battle card data. The content lives in a Notion database. Lovable reads this via the Notion API. **Field names below are EXACT and case-sensitive. The app must reference them exactly as written.**

## Database

- **Name:** GOAT MCC Intelligence *(VERIFY: the database may be titled "MCC Command Center" in the GOAT HQ workspace. The app reads by database ID, so it works either way, but this doc should state the real title. Confirm in Notion and correct.)*
- **Database ID:** `373969368f278070aa6fc602e79e20b0`
- One record = one MCC code (one row).
- **Backend:** Notion (managed by admins). The app reads from it; it does not write to it.
- **Connection:** internal integration token (managed secret `NOTION_API_KEY`). The integration must be shared with the database via the integration's **Content access** tab, not the database's connections menu. Missing this causes persistent 404s.

## Search Behavior

Three fields power search. A query should match against any of them:

- **MCC** (e.g. "4722")
- **Industry** (e.g. "travel", "tour operator")
- **Also Known As** (e.g. "CBD", "vape", "prop firm")

When a user selects a result, the app loads that full record into the battle card.

## Field Name Verification (resolve before next content push)

Three field names have conflicting references across project documents. The strings below are what this schema and the app currently expect. **Open the Notion database properties and confirm the literal strings; correct this doc and the app together if they differ.**

| Schema expects | Conflicting reference seen elsewhere |
|---|---|
| `Chargeback Profile` | "Chargeback Risk" |
| `Top 3 Painpoints` | "Top 3 Pain Points" |
| `Ideal Merchant Volume Range` | Absent from one field inventory; confirm the property exists at all |

## Fields

**Types:** Title (unique record title), Text (rich text / paragraphs), Select (single choice), Multi-select (tags / array).

Many Text fields contain multi-line content (lists, multiple sentences). The app should render line breaks and simple lists cleanly.

### Identification

| Field Name | Type | Notes |
|---|---|---|
| MCC | Title | Primary identifier. Searchable. |
| MCC Description | Text | Official network/ISO description. |
| Industry | Text | Plain-language industry name. Searchable. |
| Also Known As | Multi-select | Search synonyms/keywords. Render as tag chips. Searchable. |
| Business Examples | Text | Example business types in this MCC. |

### Risk Intelligence

| Field Name | Type | Notes |
|---|---|---|
| Why High Risk | Text | |
| Primary Risk Factors | Multi-select | Render as tag chips. |
| Typical Reserve Requirements | Text | |
| Common Decline Reasons | Text | |
| Chargeback Profile | Select | Options: Low, Moderate, High, Very High. Render as a colored status chip (see design system risk mapping). **VERIFY name.** |
| Shutdown Triggers | Text | |

### Merchant Pain Points

| Field Name | Type | Notes |
|---|---|---|
| Top 3 Painpoints | Text | Usually a numbered list. **VERIFY name.** |
| Cash Flow Impact | Text | |
| Cost of Processing Instability | Text | |

### GOAT Sales Intelligence

| Field Name | Type | Notes |
|---|---|---|
| GOAT Hook Sentence | Text | One line. Featured at top of card. Copy-enabled. |
| GOAT UVP | Text | |
| GOAT Placement Advantage | Text | |
| Why Goat? | Text | |
| Competitor Landscape | Text | |
| Ideal Merchant Volume Range | Text | Shown as a badge in the top brief. **VERIFY exists.** |
| What Not To Say | Text | |

### Discovery

| Field Name | Type | Notes |
|---|---|---|
| Key Discovery Questions | Text | List of questions. Copy-enabled (each line). |
| Qualification Red Flags | Text | |

### Objection Handling

| Field Name | Type | Notes |
|---|---|---|
| Common Objections | Text | |
| Objection Responses | Text | Copy-enabled. Pair visually with objections. |

### Compliance & Documentation

| Field Name | Type | Notes |
|---|---|---|
| Compliance Documentation Required | Text | |
| Underwriting Flags To Address Early | Text | |
| Typical Approval Timeline | Text | |

### Pre-Application Intelligence

| Field Name | Type | Notes |
|---|---|---|
| Pre-App Checklist | Text | Checklist-style content. |
| Bank-Specific Requirements | Text | |

### Meeting Preparation

| Field Name | Type | Notes |
|---|---|---|
| Green Light Signals | Text | |
| Industry Context Brief | Text | |
| Voice of the Merchant | Text | Quoted merchant language. Featured in Meeting Mode. |

### Asset Generation Hooks

| Field Name | Type | Notes |
|---|---|---|
| One-Pager Headline | Text | Feeds future asset customization. Copy-enabled. |
| Suggested CTA | Text | |
| Outreach Subject Lines | Text | Copy-enabled (each line). |

## Retired Fields

The following properties were removed from the Notion database. The app must not reference them, and no battle card group includes them:

- ~~Deal Structuring Notes~~
- ~~Checklist Before Submitting~~

If any drafted record content still includes these fields, fold their content into Bank-Specific Requirements or Pre-App Checklist as appropriate, or drop it.

## Recommended (not yet in DB)

**Status** | Select | Options: Draft, Under Review, Live.

Lets admins publish only vetted records and hide unfinished ones from agents. **Priority has increased:** upcoming records carry [CONFIRM INTERNALLY] placeholders on proprietary data (reserve structures, bank fit, approval timelines). This field is what prevents a rep from quoting an unconfirmed figure in a live meeting. Add the property, default existing records to Live, default new records to Draft, and have the app filter search results to Status = Live for agent-role users (admins see all).

## Notes for the Build

- Treat all field values as potentially multi-line; preserve line breaks.
- Multi-select fields return arrays; render each value as a chip.
- Chargeback Profile drives a colored indicator; never show its color without the text label.
- If a field is empty for a given MCC, hide it gracefully (do not show an empty section or a blank label).
