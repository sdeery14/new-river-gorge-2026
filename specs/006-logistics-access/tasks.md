# Tasks: Logistics & Access Cheat Sheets

**Input**: Design documents from `/specs/006-logistics-access/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, contracts/logistics-guide-template.md, quickstart.md

**Tests**: Not requested — no test tasks included.

**Organization**: Tasks grouped by user story. US1 (P1) comes first as the access table is the core deliverable. US2 (P2) can run in parallel with US1 (different section). US3 and US4 follow sequentially as they reference content from US1/US2.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different sections, no dependencies)
- **[Story]**: Which user story this task belongs to (US1, US2, US3, US4)
- All paths relative to repository root

---

## Phase 1: Setup

**Purpose**: Create deliverable file and establish document structure

- [x] T001 Create `logistics/` directory and copy template from `specs/006-logistics-access/contracts/logistics-guide-template.md` to `logistics/README.md`
- [x] T002 Replace template header placeholders in `logistics/README.md` with: feature title, geographic scope note (Fayetteville base, all drive times from rental house), and blanket call-ahead disclaimer for February access

**Checkpoint**: Document scaffold ready with structure and header in place.

---

## Phase 2: User Story 1 — Quick Access Cheat Sheet (Priority: P1) 🎯 MVP

**Goal**: Enable 30-second access lookup for any bouldering area or trail system from a single consolidated table on a phone.

**Independent Test**: Open `logistics/README.md` on a phone, find the drive time, parking GPS link, and approach summary for Meadow River within 30 seconds — without opening any other document.

### Implementation

- [x] T003 [US1] Populate bouldering area rows in the Access Quick Reference table of `logistics/README.md` using research.md Section 1 findings. Write one row per access point: Meadow River (1 row), Summersville Lake (1 row), Gorge Boulders — Endless Wall (1 row), Gorge Boulders — Bridge Buttress (1 row), Gorge Boulders — Kaymoor (1 row). Each row must include per FR-001 and data-model.md Access Point entity: location name, drive time, parking (tappable Google Maps GPS link + one-line note), approach (one-line: distance, time, difficulty), access warning (⚠️ if February hazard), and link to full area profile in `areas/`
- [x] T004 [US1] Populate trail system rows in the Access Quick Reference table of `logistics/README.md` using research.md Section 1 findings. Write one row per trail system: Arrowhead Trails, Babcock State Park, Summit Bechtel Reserve. Same field requirements as T003 per FR-001 and FR-002, with links to full trail profiles in `trails/`
- [x] T005 [US1] Write Winter Access Warnings section in `logistics/README.md` per FR-004 and FR-007. For each location with a February access risk, write a subsection with: hazard description, alternate access route or alternate area suggestion, and how to check status morning-of. Locations to cover: Fayette Station Road (icy → Canyon Rim alternate), Summersville Lake gates (Nov-Apr gating → call USACE), Kaymoor steps (icy steel grate → choose different area), Babcock interior roads (may be gated → call park), Summit Bechtel (private access → must call BSA)

**Checkpoint**: Master access table populated with all 8 locations. Group can find any parking/approach in 30 seconds. Winter warnings documented with alternates.

---

## Phase 3: User Story 2 — NPS Regulations & Access Rules (Priority: P2)

**Goal**: Provide consolidated land-manager regulations so the group knows the rules at every bouldering area and trail system without opening individual profiles.

**Independent Test**: Open `logistics/README.md`, find the crash pad policy and chalk rules for NPS-managed areas within 30 seconds.

**Can run in parallel with Phase 2** — writes to a different section of the document.

### Implementation

- [x] T006 [P] [US2] Write NPS — New River Gorge National Park regulations subsection in `logistics/README.md` per FR-003 and data-model.md Regulation Set entity. Applies to: Gorge Boulders (all sectors). Include table with: crash pads, chalk, brushing restrictions, group size, February closures (none — peregrine is Mar-Jul), fees (none). Add verify contact (NPS 304-574-2115) and source citation. Flag all unverified items with `[UNVERIFIED]`
- [x] T007 [P] [US2] Write USACE — Summersville Lake regulations subsection in `logistics/README.md` per FR-003. Include: applicable areas, crash pads, chalk, seasonal gate closures (Nov-Apr), fees, verify contact (304-872-3459), source citation
- [x] T008 [US2] Write remaining land manager subsections in `logistics/README.md` per FR-003. Cover: Private/County ROW (Meadow River — no formal regulations), Active SWV (Arrowhead Trails — community ethic: stay off when muddy), WV State Parks (Babcock — bikes on roads/railroad grades only, blaze orange for hunting season), BSA (Summit Bechtel — private, fees likely, waiver required, access not guaranteed). Each must include applicable areas, key rules, and verify contact

**Checkpoint**: Regulations section complete with all land managers covered. Group can find rules for any area without opening individual profiles.

---

## Phase 4: User Story 3 — Mid-Week Roster Change Logistics (Priority: P3)

**Goal**: Provide a clear Wednesday transition plan covering car handoff, airport pickup, and lodging adjustment so the group doesn't waste time coordinating on the day.

**Independent Test**: Read the roster-change section and find answers to: Does the departing member leave a car? What airport should the arriving member use? How do room assignments change?

### Implementation

- [x] T009 [US3] Write Nearest Airports table in `logistics/README.md` using research.md Section 2 findings. Include 4 airports: CRW (Yeager/Charleston, ~1.5 hr, recommended), LWB (Greenbrier Valley/Lewisburg, ~1.25 hr, secondary), BKW (Beckley, ~40 min, limited), ROA (Roanoke, ~2.5 hr, backup). Table columns per data-model.md: airport name, code, drive time, airlines, rental cars, notes/recommendation. Mark CRW as the recommended primary option
- [x] T010 [US3] Write Roster-Change Day (Wednesday) section in `logistics/README.md` per FR-005 using role-based placeholders. Structure as: Morning (Departing Member leaves — cover two car scenarios: took own car vs. carpooled), Afternoon (Arriving Member arrives — cover two pickup scenarios: rents car at CRW vs. group pickup), Evening (full new group — lodging adjustment, fleet update, welcome dinner reference to rest-day guide). Include estimated times and drive time from CRW
- [x] T011 [US3] Add flight delay contingency note to the roster-change section in `logistics/README.md` per edge case 2 from spec.md. Note pickup plan flexibility and suggest contingency activities for the waiting group (reference rest-day guide for Wednesday suggestions in Feature 005)

**Checkpoint**: Roster-change logistics complete. Group can coordinate Wednesday transition without additional research.

---

## Phase 5: User Story 4 — Car Strategy & Carpooling (Priority: P4)

**Goal**: Provide fleet management guidance and sample carpooling plans so the group can efficiently split across activities without wasted driving.

**Independent Test**: Look up a split-day scenario (3 boulder, 2 bike) and find a carpooling plan showing which car goes where.

**Depends on**: Phase 2 (US1) for parking capacity notes in carpooling scenarios.

### Implementation

- [x] T012 [US4] Write Fleet Overview table in the Car Strategy section of `logistics/README.md` per FR-006 using generic role-based templates. Show: group size, cars available (Car A/B/C), and drivers for first half (Sat-Wed, 6 people) and second half (Wed-Sat, adjusted fleet). Cover both 2-car and 3-car fleet configurations. Note minimum viable fleet size per edge case 3 from spec.md
- [x] T013 [US4] Write Scenario 1: Full Group — Same Destination carpooling plan in `logistics/README.md` per FR-006. Show which cars go, passenger distribution, departure time, and parking capacity note for the destination. Include sub-variants for each bouldering area (parking capacity varies)
- [x] T014 [P] [US4] Write Scenario 2: Split Day — Boulder + Bike carpooling plan in `logistics/README.md` per FR-006. Show Car A to bouldering area, Car B to trail system, passenger splits, departure times, and mid-day coordination notes. Reference parking from the access table
- [x] T015 [P] [US4] Write Scenario 3: Bad Weather — Town Day carpooling plan in `logistics/README.md` per FR-006. Show reduced car deployment (1 car or walk to downtown), reference indoor options from rest-day guide (Feature 005), note that parking is not a concern for town days

**Checkpoint**: Car strategy complete with 3+ scenarios. Group can coordinate daily driving without morning debates.

---

## Phase 6: Supporting Content

**Purpose**: Town essentials and pre-trip checklist that support all user stories

- [x] T016 Write Town Essentials section in `logistics/README.md` using research.md Section 4 findings. Include: gas stations table (Sheetz 24-hr as base camp station, Exxon, Shell in Oak Hill), cell service table by carrier (AT&T best, Verizon second, T-Mobile spotty) with gorge dead-zone warning, and brief car-dependence note (downtown walkable, all climbing/biking requires driving)
- [x] T017 Write Pre-Trip Verification Checklist in `logistics/README.md` per FR-008 and research.md Section 5. Include all items with contact, why, and when-to-check columns per data-model.md Verification Item entity. Items: NPS conditions/regulations, USACE gate status, Summit Bechtel access, Babcock road access, Arrowhead conditions, Water Stone Outdoors beta, NRAC access alerts, WV road conditions (511), Ridge Rider bike rental availability

**Checkpoint**: Supporting content complete. All town logistics and pre-trip preparation covered.

---

## Phase 7: Polish & Cross-Cutting Concerns

**Purpose**: Quality assurance across all sections — source verification, formatting, scope compliance, link validation

- [x] T018 [P] Source verification pass on `logistics/README.md` per FR-009. For every access claim (drive times, GPS coordinates, regulations, fees): confirm a source is cited inline or in a Source field. Flag any uncited claim with `[UNVERIFIED]`. Verify SC-005: 100% of access claims have source or `[UNVERIFIED]`
- [x] T019 [P] Phone readability check on `logistics/README.md` per FR-010. Verify: all tables ≤6 columns, sections have clear headings, GPS links are tappable, content is skimmable on a mobile screen. Fix any table that exceeds column limit
- [x] T020 [P] Scope compliance check on `logistics/README.md` per FR-012. Search entire document for any sport climbing, trad climbing, route climbing, pitch, or gear references. Remove any found. Confirm 100% bouldering-trip context
- [x] T021 Cross-reference validation on `logistics/README.md` per FR-011. Verify every profile link in the access table resolves to an actual file in `areas/` or `trails/`. Verify every GPS link is a valid, tappable Google Maps URL. No broken links. No orphaned rows pointing to nonexistent profiles. Verify SC-006 (every parking location has a tappable GPS link)
- [x] T022 Write document footer in `logistics/README.md` with last-updated date (2026-02-11) and source verification date. Add note: "Sources verified as of 2026-02-11. Call ahead for February 2026 access."

**Checkpoint**: All quality gates pass. Document ready for checklist validation.

---

## Dependencies & Execution Order

### Phase Dependencies

```
Phase 1: Setup ──────────────────────────┐
                                          ▼
