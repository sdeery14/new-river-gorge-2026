# Tasks: Bike Rentals

**Input**: Design documents from `/specs/010-bike-rentals/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, quickstart.md

**Tests**: Not requested — no test tasks included.

**Organization**: Tasks grouped by user story. US1 (P1) is the MVP rental shop directory. US2 (P2) adds beginner guidance to the same file. Polish depends on all content being complete.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (US1, US2)
- All paths relative to repository root

---

## Phase 1: Setup

**Purpose**: No setup needed — `trails/` directory already exists. File created in Phase 2.

*(No tasks — proceed directly to Phase 2)*

---

## Phase 2: User Story 1 — Rental Shop Directory (Priority: P1) 🎯 MVP

**Goal**: Provide a quick-reference table of rental shops with contact info, pricing, February availability, and fallback strategies so a group member can find and book a rental in one phone call.

**Independent Test**: Open `trails/bike-rentals.md`, scan the quick-reference table, identify which shops are likely open in February, and find a phone number to call. Should take under 30 seconds.

### Implementation

- [x] T001 [US1] Write `trails/bike-rentals.md` header and quick-reference shop table. Include: title, purpose statement, and prominent February closure warning within the first 3 lines per SC-004 ("⚠️ February Warning: HIGH RISK that no bike rental shop will be open"). Then write the quick-reference comparison table per FR-001 with columns: Shop Name, Location, Distance, Phone, Daily Rate, Bike Types, February Status. Include all 4 local shops from research.md Section 1: New River Bikes (Fayetteville, $40/day, open except Wed), Arrowhead Bike Farm (Fayetteville, contact for pricing, likely open), ACE Adventure Resort (Oak Hill ~15 min, $19-39, likely open), Adventures on the Gorge (Lansing ~10 min, e-bike only). Sort by likelihood of February availability. Flag all pricing and availability [UNVERIFIED]. Format for phone readability per FR-009 — max 5-6 columns, no horizontal scroll
- [x] T002 [US1] Write expanded shop details section in `trails/bike-rentals.md`. For each of the 4 local shops, include a subsection with: full address, phone, website, hours, rental pricing details, bike types available, reservation requirements (advance notice, deposit, ID, waiver), rental duration options (half-day, full day), and damage/liability policy per FR-002. Use research.md Section 1 for all data. Note that Water Stone Outdoors does NOT rent bikes (climbing gear only) and Ridge Rider MTB could not be verified as an active business. Flag all data [UNVERIFIED] per FR-008
- [x] T003 [US1] Write out-of-town alternatives section in `trails/bike-rentals.md`. Per FR-003, include 2 out-of-town shops from research.md Section 2: Blackwater Bikes (Davis, WV, ~1.5 hrs, $50-120/day, good MTB selection) and Free Spirit Adventures (Caldwell, WV, ~1.5 hrs, Greenbrier River Trail oriented). For each: location, phone, distance from Fayetteville, pricing, bike types, and a note on logistics (rent the day before, transport bike to NRG). Flag all data [UNVERIFIED]
- [x] T004 [US1] Write bring-your-own-bike section in `trails/bike-rentals.md`. Per FR-004, cover: transport options (hitch rack, roof rack, inside vehicle), flying logistics (airline bike bags $35-75 each way), rental car rack compatibility note, and advantages over renting (guaranteed availability, no February closure risk). Use research.md Section 5 for data. Position bring-your-own as the most reliable February strategy

**Checkpoint**: Shop directory complete. MVP — a reader can find a rental shop and phone number in under 30 seconds, or find a fallback strategy if shops are closed.

---

## Phase 3: User Story 2 — Beginner Rental Guidance (Priority: P2)

**Goal**: Provide first-time mountain bikers with practical guidance on bike type, sizing, gear, and February-specific riding tips so they show up prepared.

**Independent Test**: A first-time renter reads the beginner section and can answer: "What kind of bike should I ask for?", "What size?", "What else do I need?", and "What should I know about riding in February?"

### Implementation

- [x] T005 [US2] Write beginner rental guidance section in `trails/bike-rentals.md`. Per FR-005, include 4 subsections: (1) **Bike Type** — recommend hardtail for green/blue trails, explain why not road/hybrid/cruiser, note full-suspension as upgrade option. (2) **Sizing** — height-to-frame-size table from research.md Section 3: S (5'0"-5'4"), M (5'4"-5'8"), L (5'8"-6'0"), XL (6'0"+). Note standover height matters most and shop staff will fit you. (3) **Gear Checklist** — what's included with rental (bike + helmet) vs. what to bring (gloves, layers, appropriate shoes, water). (4) **February Riding Tips** — clothing layers for 30-45°F, freeze-thaw awareness (don't ride muddy trails), when to skip riding, tire pressure note. Cross-reference conditions guide for daily weather decisions. Use research.md Section 3 and Section 4 for all data

**Checkpoint**: Beginner guidance complete. A first-timer can answer all 4 core questions.

---

## Phase 4: Polish & Cross-Cutting Concerns

**Purpose**: Quality assurance, cross-references, and integration with the rest of the repo.

**Depends on**: Phases 2-3 (all content must be complete)

- [x] T006 Add cross-references throughout `trails/bike-rentals.md`. Per FR-007 and SC-006: link to trail profiles at least twice — link to Arrowhead trail profile (`trails/arrowhead.md`) near the Arrowhead Bike Farm shop entry, link to trails overview (`trails/README.md`) in the beginner section for trail difficulty info. Also link to conditions guide (`conditions/README.md`) from the February riding tips for daily weather decisions. Add a footer with back-link to trail overview
- [x] T007 [P] Update `trails/README.md` bike rental section. Replace the current inline rental table (lines ~73-90) with a brief summary and a link to the new dedicated guide (`trails/bike-rentals.md`). Keep the February warning in the overview but direct readers to the full guide for shop details, beginner guidance, and fallback strategies
- [x] T008 [P] Update root `README.md` with bike rentals entry. Add "Where do I rent a bike?" → Bike Rental Guide to the Quick Start table. Add "Bike Rental Guide" subsection to "What's in the Repo" section with brief description. Add `bike-rentals.md` to the repo structure tree under `trails/`
- [x] T009 [P] Source verification pass on `trails/bike-rentals.md`. Verify FR-008 and SC-005: every pricing claim, availability status, phone number, address, and hours is flagged [UNVERIFIED] where not confirmed from primary sources. Check that no unflagged factual claims slipped through
- [x] T010 [P] Scope compliance check on `trails/bike-rentals.md`. Search for sport climbing, trad climbing, route climbing, pitch, or roped-climbing references. Remove any found. Verify FR-010 and SC-007: zero violations
- [x] T011 [P] Phone readability check on `trails/bike-rentals.md`. Verify FR-009: tables fit on a phone screen (no more than 5-6 columns), headings are clear and scannable, quick-reference table is navigable in under 30 seconds, no horizontal scroll issues. Verify SC-004: February closure warning appears within first 3 lines

**Checkpoint**: All quality gates pass. Bike rental guide ready for use.

---

## Dependencies & Execution Order

### Phase Dependencies

```
Phase 1: Setup (none needed) ──────────────┐
                                            ▼
