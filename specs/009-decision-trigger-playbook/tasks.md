# Tasks: Decision Trigger Playbook

**Input**: Design documents from `/specs/009-decision-trigger-playbook/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, quickstart.md

**Tests**: Not requested — no test tasks included.

**Organization**: Tasks grouped by user story. US1 (P1) is the MVP decision tree + weather triggers. US2 and US3 build on the same document file. Polish depends on all content being complete.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (US1, US2, US3)
- All paths relative to repository root

---

## Phase 1: Setup

**Purpose**: Create playbook directory

- [x] T001 Create `playbook/` directory at repository root

**Checkpoint**: Directory structure ready.

---

## Phase 2: User Story 1 — Weather-Based Go/No-Go Decision (Priority: P1) 🎯 MVP

**Goal**: Provide a quick-reference decision tree and weather triggers at 3 decision windows so the group can decide Chattanooga vs NRG in under 60 seconds.

**Independent Test**: Open `playbook/README.md`, check a sample Chattanooga forecast showing 4 consecutive rain days, and follow the decision tree to a clear "pivot to NRG" recommendation.

### Implementation

- [x] T002 [US1] Write `playbook/README.md` header and quick-reference decision tree. Include: title, purpose statement, and a flowchart-style decision table at the very top covering the 3 most common scenarios (Chattanooga rain → pivot NRG, mixed weather → compare, both clear → stay Chattanooga). Must be navigable in under 60 seconds per FR-009. Format for phone readability per FR-011
- [x] T003 [US1] Write 7-day decision window section in `playbook/README.md`. Include: date (Feb 7), forecast reliability (Low — general trends only), trigger criteria table (3+ consecutive rain days in Chattanooga = pivot, 2 rain days = watch, mixed = compare NRG forecast), available actions (book backup NRG lodging, hold flexible flights), booking flexibility (High — most reservations still changeable). Cross-reference research.md Section 5 for window structure
- [x] T004 [US1] Write 3-day decision window section in `playbook/README.md`. Include: date (Feb 11), forecast reliability (Moderate — pattern confidence), trigger criteria table (same thresholds but higher confidence), available actions (make the firm call, cancel/rebook lodging, adjust rental cars), booking flexibility (Medium — depends on policy tier). Note this is the critical decision point per research.md
- [x] T005 [US1] Write 1-day decision window section in `playbook/README.md`. Include: date (Feb 13), forecast reliability (High — hour-by-hour), trigger criteria (confirm or emergency pivot), available actions (final confirmation, last-minute rental car switch), booking flexibility (Low — sunk costs likely). Note: morning-of daily decisions are handled by the Conditions Guide (Feature 004), not this playbook
- [x] T006 [US1] Write weather comparison table (Chattanooga vs NRG) in `playbook/README.md`. Side-by-side table per FR-003 with 7 metrics from research.md Section 1: temperature range, dew point, rain frequency, drying speed, rain shelter count, winter access risk, estimated climbable days per week. Include rain-resilience comparison noting NRG's shelter advantage vs Chattanooga's faster drying and warmer temps. All data flagged [UNVERIFIED]

**Checkpoint**: Decision tree and weather triggers complete. MVP — a reader can follow the tree to a destination recommendation.

---

## Phase 3: User Story 2 — Booking & Cancellation Timeline (Priority: P2)

**Goal**: Show the financial and logistical constraints at each decision window so weather-based decisions are actionable.

**Independent Test**: Open `playbook/README.md` and identify, for a given date before the trip, which bookings are still cancellable and the estimated cost of switching.

### Implementation

- [x] T007 [US2] Write booking & cancellation timeline section in `playbook/README.md`. Include: countdown table per FR-004 showing booking types (flights, lodging, rental cars) × cancellation policies from research.md Sections 2-4. Show financial exposure at each decision window per FR-005: estimated sunk costs and switching costs. Recommend flexibility strategies (Southwest flights, VRBO Relaxed/Moderate, Pay Later rental cars). Flag all cost estimates and policies [UNVERIFIED] per FR-010. Include a "What policy does YOUR booking use?" prompt so the group can fill in their actual terms
- [x] T008 [US2] Write mid-week roster switching considerations in `playbook/README.md`. Address FR-008: if destination switches late, the mid-week roster change (one departs Wed, one arrives Wed) may require different flights for different people. Note which logistics are affected: arrival airport (CHA vs CRW), rental car pickup/dropoff, lodging headcount timing. Cross-reference logistics/README.md roster-change section

**Checkpoint**: Booking timeline complete. Weather decisions are now informed by financial constraints.

---

## Phase 4: User Story 3 — Contingency Paths (Priority: P3)

**Goal**: Provide recommendations for degraded scenarios when the Chattanooga-vs-NRG binary doesn't yield a clear answer.

**Independent Test**: Open `playbook/README.md` with a scenario where both locations show 3+ rain days, and find a clear recommendation.

### Implementation

- [x] T009 [US3] Write contingency paths section in `playbook/README.md`. Cover at least 3 scenarios per FR-006 and SC-004: (1) Both destinations show 3+ rain days — compare shelter count, recommend NRG for overhangs or Chattanooga for Dayton Pocket depending on rain pattern; (2) Committed to NRG but key access closed (Summersville Lake gates, roads iced) — show which areas remain viable (Gorge Boulders always accessible, Meadow River road access); (3) Forecast reversal after pivot decision — assess whether to reverse based on remaining booking flexibility from US2 timeline. Each contingency: scenario description, assessment criteria, recommendation, cross-reference to relevant guide

**Checkpoint**: All contingency paths defined. Playbook handles edge cases.

---

## Phase 5: Polish & Cross-Cutting Concerns

**Purpose**: Quality assurance, cross-references, and integration with the rest of the repo.

**Depends on**: Phases 2-4 (all content must be complete)

- [x] T010 Add cross-references throughout `playbook/README.md`. Per FR-007 and SC-006: link to Conditions Guide (conditions/README.md) at least 3 times for NRG weather data, link to Logistics Guide (logistics/README.md) for access details and pre-trip checklist, link to Chattanooga repo (https://github.com/sdeery14/chattanooga-2026) for companion conditions data. Add footer with last-updated date and link to conditions guide for daily in-trip decisions
- [x] T011 [P] Add playbook link to root `README.md`. Add entry to Quick Start table: "When do we switch to NRG?" → Playbook. Add "Decision Trigger Playbook" subsection to "What's in the Repo" section with brief description. Add playbook to repo structure tree
- [x] T012 [P] Source verification pass on `playbook/README.md`. Verify FR-010 and SC-005: every weather threshold, cost estimate, booking deadline, and cancellation policy is flagged [UNVERIFIED] where not confirmed from primary sources. Check that cross-references to Feature 004 and Feature 006 use correct anchor links
- [x] T013 [P] Scope compliance check on `playbook/README.md`. Search for sport climbing, trad climbing, route climbing, pitch, or roped-climbing references. Remove any found. Verify FR-012 and SC-007: zero violations
- [x] T014 Phone readability check on `playbook/README.md`. Verify FR-011: tables fit on a phone screen (no more than 5-6 columns), headings are clear and scannable, decision tree is navigable in under 60 seconds, no horizontal scroll issues

**Checkpoint**: All quality gates pass. Playbook ready for use.

---

## Dependencies & Execution Order

### Phase Dependencies

```
Phase 1: Setup ─────────────────────────────┐
                                             ▼
