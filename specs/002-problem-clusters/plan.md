# Implementation Plan: Problem Clusters

**Branch**: `002-problem-clusters` | **Date**: 2026-02-10 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/002-problem-clusters/spec.md`
**Depends On**: Feature 001 (Primary Bouldering Areas) — merged to main

## Summary

Create curated problem cluster documents for each bouldering area (Meadow River, Summersville Lake, Gorge Boulders) with problems organized by grade band (V0-V3, V4-V6, V7-V10+). Each problem entry includes name, grade, style, shelter status, landing quality, descriptive location, Mountain Project link, and source. Two cross-area summary documents aggregate sheltered classics (rain-day reference) and hard climbing objectives (V10 week planner). All documents are phone-first Markdown with tappable links.

## Technical Context

**Format**: GitHub-flavored Markdown
**Storage**: Flat files in `areas/` directory at repository root (alongside Feature 001 profiles)
**Target Platform**: GitHub web/mobile rendering, any Markdown viewer on phone
**Project Type**: Documentation (no application code)
**Performance Goals**: Problem list scannable within 30 seconds; grade band selection in under 10 seconds
**Constraints**: Phone-legible tables (≤8 columns), tappable Mountain Project links, self-contained entries
**Scale/Scope**: 3 area problem cluster documents + 2 cross-area summaries = 5 new files

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| Principle | Gate | Status |
|-----------|------|--------|
| I. Decision-Support First | Quick-reference counts at top of each grade band; phone-first tables; 30-second scan goal | PASS |
| II. Bouldering Scope Boundary | 100% boulder problems, V-scale only, zero route content | PASS |
| III. Ability-Aware, Hard-Climbing Priority | Grade bands with V7-V10+ section; cross-area hard-climbing summary; conditions notes for projecting | PASS |
| IV. Mountain Biking | N/A for this feature | N/A |
| V. Weather-Resilience | Shelter status on every problem entry; shelter type specified; cross-area sheltered classics summary | PASS |
| VI. Source Accuracy | Every problem cites source; Mountain Project links where available; [UNVERIFIED] flags | PASS |

**Post-design re-check**: All gates still pass. No violations requiring justification.

## Project Structure

### Design Artifacts (this feature)

```text
specs/002-problem-clusters/
├── spec.md                                    # Feature specification
├── plan.md                                    # This file
├── research.md                                # Phase 0: problem research & decisions
├── data-model.md                              # Phase 1: problem entry schema
├── quickstart.md                              # Phase 1: how to use problem cluster docs
├── contracts/
│   ├── problem-cluster-template.md            # Phase 1: template for per-area problem docs
│   └── cross-area-summary-template.md         # Phase 1: template for cross-area summaries
├── checklists/
│   └── requirements.md                        # Spec quality checklist
└── tasks.md                                   # Phase 2: task list
```

### Deliverable Documents (repository root)

```text
areas/
├── README.md                    # (Feature 001 — existing, no changes)
├── meadow-river.md              # (Feature 001 — existing, no changes)
├── summersville-lake.md          # (Feature 001 — existing, no changes)
├── gorge-boulders.md             # (Feature 001 — existing, no changes)
├── problems-meadow-river.md     # NEW: Problem clusters for Meadow River
├── problems-summersville-lake.md # NEW: Problem clusters for Summersville Lake
├── problems-gorge-boulders.md   # NEW: Problem clusters for Gorge Boulders
├── sheltered-classics.md        # NEW: Cross-area sheltered problems (rain-day ref)
└── hard-climbing.md             # NEW: Cross-area V7-V10+ summary (week planner)
```

**Structure Decision**: Problem cluster files live in `areas/` alongside Feature 001 profiles. Naming convention `problems-{area}.md` keeps them adjacent to their parent profile in directory listing. Cross-area summaries are standalone files for single-document rain-day and hard-climbing decisions.

## Implementation Approach

### Phase 1: Setup
- No new directories needed (`areas/` exists from Feature 001)

### Phase 2: Research
- Research named problems at each area from Mountain Project, guidebooks, community sources
- Organize by area → sector → grade band
- Flag all data [UNVERIFIED] given web access limitations

### Phase 3: Per-Area Problem Clusters (can be parallelized)
- Write each area's problem cluster document using `contracts/problem-cluster-template.md`
- Organize by grade band (V7-V10+ first per Constitution Principle III)
- Include all required fields per FR-002
- Link back to parent area profile per FR-011

### Phase 4: Cross-Area Summaries
- Write sheltered classics summary (FR-008) — aggregates sheltered problems across all areas
- Write hard-climbing summary (FR-009) — aggregates V7-V10+ across all areas
- Both depend on per-area docs being complete

### Phase 5: Cross-Validation
- Verify all 12 FRs met
- Verify consistency between problem clusters and Feature 001 area profiles
- Phone-screen readability test

## Key Research Findings

| Area | Est. Curated Problems | Research Challenge |
|------|----------------------|-------------------|
| Meadow River | 20-40 | Sparsely documented; few named problems on Mountain Project |
| Summersville Lake | 40-80 | Best documented (Mike Williams guidebook); most volume |
| Gorge Boulders | 15-30 | Cliff-base boulders often unnamed; scattered across 4 sectors |

## Risks

| Risk | Mitigation |
|------|-----------|
| Very few named problems available from sources — NRG bouldering is developing | Include all known problems; use descriptive identifiers for unnamed boulders; flag with [UNVERIFIED] |
| Mountain Project links may not exist for many problems | Include links where available; note "Not on MP" for undocumented problems |
| Shelter status hard to determine without visiting | Use rock geometry inference (overhanging = sheltered); flag uncertain shelter as [UNVERIFIED] |
| Problem location descriptions may be vague without firsthand knowledge | Use best available info from guidebooks/MP; flag as [UNVERIFIED]; recommend verification at Water Stone Outdoors |
