# Feature Specification: Decision Trigger Playbook

**Feature Branch**: `009-decision-trigger-playbook`
**Created**: 2026-02-11
**Status**: Draft
**Input**: User description: "009 | Decision Trigger Playbook from the vision.md"

## User Scenarios & Testing

### User Story 1 - Weather-Based Go/No-Go Decision (Priority: P1)

The trip organizer checks the Chattanooga and NRG weather forecasts in the days leading up to the trip and needs a clear, unambiguous framework to decide: stick with Chattanooga or pivot to New River Gorge. The playbook provides specific weather thresholds at defined decision windows (7 days out, 3 days out, 1 day out) so the group can make a confident call without second-guessing.

**Why this priority**: This is the entire reason the playbook exists. Without clear weather triggers, the group either waits too long (losing booking flexibility) or panics and switches prematurely.

**Independent Test**: Open the playbook, check a sample 7-day forecast for Chattanooga showing 4 consecutive rain days, and follow the decision tree to a clear "pivot to NRG" recommendation with a confidence assessment.

**Acceptance Scenarios**:

1. **Given** the Chattanooga forecast shows 3+ consecutive rain days in the trip week, **When** the organizer consults the playbook at the 7-day window, **Then** the playbook recommends "pivot to NRG" with a confidence assessment based on the NRG forecast.
2. **Given** both forecasts show mixed weather (1-2 rain days each), **When** the organizer consults the playbook, **Then** the playbook provides a comparative assessment showing expected climbable days at each location.
3. **Given** the Chattanooga forecast improves after an initial pivot decision, **When** the organizer checks the 3-day window, **Then** the playbook addresses whether to reverse the decision based on remaining cancellation flexibility.

---

### User Story 2 - Booking & Cancellation Timeline (Priority: P2)

The trip organizer needs to know the financial and logistical deadlines for both destinations — when flights, lodging, and rental cars must be booked or can still be cancelled — so that the weather-based decision aligns with what's actually still changeable. The playbook presents a countdown timeline showing what's locked, what's flexible, and what the cost of switching is at each decision window.

**Why this priority**: A weather trigger is useless if the group has already locked in non-refundable bookings. The timeline makes weather decisions actionable.

**Independent Test**: Open the playbook's countdown timeline and identify, for any given date before the trip, exactly which bookings are still cancellable and what the financial exposure is for switching.

**Acceptance Scenarios**:

1. **Given** the group is at the 7-day-out window, **When** they consult the booking timeline, **Then** they see which reservations (flights, lodging, rental cars) are still modifiable and the estimated cost of switching destinations.
2. **Given** the group is at the 3-day-out window with non-refundable flights to Chattanooga, **When** they consult the timeline, **Then** they see the sunk cost and whether rebooking to NRG is financially viable.

---

### User Story 3 - Contingency Paths (Priority: P3)

The trip organizer encounters a scenario not covered by the simple "Chattanooga vs. NRG" binary — both locations have bad forecasts, or NRG has access issues (Summersville Lake gates closed, roads iced). The playbook provides contingency paths for degraded scenarios so the group always has a next step.

**Why this priority**: Edge cases happen. The playbook should prevent the group from being stuck with no plan when the primary trigger logic doesn't yield a clear answer.

**Independent Test**: Open the playbook with a scenario where both locations show 3+ rain days, and find a clear recommendation (e.g., pick the location with better shelter options, or consider a third option).

**Acceptance Scenarios**:

1. **Given** both Chattanooga and NRG forecasts show 3+ rain days, **When** the organizer consults the contingency section, **Then** the playbook provides a comparative rain-resilience assessment and a recommendation based on shelter availability.
2. **Given** the group has committed to NRG but a key access point is confirmed closed (e.g., Summersville Lake gates), **When** the organizer checks contingencies, **Then** the playbook shows which remaining areas are still viable and whether the trip is still worth taking.

---

### Edge Cases

- What happens when forecasts flip dramatically between decision windows (e.g., clear at 7 days, rain at 3 days)?
- How does the playbook handle forecast uncertainty (e.g., 50% chance of rain — is that a trigger or not)?
- What if the mid-week roster change complicates a late destination switch (different flights, different arrival logistics)?
- What if neither destination has acceptable climbing weather for the full week?

## Requirements

### Functional Requirements

