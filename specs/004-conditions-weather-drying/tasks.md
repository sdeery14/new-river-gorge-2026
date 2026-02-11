# Tasks: Conditions, Weather & Drying Guide

**Input**: Design documents from `/specs/004-conditions-weather-drying/`
**Prerequisites**: plan.md, spec.md, research.md, research-nuttall-sandstone.md, research-february-weather.md, data-model.md, contracts/, quickstart.md

**Tests**: Not applicable — this is a documentation-only feature (Markdown files).

**Organization**: Tasks are grouped by user story. US2 and US3 depend on US1 being complete (they add sections to `conditions/README.md` created in US1). All content goes into a single file — tasks within each phase are sequential.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

---

## Phase 1: Setup

**Purpose**: Verify prerequisites and confirm project structure is ready

- [x] T001 Verify Features 001, 002, 003 deliverables exist: `areas/` directory (README.md, meadow-river.md, summersville-lake.md, gorge-boulders.md), `areas/` problem cluster files, and `trails/` directory (README.md, arrowhead.md, summit-bechtel.md, babcock.md) — needed for cross-references and consistency validation
- [x] T002 Create `conditions/` directory at repository root

---

## Phase 2: Foundational (Research Data Prep)

**Purpose**: Confirm research data is organized and complete before writing the guide

**⚠️ CRITICAL**: Guide writing (Phase 3) cannot begin until research data is confirmed.

- [x] T003 Review and confirm Nuttall sandstone research data in `specs/004-conditions-weather-drying/research-nuttall-sandstone.md`: rock composition (~98% quartz arenite, silica cement), friction behavior (dry/wet/frozen), seepage patterns (horizontal breaks, crack systems, formation contacts, 4-8 hr lag), drying times by wall angle, surface-dry vs. friction-restored distinction, freeze/thaw behavior, community ethic reasoning, sandstone comparisons.
- [x] T004 [P] Review and confirm February weather research data in `specs/004-conditions-weather-drying/research-february-weather.md`: temperature ranges (avg high 42-45°F, avg low 23-27°F), precipitation (~3.1 in/month, 12-15 precip days), wind (~6-7 mph, prevailing west), daylight (~10.5-11 hrs), freeze/thaw crossing days (~18-22/Feb), multi-day rain frequency (~2-3/Feb), 7-day climbable days estimate (~3-5).
- [x] T005 [P] Review and confirm per-area microclimate research data in `specs/004-conditions-weather-drying/research.md`: gorge wind patterns (prevailing west = sheltered gorge floor), per-area comparison (Meadow River: MODERATE wind/GOOD shelter/fastest drying; Summersville Lake: HIGH wind/POOR shelter/moderate drying; Gorge Boulders: LOW wind/EXCELLENT shelter/slowest drying), trail system weather notes, drying speed ranking, best/worst weather scenarios per area.

**Checkpoint**: All research data reviewed and ready for guide writing

---

## Phase 3: User Story 1 — Sandstone Primer & Drying Reference (Priority: P1) 🎯 MVP

**Goal**: A climber can determine whether it's safe to climb right now, how long to wait if not, and which wall angles are climbable first after rain. The foundational rock behavior reference.

**Independent Test**: Open `conditions/README.md` on a phone at the crag. A climber can determine within 30 seconds: (1) safe to climb now? (2) how long to wait? (3) which wall angles first?

### Implementation for User Story 1

