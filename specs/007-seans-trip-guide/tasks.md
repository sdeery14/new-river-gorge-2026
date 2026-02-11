# Tasks: Sean's Personal Trip Guide

**Input**: Design documents from `/specs/007-seans-trip-guide/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, contracts/seans-guide-template.md, quickstart.md

**Tests**: Not requested — no test tasks included.

**Organization**: Tasks grouped by user story. US1 (P1) is the MVP daily decision matrix. US2-US4 write to different sections and can run in parallel after Setup. Supporting content depends on US1-US4 for cross-references.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different sections, no dependencies)
- **[Story]**: Which user story this task belongs to (US1, US2, US3, US4)
- All paths relative to repository root

---

## Phase 1: Setup

**Purpose**: Create deliverable file and establish document structure

- [x] T001 Create `sean/` directory and copy template from `specs/007-seans-trip-guide/contracts/seans-guide-template.md` to `sean/README.md`
- [x] T002 Replace template header placeholders in `sean/README.md` with: Sean's context (V1-V3 bouldering, MTB priority), trip dates (Feb 14-21, 2026), second-person voice intro, and link to group documents

**Checkpoint**: Document scaffold ready with structure and header in place.

---

## Phase 2: User Story 1 — Daily Decision Matrix (Priority: P1) 🎯 MVP

**Goal**: Enable Sean to determine his recommended activity for any weather scenario within 30 seconds.

**Independent Test**: Open `sean/README.md` on a phone, pick a weather scenario (e.g., "35°F, cloudy, rained last night"), and find the recommended activity and destination within 30 seconds.

### Implementation

- [x] T003 [US1] Populate the Daily Decision Matrix table in `sean/README.md` using conditions/README.md decision framework, personalized for Sean's V1-V3 goals and MTB priority. Write at least 6 scenario rows per data-model.md Decision Matrix Row entity: Clear+Cold+High Energy (bike AM → boulder PM), Clear+Warm (Summersville Lake slabs), Rain/Drizzle (Gorge overhangs or rest), Freeze/Thaw Morning (bike frozen ground → boulder after noon), Windy+Dry (Meadow River wind-exposed), Extended Wet (rest day). Each row must include: scenario, activity, destination, time window, one-line rationale
- [x] T004 [US1] Write fallback guidance below the decision matrix in `sean/README.md`. Include: "If trails are too wet to ride" redirect to bouldering, "If all areas are wet" nuclear rest-day plan referencing Sean's food picks and rest-day activities from US4 section. Add note about checking conditions/README.md for detailed weather data

**Checkpoint**: Decision matrix populated. Sean can find his activity recommendation for any weather in 30 seconds.

---

## Phase 3: User Story 2 — Bouldering Hit List (Priority: P2)

**Goal**: Provide Sean with a curated V1-V3 problem list at each area so he doesn't have to scan the full area profiles.

**Independent Test**: Open `sean/README.md`, pick an area (Summersville Lake), find at least 3 V1-V3 problems with grade, style, and personal note within 30 seconds.

**Can run in parallel with Phase 2** — writes to a different section of the document.

### Implementation

- [x] T005 [P] [US2] Write Summersville Lake hit list subsection in `sean/README.md` using research.md Section 1 data. Mark as "Your Best Beginner Area." Include all 13 named V0-V3 problems in a table per data-model.md Hit List Entry: problem name, grade, style, shelter status, and personal quality note. Highlight 4 classics (⭐). Note: all flat landings (safest), February drawdown exposes extra boulders, but POOR rain resilience. Link to full profile at `areas/summersville-lake.md`
- [x] T006 [P] [US2] Write Meadow River hit list subsection in `sean/README.md` using research.md Section 1 data. Mark as "Your Rain-Day Backup." Include all 6 named V0-V3 problems in a table. Highlight 2 classics (⭐ The Warm-Up, Juggy Roof). Note: 3 sheltered problems for rain days, flat landings, short roadside approaches. Link to full profile at `areas/meadow-river.md`
- [x] T007 [P] [US2] Write Gorge Boulders hit list subsection in `sean/README.md` using research.md Section 1 data. Mark as "Shelter Day Only" with honest note: limited V1-V3 (6 usable, excluding Kaymoor Feb), all uneven landings, hazardous approaches. Include 6 usable problems in a table. Highlight 1 classic (⭐ Gorge Warm-Up). Note Kaymoor exclusion (icy steel steps). Link to full profile at `areas/gorge-boulders.md`
- [x] T008 [US2] Write Skills Progression subsection in `sean/README.md` using research.md progression path. Show ordered path from V0 → V3 by style: Slab (Long Point Warm-Up → Lakeshore Slab → River Slab), Overhang (Easy Overhang → Juggy Roof → Gorge Warm-Up), Mantle (The Platform → Meadow Mantle → Sandy Mantle), Traverse (Easy Traverse → Beginner Traverse)

**Checkpoint**: Bouldering hit list complete with 25+ curated problems across 3 areas. Sean can find problems in his grade at any area without opening full profiles.

---

## Phase 4: User Story 3 — Mountain Biking Priority Stack (Priority: P3)

**Goal**: Give Sean a ranked trail list with conditions gates so he doesn't default to "just boulder" when riding is viable.

**Independent Test**: Open `sean/README.md`, find trail #1, see what conditions it needs, and find the fallback.

**Can run in parallel with Phases 2 and 3** — writes to a different section.

### Implementation

- [x] T009 [P] [US3] Write MTB priority stack summary table in `sean/README.md` using research.md Section 2. Include 3 rows per data-model.md Trail Priority Entry: rank, trail name, drive time, conditions gate, fallback. Add February reality note ("opportunistic, not guaranteed — you may get zero rideable days") and community ethic warning (never ride wet/soft trails). Add "don't ride" scenario row directing to bouldering or rest
- [x] T010 [US3] Write individual trail subsections (#1 Arrowhead, #2 Summit Bechtel, #3 Babcock) in `sean/README.md`. One paragraph each in second-person voice with: why this rank, what conditions it needs, best pairing with bouldering (e.g., Arrowhead AM → Gorge PM), access notes, and link to full trail profile in `trails/`

**Checkpoint**: MTB priority stack complete. Sean knows which trail to ride first and when to skip riding entirely.

---

## Phase 5: User Story 4 — Food, Drink & Rest-Day Picks (Priority: P4)

**Goal**: Curate Sean's personal dining, brewery, and rest-day favorites so he has a "definitely want to hit" list.

**Independent Test**: Open `sean/README.md`, find Sean's top 3 dining picks with personal notes about what to try.

**Can run in parallel with Phases 2-4** — writes to a different section.

### Implementation

- [x] T011 [P] [US4] Write dining picks table in `sean/README.md` using research.md Section 3 curations. Include 4-6 restaurants per data-model.md Personal Pick entity: name, type, personal note (what to try/why), best-for occasion. Highlight Cathedral Cafe (brunch), Pies & Pints (group dinner), Secret Sandwich Society (casual), The Handle Bar (post-ride). Flag all February hours as [UNVERIFIED]. Link to full rest-day guide
- [x] T012 [P] [US4] Write breweries & taphouses table in `sean/README.md`. Include Bridge Brew Works and Southside Junction Tap House with personal notes on beer style focus and food availability. Flag February hours as [UNVERIFIED]
- [x] T013 [US4] Write "Your Rest-Day Flow" suggested itinerary in `sean/README.md`. Combine dining + activity picks into a suggested day: morning (Cathedral Cafe brunch) → midday (Canyon Rim Boardwalk or Endless Wall Trail) → afternoon (Water Stone Outdoors for beta) → evening (Pies & Pints or brewery). Reference full rest-day guide for more options

**Checkpoint**: Food & rest-day picks complete. Sean has his personal favorites list ready to share with the group.

---

## Phase 6: Supporting Content

**Purpose**: Sample week, packing checklist, and logistics that reference US1-US4 content

**Depends on**: Phases 2-5 (references decision matrix scenarios, area picks, dining choices)

- [x] T014 Write sample week itinerary table in `sean/README.md` per FR-011 and data-model.md Sample Day entity. Cover 8 days (Sat Feb 14 arrival through Sat Feb 21 departure). Include realistic weather variation: 3 clear days, 1 freeze/thaw, 1 rain day, 1 rest day, roster-change Wednesday. Each row: day, weather, morning activity, afternoon activity, evening plan, notes. Clearly label as "example itinerary — not a prediction"
- [x] T015 Write packing checklist in `sean/README.md` per FR-006 and data-model.md Packing Item entity. Four categories: Bouldering Gear (crash pad, shoes, chalk, brush — nylon only per NPS), Mountain Biking Gear (helmet, gloves, bike or rental note), February Weather Gear (microspikes, layers, rain shell, headlamp), General (phone charger, offline maps downloaded, this guide downloaded). Each item with one-line "why" note. Use checkbox format
- [x] T016 Write logistics summary in `sean/README.md` per FR-007. Include: trip details table (arrival Sat Feb 14, departure Sat Feb 21, car assignment TBD, lodging TBD, roster-change role: present full week), emergency contacts table (NPS, local hospital, group contact), and key links section pointing to all 5 group documents (areas/, trails/, conditions/, rest-day/, logistics/)

**Checkpoint**: Supporting content complete. Sean has a full-week itinerary example, gear checklist, and personal logistics reference.

---

## Phase 7: Polish & Cross-Cutting Concerns

**Purpose**: Quality assurance across all sections — source verification, formatting, scope compliance, link validation

- [x] T017 [P] Source verification pass on `sean/README.md` per FR-009. For every factual claim (problem grades, drive times, restaurant hours, trail conditions): confirm a source is cited or inherited from Features 001-006 with `[UNVERIFIED]` flag preserved. Flag any new uncited claim with `[UNVERIFIED]`. Verify SC-004: 100% of claims sourced or flagged
- [x] T018 [P] Phone readability check on `sean/README.md` per FR-008. Verify: all tables ≤6 columns (data-model allows max 6 fields per table), sections have clear headings, content is skimmable on a mobile screen. Fix any table exceeding column limit
- [x] T019 [P] Scope compliance check on `sean/README.md` per FR-010. Search entire document for sport climbing, trad climbing, route climbing, pitch, or gear-list-for-roped-climbing references. Remove any found. Confirm 100% bouldering-trip context. Verify SC-005
- [x] T020 Cross-reference link validation on `sean/README.md`. Verify every profile link (areas/, trails/, conditions/, rest-day/, logistics/) resolves to an actual file. Verify no broken anchor links. No orphaned references to nonexistent profiles
- [x] T021 Write document footer in `sean/README.md` with last-updated date (2026-02-11), source note ("All problem data from Feature 002 [UNVERIFIED]. Verify conditions morning-of."), and "This guide is for you, Sean" closing

**Checkpoint**: All quality gates pass. Document ready for checklist validation.

---

## Dependencies & Execution Order

### Phase Dependencies

```
Phase 1: Setup ──────────────────────────┐
                                          ▼
