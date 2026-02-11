# Implementation Plan: Bike Rentals

**Branch**: `010-bike-rentals` | **Date**: 2026-02-11 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/010-bike-rentals/spec.md`

## Summary

Create a bike rental guide at `trails/bike-rentals.md` providing a quick-reference shop directory (local + out-of-town alternatives), beginner rental guidance (bike type, sizing, gear, February tips), and prominent February closure warnings. The guide cross-references Feature 003 trail profiles rather than duplicating trail data.

## Technical Context

**Format**: GitHub-flavored Markdown
**Output**: Single file — `trails/bike-rentals.md`
**Dependencies**: Feature 003 (Mountain Biking Trails) for trail cross-references
**Testing**: Manual review — phone readability, [UNVERIFIED] flagging, scope compliance
**Target Platform**: GitHub rendering + phone browser
**Project Type**: Documentation only — no application code
**Constraints**: Phone-first layout, no horizontal scroll, bouldering scope only for climbing mentions

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| # | Principle | Status | Notes |
|---|-----------|--------|-------|
| I | Decision-Support First | PASS | Quick-reference shop table at top; 30-second scan target (SC-001). Beginner guidance answers 4 core questions. Phone-first layout required (FR-009). |
| II | Bouldering Scope Boundary | PASS | FR-010 explicitly prohibits sport/trad/route references. SC-007 verifies zero violations. Any climbing mentions are bouldering only. |
| III | Ability-Aware, Hard-Climbing Priority | N/A | Bike rental guide — no climbing grade content. Beginner riders (V1-V3 climbers riding on rest days) are the primary audience for US2. |
| IV | MTB as First-Class Activity | PASS | This feature directly supports MTB with rental logistics and beginner guidance. Equal research rigor applied — shop details, sizing, gear, February conditions all documented. |
| V | Weather-Resilience as Core Value | PASS | February closure warning is the first thing readers see (SC-004). Beginner guidance includes freeze-thaw conditions, when to skip riding (FR-005). Cross-references conditions guide. |
| VI | Source Accuracy & Recency | PASS | FR-008 requires all unverified claims flagged [UNVERIFIED]. SC-005 requires 100% compliance. Research identified primary sources for shop data. |

**Result: All gates PASS. No violations.**

## Project Structure

### Documentation (this feature)

```text
specs/010-bike-rentals/
├── plan.md              # This file
├── research.md          # Phase 0 output — shop data, beginner guidance research
├── data-model.md        # Phase 1 output — entity definitions
├── quickstart.md        # Phase 1 output — implementation steps
├── checklists/
│   └── requirements.md  # Spec quality checklist
└── tasks.md             # Phase 2 output (/speckit.tasks)
```

### Content (repository root)

```text
trails/
├── README.md            # Existing — trail overview with bike rental section to update
├── bike-rentals.md      # NEW — dedicated bike rental guide (this feature)
├── arrowhead.md         # Existing — cross-referenced for trail profiles
├── summit-bechtel.md    # Existing — cross-referenced for trail profiles
└── babcock.md           # Existing — cross-referenced for trail profiles
```

**Structure Decision**: Single new file `trails/bike-rentals.md` added to the existing `trails/` section. The existing `trails/README.md` bike rental section will be updated to link to the dedicated guide. Root `README.md` updated with bike rental entry.

## Document Structure

The guide follows this section order:

1. **Title + February Closure Warning** — prominent warning within first 3 lines (SC-004)
2. **Quick-Reference Shop Table** — all shops sorted by February availability likelihood (FR-001, SC-001)
3. **Shop Details** — expanded entries with reservation requirements, policies (FR-002)
4. **Out-of-Town Alternatives** — shops in nearby towns for when local shops are closed (FR-003)
5. **Bring Your Own Bike** — transport logistics for the group (FR-004)
6. **Beginner Rental Guidance** — bike type, sizing, gear, February tips (FR-005)
7. **Cross-References** — links to trail profiles (FR-007)

## Key Data Points (from research)

### Local Shops Identified

| Shop | Location | Daily Rate | Feb Status |
|------|----------|-----------|------------|
| New River Bikes | Fayetteville | $40 | Open (except Wed) [UNVERIFIED] |
| Arrowhead Bike Farm | Fayetteville | Contact for pricing [UNVERIFIED] | Likely open [UNVERIFIED] |
| ACE Adventure Resort | Oak Hill (~15 min) | $19-39 [UNVERIFIED] | Likely open [UNVERIFIED] |
| Adventures on the Gorge | Lansing (~10 min) | [UNVERIFIED] | E-bike only [UNVERIFIED] |

### Out-of-Town Alternatives

| Shop | Location | Distance | Daily Rate |
|------|----------|----------|-----------|
| Blackwater Bikes | Davis, WV | ~1.5 hrs [UNVERIFIED] | $50-120 |
| Free Spirit Adventures | Caldwell, WV | ~1.5 hrs [UNVERIFIED] | [UNVERIFIED] |

### Key Research Findings

- **Ridge Rider MTB**: Not found as an established business. May be inactive or renamed. Remove from guide or flag as unverifiable.
- **Water Stone Outdoors**: Confirmed climbing-gear only — does NOT rent bikes.
- **New River Bikes**: Best confirmed local option — established 1989, $40/day full-day MTB rentals, shuttle service available.
- **Arrowhead Bike Farm**: Confirmed bike rentals (Trek MTBs) — ideal for Arrowhead trail access.

### Beginner Guidance Data

- **Recommended bike**: Hardtail for green/blue trails (lighter, cheaper, helps learn line selection)
- **Sizing**: S (5'0"-5'4"), M (5'4"-5'8"), L (5'8"-6'0"), XL (6'0"+)
- **Included with rental**: Bike + helmet typically
- **Bring yourself**: Gloves, layers, appropriate shoes, water
- **February freeze-thaw**: Don't ride muddy trails; morning frozen ground OK, finish before warming softens trails

## Risks

| Risk | Likelihood | Mitigation |
|------|-----------|------------|
| No local shops open in February | High | Prominent warning + out-of-town alternatives + bring-your-own section |
| Shop data outdated by trip time | Medium | All data flagged [UNVERIFIED]; guide includes phone numbers for confirmation |
| Beginner shows up unprepared | Low | Gear checklist + sizing table + February tips section |