Phase 2: US1 (Access Table) ────────────┐
                                         │
Phase 3: US2 (Regulations) ─────────────┤ (US1 and US2 can run in parallel)
                                         │
                                         ▼
Phase 4: US3 (Roster-Change) ──────────┐
                                        │ (US3 and US4 can run in parallel)
Phase 5: US4 (Car Strategy) ───────────┤ (depends on US1 for parking notes)
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
- **US3 (P3)**: Can start after Setup. References airports (independent research), dinner suggestions (cross-ref Feature 005).
- **US4 (P4)**: Depends on US1 completion (references parking capacity from access table). Can run parallel with US3.

### Parallel Opportunities

**Between Phase 2 and Phase 3**:
- US1 (T003-T005) and US2 (T006-T008) can run in parallel — they write to different sections

**Within Phase 3 (US2)**:
- T006 and T007 can run in parallel (different land manager subsections)

**Within Phase 5 (US4)**:
- T014 and T015 can run in parallel (different carpooling scenarios)

**Within Phase 7 (Polish)**:
- T018, T019, T020 can all run in parallel (different validation concerns)

---

## Implementation Strategy

### MVP First (Access Table Only)

1. Complete Phase 1: Setup (T001-T002)
2. Complete Phase 2: US1 — Access Quick Reference (T003-T005)
3. **STOP and VALIDATE**: The group can already look up any parking/approach in 30 seconds. Minimum viable logistics guide.

### Incremental Delivery

1. Setup → Document scaffold ready
2. Add US1 (Access Table + Winter Warnings) → Group can find any location in 30 seconds
3. Add US2 (Regulations) → Group knows rules at every area
4. Add US3 (Roster-Change) → Wednesday transition planned
5. Add US4 (Car Strategy) → Daily driving coordinated
6. Add Supporting Content → Town essentials and pre-trip checklist
7. Polish → All quality gates verified

Each increment adds standalone value without breaking previous content.

---

## Notes

- All tasks write to a single file: `logistics/README.md`
- [P] tasks write to different sections — no merge conflicts
- Research data in `specs/006-logistics-access/research.md` is the primary source for all content tasks
- Required fields per entity type are defined in `specs/006-logistics-access/data-model.md`
- Access data is consolidated from Features 001 and 003 — do not duplicate full climbing/biking content, use abbreviated one-liners with links
- Constitution gates (Principles I, II, V, VI) apply — see `quickstart.md` for gate summary
- GPS coordinates from Features 001/003 are approximate and `[UNVERIFIED]` — preserve those flags
- Car strategy and roster-change sections use generic role-based placeholders (Car A/B/C, Departing Member, Arriving Member) per clarification