- [x] T006 [US1] Create `conditions/README.md` with document header, introduction, and "Can I Climb Right Now?" quick decision section at top. Include: rock state table (dry/damp/wet/frozen/thawing → safe/no/wait + action), per FR-010 phone-first layout with quick reference at top. Link to detailed sections below via anchors. All data [UNVERIFIED] (FR-009).
- [x] T007 [US1] Write Nuttall sandstone primer section in `conditions/README.md` per FR-001. Include: rock composition (~98% quartz, silica cement, "bullet-hard"), friction behavior table (dry=excellent/wet=dangerous/frozen=excellent), seepage patterns (horizontal breaks, crack systems, formation contacts, 4-8 hr lag after rain stops), why seepage can increase after rain ends. Include "Why You Must Not Climb Wet Sandstone" subsection with rock preservation reasoning (friable when saturated, holds can break, community ethic). Accessible to first-time sandstone climbers. Source citations. All data [UNVERIFIED] (FR-009).
- [x] T008 [US1] Write drying reference table section in `conditions/README.md` per FR-002. Include: wall angle × conditions matrix (overhang/vertical/slab × sun+wind/overcast/overcast+cold) with time estimates from research. Distinguish "surface dry" vs. "friction restored" with explanation. Include February modifier note (add 20-50% to drying times in cold/overcast). Table ≤8 columns (FR-010). Cross-reference the existing drying table in `areas/README.md` for consistency (FR-007). All data [UNVERIFIED] (FR-009).
- [x] T009 [US1] Write freeze/thaw guide section in `conditions/README.md` per FR-008. Include: frozen rock friction behavior (excellent when dry-frozen), thaw cycle timeline for a typical February day (frozen overnight → thaw begins ~10 AM → wet transition → drying), danger of climbing during thaw transition (invisible meltwater film), how freeze/thaw affects trail conditions (cross-reference `trails/README.md` February tips). Include timeline table with times/temps/conditions/climbing impact. All data [UNVERIFIED] (FR-009).

**Checkpoint**: Sandstone primer and drying reference complete. A climber can make go/no-go decisions from their phone.

---

## Phase 4: User Story 2 — February Weather & Daily Planning (Priority: P2)

**Goal**: The group can interpret February weather forecasts and make morning activity decisions (climb, ride, or rest) with area recommendations.

**Independent Test**: Open `conditions/README.md` February weather section on a phone the morning of a climbing day. A group member can determine in under 60 seconds: (1) climbing day, biking day, or rest day? (2) which time window offers best conditions?

**Depends on**: Phase 3 (US1) — needs the document to exist.

### Implementation for User Story 2

- [x] T010 [US2] Add February weather data section to `conditions/README.md` per FR-003. Include: seasonal data table (avg high/low, precip days, precip types, wind speed/direction, daylight hours), typical February day timeline table (time × temp × conditions × climbing impact from 6 AM through sunset), extreme temperature notes, diurnal freeze/thaw cycle, expected climbable days in a 7-day window (~3-5), and multi-day rain event frequency. Source citations (NOAA climate normals, NWS Charleston). All data [UNVERIFIED] (FR-009). Tables ≤8 columns (FR-010).
- [x] T011 [US2] Add daily decision framework section to `conditions/README.md` per FR-004. Include: scenario table mapping weather conditions to activity and area recommendations with at least 6 scenarios per SC-005: (1) clear+cold+frozen, (2) clear+warm, (3) overcast+dry, (4) active rain, (5) post-rain drying (sunny+wind), (6) freeze/thaw transition day. Each row: scenario name, temp range, precipitation, wind, activity recommendation (climb/ride/rest), area recommendation, best time window, notes. Table ≤8 columns (FR-010). Link to area profiles and trail profiles (FR-007). All data [UNVERIFIED] (FR-009).

**Checkpoint**: February weather reference and daily framework complete. Group can make morning decisions.

---

## Phase 5: User Story 3 — Per-Area Weather Matrix (Priority: P3)

**Goal**: The group can compare all bouldering areas by weather conditions and identify the best area for today in under 30 seconds.

**Independent Test**: Open `conditions/README.md` per-area weather matrix on a phone. A group member can identify the best area for today's weather in under 30 seconds.

**Depends on**: Phase 3 (US1) — needs the document to exist.

### Implementation for User Story 3