Phase 2: US1 (Decision Tree + Weather) ─────┐
                                             │
Phase 3: US2 (Booking Timeline) ────────────┤ (sequential — same file)
                                             │
Phase 4: US3 (Contingency Paths) ──────────┤
                                             │
                                             ▼
Phase 5: Polish ─────────────────────────── (depends on all content complete)
```

### User Story Dependencies

- **US1 (P1)**: Can start after Setup. No dependencies. **Start here — MVP.**
- **US2 (P2)**: Can start after US1 (builds on the same document, references decision windows from US1).
- **US3 (P3)**: Can start after US1 (references decision framework). Can run parallel with US2 if writing to different sections.

### Within-Phase Dependencies

**US1 (Phase 2)**: T002 (header + decision tree) → T003-T005 (decision windows, sequential — same section) → T006 (comparison table, can be parallel with T003-T005 if writing different section).

**Polish (Phase 5)**: T010 (cross-references) depends on all content. T011-T014 can run in parallel (different files or different validation concerns).

### Parallel Opportunities

**Within Phase 2 (US1)**:
- T006 (comparison table) can run in parallel with T003-T005 (decision windows) if writing to different sections of the file

**Within Phase 5 (Polish)**:
- T011, T012, T013, T014 can all run in parallel (T011 edits README.md, T012-T014 are validation checks)

---

## Implementation Strategy

### MVP First (Decision Tree Only)

1. Complete Phase 1: Setup (T001)
2. Complete Phase 2: US1 — Decision Tree + Weather Triggers (T002-T006)
3. **STOP and VALIDATE**: A reader can follow the decision tree to a destination recommendation. Minimum viable playbook.

### Incremental Delivery

1. Setup → Directory created
2. Add US1 (Decision Tree) → Reader can make a weather-based go/no-go decision
3. Add US2 (Booking Timeline) → Decision is informed by financial constraints
4. Add US3 (Contingency Paths) → Edge cases handled
5. Polish → All quality gates verified, integrated with rest of repo

Each increment adds standalone value without breaking previous content.

---

## Notes

- All content goes in a single file (`playbook/README.md`) — tasks are sequential within phases (same file constraint)
- Cross-reference Feature 004 and Feature 006 rather than duplicating their data
- Booking details are placeholders — design sections so actual terms can be dropped in later
- All weather data, costs, and policies should be flagged [UNVERIFIED]
- The decision tree at the top is the most important piece — optimize for that being useful even if nothing else is read
