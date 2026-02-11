# Feature Specification: Logistics & Access Cheat Sheets

**Feature Branch**: `006-logistics-access`
**Created**: 2026-02-11
**Status**: Draft
**Input**: User description: "006 | Logistics & Access Cheat Sheets from the vision.md"

## Clarifications

### Session 2026-02-11

- Q: Should this feature produce a single file or multiple files? → A: Single file at `logistics/README.md` — all sections in one scrollable document, consistent with Feature 004 and 005 single-file patterns.
- Q: Should car and lodging sections use actual member names or generic templates? → A: Generic role-based templates (e.g., "Car A", "Departing Member", "Arriving Member") with placeholders the group fills in before the trip.
- Q: How much access detail should the cheat sheet duplicate from area/trail profiles? → A: Abbreviated one-line summaries (parking note, approach note, access warning) with links to the full area/trail profiles for details.

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Quick Access Cheat Sheet (Priority: P1)

It's 7:30 AM and the group has picked today's bouldering area from the conditions guide. Now they need the operational details: how to get there, where to park, how long the approach is, and any access gotchas. Instead of opening 3-4 different area profile documents and hunting for logistics fields buried in each one, a member opens a single cheat sheet and finds a consolidated table with drive times, parking GPS links, approach summaries, and access warnings for every bouldering area and trail system — all on one screen.

**Why this priority**: This is the core "last mile" problem. Features 001 and 003 contain logistics details scattered across 6+ individual profile documents. The group needs a single quick-reference layer that consolidates all access info so the morning decision-to-departure time is under 5 minutes. Directly implements Constitution Principle I (Decision-Support First).

**Independent Test**: Open the access cheat sheet on a phone. Without opening any other document, find the drive time, parking location, and approach summary for any bouldering area or trail system within 30 seconds.

**Acceptance Scenarios**:

1. **Given** the group has decided to climb at Meadow River, **When** a member opens the access cheat sheet, **Then** they find drive time, parking GPS link, approach distance/time, and any access warnings in a single table row — without navigating to the Meadow River area profile.
2. **Given** the group wants to pair a morning bike ride with afternoon bouldering, **When** a member checks the cheat sheet, **Then** they find both trail system and bouldering area access details side by side, with combined drive time visible.
3. **Given** a member is driving to a trailhead for the first time, **When** they check the cheat sheet, **Then** they find a tappable GPS link and a short text route summary (e.g., "US-19 S → Fayette Station Rd, 10 min").

---

### User Story 2 - NPS Regulations & Access Rules (Priority: P2)

A group member wants to know the rules before they boulder in a National Park. Can they use crash pads? Is chalk allowed? Are there group size limits? What about seasonal closures in February? Instead of re-reading each area profile to find the regulations section, they open a consolidated regulations reference and find all NPS rules, fee areas, and access restrictions in one place.

**Why this priority**: NRG became a National Park in 2020 and has specific climbing regulations. Violating them (even unknowingly) risks fines and sets a bad precedent for the climbing community. A consolidated reference prevents the group from missing rules buried in individual area profiles.

**Independent Test**: Open the regulations reference. Find the crash pad policy, chalk policy, and any February-specific closures for NPS-managed bouldering areas within 30 seconds.

**Acceptance Scenarios**:

1. **Given** the group is bouldering in NPS-managed Gorge Boulders, **When** a member checks the regulations reference, **Then** they find crash pad rules, chalk/brushing rules, group size guidance, and any seasonal restrictions clearly listed.
2. **Given** a member is unsure whether Summersville Lake is NPS or USACE-managed, **When** they check the regulations reference, **Then** they see the land manager for each area alongside applicable rules.
3. **Given** some bouldering areas may have February-specific closures or access restrictions, **When** a member reviews the reference, **Then** any seasonal closures or winter access warnings are prominently flagged.

---

### User Story 3 - Mid-Week Roster Change Logistics (Priority: P3)

Wednesday is transition day — one member departs in the morning and another arrives in the afternoon. The group needs to coordinate: Does the departing member take a car? Does the arriving member need a pickup? How does lodging change (room assignments, headcount)? How does car capacity affect carpooling for the rest of the week? A member opens the roster-change logistics section and finds a clear plan for the Wednesday transition, including car handoff, lodging adjustments, and pickup logistics.

**Why this priority**: The mid-week roster change is a unique logistical challenge for this trip. Feature 005 addressed Wednesday as a rest-day activity planning scenario; this feature addresses the operational logistics — cars, lodging, and coordination. Without this, Wednesday devolves into chaos.