- [x] T012 [US3] Add per-area weather comparison matrix to `conditions/README.md` per FR-005. Include: comparison table covering all 3 bouldering areas (Meadow River, Summersville Lake, Gorge Boulders) with: wind exposure, sun/shade pattern, shelter quality, drying speed rank and modifier, humidity, best conditions, worst conditions. Each area links to its profile in `areas/` (FR-007, FR-011). Add brief trail system weather notes for Arrowhead, Summit Bechtel, Babcock with links to `trails/` profiles. Table ≤8 columns (FR-010). All data [UNVERIFIED] (FR-009).
- [x] T013 [US3] Add wind patterns section to `conditions/README.md` per FR-006. Include: New River Gorge geography and wind (gorge orientation, prevailing west wind = sheltered gorge floor), rim vs. gorge floor wind comparison, how wind affects climbing (friction enhancement from drying, comfort reduction from wind chill), wind chill reference at common February temperatures. Add drying speed ranking (1. Meadow River fastest, 2. Summersville Lake moderate, 3. Gorge Boulders slowest) with explanation. All data [UNVERIFIED] (FR-009).

**Checkpoint**: Per-area weather comparison complete. Group can pick the best area based on weather.

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Cross-validate, add cross-references, and verify completeness.

- [x] T014 Add bidirectional links per FR-011: update `areas/README.md` to link its drying reference table to `conditions/README.md#drying-reference`, update `trails/README.md` February riding tips to cross-reference `conditions/README.md#freeze-thaw-guide`. Verify `conditions/README.md` links back to all area and trail profiles. Add sources and footer to `conditions/README.md`.
- [x] T015 [P] Verify all 11 functional requirements (FR-001 through FR-011) are met in `conditions/README.md`. Check each FR against the document and confirm compliance. Verify SC-005 (at least 6 weather scenarios). Verify SC-006 (internal consistency with existing area profiles).
- [x] T016 [P] Phone-readability check: verify all tables in `conditions/README.md` are ≤8 columns wide (FR-010), [UNVERIFIED] flags are present on all unverified data (FR-009), bidirectional links work (FR-011), IMBA difficulty ratings in trail notes are consistent with `trails/` profiles, and document renders correctly on GitHub mobile.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies — can start immediately
- **Foundational (Phase 2)**: Depends on Setup completion
- **US1 (Phase 3)**: Depends on Foundational (Phase 2) — BLOCKS US2, US3
- **US2 (Phase 4)**: Depends on US1 (Phase 3) — adds sections to `conditions/README.md`
- **US3 (Phase 5)**: Depends on US1 (Phase 3) — adds sections to `conditions/README.md`
- **Polish (Phase 6)**: Depends on US1, US2, US3 all complete

### User Story Dependencies

- **US1 (P1)**: Can start after Foundational (Phase 2) — Creates the file and foundational content
- **US2 (P2)**: Depends on US1 — adds weather and decision framework sections
- **US3 (P3)**: Depends on US1 — adds per-area matrix and wind sections. Independent of US2.

### Within Each User Story

- All tasks within a user story are sequential (same file, building content incrementally)
- No parallel opportunities within stories since all content goes into one file

### Parallel Opportunities

- **Phase 2**: T004, T005 can run in parallel (different research files)
- **Phase 3-5**: All sequential (single file, sections depend on prior sections)
- **Phase 4-5**: US2 and US3 add different sections — could theoretically be parallel but recommend sequential to avoid merge conflicts in same file
- **Phase 6**: T015 and T016 can run in parallel (different validation concerns)

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (verify prerequisites, create directory)
2. Complete Phase 2: Foundational (confirm research data)
3. Complete Phase 3: US1 — Write sandstone primer, drying reference, freeze/thaw guide
4. **STOP and VALIDATE**: A climber can make a go/no-go decision from their phone
5. The sandstone primer alone delivers the core value of the feature

### Incremental Delivery

1. Complete Setup + Foundational → Ready to write
2. Add US1 (sandstone primer + drying + freeze/thaw) → Core value delivered (MVP!)
3. Add US2 (February weather + daily framework) → Morning planning tool added
4. Add US3 (per-area matrix + wind) → Area comparison tool added
5. Polish → Cross-references, validation, phone readability confirmed
6. Each story adds a distinct planning capability without breaking previous stories
