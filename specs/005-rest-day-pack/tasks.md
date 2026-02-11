# Tasks: Rest-Day & Low-Energy Pack

**Input**: Design documents from `/specs/005-rest-day-pack/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, contracts/rest-day-guide-template.md, quickstart.md

**Tests**: Not requested — no test tasks included.

**Organization**: Tasks grouped by user story. Note: US1 (P1) is implemented *after* US2 and US3 because the quick-reference table and sample itineraries depend on content from those sections existing first.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different sections, no dependencies)
- **[Story]**: Which user story this task belongs to (US1, US2, US3, US4)
- All paths relative to repository root

---

## Phase 1: Setup

**Purpose**: Create deliverable file and establish document structure

- [x] T001 Create `rest-day/` directory and copy template from `specs/005-rest-day-pack/contracts/rest-day-guide-template.md` to `rest-day/README.md`
- [x] T002 Replace template header placeholders in `rest-day/README.md` with: feature title, geographic scope note (Fayetteville + 20-min radius; hot springs up to 90 min), and blanket call-ahead disclaimer for February hours
- [x] T003 Write the Energy Tiers reference table with Low/Medium/High definitions per FR-002 in `rest-day/README.md`, replacing the placeholder table. Include Feature 003 cross-reference link for mountain biking in the High tier

**Checkpoint**: Document scaffold ready with structure, header, and energy tier framework in place.

---

## Phase 2: User Story 2 — Dining & Brewery Planning (Priority: P2)

**Goal**: Provide complete dining and brewery listings so the group can find a place to eat or drink any night of the trip.

**Independent Test**: Look up dinner options for a group of 5-6 on a Tuesday in February. Every listing has cuisine type, price range, group suitability, and winter hours (or `[UNVERIFIED]` flag).

**Why before US1**: The quick-reference table (US1) cannot be populated until dining/brewery content exists.

### Implementation

- [x] T004 [US2] Write 8 Fayetteville restaurant profiles in the Dining section of `rest-day/README.md` using research.md Section 1 findings. Each profile must include: name, location, cuisine, price ($/$$/$$S), winter hours (or `[UNVERIFIED]`), group suitability for 5-6, reservation status, and source citation per FR-003 and data-model.md Venue entity fields. Restaurants: Cathedral Cafe, Pies & Pints, Secret Sandwich Society, The Gaines Estate, Firecreek BBQ, Elliott's Whitewater, Southside Junction Tap House, The Handle Bar + Kitchen
- [x] T005 [US2] Write 3 Oak Hill / Route 19 restaurant profiles in the Dining section of `rest-day/README.md` using research.md Section 1 findings. Same field requirements as T004. Restaurants: Café 110, El Rio, OK Chinese Buffet. Include drive time from Fayetteville (~10-15 min) for each
- [x] T006 [P] [US2] Write Bridge Brew Works brewery profile in the Breweries section of `rest-day/README.md` using research.md Section 2 findings. Must include all data-model.md Brewery entity fields: location/address, winter hours (note conflicting sources, flag `[UNVERIFIED]`), beer style, food availability (pizza/tacos/food truck), outdoor seating (note February relevance), atmosphere, group suitability, source citations per FR-004
- [x] T007 [P] [US2] Write Southside Junction Tap House brewery profile in the Breweries section of `rest-day/README.md` using research.md Section 2 findings. Same field requirements as T006. Note: this venue doubles as brewpub (12 rotating local craft taps); note overlap with dining section. If Freefolk Brewery is confirmed open, write its profile instead per FR-004

**Checkpoint**: Dining and brewery sections complete. Group can find dinner and drinks.

---

## Phase 3: User Story 3 — Medium-Energy Activity Selection (Priority: P3)

**Goal**: Provide hiking, sightseeing, indoor, hot springs, and grocery listings so the group has non-climbing activity options across all energy levels.

**Independent Test**: Select a medium-energy activity and confirm it includes duration, effort level, and February-specific notes.

**Why before US1**: The quick-reference table and sample itineraries (US1) need these sections to exist before they can be compiled.

### Implementation

- [x] T008 [P] [US3] Write The Greenbrier hot springs profile in the Hot Springs & Spa section of `rest-day/README.md` using research.md Section 3 findings. Must include: location (White Sulphur Springs, WV), drive time (~1.5 hrs), cost ($$$ luxury, flag `[UNVERIFIED]`), reservations (required), February availability, treatment description. Add honest framing note that this is the only hot springs option within 90 minutes and it is a luxury resort per FR-005
- [x] T009 [P] [US3] Write 4 medium-to-high energy hiking trail profiles in the Hiking & Sightseeing section of `rest-day/README.md` using research.md Section 4 findings. Each must include all data-model.md Trail entity fields per FR-006. Trails: Endless Wall Trail to Diamond Point (2.2 mi RT, Moderate), Long Point Trail (3-5 mi RT, note conflicting distance sources `[UNVERIFIED]`), Castle Rock Trail at Grandview (1 mi loop, Easy-Moderate), Kaymoor Miners Trail (6 mi RT, Strenuous). Assign correct energy tier to each
- [x] T010 [P] [US3] Write 5 low-energy sightseeing and short walk entries in the Hiking & Sightseeing section of `rest-day/README.md` using research.md Section 4 findings. Each must include all data-model.md Trail entity fields per FR-006. Entries: Canyon Rim Overlook Boardwalk (0.1 mi, Easy), Grandview Rim Trail (1.6 mi one way, Easy/flat), Tunnel Trail at Grandview (0.6 mi RT, Easy), New River Gorge Bridge / Canyon Rim Visitor Center (drive-up, no hike), Thurmond Ghost Town (drive + short walk, free). Add blanket February trail conditions disclaimer noting potential ice/mud
- [x] T011 [P] [US3] Write 6 indoor activity listings in the Indoor Options section of `rest-day/README.md` using research.md Section 5 findings. Each must include: type, location with drive time, cost (or `[UNVERIFIED]`), winter hours (or `[UNVERIFIED]`), group suitability, reservation status, source citation per FR-007. Venues: Gripped Fitness (bouldering gym, Fayetteville), Leisure Lanes (bowling, 24 lanes), Marquee Cinemas (movies), Beckley Exhibition Coal Mine (~25 min, note possible February closure), The Mystery Hole, Outside In Climbing Gym (Beckley)
- [x] T012 [P] [US3] Write grocery store table in the Grocery Stores section of `rest-day/README.md` using research.md Section 6 findings. Table must include: store name, location, drive time, hours, selection quality per FR-008 and data-model.md Grocery entity. Stores: Walmart Supercenter (Fayetteville, 6a-11p), Kroger (Oak Hill, ~10-15 min), Foodland (Oak Hill, `[UNVERIFIED]`)

**Checkpoint**: All activity category sections complete. Guide has content across all 6+ categories (SC-005).

---

## Phase 4: User Story 1 — Quick Rest-Day Decision (Priority: P1) 🎯 MVP

**Goal**: Enable 60-second activity identification via the quick-reference table, and provide pre-built day plans via sample itineraries so a tired group can decide without effort.

**Independent Test**: Open `rest-day/README.md` on a phone, scan the quick-reference table, and identify 3+ energy-appropriate options within 60 seconds.

**Depends on**: Phase 2 (US2) and Phase 3 (US3) — table and itineraries reference activities from those sections.

### Implementation

- [x] T013 [US1] Populate the Quick Reference summary table at the top of `rest-day/README.md` with every activity from all sections (Dining, Breweries, Hot Springs, Hiking/Sightseeing, Indoor, Grocery). Table columns per FR-001: Activity | Energy | Duration | In/Out | Cost | Feb? (6 columns max per FR-012). Each row must match an activity profile below. Verify at least 3 activities per energy tier and at least 2 indoor/low-energy options per SC-003
- [x] T014 [P] [US1] Write "Low-Energy Rainy Day" sample itinerary in the Sample Rest-Day Itineraries section of `rest-day/README.md` per FR-013. Must use time-block table format (Morning/Midday/Afternoon/Evening), reference only activities listed in the guide, assume rain or cold weather, target full day duration. Example flow: breakfast spot → indoor activity → lunch → brewery/indoor → dinner
- [x] T015 [P] [US1] Write "Medium-Energy Explorer Day" sample itinerary in the Sample Rest-Day Itineraries section of `rest-day/README.md` per FR-013. Must use time-block table format, reference only listed activities, assume dry or clearing weather. Example flow: breakfast → casual hike or sightseeing → lunch in town → scenic viewpoint → dinner + brewery
- [x] T016 [P] [US1] Write "High-Energy Active Rest Day" sample itinerary in the Sample Rest-Day Itineraries section of `rest-day/README.md` per FR-013. Must use time-block table format, reference only listed activities, assume dry weather. Example flow: early start → longer hike (Kaymoor or Long Point) → lunch → Feature 003 mountain biking reference → dinner

**Checkpoint**: Quick-reference table populated, 3 sample itineraries complete. US1 acceptance scenarios testable — 60-second phone lookup works.

---

## Phase 5: User Story 4 — Roster-Change Day Planning (Priority: P4)

**Goal**: Provide Wednesday-specific activity suggestions that account for one member departing in the morning and another arriving in the afternoon.

**Independent Test**: Consult the guide for Wednesday and find suggestions that address the split-day logistics and a group-friendly welcome dinner.

### Implementation

- [x] T017 [US4] Write the Roster-Change Day (Wednesday) section in `rest-day/README.md` per FR-010. Must include: situation description (one departs morning, one arrives afternoon), morning suggestions for smaller group, afternoon welcome activities for new arrival, evening group dinner recommendation (reference a specific restaurant from the Dining section). Note reduced group size during transition window
- [x] T018 [US4] Add travel-day flags to applicable activity listings throughout `rest-day/README.md`. Flag activities suitable for arrival Saturday (limited afternoon time) and departure Saturday (limited morning time) per edge case 4 from spec.md. Brief inline notes, not a separate section

**Checkpoint**: Wednesday roster-change and travel-day scenarios addressed. US4 acceptance scenarios testable.

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Quality assurance across all sections — source verification, formatting, scope compliance

- [x] T019 [P] Verify reservation/booking flags on every activity listing in `rest-day/README.md` per FR-009. Each listing must state: Required, Recommended, Walk-in, or N/A. Add missing flags to any listing that lacks one
- [x] T020 [P] Source verification pass on `rest-day/README.md` per FR-011. For every business claim (hours, pricing, availability): confirm a source is cited inline or in a Source field. Flag any uncited claim with `[UNVERIFIED]`. Verify SC-004: 100% of business listings have source or `[UNVERIFIED]`
- [x] T021 [P] Phone readability check on `rest-day/README.md` per FR-012. Verify: all tables ≤6 columns, sections have clear headings, content is skimmable on a mobile screen. Fix any table that exceeds column limit
- [x] T022 [P] Scope compliance check on `rest-day/README.md` per FR-014. Search entire document for any sport climbing, trad climbing, route climbing, pitch, or gear references. Remove any found. Confirm 100% bouldering-trip context
- [x] T023 Validate quick-reference table completeness in `rest-day/README.md`. Every activity profile in the document must have a corresponding row in the Quick Reference table. No orphaned listings. No table rows pointing to nonexistent profiles. Verify SC-003 (≥2 per energy tier) and SC-005 (≥6 categories)
- [x] T024 Write document footer in `rest-day/README.md` with last-updated date (2026-02-11) and source verification date. Add note: "Sources verified as of 2026-02-11. Call ahead for February 2026 hours."

**Checkpoint**: All quality gates pass. Document ready for checklist validation.

---

## Dependencies & Execution Order

### Phase Dependencies

```
Phase 1: Setup ──────────────────────────┐
                                          ▼