**Independent Test**: Read the roster-change section. Find answers to: Does the departing member leave a car? What time should the arriving member be picked up? How do room assignments change?

**Acceptance Scenarios**:

1. **Given** Wednesday morning with one member departing, **When** the group checks the roster-change logistics, **Then** they find a car handoff plan that accounts for whether the departing member drives their own car or carpooled.
2. **Given** the arriving member needs to get from the airport or meeting point to Fayetteville, **When** they check the logistics section, **Then** they find the nearest airport(s), drive time to Fayetteville, and a pickup coordination plan.
3. **Given** the group size drops from 6 to 5 on Wednesday morning and returns to 6 on Wednesday afternoon, **When** they check lodging logistics, **Then** they find guidance on room assignment adjustments during the transition window.

---

### User Story 4 - Car Strategy & Carpooling (Priority: P4)

The group has 2-3 cars for 5-6 people. On any given day, some members may boulder while others bike, hike, or rest. The group needs a carpooling strategy that gets everyone where they need to be without wasting time on complex shuttle logistics. A member opens the car strategy section and finds guidance on fleet management, daily split scenarios, and parking strategy.

**Why this priority**: Car logistics affect every single day of the trip. Poor coordination means wasted time driving back for forgotten items, stranded subgroups, or everyone driving separately to the same place. This is especially important when the group splits between activities.

**Independent Test**: Look up a scenario where 3 members boulder and 2 members bike. Find a carpooling plan that gets both subgroups to their destinations with minimal driving overhead.

**Acceptance Scenarios**:

1. **Given** the full group (6 people, 2-3 cars) wants to go to the same bouldering area, **When** they check the car strategy, **Then** they find which parking areas can accommodate their vehicles and whether one car is sufficient.
2. **Given** the group splits (3 boulder, 2 bike, 1 rests), **When** they check the split-day carpooling guide, **Then** they find a sample plan showing which car goes where and an estimated morning departure time.
3. **Given** mid-week when one car may leave with the departing member, **When** the group checks car logistics, **Then** they see how the reduced fleet affects carpooling options for the remaining days.

---

### Edge Cases

