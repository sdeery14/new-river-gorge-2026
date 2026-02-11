# Tasks: Interactive Area Maps

**Input**: Design documents from `/specs/008-interactive-area-maps/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, contracts/geojson-feature-schema.md, quickstart.md

**Tests**: Not requested — no test tasks included.

**Organization**: Tasks grouped by user story. US1 (P1) is the MVP regional overview. US2-US4 write to different map files and can run in parallel after Setup. Polish depends on all maps being complete.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (US1, US2, US3, US4)
- All paths relative to repository root

---

## Phase 1: Setup

**Purpose**: Create map directory and establish file structure

- [x] T001 Create `maps/` directory at repository root

**Checkpoint**: Directory structure ready.

---

## Phase 2: User Story 1 — Regional Overview Map (Priority: P1) 🎯 MVP

**Goal**: Show all bouldering areas, trail systems, and Fayetteville on one map for instant spatial orientation.

**Independent Test**: Open `maps/README.md` on GitHub. An interactive map renders with 7 labeled markers. Clicking any marker shows its name, category, and drive time.

### Implementation

- [x] T002 [US1] Build `maps/regional-overview.geojson` with 7 point markers per data-model.md and contracts/geojson-feature-schema.md: Summersville Lake (bouldering-area, red), Meadow River (bouldering-area, red), Gorge Boulders (bouldering-area, red), Arrowhead Trails (trail-system, green), Summit Bechtel Reserve (trail-system, green), Babcock State Park (trail-system, green), Fayetteville Town Center (town, teal). Use coordinates from research.md Section 2; look up missing coordinates via Google Maps. Each marker: `title`, `description` (category + drive time from Fayetteville), `marker-color`, `marker-size` per plan.md color scheme. All coordinates [UNVERIFIED]
- [x] T003 [US1] Write `maps/README.md` with: header explaining the maps directory, inline `geojson` code block embedding the regional overview map content, legend table (color → category mapping), note about offline maps ("These maps require GitHub rendering — download Google Maps offline for use at the crag"), and links to individual area/trail map files

**Checkpoint**: Regional overview map renders on GitHub. Users can see all 7 locations and their spatial relationships. MVP complete.

---

## Phase 3: User Story 2 — Bouldering Area Sector Maps (Priority: P2)

**Goal**: Show sectors, parking, and trailheads within each bouldering area for on-the-ground navigation.

**Independent Test**: Open `areas/summersville-lake.md` on GitHub. An inline map renders showing sectors (Long Point, Pirates Cove, Orange Oswald) and parking with color-coded markers. Click a sector marker to see grade density and shelter status.

**Can run in parallel with Phases 4-5** — writes to different map files and different Markdown documents.

### Implementation

- [x] T004 [P] [US2] Build `maps/summersville-lake.geojson` using coordinates from research.md and `areas/summersville-lake.md`. Include markers for: Long Point sector (red, large), Pirates Cove sector (red, large), Orange Oswald Wall Area sector (red, large), Long Point TH parking (gray, small — 38.1350, -80.8920). Each sector description: grade density, shelter status (all Exposed for Summersville), landing type (flat lakebed). Mark all coordinates [UNVERIFIED]
- [x] T005 [P] [US2] Build `maps/meadow-river.geojson` using coordinates from research.md and `areas/meadow-river.md`. Include markers for: Main Area/Roadside sector (red, large — near 38.0210, -80.8590), River Boulders sector (red, large), Upstream/Upper Meadow sector (red, large), gravel pulloff parking (gray, small). Each sector description: grade density, shelter status (Sheltered for overhangs, Exposed for others), short approaches. Mark all coordinates [UNVERIFIED]
- [x] T006 [P] [US2] Build `maps/gorge-boulders.geojson` using coordinates from research.md and `areas/gorge-boulders.md`. Include markers for: Endless Wall/Fern Creek sector (red, large), Nuttall/Fern Buttress sector (red, large), Endless Wall TH parking (gray, small — 38.0670, -81.0785), Nuttall TH parking (gray, small — 38.0710, -81.0835), Bridge Buttress/Fayette Station parking (gray, small — 38.0705, -81.0830), Canyon Rim VC parking (gray, small — 38.0700, -81.0750), Kaymoor TH parking (gray, small — 38.0580, -81.0690, note: ⚠️ icy steps in February). Each sector description: grade density, shelter status (Good shelter at cliff base), approach time. Mark all coordinates [UNVERIFIED]
- [x] T007 [P] [US2] Embed inline `geojson` code block + legend in `areas/summersville-lake.md`. Add an "Area Map" section with: the full GeoJSON content from `maps/summersville-lake.geojson` in a ```geojson code block, a legend table, and a note that markers are approximate [UNVERIFIED]. Place after the header/quick-reference section, before detailed sector descriptions
- [x] T008 [P] [US2] Embed inline `geojson` code block + legend in `areas/meadow-river.md` using same pattern as T007 with content from `maps/meadow-river.geojson`
- [x] T009 [P] [US2] Embed inline `geojson` code block + legend in `areas/gorge-boulders.md` using same pattern as T007 with content from `maps/gorge-boulders.geojson`

