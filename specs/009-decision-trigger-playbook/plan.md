# Implementation Plan: Decision Trigger Playbook

**Branch**: `009-decision-trigger-playbook` | **Date**: 2026-02-11 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/009-decision-trigger-playbook/spec.md`

## Summary

A single Markdown document (`playbook/README.md`) providing a structured framework for deciding whether to stick with the Chattanooga trip or pivot to New River Gorge, based on weather thresholds at defined decision windows (7-day, 3-day, 1-day out). Includes a quick-reference decision tree, side-by-side weather resilience comparison, booking/cancellation timeline with financial exposure, and contingency paths for degraded scenarios.

## Technical Context

**Language/Version**: GitHub-flavored Markdown (documentation only)
**Primary Dependencies**: None — flat Markdown files, no build tools
**Storage**: Git repository, flat files
**Testing**: Manual review against spec requirements and constitution
**Target Platform**: GitHub web rendering + mobile phone browser at the crag
**Project Type**: Documentation (single Markdown file)
**Performance Goals**: Decision tree navigable in under 60 seconds on a phone
**Constraints**: Phone-first layout, no horizontal scroll, GitHub-rendered tables only
**Scale/Scope**: 1 new file (`playbook/README.md`), 1 modified file (`README.md` root — add link)

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| # | Principle | Status | Evidence |
|---|-----------|--------|----------|
| I | Decision-Support First | PASS | FR-009: quick-reference decision tree at top, navigable in <60 seconds. Phone-first layout (FR-011). |
| II | Bouldering Scope Boundary | PASS | FR-012: zero sport/trad/route references. All climbing references are bouldering areas and V-scale problems. |
| III | Ability-Aware, Hard-Climbing Priority | PASS | Destination comparison includes grade availability at both locations. Hard-climbing quality is a factor in the comparison framework. |
| IV | Mountain Biking as First-Class Activity | PASS | Comparison framework includes MTB trail availability at both destinations as a factor. |
| V | Weather-Resilience as Core Value | PASS | This IS the feature — entire playbook is weather-based decision-making. FR-001, FR-003 define weather triggers and resilience comparison. |
| VI | Source Accuracy & Recency | PASS | FR-010: all thresholds, costs, and deadlines flagged [UNVERIFIED] where not confirmed. Research.md documents sources. |

**Gate result**: ALL PASS. No violations.

## Project Structure

### Documentation (this feature)

```text
specs/009-decision-trigger-playbook/
├── plan.md              # This file
├── research.md          # Phase 0: weather comparison + cancellation policies
├── data-model.md        # Phase 1: entity definitions
├── quickstart.md        # Phase 1: implementation steps
└── tasks.md             # Phase 2 output (/speckit.tasks)
```

### Content (repository root)

```text
playbook/
└── README.md            # NEW: Decision Trigger Playbook document

README.md                # MODIFIED: Add playbook link to Quick Start table and What's in the Repo
```

**Structure Decision**: Single new directory `playbook/` matching the existing repo pattern (each content type gets its own top-level directory). The playbook is a standalone reference document, not an appendix to conditions/ or logistics/.

## Document Sections (playbook/README.md)

The playbook follows this structure, derived from the 3 user stories:

1. **Quick-Reference Decision Tree** (FR-009) — flowchart-style table at the very top
2. **Decision Windows** (FR-002) — 7-day, 3-day, 1-day sections with trigger criteria
3. **Weather Comparison: Chattanooga vs NRG** (FR-003) — side-by-side resilience table
4. **Booking & Cancellation Timeline** (FR-004, FR-005) — countdown with financial exposure
5. **Contingency Paths** (FR-006) — degraded scenarios and recommendations
6. **Mid-Week Roster Considerations** (FR-008) — switching logistics for split arrivals
7. **Cross-References** (FR-007) — links to Conditions Guide, Logistics, Chattanooga repo

## Key Data Points (from research)

### Weather Comparison

| Factor | Chattanooga | NRG | Notes |
|--------|-------------|-----|-------|
| Feb avg high | 51-59°F | 42-45°F | Chattanooga warmer |
| Feb avg low | ~35°F | 23-27°F | NRG significantly colder |
| Rain days/month | 13-14 | Est. similar | Both expect 2-3 events per week |
| Dew point | 31-33°F | Similar range | Both excellent for friction |
| Min drying time | Variable (4-48 hrs) | Mandatory 24+ hrs | Chattanooga dries faster |
| Rain shelter areas | Dayton Pocket (gorge) | Gorge overhangs, Meadow River | Both have options |
| Winter access risk | Low | Moderate (snow/ice closures) | NRG has more access uncertainty |

### Cancellation Flexibility

| Booking Type | Best Flexibility Strategy | Free Cancel Window |
|-------------|--------------------------|-------------------|
| Flights | Southwest Airlines | Free cancellation anytime (credit) |
| Lodging | VRBO Relaxed/Moderate | 7-30 days before check-in |
| Rental car | "Pay Later" booking | Free until pickup time |

## Risk Assessment

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Booking details not finalized | High | Medium | Use placeholder framework with [UNVERIFIED] flags; design for easy updates |
| Weather data may not be directly comparable | Medium | Medium | Use consistent metrics (rain days, drying time, shelter count) for both |
| Chattanooga repo conditions data may change | Low | Low | Reference by link, don't duplicate; note version dependency |
| Group may not follow structured decision process | Medium | Low | Make the decision tree so simple it's faster than informal discussion |
