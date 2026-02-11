# Tasks: Primary Bouldering Areas

**Input**: Design documents from `/specs/001-bouldering-areas/`
**Prerequisites**: plan.md (required), spec.md (required), research.md, data-model.md, contracts/

**Tests**: Not requested in the feature specification. No test tasks included.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

---

## Phase 1: Setup

**Purpose**: Create the deliverable directory structure.

- [x] T001 Create `areas/` directory at repository root

**Checkpoint**: Directory exists and is ready for document creation.

---

## Phase 2: Foundational (Research & Data Gathering)

**Purpose**: Gather factual data from web sources that MUST be complete before any area document can be written.

**CRITICAL**: No document writing (Phases 3+) can begin until research tasks produce verified data. All research tasks use `research.md` as a starting point and augment with live web sources.

- [x] T002 Research Meadow River bouldering area via Mountain Project, NRAC (newriverclimbing.net), and Google Maps. Gather: exact parking GPS coordinates, sector names, verified problem counts by grade band, land ownership, approach details, and winter road conditions. Record findings in `specs/001-bouldering-areas/research.md` under a new "Verified Data" section.
- [x] T003 [P] Research Summersville Lake bouldering via Mountain Project, USACE Huntington District website, and Google Maps. Gather: sector names, parking GPS coordinates, verified problem counts by grade band, 2026 winter drawdown schedule, winter gate status for access roads, and USACE recreation rules. Record findings in `specs/001-bouldering-areas/research.md` under a new "Verified Data" section.
- [x] T004 [P] Research Gorge Boulders (Endless Wall, Nuttall, Bridge Buttress, Kaymoor) via Mountain Project, NPS website (nps.gov/neri), and Google Maps. Gather: per-sector problem counts and grades, parking lot GPS coordinates for each trailhead, approach trail winter conditions, and which cliff-base boulders have documented shelter. Record findings in `specs/001-bouldering-areas/research.md` under a new "Verified Data" section.
- [x] T005 [P] Verify NPS bouldering regulations at nps.gov/neri/planyourvisit/climbing.htm and the current Superintendent's Compendium. Confirm: crash pad policy, chalk policy, entrance fees, group size limits, peregrine closure dates, winter parking hours, and Fayette Station Road winter status. Record findings in `specs/001-bouldering-areas/research.md` under a new "Verified Data" section.

**Checkpoint**: All research tasks complete. `research.md` contains verified data (or items confirmed as [UNVERIFIED]) for all three areas and NPS regulations. Document writing can begin.

---

## Phase 3: User Story 1 — Quick Area Selection at the Trailhead (Priority: P1)

**Goal**: A climber can select the best bouldering area for today's conditions within 60 seconds using the overview document on a phone.

**Independent Test**: Open `areas/README.md` on a phone. Without scrolling past the first screen, identify which area to visit based on today's weather and group composition.

- [x] T006 [US1] Write `areas/README.md` using `specs/001-bouldering-areas/contracts/overview-template.md` as the structural template. Fill the Area Summary table with data from research.md: area names (linked to profile files), drive times, rain resilience ratings, grade-band density indicators (V0-V3 | V4-V6 | V7-V10+), and one-line suitability notes. Include placeholder links to area profiles (meadow-river.md, summersville-lake.md, gorge-boulders.md).
- [x] T007 [US1] Add the Quick Decision Guide section to `areas/README.md` with specific area recommendations for five scenarios: dry+cold+sunny, raining now, rain stopped (drying), short session/low energy, and hard climbing priority. Use research.md rain resilience ratings to assign recommendations.
- [x] T008 [US1] Add the Nuttall Sandstone Drying Reference table, NPS Bouldering Regulations summary, and February Conditions table to `areas/README.md` using data from `specs/001-bouldering-areas/research.md` (Decisions 4, 5). Include the community ethic note about not climbing on wet Nuttall sandstone. Add the NRAC/NPS/USACE verification contacts at the bottom.

**Checkpoint**: `areas/README.md` is complete and independently functional. A climber can make a morning area selection using only this document. This is the MVP.

---

## Phase 4: User Story 2 — Detailed Area Scouting (Priority: P2)