Phase 2: US2 (Dining & Breweries) ───────┐
                                          │
Phase 3: US3 (Activities & Grocery) ─────┤ (US2 and US3 can run in parallel)
                                          │
                                          ▼
Phase 4: US1 (Quick Ref + Itineraries) ──┐ (depends on US2 + US3 content)
                                          │
Phase 5: US4 (Roster-Change Day) ────────┤ (depends on US2 for dinner refs)
                                          │
                                          ▼
Phase 6: Polish ─────────────────────────── (depends on all content complete)
```

### User Story Dependencies

- **US2 (P2)**: Can start after Setup. No dependencies on other stories. **Start here.**
- **US3 (P3)**: Can start after Setup. No dependencies on other stories. **Can run parallel with US2.**
- **US1 (P1)**: Depends on US2 + US3 completion (table and itineraries need content to reference).
- **US4 (P4)**: Depends on US2 (references dinner recommendations). Can run parallel with US1.

### Parallel Opportunities

**Within Phase 2 (US2)**:
- T006 and T007 can run in parallel (different brewery profiles)

**Between Phase 2 and Phase 3**:
- US2 (T004-T007) and US3 (T008-T012) can run in parallel — they write to different sections

**Within Phase 3 (US3)**:
- T008, T009, T010, T011, T012 can all run in parallel (different sections of the guide)

**Within Phase 4 (US1)**:
- T014, T015, T016 can run in parallel (different itineraries)

**Within Phase 6 (Polish)**:
- T019, T020, T021, T022 can all run in parallel (different validation concerns)

---

## Implementation Strategy

### MVP First (Quick-Reference Table + Dining)

1. Complete Phase 1: Setup (T001-T003)
2. Complete Phase 2: US2 — Dining & Breweries (T004-T007)
3. Partially complete Phase 4: US1 — Populate quick-reference table with dining/brewery entries only (T013)
4. **STOP and VALIDATE**: The group can already find a dinner spot. Minimum viable rest-day guide.

### Incremental Delivery

1. Setup → Document scaffold ready
2. Add US2 (Dining & Breweries) → Group can find food/drinks
3. Add US3 (Activities & Grocery) → Full activity coverage across all categories
4. Add US1 (Quick-Ref Table + Itineraries) → 60-second decision-making enabled
5. Add US4 (Roster-Change Day) → Wednesday logistics addressed
6. Polish → All quality gates verified

Each increment adds standalone value without breaking previous content.

---

## Notes

- All tasks write to a single file: `rest-day/README.md`
- [P] tasks write to different sections — no merge conflicts
- Research data in `specs/005-rest-day-pack/research.md` is the primary source for all content tasks
- Required fields per entity type are defined in `specs/005-rest-day-pack/data-model.md`
- Constitution gates (Principles I, II, V, VI) apply — see `quickstart.md` for gate summary
- "Fayetteville Brewing Co." from spec may not exist — use Southside Junction Tap House or verified Freefolk Brewery as second brewery per research.md findings
