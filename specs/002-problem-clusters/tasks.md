# Tasks: Problem Clusters

**Input**: Design documents from `/specs/002-problem-clusters/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, contracts/, quickstart.md

**Tests**: Not applicable — this is a documentation-only feature (Markdown files).

**Organization**: Tasks are grouped by user story. US2 and US3 depend on US1 being complete. US4 is a verification pass on US1 output.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

---

## Phase 1: Setup

**Purpose**: Verify prerequisites and confirm project structure is ready

- [x] T001 Verify `areas/` directory exists with Feature 001 deliverables (README.md, meadow-river.md, summersville-lake.md, gorge-boulders.md)
- [x] T002 Verify research.md problem data is organized by area and grade band in `specs/002-problem-clusters/research.md`

---

## Phase 2: Foundational (Research Data Prep)

**Purpose**: Organize research data into implementation-ready format before writing deliverables

**⚠️ CRITICAL**: Per-area problem cluster writing (Phase 3) cannot begin until research data is confirmed organized.

- [x] T003 Review and finalize problem data for Meadow River: confirm 17 problems across 3 grade bands with all required fields (name, grade, style, shelter, landing, location, classic, conditions, source) from `specs/002-problem-clusters/research.md`
- [x] T004 [P] Review and finalize problem data for Summersville Lake: confirm 32 problems across 3 grade bands with all required fields from `specs/002-problem-clusters/research.md`
- [x] T005 [P] Review and finalize problem data for Gorge Boulders: confirm 26 problems across 4 sectors and 3 grade bands with all required fields from `specs/002-problem-clusters/research.md`

**Checkpoint**: All problem data reviewed and ready for document writing

---

## Phase 3: User Story 1 — Grade-Band Problem Selection (Priority: P1) 🎯 MVP

**Goal**: Each area has a problem cluster document with problems organized by grade band (V7-V10+ first), each entry containing name, grade, style, shelter, landing, location, and MP link. Summary counts at top of each grade band.

**Independent Test**: Open any area's problem cluster document on a phone. A V6 climber can identify 3+ quality problems at their grade within 30 seconds.

### Implementation for User Story 1

- [x] T006 [P] [US1] Write Meadow River problem clusters document at `areas/problems-meadow-river.md` using template `specs/002-problem-clusters/contracts/problem-cluster-template.md` and data from `specs/002-problem-clusters/research.md`. Include: header with link to `meadow-river.md` (FR-011), summary table with curated/classic/sheltered counts per grade band (FR-005), V7-V10+ section FIRST with conditions notes (FR-006), V4-V6 section, V0-V3 section. Organize by sector within grade bands. Each problem entry: name, grade, style, shelter status + shelter type (FR-004), landing (FR-010), location, classic marker ⭐ (FR-003), MP link where available. All entries cite source and flag [UNVERIFIED] (FR-007). 17 problems total (4 V7-V10+, 7 V4-V6, 6 V0-V3).
- [x] T007 [P] [US1] Write Summersville Lake problem clusters document at `areas/problems-summersville-lake.md` using template and research data. Include: header with link to `summersville-lake.md` (FR-011), summary table (FR-005), V7-V10+ FIRST with conditions (FR-006), V4-V6, V0-V3. Organize by sector (Long Point, Pirates Cove, Orange Oswald, Dam/Salmon Run) within grade bands (FR-012). Each entry per FR-002 schema. Note winter drawdown context. 32 problems total (6 V7-V10+, 13 V4-V6, 13 V0-V3).
- [x] T008 [P] [US1] Write Gorge Boulders problem clusters document at `areas/problems-gorge-boulders.md` using template and research data. Include: header with link to `gorge-boulders.md` (FR-011), summary table (FR-005), V7-V10+ FIRST with conditions (FR-006), V4-V6, V0-V3. MUST organize by sector (Endless Wall, Nuttall/Fern Buttress, Bridge Buttress, Kaymoor) within each grade band (FR-012). Flag Kaymoor as NOT RECOMMENDED FOR FEBRUARY. Each entry per FR-002 schema. 26 problems total (8 V7-V10+, 10 V4-V6, 8 V0-V3).

**Checkpoint**: All 3 per-area problem cluster documents complete. Each should be independently readable and useful on a phone.

---

## Phase 4: User Story 2 — Rainy-Day Sheltered Problem List (Priority: P2)

**Goal**: A single cross-area document listing all sheltered quality problems, organized by area then grade band. Rain-day decision tool — 60-second scan to find climbable rock.

**Independent Test**: Simulate active rain. Find at least 5 sheltered problems across all areas within 60 seconds, with grades spanning all three ability bands.

**Depends on**: Phase 3 (US1) — needs completed per-area docs for shelter data aggregation.

### Implementation for User Story 2

- [x] T009 [US2] Write cross-area sheltered classics summary at `areas/sheltered-classics.md` using template `specs/002-problem-clusters/contracts/cross-area-summary-template.md` (Variant 1). Aggregate all sheltered and partially sheltered problems from the 3 per-area documents. Organize by area (Meadow River first — best rain-day area, then Gorge Boulders, then Summersville Lake). Under each area: group by grade band (V7-V10+ first). Each entry: problem name, grade, style, shelter type (FR-004), landing, location, MP link. Include "How to Use" section with rain-day decision flow. Include rain resilience rating per area with link to area profile. Sources section. ~25 sheltered problems total across all areas.

**Checkpoint**: Rain-day reference document complete. Usable as standalone decision tool.

---

## Phase 5: User Story 3 — Hard-Climbing Week Planner (Priority: P3)

**Goal**: All V7-V10+ problems across all areas in a single table, sorted by grade (hardest first), classics highlighted, with conditions notes for projecting.

**Independent Test**: A V10 climber can build a ranked list of their top 10 objectives by scanning this document in under 5 minutes.

**Depends on**: Phase 3 (US1) — needs completed per-area docs for V7-V10+ data aggregation.

### Implementation for User Story 3

- [x] T010 [US3] Write cross-area hard-climbing summary at `areas/hard-climbing.md` using template `specs/002-problem-clusters/contracts/cross-area-summary-template.md` (Variant 2). Aggregate all V7-V10+ problems from the 3 per-area documents into a single table. Columns: Area, Sector, Problem (with MP link), Grade, Style, Shelter, Landing, Conditions, Classic. Sort by grade descending, then classics first within each grade. Include "How to Use" section with week-planning flow. Include shelter column for rain-day cross-reference (US3 acceptance scenario 2). Flag Kaymoor problems with February approach warning. Sources section. 18 hard problems total.

**Checkpoint**: V10 week planner complete. Covers all hard climbing across all areas in one view.

---

## Phase 6: User Story 4 — Mixed-Ability Session Planning (Priority: P4)

**Goal**: Summary tables in each per-area document make it obvious whether an area supports a mixed-ability session. Quick comparison across areas.

**Independent Test**: The group can compare problem cluster density across areas and choose one where all three ability bands have at least 3 curated problems.

**Depends on**: Phase 3 (US1) — summary tables are part of the per-area docs.

### Implementation for User Story 4

- [x] T011 [US4] Verify and enhance summary tables in all 3 per-area documents (`areas/problems-meadow-river.md`, `areas/problems-summersville-lake.md`, `areas/problems-gorge-boulders.md`) for mixed-ability comparison. Confirm each summary table shows curated count, classic count, and sheltered count per grade band. Verify Summersville Lake V0-V3 section has the most curated beginner problems of any area (acceptance scenario 2). Ensure grade bands with zero problems explicitly state "No documented problems in this grade range" (edge case). Confirm counts are accurate and match the problems listed below.

**Checkpoint**: Mixed-ability comparison is immediately visible from summary tables across all areas.

---

## Phase 7: Polish & Cross-Cutting Concerns

**Purpose**: Cross-validate all deliverables for consistency, completeness, and readability.

- [x] T012 Verify all 12 functional requirements (FR-001 through FR-012) are met across all 5 deliverable documents. Check each FR against the relevant document(s) and confirm compliance.
- [x] T013 [P] Verify consistency between problem cluster documents and Feature 001 area profiles. Check that area names, sector names, shelter descriptions, and problem density claims in `areas/README.md`, `areas/meadow-river.md`, `areas/summersville-lake.md`, `areas/gorge-boulders.md` align with the problem cluster data.
- [x] T014 [P] Verify cross-area summary consistency: confirm every sheltered problem in `areas/sheltered-classics.md` also appears (with matching shelter status) in its source per-area document. Confirm every V7-V10+ problem in `areas/hard-climbing.md` also appears in its source per-area document. No orphan entries.
- [x] T015 Phone-readability check: verify all tables in all 5 documents are ≤8 columns wide (per plan constraints), all MP links are tappable markdown format `[Name](url)`, classic markers use ⭐ consistently, and [UNVERIFIED] flags are present on all unverified data. Verify documents render correctly on GitHub mobile.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies — can start immediately
- **Foundational (Phase 2)**: Depends on Setup completion
- **US1 (Phase 3)**: Depends on Foundational (Phase 2) — BLOCKS US2, US3, US4
- **US2 (Phase 4)**: Depends on US1 (Phase 3) — needs per-area shelter data
- **US3 (Phase 5)**: Depends on US1 (Phase 3) — needs per-area V7-V10+ data
- **US4 (Phase 6)**: Depends on US1 (Phase 3) — verifies summary tables
- **Polish (Phase 7)**: Depends on US1, US2, US3, US4 all complete

### User Story Dependencies

- **US1 (P1)**: Can start after Foundational (Phase 2) — No dependencies on other stories
- **US2 (P2)**: Depends on US1 — aggregates shelter data from per-area docs
- **US3 (P3)**: Depends on US1 — aggregates V7-V10+ data from per-area docs. Independent of US2.
- **US4 (P4)**: Depends on US1 — verifies summary tables in per-area docs. Independent of US2 and US3.

### Within Each User Story

- US1: All 3 per-area documents (T006, T007, T008) can run in parallel [P]
- US2: Single document (T009), sequential
- US3: Single document (T010), sequential. Can run in parallel with US2 (T009).
- US4: Verification pass (T011), sequential after US1

### Parallel Opportunities

- **Phase 2**: T004 and T005 can run in parallel (different areas)
- **Phase 3 (US1)**: T006, T007, T008 can ALL run in parallel (different files, no dependencies)
- **Phase 4-6**: T009 (US2) and T010 (US3) can run in parallel (different files, both depend only on US1)
- **Phase 7**: T013 and T014 can run in parallel (different validation concerns)

---

## Parallel Example: User Story 1

```bash
# Launch all 3 per-area problem cluster documents in parallel:
Task: "Write Meadow River problem clusters in areas/problems-meadow-river.md"
Task: "Write Summersville Lake problem clusters in areas/problems-summersville-lake.md"
Task: "Write Gorge Boulders problem clusters in areas/problems-gorge-boulders.md"
```

## Parallel Example: User Stories 2 & 3

```bash
# After US1 is complete, launch cross-area summaries in parallel:
Task: "Write sheltered classics summary in areas/sheltered-classics.md"
Task: "Write hard-climbing summary in areas/hard-climbing.md"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (verify prerequisites)
2. Complete Phase 2: Foundational (confirm research data)
3. Complete Phase 3: US1 — Write 3 per-area problem cluster documents
4. **STOP and VALIDATE**: Each document should be independently usable on a phone
5. The 3 per-area docs alone deliver the core value of the feature

### Incremental Delivery

1. Complete Setup + Foundational → Ready to write
2. Add US1 (3 per-area docs) → Test independently → Core value delivered (MVP!)
3. Add US2 (sheltered-classics.md) + US3 (hard-climbing.md) in parallel → Rain-day + week-planning tools
4. Add US4 (summary verification) → Mixed-ability comparison confirmed
5. Polish → Cross-validate everything, phone readability confirmed
6. Each story adds a distinct planning capability without breaking previous stories
