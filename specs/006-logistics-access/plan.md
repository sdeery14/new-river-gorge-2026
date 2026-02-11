# Implementation Plan: Logistics & Access Cheat Sheets

**Branch**: `006-logistics-access` | **Date**: 2026-02-11 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/006-logistics-access/spec.md`

## Summary

Create a consolidated logistics and access cheat sheet at `logistics/README.md` covering: a master access table for all bouldering areas and trail systems (drive times, parking GPS links, approach summaries, access warnings), NPS and land-manager regulations, mid-week roster-change logistics (car handoff, airport pickup, lodging adjustments), car strategy and carpooling scenarios, and a pre-trip verification checklist. The guide consolidates access data already scattered across Features 001 and 003 into a single phone-first quick-reference, and adds new logistics content (car fleet management, roster transition planning) not covered elsewhere.

## Technical Context

**Language/Version**: GitHub-flavored Markdown (GFM)
**Primary Dependencies**: None — flat-file documentation project
**Storage**: Flat Markdown files in repository, rendered via GitHub
**Testing**: Manual review against spec requirements and constitution gates
**Target Platform**: GitHub web/mobile rendering, phone-first readability
**Project Type**: Single-file documentation deliverable
**Performance Goals**: 30-second access lookup on phone (SC-001)
**Constraints**: Tables ≤6 columns for phone readability (FR-010); all access claims sourced or flagged `[UNVERIFIED]` (FR-009); abbreviated summaries with links to full profiles (FR-011)
**Scale/Scope**: ~9 access points (3 bouldering areas + 3 trail systems + sectors), 3 regulation sets, 3+ carpooling scenarios, 1 roster-change plan; 1 deliverable file (~300-500 lines)

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| # | Principle | Status | Notes |
|---|-----------|--------|-------|
| I | Decision-Support First | ✅ PASS | Master access table at top (FR-001), consolidated regulations (FR-003), pre-trip checklist (FR-008). All designed for rapid phone lookup |
| II | Bouldering Scope Boundary | ✅ PASS | FR-012 explicitly prohibits sport/trad/route references. Trail systems included for mountain biking logistics only, not climbing |
| III | Ability-Aware, Hard-Climbing Priority | ⚪ N/A | Logistics are ability-agnostic — drive times and parking don't vary by grade band |
| IV | Mountain Biking as First-Class Activity | ✅ PASS | Trail system access details included in the master access table alongside bouldering areas (FR-001). Equal treatment |
| V | Weather-Resilience as Core Value | ✅ PASS | February-specific access warnings flagged per FR-004 (icy roads, gated access, seasonal closures). Alternate access routes for winter closures (FR-007) |
| VI | Source Accuracy & Recency | ✅ PASS | FR-009 requires source citations; unverified claims flagged with `[UNVERIFIED]`; pre-trip verification checklist (FR-008) ensures recency |

**Document Standards compliance**:
- Phone-first layout: ✅ Master access table at top, detail sections below
- Optionality over itinerary: ✅ Car strategy offers scenarios, not fixed plans; roster-change provides templates, not assignments
- Markdown only: ✅ Single GFM file

**Group & Logistics Awareness**:
- Roster shift: ✅ FR-005 dedicates a full section to Wednesday roster-change logistics
- Transportation: ✅ FR-006 covers car fleet management, split-day carpooling, and parking capacity
- Lodging: ✅ FR-005 includes lodging headcount adjustments

**Gate result**: PASS — no violations. Proceed to Phase 0.

### Post-Phase 1 Re-Check

All gates remain PASS after design. Key design decisions reviewed:
- Single-file deliverable at `logistics/README.md` aligns with Principle I (Decision-Support First) — one document to open
- Abbreviated-with-links approach prevents content duplication while keeping the cheat sheet self-sufficient for quick decisions
- Generic role-based templates (Car A/B/C, Departing Member, Arriving Member) keep the guide reusable regardless of final group arrangements
- Research confirmed Yeager Airport (CRW, ~1.5 hrs) as the recommended airport for Wednesday arrival — practical and well-served
- All access data consolidated from Features 001 and 003 with sources preserved or flagged `[UNVERIFIED]`

## Project Structure

### Documentation (this feature)

```text
specs/006-logistics-access/
├── spec.md              # Feature specification
├── plan.md              # This file
├── research.md          # Phase 0: logistics research findings
├── data-model.md        # Phase 1: entity definitions and field specs
├── quickstart.md        # Phase 1: implementation quick-reference
├── contracts/
│   └── logistics-guide-template.md  # Phase 1: document template/contract
├── checklists/
│   └── requirements.md  # Spec quality checklist
└── tasks.md             # Phase 2 output (via /speckit.tasks)
```

### Deliverable (repository root)

```text
logistics/
└── README.md            # The logistics & access cheat sheet
```

**Structure Decision**: Single-file deliverable at `logistics/README.md`, consistent with Feature 004's `conditions/README.md` and Feature 005's `rest-day/README.md`. A single file keeps all logistics content in one phone-scrollable document. The guide consolidates access data from Features 001/003 (abbreviated summaries with links) plus new logistics content (car strategy, roster change, regulations). Estimated 300-500 lines.

## Key Research Findings

See [research.md](research.md) for full details. Summary:

| Category | Key Finding | Source |
|----------|-------------|--------|
| Access Points | 3 bouldering areas (6 sectors) + 3 trail systems with full GPS/parking/approach data | Features 001, 003 profiles |
| NPS Regulations | Gorge Boulders only area under NPS; crash pads/chalk permitted; no Feb closures (peregrine Mar-Jul) | NPS nps.gov/neri |
| Airports | CRW (Charleston, ~1.5 hr) recommended; LWB (~1.25 hr) backup; BKW (~40 min) limited | Rome2Rio, airport websites |
| Winter Roads | US-19 is Priority 1 for plowing; Fayette Station Road may close in ice; secondary roads low priority | WVDOH, NPS |
| Lodging | 241+ rentals in area; 3-bedroom houses typical for 5-6 people; most can park 2-3 cars | AirDNA, VRBO |
| Cell Service | AT&T best (~84%); dead zones on gorge floor; download docs before descending | Signal Checker, NPS |
| Gas | Sheetz at 27 Whitewater Ave (24 hr) is the base camp station; Oak Hill has more options | GasBuddy |

## Risks

| Risk | Impact | Mitigation |
|------|--------|------------|
| Access data from Features 001/003 contains many `[UNVERIFIED]` items | Medium — cheat sheet inherits uncertainty | Preserve `[UNVERIFIED]` flags; pre-trip verification checklist addresses this |
| GPS coordinates in existing profiles are approximate | Low — may not drop pin exactly at parking | Note coordinates are approximate; include text route summaries as backup |
| Car fleet size unknown until closer to trip | Medium — carpooling scenarios may not match reality | Use generic templates (Car A/B/C) covering 2-car and 3-car scenarios |
| Airport flight schedules may change by Feb 2026 | Low — research is directional, not booking-level | Recommend checking flights 2-3 months before trip; note CRW as primary |
| Fayette Station Road closure frequency in February is unverified | Medium — affects Gorge Boulders access | Document Canyon Rim Visitor Center as alternate access; flag for verification |
