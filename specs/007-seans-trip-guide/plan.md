# Implementation Plan: Sean's Personal Trip Guide

**Branch**: `007-seans-trip-guide` | **Date**: 2026-02-11 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/007-seans-trip-guide/spec.md`

## Summary

Produce a single Markdown file at `sean/README.md` — Sean's personalized trip guide synthesizing all prior features (001-006) for his V1-V3 bouldering level and mountain biking priority. The guide uses second-person practical voice with curated inlining (problem names, grades, one-line notes inline; full profiles linked). Target ~300-400 lines.

## Technical Context

**Language/Version**: GitHub-Flavored Markdown (GFM)
**Primary Dependencies**: Features 001-006 deliverables (areas/, trails/, conditions/, rest-day/, logistics/)
**Storage**: Flat-file Markdown in `sean/README.md`
**Testing**: Manual validation — phone readability, link verification, scope compliance, source verification
**Target Platform**: Phone-first (GitHub mobile rendering, offline Markdown viewer)
**Project Type**: Documentation-only (no application code)
**Performance Goals**: 30-second lookup for any weather scenario → recommended activity
**Constraints**: Tables ≤6 columns, single file, ~300-400 lines, second-person voice
**Scale/Scope**: 1 file, 1 user (Sean), 7-day trip (Feb 14-21, 2026)

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| Principle | Status | Notes |
|-----------|--------|-------|
| I. Decision-Support First | PASS | Daily decision matrix at top of guide; 30-second lookup goal |
| II. Bouldering Scope Boundary | PASS | All climbing content is V-scale bouldering. No sport/trad/route references |
| III. Ability-Aware, Hard-Climbing Priority | SPECIAL | Sean's guide focuses on V1-V3 (beginner band). This is allowed — the guide is personalized, not an area profile. Hard-climbing priority applies to area profiles (Features 001-002), not personal guides |
| IV. Mountain Biking as First-Class | PASS | MTB priority stack is a dedicated section with equal rigor to bouldering |
| V. Weather-Resilience | PASS | Decision matrix includes rain/freeze/thaw scenarios with specific area recommendations |
| VI. Source Accuracy | PASS | All claims sourced or flagged [UNVERIFIED], inherited from Features 001-006 |

**Post-Phase 1 Re-check:**

| Item | Status | Notes |
|------|--------|-------|
| Principle III exception | JUSTIFIED | Personal guide inverts the priority: beginner problems first because this is Sean's guide. Area profiles (Feature 001) still prioritize hard climbing. No conflict — different document purpose |
| V1-V3 data availability | CONFIRMED | 27 named V0-V3 problems across 3 areas (6 Meadow River, 13 Summersville, 8 Gorge). 7 classics identified. Sufficient for curated hit list |
| Cross-reference integrity | CONFIRMED | All 6 dependency features are merged to main. Profile links verified in Feature 006 polish pass |

## Key Research Findings

| Finding | Detail | Impact |
|---------|--------|--------|
| V1-V3 problem inventory | 27 named problems: 6 Meadow River (2 classics), 13 Summersville (4 classics), 8 Gorge (1 classic) | Hit list has enough content for all 3 areas |
| Best beginner area | Summersville Lake — most V0-V3, all flat landings, best slab variety | Tier 1 recommendation for sunny dry days |
| Rain-day beginner options | 8 sheltered/partial problems across areas (3 Meadow, 1 Summersville, 4 Gorge) | Meadow River is the rain-day beginner pick |
| Gorge beginner limitation | Only 1 classic (Gorge Warm-Up V2), all uneven landings, hazardous approaches | Honest "limited options" note, not primary recommendation |
| MTB February reality | "Opportunistic, not guaranteed" — may get zero rideable days | Guide must gracefully handle no-ride scenarios |
| Document patterns | conditions/ uses decision-matrix, rest-day/ uses curation, logistics/ uses quick-reference | Hybrid approach: matrix at top, curations below |

## Risk Assessment

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| V1-V3 problems are unnamed/undocumented | LOW | HIGH | Feature 002 has 27 named problems — sufficient. Flag unnamed areas as "explore opportunities" |
| Personal preferences feel generic | MEDIUM | MEDIUM | Use specific recommendations ("Your best slab day: Summersville") not vague ("check area profiles") |
| Guide too long for phone | LOW | MEDIUM | Curated inlining keeps to ~300-400 lines. Quick-reference at top for scanning |
| Cross-references break | LOW | HIGH | Links verified in Feature 006 polish. Re-verify in Feature 007 polish phase |

## Project Structure

### Documentation (this feature)

```text
specs/007-seans-trip-guide/
├── plan.md              # This file
├── research.md          # V1-V3 problem inventory and pattern analysis
├── data-model.md        # Entities for personal guide
├── quickstart.md        # Implementation quick-reference
├── contracts/           # Document template
│   └── seans-guide-template.md
└── tasks.md             # Task breakdown (generated by /speckit.tasks)
```

### Deliverable (repository root)

```text
sean/
└── README.md    ← Sean's personal trip guide (single file, ~300-400 lines)
```

**Structure Decision**: Single flat file at `sean/README.md`, consistent with the single-file pattern used in Features 004 (`conditions/README.md`), 005 (`rest-day/README.md`), and 006 (`logistics/README.md`). No subdirectories needed — all content fits in one document with section anchors for navigation.

## Complexity Tracking

> No constitution violations requiring justification. Principle III exception is documented and justified above.