**Checkpoint**: All 3 bouldering area profiles show inline maps with sectors and parking. Users can navigate to sectors from the map.

---

## Phase 4: User Story 3 — Trail System Maps (Priority: P3)

**Goal**: Show trail system areas, parking, and access points for each MTB destination.

**Independent Test**: Open `trails/arrowhead.md` on GitHub. An inline map renders showing the trail system area and parking location.

**Can run in parallel with Phases 3 and 5** — writes to different map files and different Markdown documents.

### Implementation

- [x] T010 [P] [US3] Build `maps/arrowhead.geojson` using coordinates from research.md and `trails/arrowhead.md`. Include markers for: Arrowhead Trails system (green, large), trailhead parking (gray, small), The Handle Bar + Kitchen at Arrowhead Bike Farm (gold, medium — post-ride beer). Look up precise coordinates via Google Maps. Mark all [UNVERIFIED]
- [x] T011 [P] [US3] Build `maps/summit-bechtel.geojson` using coordinates from research.md and `trails/summit-bechtel.md`. Include markers for: Summit Bechtel Reserve system (green, large), parking/entrance (gray, small — 2550 Jack Furst Dr, Glen Jean). Description MUST include access note: "⚠️ MUST call (304) 465-2800 before driving — public access NOT guaranteed." Mark all [UNVERIFIED]
- [x] T012 [P] [US3] Build `maps/babcock.geojson` using coordinates from research.md and `trails/babcock.md`. Include markers for: Babcock State Park system (green, large — 486 Babcock Rd, Clifftop), parking (gray, small), Glade Creek Grist Mill (teal, small — scenic point of interest). Description: note winter road access uncertainty, call (304) 438-3004. Mark all [UNVERIFIED]
- [x] T013 [P] [US3] Embed inline `geojson` code block + legend in `trails/arrowhead.md`. Add a "Trail Map" section with the full GeoJSON content, legend, and [UNVERIFIED] note. Place after the header/quick-reference section
- [x] T014 [P] [US3] Embed inline `geojson` code block + legend in `trails/summit-bechtel.md` using same pattern as T013
- [x] T015 [P] [US3] Embed inline `geojson` code block + legend in `trails/babcock.md` using same pattern as T013

**Checkpoint**: All 3 trail profiles show inline maps with trail areas and parking.

---

## Phase 5: User Story 4 — Town Amenities Map (Priority: P4)

**Goal**: Show curated dining, brewery, gear shop, and supply locations in Fayetteville.

**Independent Test**: Open `maps/README.md` on GitHub. A second inline map (below the regional overview) renders with markers for all dining picks, breweries, Water Stone Outdoors, Walmart, and Sheetz.

**Can run in parallel with Phases 3 and 4** — writes to a different map file and adds to `maps/README.md` (different section than US1).

### Implementation

- [x] T016 [US4] Build `maps/town-amenities.geojson` with markers for all curated venues from `rest-day/README.md` and `sean/README.md`. Look up GPS coordinates via Google Maps for each address. Include: Cathedral Cafe (dining, purple), Pies & Pints (dining, purple), Secret Sandwich Society (dining, purple), The Handle Bar + Kitchen (dining, purple), Firecreek BBQ & Steaks (dining, purple), Bridge Brew Works (brewery, gold), Southside Junction Tap House (brewery, gold), Water Stone Outdoors (gear-shop, blue), Walmart Supercenter (supply, dark gray), Sheetz (supply, dark gray). Each description: venue type, one note, "February hours [UNVERIFIED]". Mark all coordinates [UNVERIFIED]
- [x] T017 [US4] Embed town amenities inline `geojson` code block + legend in `maps/README.md`. Add a "Town Amenities" section below the regional overview map with: the full GeoJSON content in a ```geojson code block, legend table (purple = dining, gold = brewery, blue = gear shop, gray = supply), and "All February hours [UNVERIFIED] — call ahead" note

**Checkpoint**: Town amenities map complete. Users can see all curated dining/shopping locations on one map.

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Quality assurance across all maps — source verification, scope compliance, rendering validation

**Depends on**: Phases 2-5 (all maps must be complete)

- [x] T018 [P] Source verification pass on all `.geojson` files and inline map sections. Verify FR-006: every GPS coordinate is either sourced (Google Maps, NPS, existing Feature docs) or flagged `[UNVERIFIED]` in the marker description. Verify SC-003: 100% coverage
- [x] T019 [P] Scope compliance check on all `.geojson` files and map legends. Search all map content for sport climbing, trad climbing, route climbing, pitch, or roped-climbing references. Remove any found. Verify FR-012 and SC-005: zero violations
- [x] T020 [P] Phone readability check on all inline map sections. Verify: legend tables readable, section headings clear, no horizontal scroll issues around map embeds. Verify FR-008
- [x] T021 Cross-reference validation on `maps/README.md` and all inline map sections. Verify every link in marker descriptions resolves to an actual file (areas/, trails/, rest-day/, logistics/). Verify SC-007: every map file has a legend in its parent document
- [x] T022 Write rendering verification footer in `maps/README.md` with: last-updated date (2026-02-11), source note ("All coordinates [UNVERIFIED] — verify before navigating"), fallback note ("If maps don't render, view `.geojson` files directly or paste into geojson.io"), and link to the conditions guide for daily planning

**Checkpoint**: All quality gates pass. Maps ready for rendering verification after push.

---

## Dependencies & Execution Order

### Phase Dependencies

```
Phase 1: Setup ──────────────────────────┐
                                          ▼