- **FR-001**: The playbook MUST define specific weather thresholds that trigger a destination switch (consecutive rain days, total rain days in 7-day window, temperature ranges).
- **FR-002**: The playbook MUST present decision windows at 7 days, 3 days, and 1 day before the trip, each with its own trigger criteria and available actions.
- **FR-003**: The playbook MUST include a side-by-side comparison framework for Chattanooga vs. NRG weather resilience (shelter availability, drying speed, number of rain-viable areas).
- **FR-004**: The playbook MUST present a countdown timeline showing booking/cancellation deadlines for flights, lodging, and rental cars at both destinations.
- **FR-005**: The playbook MUST quantify financial exposure at each decision window (estimated sunk costs, switching costs, rebooking costs).
- **FR-006**: The playbook MUST provide contingency paths for degraded scenarios (both destinations have bad weather, key NRG access points closed).
- **FR-007**: The playbook MUST cross-reference the Conditions Guide (Feature 004) for NRG-specific weather data rather than duplicating it.
- **FR-008**: The playbook MUST account for the mid-week roster change when assessing switching logistics (different flights, different arrival times).
- **FR-009**: The playbook MUST include a quick-reference decision tree at the top that can be followed in under 60 seconds.
- **FR-010**: All weather thresholds, cost estimates, and booking deadlines MUST be flagged `[UNVERIFIED]` where not confirmed from primary sources.
- **FR-011**: The playbook MUST be formatted for phone readability — skimmable tables, clear headings, no horizontal scroll.
- **FR-012**: The playbook MUST contain zero sport climbing, trad climbing, or route climbing references (bouldering scope only).

### Key Entities

- **Decision Window**: A defined point in time before the trip (7-day, 3-day, 1-day) with associated trigger criteria, available actions, and booking flexibility.
- **Weather Trigger**: A specific, measurable weather condition (e.g., "3+ consecutive rain days in Chattanooga forecast") that drives a destination recommendation.
- **Booking Commitment**: A reservation (flight, lodging, rental car) with its cancellation policy, deadline, and estimated cost.
- **Contingency Path**: An alternative plan for when the primary Chattanooga-vs-NRG decision doesn't yield a clear answer.

## Success Criteria

### Measurable Outcomes

- **SC-001**: A reader can follow the decision tree from "check forecast" to a clear destination recommendation in under 60 seconds.
- **SC-002**: Every decision window (7-day, 3-day, 1-day) has at least 2 defined weather triggers with explicit thresholds.
- **SC-003**: The booking timeline covers all major reservation types (flights, lodging, rental cars) with cancellation deadlines for both destinations.
- **SC-004**: Contingency paths exist for at least 3 degraded scenarios (both bad weather, NRG access closed, forecast reversal).
- **SC-005**: 100% of cost estimates and booking deadlines are flagged `[UNVERIFIED]` where not confirmed from primary sources.
- **SC-006**: The playbook cross-references the Conditions Guide at least 3 times rather than duplicating weather data.
- **SC-007**: Zero sport/trad/route climbing references in the document (scope compliance).

## Assumptions

1. The primary trigger for considering NRG is "Chattanooga forecast shows 3+ consecutive rain days in the week prior" (from vision.md).
2. Booking details (airline, lodging provider, cancellation policies) are not yet finalized — the playbook provides a general framework with placeholders for actual booking terms.
3. The group has access to standard weather forecasting sources (weather.gov, phone weather apps) and does not need specialized meteorological tools.
4. Decision authority rests with the group collectively, not a single person — the playbook supports group discussion, not autocratic decisions.
5. Cost estimates use approximate ranges rather than exact figures, since actual prices depend on booking timing and provider.
6. The Chattanooga companion repo exists and its conditions data can be referenced but not duplicated here.
7. Three decision windows (7-day, 3-day, 1-day) provide sufficient granularity — morning-of decisions are covered by the existing daily decision framework in Feature 004.

## Dependencies

- **Feature 004** (Conditions, Weather & Drying Guide): Provides NRG-specific weather data, drying times, and per-area weather resilience. The playbook cross-references this rather than duplicating.
- **Feature 006** (Logistics & Access Cheat Sheets): Provides NRG access details, drive times, and pre-trip checklist. The playbook references this for NRG logistics.
- **Chattanooga 2026 repo**: Provides Chattanooga-side weather resilience and area data for comparison. Referenced but not duplicated.

## Out of Scope

- Detailed Chattanooga weather analysis (lives in the companion repo)
- Daily in-trip decision-making (covered by Feature 004's Daily Decision Framework)
- Actual booking of flights, lodging, or rental cars
- Weather forecasting methodology or tools
