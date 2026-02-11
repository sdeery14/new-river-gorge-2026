# Implementation Plan: Primary Bouldering Areas

**Branch**: `001-bouldering-areas` | **Date**: 2026-02-10 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/001-bouldering-areas/spec.md`

## Summary

Create area profile documents for every bouldering zone within 45 minutes of Fayetteville, WV. Research identified 3 primary areas: Meadow River, Summersville Lake, and Gorge Boulders (with 4 sectors). Deliverables are an area overview README with a quick-reference summary table and individual area profile documents following a standardized template. All documents are phone-first Markdown, optimized for rapid morning decision-making.

## Technical Context

**Format**: GitHub-flavored Markdown
**Storage**: Flat files in `areas/` directory at repository root
**Target Platform**: GitHub web/mobile rendering, any Markdown viewer on phone
**Project Type**: Documentation (no application code)
**Performance Goals**: Area overview must fit decision-critical content within one phone screen (~20 lines)
**Constraints**: Phone-legible tables (≤7 columns), no external dependencies, all links must be tappable
**Scale/Scope**: 1 overview document + 3 area profile documents (4 files total)

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| Principle | Gate | Status |
|-----------|------|--------|
| I. Decision-Support First | Overview table fits one phone screen; quick-reference header on each profile | PASS — data-model.md defines quick-reference header as first element |
| II. Bouldering Scope Boundary | Zero sport/trad/route content in any document | PASS — FR-007 enforces; research excluded route-only areas |
| III. Ability-Aware, Hard-Climbing Priority | Grade-band tables present; V7-V10+ listed; hard-climbing density comparable across areas | PASS — FR-005 and FR-008 enforce; data-model requires grade bands |
| IV. Mountain Biking | N/A for this feature (Feature 003) | N/A |
| V. Weather-Resilience | Rain resilience rating on every area; shelter/drying/seepage documented; sector-level breakdowns | PASS — FR-002, FR-004 enforce; sectors added per clarification |
| VI. Source Accuracy | All claims sourced; [UNVERIFIED] flags on unconfirmed data | PASS — FR-006 enforces; research.md identifies all data gaps |

**Post-design re-check**: All gates still pass. No violations requiring justification.

## Project Structure

### Design Artifacts (this feature)

```text
specs/001-bouldering-areas/
├── spec.md                              # Feature specification
├── plan.md                              # This file
├── research.md                          # Phase 0: area research & decisions
├── data-model.md                        # Phase 1: area profile schema
├── quickstart.md                        # Phase 1: how to use area docs
├── contracts/
│   ├── area-profile-template.md         # Phase 1: template for individual profiles
│   └── overview-template.md             # Phase 1: template for README overview
├── checklists/
│   └── requirements.md                  # Spec quality checklist
└── tasks.md                             # Phase 2: task list (created by /speckit.tasks)
```

### Deliverable Documents (repository root)

```text
areas/
├── README.md              # Area overview: summary table, decision guide,
│                          # drying reference, NPS regulations, Feb conditions
├── meadow-river.md        # Area profile: Meadow River
├── summersville-lake.md   # Area profile: Summersville Lake
└── gorge-boulders.md      # Area profile: Gorge Boulders
                           # (sectors: Endless Wall, Nuttall, Bridge Buttress, Kaymoor)
```

**Structure Decision**: Flat `areas/` directory at repo root. No nesting — each area is one file. The overview README links to individual profiles. This matches how climbers will navigate: start at overview, drill into one area.

## Implementation Approach

### Phase 1: Setup
- Create `areas/` directory
- No dependencies to install (Markdown only)

### Phase 2: Overview Document
- Write `areas/README.md` using `contracts/overview-template.md`
- Fill summary table with researched data from `research.md`
- Include drying reference table, NPS regulations, February conditions
- Include quick decision guide

### Phase 3: Area Profiles (can be parallelized)
- Write each area profile using `contracts/area-profile-template.md`
- Research-backed content from `research.md` and web sources
- Sector breakdowns where applicable (Gorge Boulders has 4 sectors)
- Google Maps links to parking locations
- All unverified claims flagged with `[UNVERIFIED]`

### Phase 4: Cross-Validation
- Verify all FR requirements met across all documents
- Verify consistency between overview table and individual profiles
- Verify all grade-band tables present and populated
- Verify rain resilience ratings consistent
- Phone-screen test: overview table readable at phone width

## Key Research Findings (from research.md)

| Area | Drive | Rain | Problems | V10+ Density | Best Use |
|------|-------|------|----------|-------------|----------|
| Meadow River | ~30 min | Good | 50-100 [UNVERIFIED] | Some | Default bouldering day; wet-weather option |
| Summersville Lake | ~35 min | Poor | 150-250 [UNVERIFIED] | Limited | Dry days; winter drawdown; best beginner area |
| Gorge Boulders | 5-15 min | Good-Fair | 60-130 [UNVERIFIED] | Limited | Wet weather (cliff shelter); combine with hiking |

## Risks

| Risk | Mitigation |
|------|-----------|
| Problem counts are estimates — NRG bouldering is developing | Use ranges and density indicators; flag with [UNVERIFIED] |
| Meadow River access/ownership unverified | Include access warning; list verification contacts |
| NPS regulations may have changed since 2025 | Flag all NPS items [UNVERIFIED]; include phone number for pre-trip verification |
| USACE winter gate status at Summersville uncertain | Flag; include USACE phone number |