Phase 2: US1 (Regional Overview) ────────┐
                                          │
Phase 3: US2 (Area Sectors) ─────────────┤ (US1-US4 can all run in parallel)
                                          │
Phase 4: US3 (Trail Maps) ──────────────┤
                                          │
Phase 5: US4 (Town Amenities) ──────────┤
                                          │
                                          ▼
Phase 6: Polish ─────────────────────── (depends on all maps complete)
```

### User Story Dependencies

- **US1 (P1)**: Can start after Setup. No dependencies on other stories. **Start here — MVP.**
- **US2 (P2)**: Can start after Setup. No dependencies on other stories. **Can run parallel with US1.**
- **US3 (P3)**: Can start after Setup. No dependencies on other stories. **Can run parallel with US1/US2.**
- **US4 (P4)**: Can start after Setup. No dependencies on other stories. **Can run parallel with US1-US3.** Note: T017 adds to `maps/README.md` which is created in T003 — schedule after T003 if running US1 and US4 in parallel.

### Within-Phase Dependencies

**US2 (Phase 3)**: T004-T006 (build .geojson files) → T007-T009 (embed in .md files). The GeoJSON content must exist before embedding.

**US3 (Phase 4)**: T010-T012 (build .geojson files) → T013-T015 (embed in .md files). Same pattern.

### Parallel Opportunities

**Between Phases 2-5**:
- All four user stories write to different files — all can run in parallel

**Within Phase 3 (US2)**:
- T004, T005, T006 can run in parallel (different .geojson files)
- T007, T008, T009 can run in parallel (different .md files) — after T004-T006 complete

**Within Phase 4 (US3)**:
- T010, T011, T012 can run in parallel (different .geojson files)
- T013, T014, T015 can run in parallel (different .md files) — after T010-T012 complete

**Within Phase 6 (Polish)**:
- T018, T019, T020 can all run in parallel (different validation concerns)

---

## Implementation Strategy

### MVP First (Regional Overview Only)

1. Complete Phase 1: Setup (T001)
2. Complete Phase 2: US1 — Regional Overview Map (T002-T003)
3. **STOP and VALIDATE**: Push to GitHub. Users can see all 7 locations on one map. Minimum viable spatial orientation.

### Incremental Delivery

1. Setup → Directory created
2. Add US1 (Regional Overview) → Users see all locations on one map
3. Add US2 (Area Sectors) → Users see sectors within each bouldering area
4. Add US3 (Trail Maps) → Users see trail system areas and parking
5. Add US4 (Town Amenities) → Users see dining/shopping locations
6. Polish → All quality gates verified

Each increment adds standalone value without breaking previous maps.

---

## Notes

- GeoJSON coordinate order is **[longitude, latitude]** — West Virginia is approximately [-81, 38]. Easy mistake to swap
- Use `title` (not `name`) for popup headings per simplestyle spec
- Color scheme defined in plan.md — use hex codes from data-model.md Category Color Scheme
- All coordinates from Features 001-006 are [UNVERIFIED] — preserve those flags
- Town amenity coordinates need Google Maps lookup from addresses in rest-day/README.md
- Inline maps duplicate GeoJSON content between .geojson files and .md files — keep both in sync
- Marker descriptions should include shelter status for bouldering sectors (FR-009)
- GeoJSON files must be valid JSON — test with a JSON validator before committing
