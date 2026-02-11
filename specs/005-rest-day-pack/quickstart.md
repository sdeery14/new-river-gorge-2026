# Quickstart: Rest-Day & Low-Energy Pack

**Feature**: 005-rest-day-pack | **Date**: 2026-02-11

## What This Feature Produces

A single Markdown file at `rest-day/README.md` — the group's rest-day and low-energy activity guide for the New River Gorge trip.

## Deliverable

```
rest-day/
└── README.md    ← The rest-day guide (single file, ~400-600 lines)
```

## Implementation Order

1. **Create directory and scaffold** — Copy template from `contracts/rest-day-guide-template.md` to `rest-day/README.md`
2. **Quick-reference table** — Populate the master table with all researched activities (FR-001)
3. **Dining section** — Write restaurant profiles using research findings (FR-003)
4. **Brewery section** — Write brewery profiles for Bridge Brew Works + second venue (FR-004)
5. **Hot springs section** — Write The Greenbrier profile; note limited options honestly (FR-005)
6. **Hiking/sightseeing section** — Write trail and viewpoint entries from NPS research (FR-006)
7. **Indoor options section** — Write indoor venue listings (FR-007)
8. **Grocery section** — Write store listings with selection quality notes (FR-008)
9. **Sample itineraries** — Write 2-3 energy-tiered day plans combining listed activities (FR-013)
10. **Roster-change day** — Add Wednesday transition planning notes (FR-010)
11. **Source verification pass** — Ensure every claim is sourced or flagged `[UNVERIFIED]` (FR-011)
12. **Phone readability check** — Verify tables ≤6 columns, sections are skimmable (FR-012)
13. **Scope compliance check** — Confirm zero sport/trad/route climbing references (FR-014)

## Key Files to Reference During Implementation

| File | Purpose |
|------|---------|
| `specs/005-rest-day-pack/spec.md` | Requirements and acceptance criteria |
| `specs/005-rest-day-pack/research.md` | All venue/activity research with sources |
| `specs/005-rest-day-pack/data-model.md` | Required fields for each entity type |
| `specs/005-rest-day-pack/contracts/rest-day-guide-template.md` | Document structure template |
| `.specify/memory/constitution.md` | Constitution gates (especially Principles I, II, V, VI) |

## Constitution Gates to Watch

- **Principle I (Decision-Support First)**: Quick-reference table at top; sample itineraries for zero-decision days
- **Principle II (Bouldering Scope)**: No route/sport/trad climbing content — hiking is rest-day only
- **Principle V (Weather-Resilience)**: Indoor options for bad weather; February conditions on all outdoor activities
- **Principle VI (Source Accuracy)**: Every business claim sourced or `[UNVERIFIED]`

## Known Risks

- **Freefolk Brewery** may be closed — verify before including; have Southside Junction Tap House as backup
- **Hot springs** section will be thin (only The Greenbrier qualifies) — frame honestly
- **February hours** are largely unverified — blanket disclaimer + per-listing flags needed
- **Indoor options** are limited in a small town — be creative, include Beckley options