- What if a road to a bouldering area or trailhead is closed due to winter conditions (ice, snow, fallen trees)? The cheat sheet must include alternate access routes or alternate area suggestions for each location.
- What if the arriving member's flight is delayed on Wednesday? The roster-change section must note flexibility in the pickup plan and suggest contingency activities for the waiting group.
- What if the group has fewer cars than expected (e.g., a member can't bring their car)? The car strategy must note minimum viable fleet size and how it constrains daily planning.
- What if NPS regulations change between now and the trip date (February 2026)? The regulations section must note the source date and recommend a pre-trip verification call to the NPS visitor center.

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: The feature MUST produce a consolidated access cheat sheet with a master table covering every bouldering area and trail system from Features 001 and 003. Table columns: location name, drive time from Fayetteville, parking (GPS link + abbreviated one-line note), approach summary (one-line: distance, time, difficulty), and access warnings (one-line: closures, hazards, fees). Each row MUST link to the full area or trail profile for detailed information.
- **FR-002**: Each row in the access table MUST include a tappable GPS link to the parking location and a short text route summary (e.g., "US-19 S → Fayette Station Rd, 10 min").
- **FR-003**: The feature MUST include a consolidated NPS and land-manager regulations section listing: land manager for each bouldering area, crash pad policy, chalk/brushing policy, group size guidance, seasonal closures, and fee requirements.
- **FR-004**: Access warnings MUST be prominently flagged for any location with February-specific hazards: icy approach trails, gated roads, reduced winter parking, or seasonal closures.
- **FR-005**: The feature MUST include a roster-change logistics section covering the Wednesday mid-week transition: car handoff plan, arrival/departure coordination, nearest airport(s) with drive time, lodging headcount adjustment, and room assignment guidance.
- **FR-006**: The feature MUST include a car strategy section covering: expected fleet size (number of cars), daily carpooling scenarios (full group, split activities, bad weather day), and parking capacity notes for each bouldering area and trail system.
- **FR-007**: The feature MUST include alternate access or alternate area suggestions for each location where the primary access route may be closed in winter.
- **FR-008**: The feature MUST include a pre-trip verification checklist listing calls and website checks to confirm access, closures, and regulations before the trip date.
- **FR-009**: All claims about drive times, regulations, fees, and access conditions MUST cite sources. Unverified claims MUST be flagged with `[UNVERIFIED]`.
- **FR-010**: All documents MUST be phone-readable: tables no wider than 6 columns, quick-reference at top, details below. GPS links must be tappable on mobile.
- **FR-011**: The feature MUST cross-reference Features 001 and 003 via links to full area and trail profiles. The cheat sheet provides abbreviated one-line summaries of access details; it does not duplicate climbing, biking, or full approach narrative content.
- **FR-012**: The feature MUST be 100% bouldering-trip context — no sport climbing, trad climbing, or route-climbing references.

### Key Entities

- **Access Point**: A specific parking/trailhead location with GPS coordinates, text route summary, drive time from Fayetteville, lot description (capacity, surface, winter maintenance), and approach details (distance, time, difficulty, hazards). Each bouldering area and trail system has one or more access points.
- **Regulation Set**: A collection of rules applicable to a land management jurisdiction (NPS, USACE, WV State Parks, etc.). Attributes: land manager name, applicable areas, crash pad policy, chalk/brushing policy, group size guidance, seasonal closures, fees, source citation.
- **Car Fleet**: The group's vehicle resources, expressed as generic role-based templates (Car A, Car B, Car C). Attributes: number of cars, passenger capacity per car, how fleet changes at mid-week roster shift. Uses placeholders the group fills in before the trip.
- **Roster Transition**: The Wednesday mid-week member swap, expressed with role placeholders (Departing Member, Arriving Member). Attributes: departure timing, arrival timing, car handoff plan, airport/pickup logistics, lodging adjustment. Specific names filled in before the trip.

## Assumptions

- **Single-file deliverable**: All logistics content lives in one file at `logistics/README.md`, consistent with Feature 004 (`conditions/README.md`) and Feature 005 (`rest-day/README.md`). Estimated 300-500 lines.
- **Fayetteville is the base town**: All drive times, directions, and logistics are relative to a rental house in or near Fayetteville, WV.
- **Group size is 5-6 with mid-week roster change**: One member departs Wednesday morning, another arrives Wednesday afternoon. Fleet size and lodging capacity shift accordingly.
- **Fleet size is 2-3 cars**: The group travels with 2-3 personal vehicles. The exact number depends on who drives to WV versus flies.
- **Generic templates, not filled-in plans**: Car strategy, roster-change, and lodging sections use role-based placeholders (Car A/B/C, Departing Member, Arriving Member) rather than actual names. The group fills in specifics before the trip.
- **Lodging is a rental house**: The group is staying in a single rental house (Airbnb or similar), not a hotel. Room assignments and capacity are relevant.
- **Nearest airports**: Yeager Airport (Charleston, WV, ~1 hr) and Greenbrier Valley Airport (Lewisburg, WV, ~1 hr) are the most likely arrival points for the mid-week member. Beckley may also be relevant.
- **GPS links use Google Maps format**: For maximum compatibility with phone navigation apps.
- **Access details already exist in Features 001 and 003**: This feature consolidates and augments — it does not duplicate full area/trail profiles.
- **NPS regulations are based on current (2025-2026) policies**: The group should verify closer to the trip date, especially regarding any new climbing management plans.

## Dependencies

- **Feature 001 (Primary Bouldering Areas)**: Required — provides bouldering area locations, parking, approaches, NPS notes, and access details to consolidate.
- **Feature 003 (Mountain Biking Trails)**: Required — provides trail system locations, parking, and access details to consolidate.
- **Feature 005 (Rest-Day Pack)**: Optional — the roster-change logistics section builds on the Wednesday activity planning in Feature 005 but adds operational logistics (cars, lodging) that Feature 005 does not cover.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A group member can find the drive time, parking GPS link, and approach summary for any bouldering area or trail system within 30 seconds using only the access cheat sheet on a phone.
- **SC-002**: All NPS-managed bouldering areas have their regulations (crash pads, chalk, group size, closures) documented in the consolidated regulations section — no need to open individual area profiles.
- **SC-003**: The roster-change logistics section answers all three key questions: car handoff plan, airport/pickup coordination, and lodging adjustment — without requiring additional research.
- **SC-004**: The car strategy section covers at least 3 daily scenarios (full group same destination, split activities, bad weather day) with sample carpooling plans.
- **SC-005**: 100% of access claims cite sources or are flagged with `[UNVERIFIED]`.
- **SC-006**: All tables are phone-readable (no wider than 6 columns) and every parking location has a tappable GPS link.
- **SC-007**: Every location with a February access risk (icy roads, gated access, seasonal closures) has an alternate access route or alternate area suggestion documented.
