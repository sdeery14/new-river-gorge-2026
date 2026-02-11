# Tasks: Mountain Biking Trails

**Input**: Design documents from `/specs/003-mountain-biking-trails/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, contracts/, quickstart.md

**Tests**: Not applicable — this is a documentation-only feature (Markdown files).

**Organization**: Tasks are grouped by user story. US2 and US3 depend on US1 being complete (they add sections to `trails/README.md` created in US1).

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

---

## Phase 1: Setup

**Purpose**: Verify prerequisites and confirm project structure is ready

- [x] T001 Verify Feature 001 deliverables exist in `areas/` directory (README.md, meadow-river.md, summersville-lake.md, gorge-boulders.md) — needed for bouldering-area pairing data
- [x] T002 Create `trails/` directory at repository root

---

## Phase 2: Foundational (Research Data Prep)

**Purpose**: Confirm research data is organized and complete before writing deliverables

**⚠️ CRITICAL**: Trail profile writing (Phase 3) cannot begin until research data is confirmed.

- [x] T003 Review and confirm Arrowhead Trails research data in `specs/003-mountain-biking-trails/research.md`: location, drive time, mileage, difficulty range, trail style, land manager, fees, February conditions (freeze/thaw, mud, ice, closures), condition sources. Confirm tier: Primary.
- [x] T004 [P] Review and confirm Summit Bechtel Reserve research data in `specs/003-mountain-biking-trails/research.md`: location, drive time, mileage, difficulty range, IMBA-designed system, BSA private facility, public access uncertainty, February conditions. Confirm tier: Conditional.
- [x] T005 [P] Review and confirm Babcock State Park research data in `specs/003-mountain-biking-trails/research.md`: location, drive time, limited MTB mileage (old roads only), difficulty range, state park access, February conditions. Confirm tier: Supplementary.
- [x] T006 [P] Review and confirm bike rental shop data in `specs/003-mountain-biking-trails/research.md`: Ridge Rider, ACE Adventure Resort, Adventures on the Gorge, New River Bikes. Confirm February availability assessment (HIGH RISK of no rentals).

**Checkpoint**: All research data reviewed and ready for document writing

---

## Phase 3: User Story 1 — Trail System Profiles (Priority: P1) 🎯 MVP

**Goal**: Each trail system has a profile document with trails, difficulty ratings, February conditions, and access info. An overview document provides a summary table and decision guide. A rider can pick a trail system from their phone in 30 seconds.

**Independent Test**: Open `trails/README.md` on a phone. A rider can identify at least 2 rideable trail systems and pick one based on difficulty and drive time within 30 seconds.

### Implementation for User Story 1

- [x] T007 [P] [US1] Write Arrowhead Trails profile at `trails/arrowhead.md` using template `specs/003-mountain-biking-trails/contracts/trail-system-template.md` and research data. Include: header banner with drive time/viability/land manager (FR-001), trail table with individual trails per FR-002 (name, IMBA difficulty, distance, elevation, ride time, surface, features), February conditions section per FR-003 (freeze/thaw, mud HIGH, ice moderate, best riding days, overall FAIR viability), access/parking per FR-006 (GPS, road conditions, fees: Free), condition sources (Trailforks, Active SWV Facebook, Water Stone Outdoors phone). Link back to `trails/README.md` (FR-011). Flag all data [UNVERIFIED] (FR-009). Tier: PRIMARY.
- [x] T008 [P] [US1] Write Summit Bechtel Reserve profile at `trails/summit-bechtel.md` using template and research data. Include: header with drive time/viability/land manager (FR-001), trail categories (beginner flow, connectors, flow/DH, XC, skills area) per FR-002 with [UNVERIFIED] individual trail data, February conditions per FR-003 (mud HIGH, ice MODERATE-HIGH, viability UNCERTAIN). **MUST prominently flag**: private BSA facility, public access uncertain, winter access unconfirmed. Include pre-trip verification call: (304) 465-2800. Access/parking per FR-006. Condition sources. Link back to README (FR-011). Tier: CONDITIONAL.
- [x] T009 [P] [US1] Write Babcock State Park profile at `trails/babcock.md` using template and research data. Include: header with drive time/viability/land manager (FR-001), bike-legal routes only (old roads/railroad grades, NOT hiking trails) per FR-002, February conditions per FR-003 (mud HIGH, ice MODERATE-HIGH, park roads may be gated, viability LOW-MODERATE). Note this is NOT a purpose-built MTB system. Include Glade Creek Grist Mill pairing suggestion. Access/parking per FR-006. Condition sources. Link back to README (FR-011). Tier: SUPPLEMENTARY.
- [x] T010 [US1] Write trail overview at `trails/README.md` using template `specs/003-mountain-biking-trails/contracts/trail-overview-template.md` and data from the 3 completed trail profiles. Include: summary table with all 3 systems (name linked to profile, drive time, difficulty range, mileage, February viability, tier, best-for notes) per FR-004, quick decision guide per FR-012 (dry+frozen → Arrowhead; wet/muddy → skip riding; want best trails → Summit if accessible; scenic light ride → Babcock), IMBA difficulty scale key per FR-005, February riding tips section. Link to each profile (FR-011). All data [UNVERIFIED] (FR-009). Phone-readable tables (FR-010).

**Checkpoint**: All 4 trail documents complete (3 profiles + overview). Each independently readable on a phone.

---

## Phase 4: User Story 2 — Bouldering-Area Pairings (Priority: P2)

**Goal**: A pairing section in the trail overview shows ride+boulder day combinations with drive times, enabling the group to plan a full day with both activities.

**Independent Test**: Open `trails/README.md` pairing section. A group member can build a ride+boulder day plan with total drive times in under 60 seconds.

**Depends on**: Phase 3 (US1) — needs completed trail profiles and overview document.

### Implementation for User Story 2

- [x] T011 [US2] Add bouldering-area pairing section to `trails/README.md` per FR-007. Cross-reference Feature 001 area profiles for drive times and rain resilience. Include at least 6 pairings from research.md: Arrowhead+Gorge Boulders (best — both close to town), Arrowhead+Meadow River, Summit Bechtel+Gorge Boulders, Summit Bechtel+Meadow River, Babcock+Summersville Lake, Babcock+Meadow River. Each pairing: trail system, bouldering area, trail-to-boulder drive time, total day drive time, suggested schedule (ride AM + boulder PM or vice versa), weather scenario notes. Include rain-day pivot scenario (ride morning → sheltered bouldering afternoon). Table ≤8 columns (FR-010).

**Checkpoint**: Pairing reference complete. Group can plan ride+boulder days from a single table.

---

## Phase 5: User Story 3 — Bike Rental & Logistics (Priority: P3)

**Goal**: A rental section in the trail overview lists shops with February availability, so riders without bikes can find (or learn they can't find) rentals.

**Independent Test**: Open `trails/README.md` rental section. A non-bike-owner can find rental info (or learn about February limitations) within 30 seconds.

**Depends on**: Phase 3 (US1) — needs the overview document to exist.

### Implementation for User Story 3

- [x] T012 [US3] Add bike rental section to `trails/README.md` per FR-008. Include February availability warning prominently (HIGH RISK of no rentals in mid-February). List all identified shops from research.md: Ridge Rider Mountain Bikes (best option, February status unknown), ACE Adventure Resort (seasonal, unlikely Feb), Adventures on the Gorge (seasonal, unlikely Feb), New River Bikes (status unknown). Each shop: name, location, price range, bike types, hours, February availability status, contact info (phone/website). Include contingency options (bring own bikes, rent in Charleston/Beckley, contact Ridge Rider in advance). Table ≤7 columns (FR-010). All data [UNVERIFIED] (FR-009).

**Checkpoint**: Rental reference complete. Riders know their options and limitations for February.

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Cross-validate all deliverables for consistency, completeness, and readability.

- [x] T013 Verify all 12 functional requirements (FR-001 through FR-012) are met across all 4 deliverable documents (`trails/README.md`, `trails/arrowhead.md`, `trails/summit-bechtel.md`, `trails/babcock.md`). Check each FR against the relevant document(s) and confirm compliance.
- [x] T014 [P] Verify consistency between trail documents and Feature 001 area profiles. Check that area names, drive times, and rain resilience ratings referenced in bouldering pairings match the data in `areas/README.md`, `areas/meadow-river.md`, `areas/summersville-lake.md`, `areas/gorge-boulders.md`.
- [x] T015 [P] Phone-readability check: verify all tables in all 4 documents are ≤8 columns wide, IMBA difficulty ratings are used consistently (FR-005), bidirectional links work (FR-011), [UNVERIFIED] flags are present on all unverified data (FR-009), and documents render correctly on GitHub mobile.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies — can start immediately
- **Foundational (Phase 2)**: Depends on Setup completion
- **US1 (Phase 3)**: Depends on Foundational (Phase 2) — BLOCKS US2, US3
- **US2 (Phase 4)**: Depends on US1 (Phase 3) — needs trail overview for pairing section
- **US3 (Phase 5)**: Depends on US1 (Phase 3) — needs trail overview for rental section
- **Polish (Phase 6)**: Depends on US1, US2, US3 all complete

### User Story Dependencies

- **US1 (P1)**: Can start after Foundational (Phase 2) — No dependencies on other stories
- **US2 (P2)**: Depends on US1 — adds pairing section to `trails/README.md`. Also reads Feature 001 area profiles.
- **US3 (P3)**: Depends on US1 — adds rental section to `trails/README.md`. Independent of US2.

### Within Each User Story

- US1: All 3 per-system profiles (T007, T008, T009) can run in parallel [P]. README (T010) depends on all 3 completing.
- US2: Single section addition (T011), sequential after US1.
- US3: Single section addition (T012), sequential after US1. Can run in parallel with US2 (different section of same file — but recommend sequential to avoid merge conflicts).

### Parallel Opportunities

- **Phase 2**: T004, T005, T006 can run in parallel (different trail systems)
- **Phase 3 (US1)**: T007, T008, T009 can ALL run in parallel (different files, no dependencies)
- **Phase 4-5**: T011 (US2) and T012 (US3) edit the same file — recommend sequential
- **Phase 6**: T014 and T015 can run in parallel (different validation concerns)

---

## Parallel Example: User Story 1

```bash
# Launch all 3 trail system profiles in parallel:
Task: "Write Arrowhead Trails profile in trails/arrowhead.md"
Task: "Write Summit Bechtel Reserve profile in trails/summit-bechtel.md"
Task: "Write Babcock State Park profile in trails/babcock.md"

# Then write the overview (depends on all 3 profiles):
Task: "Write trail overview in trails/README.md"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (verify prerequisites, create directory)
2. Complete Phase 2: Foundational (confirm research data)
3. Complete Phase 3: US1 — Write 3 trail profiles + overview
4. **STOP and VALIDATE**: Each document should be independently usable on a phone
5. The 4 trail documents alone deliver the core value of the feature

### Incremental Delivery

1. Complete Setup + Foundational → Ready to write
2. Add US1 (4 trail docs) → Test independently → Core value delivered (MVP!)
3. Add US2 (pairing section in README) → Ride+boulder day planning tool
4. Add US3 (rental section in README) → Bike rental reference
5. Polish → Cross-validate everything, phone readability confirmed
6. Each story adds a distinct planning capability without breaking previous stories
