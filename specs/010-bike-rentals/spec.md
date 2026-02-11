# Feature Specification: Bike Rentals

**Feature Branch**: `010-bike-rentals`
**Created**: 2026-02-11
**Status**: Draft
**Input**: User description: "010 | Bike Rentals from the vision doc"

## User Scenarios & Testing

### User Story 1 - Rental Shop Directory (Priority: P1)

A group member wants to rent a mountain bike for the trip but doesn't know which shops near Fayetteville are open in February or what they charge. The directory provides a quick-reference table of local and nearby rental shops with contact info, pricing, bike types, February availability status, and reservation requirements — so the rider can find and book a rental in one phone call.

**Why this priority**: Without knowing where to rent, none of the other rental guidance matters. This is the foundation — answer "where can I get a bike?"

**Independent Test**: Open the rental guide, scan the quick-reference table, identify which shops are likely open in February, and find a phone number to call. Should take under 30 seconds.

**Acceptance Scenarios**:

1. **Given** a group member needs a rental bike, **When** they open the rental guide, **Then** they see a comparison table of all rental shops sorted by likelihood of February availability, with phone numbers and estimated pricing.
2. **Given** a group member calls a shop listed as "likely open," **When** the shop confirms availability, **Then** the guide provides reservation requirements (advance notice, credit card, ID, waiver).
3. **Given** all local shops are closed for winter, **When** the reader checks the guide, **Then** they find out-of-town alternatives (Charleston, Beckley) and a bring-your-own-bike strategy.

---

### User Story 2 - Beginner Rental Guidance (Priority: P2)

A group member who has never rented a mountain bike (or is new to MTB) needs guidance on what kind of bike to ask for, what size, what gear to bring or rent alongside, and basic tips for riding NRG trails in February conditions. The guide provides beginner-specific recommendations so a first-timer can show up prepared.

**Why this priority**: Several group members are V1-V3 climbers who may ride instead of climb on some days. They need practical guidance to avoid renting the wrong bike or showing up unprepared.

**Independent Test**: A first-time renter reads the beginner section and can answer: "What kind of bike should I ask for?", "What size?", "What else do I need?", and "What should I know about riding in February?"

**Acceptance Scenarios**:

1. **Given** a beginner renter, **When** they read the beginner guidance, **Then** they know to ask for a hardtail or full-suspension mountain bike (not a road or hybrid bike), understand basic sizing, and know what additional gear is needed (helmet, gloves, layers).
2. **Given** February conditions (cold, potentially frozen/muddy ground), **When** a beginner reads the guide, **Then** they understand when trails are rideable vs. when to skip riding, and what to wear.

---

### Edge Cases

- What if no rental shops are open in February at all? (High probability — documented in trails/README.md)
- What if a shop is open but only has limited bike sizes or types?
- What if the group decides to rent from an out-of-town shop — how do they transport the bikes?
- What if a rental bike breaks down on the trail?

## Requirements

### Functional Requirements

- **FR-001**: The guide MUST include a quick-reference comparison table of all identified rental shops with: shop name, location, distance from Fayetteville, phone number, estimated pricing, bike types available, and February availability status.
- **FR-002**: Each rental shop entry MUST include: reservation requirements (advance notice, deposit, ID), rental duration options (half-day, full day), and any known policies (waivers, damage liability).
- **FR-003**: The guide MUST include out-of-town alternatives (shops in Charleston, Beckley, or en route) for when local shops are closed.
- **FR-004**: The guide MUST include a "bring your own bike" section covering transport logistics for the group.
- **FR-005**: The guide MUST include a beginner guidance section covering: recommended bike type for NRG trails, basic sizing guidance, required and recommended gear, and February-specific riding tips.
- **FR-006**: The guide MUST prominently warn about the high risk of February closures — Fayetteville's outdoor economy is seasonal (May-October) and most rental operations are unlikely to be open.
- **FR-007**: The guide MUST cross-reference the Trail Profiles (Feature 003) for trail difficulty and conditions rather than duplicating that information.
- **FR-008**: All pricing, hours, and availability claims MUST be flagged `[UNVERIFIED]` where not confirmed from primary sources.
- **FR-009**: The guide MUST be formatted for phone readability — skimmable tables, clear headings, no horizontal scroll.
- **FR-010**: The guide MUST contain zero sport climbing, trad climbing, or route climbing references (bouldering scope only for any climbing mentions).

### Key Entities

- **Rental Shop**: A business that rents mountain bikes. Attributes: name, location, distance from Fayetteville, phone, website/social, pricing, bike types, February status, reservation policy.
- **Bike Type**: Category of rental bike (hardtail, full-suspension, etc.) with suitability notes for NRG trails.
- **Fallback Option**: An alternative to local rental when shops are closed (out-of-town shop, bring-your-own, skip riding).

## Success Criteria

### Measurable Outcomes

- **SC-001**: A reader can identify the most likely available rental shop and its phone number in under 30 seconds from the quick-reference table.
- **SC-002**: The guide covers at least 3 local/nearby rental shops and at least 2 out-of-town alternatives.
- **SC-003**: The beginner guidance section answers the 4 core questions: what bike type, what size, what gear, and what to know about February riding.
- **SC-004**: The February closure warning appears within the first 3 lines of the document so readers see it immediately.
- **SC-005**: 100% of pricing and availability claims are flagged `[UNVERIFIED]` where not confirmed from primary sources.
- **SC-006**: The guide cross-references Trail Profiles at least twice rather than duplicating trail data.
- **SC-007**: Zero sport/trad/route climbing references in the document (scope compliance).

## Assumptions

1. The guide is added to the existing `trails/` section as a dedicated rental page (`trails/bike-rentals.md`) since bike rentals are a sub-topic of the mountain biking feature (Feature 003).
2. Most local rental shops will be closed in February — the guide is designed around this reality, prioritizing fallback strategies alongside the shop directory.
3. The group may include first-time mountain bikers who need basic guidance beyond just "where to rent."
4. Pricing information will be approximate ranges (e.g., "$50-80/day") rather than exact figures, flagged [UNVERIFIED].
5. The guide does not need to cover bike purchase — only rental and bring-your-own strategies.
6. Beginner guidance covers enough to get someone safely on an easy (green) trail, not to teach advanced mountain biking skills.

## Dependencies

- **Feature 003** (Mountain Biking Trails): Provides trail profiles, difficulty ratings, and February conditions. The rental guide cross-references this rather than duplicating.

## Out of Scope

- Bike purchase recommendations or gear reviews
- Advanced mountain biking technique instruction
- E-bike specific guidance (unless a shop specifically offers them)
- Bike maintenance or repair guides
