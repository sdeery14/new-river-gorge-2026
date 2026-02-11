# Quickstart: Logistics & Access Cheat Sheets

**Feature**: 006-logistics-access | **Date**: 2026-02-11

## What This Feature Produces

A single Markdown file at `logistics/README.md` — the group's consolidated logistics and access cheat sheet for the New River Gorge trip.

## Deliverable

```
logistics/
└── README.md    ← The logistics & access cheat sheet (single file, ~300-500 lines)
```

## Implementation Order

1. **Create directory and scaffold** — Copy template from `contracts/logistics-guide-template.md` to `logistics/README.md`
2. **Access quick-reference table** — Populate master table with all bouldering areas and trail systems from Features 001/003, using abbreviated summaries with profile links (FR-001, FR-002)
3. **Regulations section** — Write consolidated NPS, USACE, and other land-manager regulations (FR-003)
4. **Winter access warnings** — Flag February hazards with alternate access for each location (FR-004, FR-007)
5. **Car strategy section** — Write fleet overview and 3+ daily carpooling scenarios using generic templates (FR-006)
6. **Roster-change logistics** — Write Wednesday transition plan with car handoff, airport, lodging adjustment (FR-005)
7. **Airport reference** — Write nearest airports table with drive times and recommendations (supports FR-005)
8. **Town essentials** — Write gas stations, cell service, and walkability notes
9. **Pre-trip verification checklist** — Compile all calls/checks to confirm access before trip (FR-008)
10. **Source verification pass** — Ensure every claim is sourced or flagged `[UNVERIFIED]` (FR-009)
11. **Phone readability check** — Verify tables ≤6 columns, sections are skimmable (FR-010)
12. **Scope compliance check** — Confirm zero sport/trad/route climbing references (FR-012)

## Key Files to Reference During Implementation

| File | Purpose |
|------|---------|
| `specs/006-logistics-access/spec.md` | Requirements and acceptance criteria |
| `specs/006-logistics-access/research.md` | All logistics research with sources |
| `specs/006-logistics-access/data-model.md` | Required fields for each entity type |
| `specs/006-logistics-access/contracts/logistics-guide-template.md` | Document structure template |
| `areas/README.md` | Bouldering area overview (source for access data) |
| `areas/meadow-river.md` | Meadow River access details |
| `areas/summersville-lake.md` | Summersville Lake access details |
| `areas/gorge-boulders.md` | Gorge Boulders access details (multiple sectors) |
| `trails/README.md` | Trail systems overview (source for access data) |
| `trails/arrowhead.md` | Arrowhead Trails access details |
| `trails/babcock.md` | Babcock State Park access details |
| `trails/summit-bechtel.md` | Summit Bechtel Reserve access details |
| `.specify/memory/constitution.md` | Constitution gates (especially Principles I, II, V, VI) |

## Constitution Gates to Watch

- **Principle I (Decision-Support First)**: Master access table at top; pre-trip checklist for verification
- **Principle II (Bouldering Scope)**: No route/sport/trad climbing content — trail systems are for MTB logistics only
- **Principle V (Weather-Resilience)**: February access warnings on all hazardous locations; alternate access routes
- **Principle VI (Source Accuracy)**: Every access claim sourced or `[UNVERIFIED]`

## Known Risks

- **GPS coordinates are approximate** — many from Features 001/003 are `[UNVERIFIED]`. Include text route summaries as backup
- **Fayette Station Road** may close in ice — document Canyon Rim Visitor Center as alternate
- **Summit Bechtel** public access not guaranteed — MUST be in pre-trip verification checklist
- **Car fleet size unknown** — use generic templates covering both 2-car and 3-car scenarios
- **Cell service unreliable in gorge** — note to download documents before descending