Phase 2: US1 (Decision Matrix) ─────────┐
                                         │
Phase 3: US2 (Hit List) ───────────────┤ (US1-US4 can all run in parallel)
                                         │
Phase 4: US3 (MTB Stack) ──────────────┤
                                         │
Phase 5: US4 (Food Picks) ─────────────┤
                                         │
                                         ▼
Phase 6: Supporting Content ───────────┐
                                        │
                                        ▼
Phase 7: Polish ─────────────────────── (depends on all content complete)
```

### User Story Dependencies

- **US1 (P1)**: Can start after Setup. No dependencies on other stories. **Start here — MVP.**
- **US2 (P2)**: Can start after Setup. No dependencies on other stories. **Can run parallel with US1.**
- **US3 (P3)**: Can start after Setup. No dependencies on other stories. **Can run parallel with US1/US2.**
- **US4 (P4)**: Can start after Setup. No dependencies on other stories. **Can run parallel with US1-US3.**

### Parallel Opportunities

**Between Phases 2-5**:
- All four user stories (T003-T013) write to different sections — all can run in parallel

**Within Phase 3 (US2)**:
- T005, T006, T007 can run in parallel (different area subsections)

**Within Phase 5 (US4)**:
- T011 and T012 can run in parallel (dining vs. brewery subsections)

**Within Phase 7 (Polish)**:
- T017, T018, T019 can all run in parallel (different validation concerns)

---

## Implementation Strategy

### MVP First (Decision Matrix Only)

1. Complete Phase 1: Setup (T001-T002)
2. Complete Phase 2: US1 — Daily Decision Matrix (T003-T004)
3. **STOP and VALIDATE**: Sean can already determine his recommended activity for any weather scenario in 30 seconds. Minimum viable personal guide.

### Incremental Delivery

1. Setup → Document scaffold ready
2. Add US1 (Decision Matrix) → Sean can decide what to do each morning
3. Add US2 (Hit List) → Sean knows which problems to try at each area
4. Add US3 (MTB Stack) → Sean knows which trail to ride and when
5. Add US4 (Food Picks) → Sean has his personal dining/rest favorites
6. Add Supporting Content → Full week itinerary, packing list, logistics
7. Polish → All quality gates verified

Each increment adds standalone value without breaking previous content.

---

## Notes

- All tasks write to a single file: `sean/README.md`
- [P] tasks write to different sections — no merge conflicts
- V1-V3 problem data in `specs/007-seans-trip-guide/research.md` is the primary source for hit list tasks
- Required fields per entity type are defined in `specs/007-seans-trip-guide/data-model.md`
- Second-person voice throughout ("Your best slab day", "You'll want to ride early")
- Curated inlining: problem names/grades/notes inline, full profiles linked
- All problem data from Features 001-002 is [UNVERIFIED] — preserve those flags
- Restaurant hours flagged [UNVERIFIED] unless confirmed for February
- Sample week itinerary is hypothetical — clearly label as example, not prediction