**Goal**: Each area has a consistent, complete profile document with logistics, grade spread, weather resilience, approach, and regulations.

**Independent Test**: Pick any area profile. A first-time reader can extract driving directions, parking, approach, grade spread, and weather-resilience details without reading end-to-end.

- [x] T009 [P] [US2] Write `areas/meadow-river.md` using `specs/001-bouldering-areas/contracts/area-profile-template.md`. Fill all required sections with data from research.md: quick reference header (drive time, rain resilience, problem count, Google Maps link), grade band table, group suitability, weather resilience table (shelter, seepage, drying, wind, rain verdict), approach & access, regulations, and climbing style. Include sector breakdowns if research identified distinct sectors. Flag unverified claims with `[UNVERIFIED]`. Add sources list at bottom.
- [x] T010 [P] [US2] Write `areas/summersville-lake.md` using `specs/001-bouldering-areas/contracts/area-profile-template.md`. Fill all required sections with data from research.md. Include the winter drawdown advantage (77-ft drop exposing additional boulders in February). Note USACE land management, winter gate status for access roads, and Long Point trailhead as the most reliable winter access point. Include sector breakdowns if research identified distinct sectors (Long Point, Pirates Cove, etc.). Flag unverified claims with `[UNVERIFIED]`. Add sources list at bottom.
- [x] T011 [P] [US2] Write `areas/gorge-boulders.md` using `specs/001-bouldering-areas/contracts/area-profile-template.md`. Fill all required sections with data from research.md. MUST include 4 sector breakdowns: (1) Endless Wall / Fern Creek, (2) Nuttall / Fern Buttress, (3) Bridge Buttress, (4) Kaymoor. Each sector needs its own rain resilience rating, grade-band breakdown, shelter notes, and approach details from main parking. Note NPS regulations apply to all sectors. Flag Kaymoor as not recommended for February due to icy steel staircase. Flag unverified claims with `[UNVERIFIED]`. Add sources list at bottom.

**Checkpoint**: All three area profiles are complete. Each follows the same template structure. A climber can open any profile and find all required information in predictable locations.

---

## Phase 5: User Story 3 — Wet-Weather Fallback Planning (Priority: P3)

**Goal**: On a rainy day, the group can identify climbable rock and estimate when other areas will dry, using only the area documents.

**Independent Test**: Simulate a rainy-day decision. Using only the area documents, identify at least one area with problems climbable during active rain, and estimate drying times for other areas.

- [x] T012 [US3] Review and update the Quick Decision Guide in `areas/README.md` to include specific sector-level rain recommendations now that area profiles are written. The "Raining now" entry must name specific sectors (e.g., "Gorge Boulders → Endless Wall cliff-base overhangs" or "Meadow River → overhanging sector"). The "Rain stopped, drying" entry must reference the drying time table with area-specific notes.
- [x] T013 [US3] Verify that all three area profiles (`areas/meadow-river.md`, `areas/summersville-lake.md`, `areas/gorge-boulders.md`) have complete weather resilience tables with a "Rain verdict" row that explicitly answers: "Can you climb here during active rain? If so, which problems/sectors?" Ensure at least one area has a definitive "yes" answer with specific sector or problem type identified.

**Checkpoint**: A climber standing in rain can use README.md to find climbable rock within 60 seconds. Drying estimates are available for post-rain planning.

---

## Phase 6: User Story 4 — Hard-Climbing Objective Targeting (Priority: P4)

**Goal**: V10 climbers can rank areas by hard-problem concentration and identify whether hard lines are sheltered or exposed.

**Independent Test**: A V10 climber can identify the top areas for hard climbing by reading the overview table's V7-V10+ column and the profiles' grade-band tables.

- [x] T014 [US4] Review and update the V7-V10+ column in the Area Summary table in `areas/README.md` to ensure density indicators accurately reflect the verified data from each area profile. Ensure the "Hard climbing priority" entry in the Quick Decision Guide names the area with the best V7-V10+ density.
- [x] T015 [US4] Review all three area profiles and ensure the grade band table's V7-V10+ row includes style notes (e.g., "Few — overhanging, sheltered" or "Some — exposed vertical faces"). Verify that weather resilience sections note whether hard problems specifically are sheltered or exposed, so V10 climbers can plan around weather.

