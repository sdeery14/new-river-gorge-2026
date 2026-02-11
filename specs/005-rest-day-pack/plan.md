# Implementation Plan: Rest-Day & Low-Energy Pack

**Branch**: `005-rest-day-pack` | **Date**: 2026-02-11 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/005-rest-day-pack/spec.md`

## Summary

Create a comprehensive rest-day and low-energy activity guide for the New River Gorge trip, covering dining, breweries, hot springs, hiking/sightseeing, indoor options, and grocery stores within a 20-minute drive of Fayetteville (hot springs up to 90 minutes). Activities are organized by energy tier (Low / Medium / High) with a quick-reference table, detailed venue profiles, and 2-3 sample rest-day itineraries. The guide is a single Markdown file designed for phone-first decision-making when the group is tired and unmotivated to research.

## Technical Context

**Language/Version**: GitHub-flavored Markdown (GFM)
**Primary Dependencies**: None — flat-file documentation project
**Storage**: Flat Markdown files in repository, rendered via GitHub
**Testing**: Manual review against spec requirements and constitution gates
**Target Platform**: GitHub web/mobile rendering, phone-first readability
**Project Type**: Single-file documentation deliverable
**Performance Goals**: 60-second activity identification on phone (SC-001)
**Constraints**: Tables ≤6 columns for phone readability (FR-012); all business claims sourced or flagged `[UNVERIFIED]` (FR-011)
**Scale/Scope**: ~20-30 venue/activity listings across 7 categories; 2-3 sample itineraries; 1 deliverable file

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| # | Principle | Status | Notes |
|---|-----------|--------|-------|
| I | Decision-Support First | ✅ PASS | Quick-reference table at top (FR-001), energy-tier filtering (FR-002), sample itineraries for zero-decision rest days (FR-013) |
| II | Bouldering Scope Boundary | ✅ PASS | No climbing content in this feature. FR-014 explicitly prohibits sport/trad/route references. Hiking and sightseeing are rest-day activities only |
| III | Ability-Aware, Hard-Climbing Priority | ⚪ N/A | Rest-day activities are not climbing-specific; energy tiers replace ability bands for this feature |
| IV | Mountain Biking as First-Class Activity | ✅ PASS | High-energy tier cross-references Feature 003 trail profiles. Does not duplicate biking content |
| V | Weather-Resilience as Core Value | ✅ PASS | Indoor options for severe weather (FR-007); February conditions noted per activity (FR-006); sample itineraries include rainy-day variant |
| VI | Source Accuracy & Recency | ✅ PASS | FR-011 requires source citations; unverified claims flagged with `[UNVERIFIED]`; February/winter hours explicitly required |

**Document Standards compliance**:
- Phone-first layout: ✅ Quick-reference table at top, detail sections below
- Optionality over itinerary: ✅ Reference listings provide options; sample itineraries are suggestions, not fixed plans
- Markdown only: ✅ Single GFM file

**Group & Logistics Awareness**:
- Roster shift: ✅ FR-010 addresses Wednesday roster change as natural rest-day candidate
- Group size: ✅ Restaurant suitability assessed for 5-6 people

**Gate result**: PASS — no violations. Proceed to Phase 0.

### Post-Phase 1 Re-Check

All gates remain PASS after design. Key design decisions reviewed:
- Single-file deliverable aligns with Principle I (Decision-Support First) — one document to open
- Document template enforces phone-first table widths (Principle I + Document Standards)
- Research revealed "Fayetteville Brewing Co." may not exist under that name — FR-004 satisfied by Bridge Brew Works + Southside Junction Tap House (or Freefolk Brewery if verified open)
- Hot springs limited to The Greenbrier only — honest framing prevents misleading content (Principle VI)
- All research items flagged `[UNVERIFIED]` where sources couldn't confirm February 2026 specifics (Principle VI)

## Project Structure

### Documentation (this feature)

```text
specs/005-rest-day-pack/
├── spec.md              # Feature specification
├── plan.md              # This file
├── research.md          # Phase 0: venue/activity research findings
├── data-model.md        # Phase 1: entity definitions and field specs
├── quickstart.md        # Phase 1: implementation quick-reference
├── contracts/
│   └── rest-day-guide-template.md  # Phase 1: document template/contract
├── checklists/
│   └── requirements.md  # Spec quality checklist
└── tasks.md             # Phase 2 output (via /speckit.tasks)
```

### Deliverable (repository root)

```text
rest-day/
└── README.md            # The rest-day & low-energy activity guide
```

**Structure Decision**: Single-file deliverable at `rest-day/README.md`, consistent with Feature 004's single-file approach (`conditions/README.md`). A single file keeps all rest-day content in one phone-scrollable document. The guide is not large enough to warrant splitting — estimated 400-600 lines covering ~25 listings plus itineraries.

## Implementation Approach

### Phase 1: Setup & Scaffolding
- Create `rest-day/` directory
- Copy document template from `contracts/rest-day-guide-template.md`
- Establish section structure with placeholder headings

### Phase 2: Quick-Reference Table & Energy Tier Framework
- Build the master quick-reference table (FR-001)
- Define energy tier categories with descriptions (FR-002)
- Populate table with all researched activities

### Phase 3: Venue & Activity Profiles
- **Dining section**: Restaurant listings with required fields per FR-003
- **Brewery section**: Bridge Brew Works + Southside Junction Tap House (or Freefolk Brewery if verified open) per FR-004
- **Hot springs section**: Listings with drive time, cost, reservations per FR-005
- **Hiking/sightseeing section**: Trail and viewpoint entries per FR-006
- **Indoor options section**: Severe-weather activities per FR-007
- **Grocery section**: Key stores with location, hours, selection notes per FR-008

### Phase 4: Sample Itineraries & Roster-Change Day
- Write 2-3 sample itineraries by energy level (FR-013)
- Add roster-change day (Wednesday) planning notes (FR-010)
- Flag travel-day-friendly activities

### Phase 5: Source Verification & Cross-Validation
- Verify all business claims are sourced or flagged `[UNVERIFIED]` (FR-011)
- Confirm reservation/booking flags on all listings (FR-009)
- Validate phone readability (table widths ≤6 columns) (FR-012)
- Confirm no sport/trad/route climbing references (FR-014)
- Cross-reference Feature 003 for mountain biking high-energy tier

## Key Research Findings

See [research.md](research.md) for full details. Summary of coverage area:

| Category | Count | Coverage Area | Key Sources |
|----------|-------|---------------|-------------|
| Dining | 11 restaurants | Fayetteville (8) + Oak Hill (3) | visitfayettevillewv.com, TripAdvisor, venue websites |
| Breweries | 2-3 venues | Fayetteville | Bridge Brew Works (confirmed), Freefolk (verify), Southside Junction |
| Hot Springs | 1 (The Greenbrier) | White Sulphur Springs (90 min) | findinghotsprings.com, resort website |
| Hiking/Sightseeing | 8 trails/sites | NRG National Park | NPS.gov, AllTrails |
| Indoor Options | 6 venues | Fayetteville + Oak Hill + Beckley | visitfayettevillewv.com, venue websites |
| Grocery | 3 stores | Fayetteville (1) + Oak Hill (2) | walmart.com, kroger.com, Yelp |

## Risks

| Risk | Impact | Mitigation |
|------|--------|------------|
| February closures reduce available dining options | Medium — fewer listings than expected | Flag seasonal closures; extend search to full 20-min radius including Oak Hill |
| Hot springs may not exist within 90-min radius | Low — optional category | Research thoroughly; if none found, document absence and suggest alternatives |
| Business hours/pricing hard to verify for February 2026 | Medium — stale data | Flag all unverified info with `[UNVERIFIED]`; note source dates |
| Fayetteville is small — limited indoor options | Low — severe-weather fallback | Include creative options (rental house activities, nearby towns) |
