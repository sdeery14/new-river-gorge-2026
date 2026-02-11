# Implementation Plan: Conditions, Weather & Drying Guide

**Branch**: `004-conditions-weather-drying` | **Date**: 2026-02-10 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/004-conditions-weather-drying/spec.md`

## Summary

Create a comprehensive conditions reference at `conditions/README.md` covering Nuttall sandstone behavior (friction, seepage, drying times), February weather patterns for the NRG area, a per-area weather comparison matrix, and a daily decision framework. Single-file design with section anchors for direct linking from area and trail profiles. This is the "core reference for daily decision-making" — the document the group consults every morning to decide what to do and where to go.

## Technical Context

**Language/Version**: N/A — documentation-only feature (Markdown files)
**Primary Dependencies**: Feature 001 area profiles, Feature 002 problem clusters, Feature 003 trail profiles
**Storage**: GitHub-hosted Markdown files
**Testing**: N/A — documentation-only (manual phone-readability verification)
**Target Platform**: GitHub-rendered Markdown on mobile phones
**Project Type**: Documentation
**Performance Goals**: 30-second phone scan for climb/wait/skip decision (SC-001)
**Constraints**: Tables ≤8 columns; phone-first layout; all data [UNVERIFIED]; single file design
**Scale/Scope**: 1 deliverable file, 3 bouldering areas + 3 trail systems in weather matrix, 6+ weather scenarios

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| Principle | Pre-Design | Post-Design | Notes |
|-----------|-----------|-------------|-------|
| I. Decision-Support First | PASS | PASS | Quick-reference decision tree at top, drying table, daily framework — all phone-scannable |
| II. Bouldering Scope Boundary | PASS | PASS | All climbing content is bouldering-specific; no route references |
| III. Ability-Aware, Hard-Climbing Priority | N/A | N/A | Weather affects all ability levels equally; area matrix links to profiles with grade data |
| IV. Mountain Biking as First-Class Activity | PASS | PASS | Trail weather notes and freeze/thaw guidance included in per-area matrix |
| V. Weather-Resilience as Core Value | PASS | PASS | This IS the weather-resilience feature — the authoritative reference |
| VI. Source Accuracy & Recency | PASS | PASS | [UNVERIFIED] flagging throughout, source citations, data gaps documented |

All gates pass. No violations.

## Project Structure

### Documentation (this feature)

```text
specs/004-conditions-weather-drying/
├── plan.md                              # This file
├── research.md                          # Per-area microclimate & wind data
├── research-nuttall-sandstone.md        # Rock behavior research
├── research-february-weather.md         # February climate data
├── data-model.md                        # Entity definitions
├── quickstart.md                        # Integration workflows
├── checklists/
│   └── requirements.md                  # Spec quality checklist
└── contracts/
    └── conditions-guide-template.md     # Document template
```

### Deliverables (repository root)

```text
conditions/
└── README.md              # Complete conditions guide: sandstone primer,
                           # drying reference, February weather, daily
                           # decision framework, per-area weather matrix,
                           # freeze/thaw guide
```

**Structure Decision**: Single file `conditions/README.md` per clarification session. All 3 user story topics (sandstone primer, February weather, per-area matrix) are sections within this one file. Section anchors enable direct linking from `areas/` and `trails/` documents. This keeps the daily decision flow in one place — no jumping between files at the crag.

## Implementation Approach

### Phase 1: Setup
- Verify Features 001, 002, 003 deliverables exist (needed for cross-references and consistency)
- Create `conditions/` directory

### Phase 2: Research Data Prep
- Confirm research data is organized and complete for all 3 topics
- Verify per-area data matches existing area profiles

### Phase 3: User Story 1 — Sandstone Primer & Drying Reference (P1 MVP)
- Write the "Can I Climb Right Now?" quick decision section (top of file)
- Write the Nuttall sandstone primer (composition, friction, seepage, ethic)
- Write the drying reference table (wall angle × conditions matrix)
- Write the freeze/thaw guide

### Phase 4: User Story 2 — February Weather & Daily Planning (P2)
- Add February weather data section (temperatures, precipitation, wind, daylight)
- Add daily decision framework (scenario → activity → area table)
- Add typical February day timeline

### Phase 5: User Story 3 — Per-Area Weather Matrix (P3)
- Add per-area weather comparison matrix (all 3 bouldering areas)
- Add trail system weather notes
- Add drying speed ranking
- Add "Where Do We Go Today?" scenario table

### Phase 6: Cross-References & Polish
- Add bidirectional links to/from `areas/` and `trails/` documents
- Verify consistency with existing weather data in area profiles
- Phone-readability check (tables ≤8 columns)
- Verify all [UNVERIFIED] flags present
- Verify all 11 FRs met

### Key Differences from Previous Features

| Aspect | Areas/Trails (001-003) | Conditions (004) |
|--------|----------------------|------------------|
| Directory | `areas/`, `trails/` | `conditions/` |
| File count | Multiple (3-4 per feature) | Single file (README.md) |
| Content type | Per-location profiles | Cross-cutting reference |
| Primary use | "Tell me about this area" | "What should we do today?" |
| Relationship | Area-specific weather summaries | Authoritative weather reference |
| Updates existing docs | No | Yes — adds links from areas/ and trails/ |

### Parallel Opportunities

- Phase 3 sections (primer, drying table, freeze/thaw) can be written in parallel (different sections of same file — recommend sequential to maintain narrative flow)
- Phase 6 cross-reference validation can be parallelized (areas/ check vs. trails/ check)

### Cross-Reference Strategy

This feature adds links FROM existing documents TO `conditions/README.md`:
- `areas/README.md`: Link drying reference table to `conditions/README.md#drying-reference`
- `areas/*.md`: Link weather resilience sections to `conditions/README.md#per-area-weather-matrix`
- `trails/README.md`: Link February riding tips to `conditions/README.md#freeze-thaw-guide`

And links FROM `conditions/README.md` TO existing documents:
- Per-area matrix links to `areas/*.md` for area-specific details
- Daily framework links to `areas/README.md` and `trails/README.md` for area/trail selection