**Checkpoint**: V10 climbers can compare hard-problem density across all areas at a glance in README.md and find shelter/exposure details for hard problems in each profile.

---

## Phase 7: Polish & Cross-Cutting Concerns

**Purpose**: Validate consistency, completeness, and readability across all documents.

- [x] T016 Verify consistency between `areas/README.md` summary table data and the individual area profiles. Check: drive times, rain resilience ratings, and grade-band density indicators match between overview and profiles. Fix any discrepancies.
- [x] T017 [P] Verify all 11 functional requirements (FR-001 through FR-011) are met across all 4 documents in `areas/`. Walk through each FR and confirm it is satisfied, noting the specific document and section. Flag any gaps.
- [x] T018 [P] Verify all factual claims in `areas/` documents are sourced per FR-006. Check that every area profile has a sources list at the bottom. Confirm all unverified claims are flagged with `[UNVERIFIED]`. Ensure zero unsourced assertions exist.
- [x] T019 Verify `areas/README.md` Area Summary table renders readably at phone width. The table must have ≤7 columns and fit on one screen (~20 lines for decision-critical content). If the table is too wide, adjust column headers or content for phone legibility.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies — can start immediately
- **Foundational (Phase 2)**: Depends on Setup — BLOCKS all document writing
- **US1 (Phase 3)**: Depends on Foundational (Phase 2) — produces the MVP
- **US2 (Phase 4)**: Depends on Foundational (Phase 2) — can run in parallel with US1
- **US3 (Phase 5)**: Depends on US1 (Phase 3) AND US2 (Phase 4) — reviews and enhances existing docs
- **US4 (Phase 6)**: Depends on US2 (Phase 4) — reviews and enhances existing docs
- **Polish (Phase 7)**: Depends on all prior phases

### Parallel Opportunities

- **Phase 2**: T003, T004, T005 can all run in parallel with T002
- **Phase 3**: T006 → T007 → T008 are sequential (building the same file)
- **Phase 4**: T009, T010, T011 can all run in parallel (different files)
- **Phase 5**: T012 and T013 are sequential (T012 updates README, T013 verifies profiles)
- **Phase 6**: T014 and T015 can run in parallel (different files)
- **Phase 7**: T017 and T018 can run in parallel

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (T001)
2. Complete Phase 2: Research (T002-T005)
3. Complete Phase 3: Write README.md overview (T006-T008)
4. **STOP and VALIDATE**: Can a climber select an area using only README.md?
5. This delivers decision-making value even without detailed profiles.

### Incremental Delivery

1. Setup + Research → Foundation ready
2. Add US1 (README.md) → MVP: morning area selection works
3. Add US2 (3 area profiles) → Full detail: logistics, approach, grades, weather
4. Add US3 (wet-weather enhancement) → Rain-day decisions are airtight
5. Add US4 (hard-climbing enhancement) → V10 climbers can plan the week
6. Polish → Consistency validated, sources verified, phone-tested

### Parallel Execution Example

```
After Phase 2 completes:

Agent A: T006 → T007 → T008 (README.md, sequential)
Agent B: T009 (meadow-river.md)
Agent C: T010 (summersville-lake.md)
Agent D: T011 (gorge-boulders.md)

After all profiles complete:

Agent A: T012 → T013 (wet-weather review)
Agent B: T014 (overview hard-climbing update)
Agent C: T015 (profile hard-climbing review)
```

---

## Notes

- [P] tasks = different files, no dependencies
- [Story] label maps task to specific user story for traceability
- All area profiles use `specs/001-bouldering-areas/contracts/area-profile-template.md` as structural template
- README.md uses `specs/001-bouldering-areas/contracts/overview-template.md` as structural template
- Research data is in `specs/001-bouldering-areas/research.md`
- Data model (profile schema) is in `specs/001-bouldering-areas/data-model.md`
- Commit after each phase or logical group
- Stop at any checkpoint to validate independently
