# Quickstart: Sean's Personal Trip Guide

**Feature**: 007-seans-trip-guide | **Date**: 2026-02-11

## What This Feature Produces

A single Markdown file at `sean/README.md` — Sean's personalized trip guide for the New River Gorge bouldering/biking trip.

## Deliverable

```
sean/
└── README.md    ← Sean's personal trip guide (single file, ~300-400 lines)
```

## Implementation Order

1. **Create directory and scaffold** — Copy template from `contracts/seans-guide-template.md` to `sean/README.md`
2. **Daily decision matrix** — Populate weather/energy → activity/destination table from conditions/README.md framework, personalized for V1-V3 and MTB (FR-001)
3. **Bouldering hit list** — Curate V1-V3 problems per area from research.md Section 1 data (FR-002)
4. **Mountain biking priority stack** — Rank trails with conditions gates from research.md Section 2 (FR-003)
5. **Food & drink picks** — Curate personal favorites from rest-day/README.md (FR-004)
6. **Sample week itinerary** — Write 8-day table with realistic weather variation (FR-011)
7. **Packing checklist** — Write activity-specific gear list for bouldering + MTB + February (FR-006)
8. **Logistics summary** — Write personal arrival/departure, car, contacts (FR-007)
9. **Source verification pass** — Ensure every claim sourced or flagged `[UNVERIFIED]` (FR-009)
10. **Phone readability check** — Verify tables ≤6 columns, skimmable sections (FR-008)
11. **Scope compliance check** — Confirm zero sport/trad/route references (FR-010)

## Key Files to Reference During Implementation

| File | Purpose |
|------|---------|
| `specs/007-seans-trip-guide/spec.md` | Requirements and acceptance criteria |
| `specs/007-seans-trip-guide/research.md` | V1-V3 problem inventory (27 named problems) and trail ranking |
| `specs/007-seans-trip-guide/data-model.md` | Required fields for each entity type |
| `specs/007-seans-trip-guide/contracts/seans-guide-template.md` | Document structure template |
| `areas/meadow-river.md` | Meadow River full profile (6 V0-V3 problems) |
| `areas/summersville-lake.md` | Summersville Lake full profile (13 V0-V3 problems) |
| `areas/gorge-boulders.md` | Gorge Boulders full profile (8 V0-V3 problems) |
| `trails/arrowhead.md` | Arrowhead Trails profile (primary MTB pick) |
| `trails/babcock.md` | Babcock State Park profile |
| `trails/summit-bechtel.md` | Summit Bechtel Reserve profile |
| `conditions/README.md` | Weather decision framework (source for daily matrix) |
| `rest-day/README.md` | Dining and activity options (source for personal picks) |
| `logistics/README.md` | Access, car strategy, airports (source for logistics summary) |
| `.specify/memory/constitution.md` | Constitution gates |

## Constitution Gates to Watch

- **Principle I (Decision-Support First)**: Decision matrix at top; 30-second lookup for any weather scenario
- **Principle II (Bouldering Scope)**: No route/sport/trad content — MTB sections are for biking logistics only
- **Principle III (Ability-Aware)**: Personal guide inverts normal priority — V1-V3 first (this is Sean's guide, not an area profile)
- **Principle IV (MTB First-Class)**: Biking priority stack is a dedicated section with equal rigor
- **Principle V (Weather-Resilience)**: Decision matrix covers rain, freeze/thaw, wind, extended wet scenarios
- **Principle VI (Source Accuracy)**: All claims sourced or `[UNVERIFIED]`

## Known Risks

- **Problem names from Feature 002 are [UNVERIFIED]** — all derived from Mountain Project / local knowledge, not guidebook-confirmed
- **Restaurant hours in February are uncertain** — flag all dining hours as [UNVERIFIED] unless confirmed
- **Summit Bechtel access not guaranteed** — include in MTB stack but note conditional access
- **Sample week weather is hypothetical** — clearly label as "example" not prediction
- **Sean's actual preferences are assumed** — guide makes reasonable recommendations based on V1-V3 profile and MTB interest; Sean can edit post-generation