Phase 2: US1 (Shop Directory) ────────────┐
                                           │
Phase 3: US2 (Beginner Guidance) ─────────┤ (sequential — same file)
                                           │
                                           ▼
Phase 4: Polish ──────────────────────── (depends on all content complete)
```

### User Story Dependencies

- **US1 (P1)**: No dependencies. **Start here — MVP.**
- **US2 (P2)**: Can start after US1 (builds on the same document, appends beginner section).

### Within-Phase Dependencies

**US1 (Phase 2)**: T001 (header + table) → T002 (shop details) → T003 (out-of-town) → T004 (bring-your-own). Sequential — same file, sections build on each other.

**Polish (Phase 4)**: T006 (cross-references) depends on all content. T007-T011 can run in parallel (different files or different validation concerns).

### Parallel Opportunities

**Within Phase 4 (Polish)**:
- T007, T008, T009, T010, T011 can all run in parallel (T007 edits trails/README.md, T008 edits root README.md, T009-T011 are validation checks on bike-rentals.md)

---

## Implementation Strategy

### MVP First (Shop Directory Only)

1. Complete Phase 2: US1 — Shop Directory + Fallbacks (T001-T004)
2. **STOP and VALIDATE**: A reader can find a rental shop and phone number in under 30 seconds. Minimum viable guide.

### Incremental Delivery

1. Add US1 (Shop Directory) → Reader can find and contact a rental shop or fallback option
2. Add US2 (Beginner Guidance) → First-time renter shows up prepared
3. Polish → All quality gates verified, integrated with rest of repo

Each increment adds standalone value without breaking previous content.

---

## Notes

- All content goes in a single file (`trails/bike-rentals.md`) — tasks within phases are sequential (same file constraint)
- Cross-reference Feature 003 trail profiles rather than duplicating trail data
- February closure warning is the #1 priority — must appear in first 3 lines
- All shop data, pricing, and availability flagged [UNVERIFIED]
- The guide treats bring-your-own as the most reliable strategy, with rental as a backup
