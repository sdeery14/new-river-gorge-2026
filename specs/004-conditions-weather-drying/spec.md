# Feature Specification: Conditions, Weather & Drying Guide

**Feature Branch**: `004-conditions-weather-drying`
**Created**: 2026-02-10
**Status**: Draft
**Input**: User description: "004 from the vision.md"
**Depends On**: Feature 001 (Primary Bouldering Areas), Feature 002 (Problem Clusters)

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Nuttall Sandstone Primer & Drying Reference (Priority: P1)

A climber is at the crag after overnight rain. The rock looks damp in some places but dry in others. They need to understand: Is it safe to climb? Will chalk work? How long until the vertical faces dry? Is seepage going to appear on the overhangs later?

This user story provides a comprehensive Nuttall sandstone reference — friction behavior, seepage patterns, drying time estimates by wall angle and conditions, and the "do not climb wet rock" ethic with the reasoning behind it. It's the foundational knowledge that makes all other weather decisions possible.

**Why this priority**: This is the core reason Feature 004 exists. Without understanding how Nuttall sandstone behaves in wet/cold conditions, no amount of weather data or area comparisons is useful. A climber who understands the rock can make good decisions at any area; without this knowledge, even a dry forecast doesn't help them assess conditions on arrival.

**Independent Test**: Open `conditions/README.md` on a phone at the crag. A climber can determine within 30 seconds: (1) whether it's safe to climb right now, (2) how long to wait if not, and (3) which wall angles are climbable first after rain.

**Acceptance Scenarios**:

1. **Given** it rained last night and stopped at 6 AM, **When** a climber opens the drying reference at 9 AM, **Then** they can estimate when vertical faces will be climbable based on current sun/wind/temperature conditions.
2. **Given** a climber is on a steep overhang after recent rain, **When** they notice moisture on a horizontal break, **Then** they can consult the seepage section to understand whether the problem will get wetter or drier over the coming hours.
3. **Given** temperatures are near freezing and the rock was wet yesterday, **When** a climber checks the primer, **Then** they can determine whether frozen rock is safe to climb on and what happens as it thaws.

---

### User Story 2 - February Weather Patterns & Daily Planning (Priority: P2)

It's 7 AM on a trip day. The group needs to decide what to do today. They check the weather app but don't know what February weather typically looks like in the NRG area — is 38F and overcast a good bouldering day? How often does February produce multi-day rain events? What's the wind pattern in the gorge?

This user story provides February-specific seasonal weather data for the New River Gorge area: temperature ranges, precipitation frequency and type, wind patterns, daylight hours, and how these translate into climbing conditions. It includes a daily planning framework that connects weather forecast data to area selection.

**Why this priority**: February weather intelligence is the bridge between the sandstone primer (US1) and actual trip planning. Without knowing what "normal" February weather looks like, the group can't interpret forecasts or calibrate expectations. This story converts raw weather data into climbing-relevant guidance.

**Independent Test**: Open `conditions/README.md` February weather section on a phone the morning of a climbing day. A group member can determine in under 60 seconds: (1) whether today is a climbing day, a biking day, or a rest day, and (2) which time window offers the best conditions.

**Acceptance Scenarios**:

1. **Given** the forecast shows 42F, overcast, 20% chance of rain, **When** a group member checks the February weather guide, **Then** they can assess whether these are typical good-day conditions and plan accordingly.
2. **Given** three consecutive rainy days are forecast, **When** a group member checks the guide, **Then** they can see how common multi-day rain events are in February and what the typical recovery pattern looks like.
3. **Given** the forecast shows 25F overnight warming to 45F, **When** a group member checks the daily planning framework, **Then** they can determine the optimal time window for climbing (after thaw, before afternoon moisture) and which areas to prioritize.

---

### User Story 3 - Per-Area Weather Behavior Matrix (Priority: P3)

The group has decided it's a climbing day, but the weather is mixed — some sun, some clouds, light wind. They need to choose between Meadow River, Summersville Lake, and the Gorge Boulders. Each area behaves differently in the same weather: Meadow River has overhangs that stay dry, the gorge floor is sheltered from wind but shaded, and Summersville Lake is exposed but gets morning sun.

This user story provides a consolidated comparison of how each bouldering area and trail system behaves under different weather conditions — wind exposure, sun/shade patterns, drying speed, shelter quality, and microclimate differences. It's the "which area today?" weather guide.

**Why this priority**: This story ties the sandstone primer and weather data to specific area recommendations. It's the final decision tool that converts "today's conditions" into "go to this area." Without it, the group has to mentally cross-reference multiple area profiles — this story does that comparison for them in one place.

**Independent Test**: Open `conditions/README.md` per-area weather matrix on a phone. A group member can identify the best area for today's specific weather conditions in under 30 seconds by scanning the comparison table.

**Acceptance Scenarios**:

1. **Given** it's raining actively, **When** a group member opens the weather matrix, **Then** they can identify which areas have shelter for climbing during rain and which to avoid.
2. **Given** it rained yesterday but is now sunny and windy, **When** a group member opens the matrix, **Then** they can see which areas dry fastest and estimate when each area becomes climbable.
3. **Given** temperatures are below freezing with no precipitation, **When** a group member opens the matrix, **Then** they can see which areas have the best friction conditions and which may have residual ice on approaches.

---

### Edge Cases

- What if conditions don't match any scenario in the guide? (Unusual weather events like ice storms, unseasonable warmth, etc.) — The guide should provide general principles that enable reasoning about novel situations, not just lookup tables for specific scenarios.
- What if the sandstone primer contradicts a specific area profile's drying data? — This guide is the authoritative source for rock behavior; area profiles contain area-specific notes. If there's a conflict, the detailed area-specific data in the per-area matrix (US3) takes precedence for that area.
- What if the group includes members who've never climbed on sandstone? — The primer should be accessible to first-time sandstone climbers without assuming prior knowledge of rock types.
- What about conditions that affect mountain biking but not climbing? — Include trail-relevant weather notes (freeze/thaw for dirt trails) that cross-reference the existing trail profiles in `trails/`.

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: The guide MUST include a Nuttall sandstone primer covering: rock composition, friction behavior when wet vs. dry vs. frozen, seepage patterns (where water emerges and why), and the community ethic against climbing wet sandstone with the reasoning (rock preservation, friability when saturated).
- **FR-002**: The guide MUST include drying time estimates organized by wall angle (overhang, vertical, slab) and drying conditions (sun+wind, overcast, overcast+cold). Estimates MUST distinguish between "surface dry" and "friction restored."
- **FR-003**: The guide MUST include February-specific seasonal weather data for the Fayetteville/NRG area: typical temperature ranges (highs, lows), precipitation frequency and type (rain, sleet, snow, mix), average precipitation amounts, wind speed and direction patterns, and daylight hours.
- **FR-004**: The guide MUST include a daily planning framework that maps weather forecast conditions to activity recommendations (climb, ride, rest) and area selection.
- **FR-005**: The guide MUST include a per-area weather comparison matrix covering all 3 bouldering areas (Meadow River, Summersville Lake, Gorge Boulders) with: wind exposure, sun/shade pattern, shelter quality, drying speed relative to other areas, and best/worst weather scenarios for each.
- **FR-006**: The guide MUST include wind pattern information for the New River Gorge — how gorge geography affects wind at different areas, typical February wind speeds, and how wind affects climbing conditions (friction, comfort, drying).
- **FR-007**: The guide MUST cross-reference Feature 001 area profiles and Feature 003 trail profiles, linking to relevant documents for area-specific details rather than duplicating content.
- **FR-008**: The guide MUST include a freeze/thaw section covering: how frozen rock affects friction and safety, the thaw cycle timeline on a typical February day, and how freeze/thaw affects both climbing conditions and trail conditions.
- **FR-009**: All data MUST be flagged as [UNVERIFIED] where not confirmed by primary sources. Source citations MUST be included.
- **FR-010**: All tables MUST be phone-readable (no more than 8 columns) and the document MUST follow the phone-first layout standard (quick-reference at top, details below).
- **FR-011**: The guide MUST include bidirectional links to/from related documents (area profiles in `areas/`, trail profiles in `trails/`).

### Key Entities

- **Rock Behavior Profile**: Nuttall sandstone characteristics — friction curve, seepage mechanics, drying rates, freeze/thaw behavior. The core reference for all weather-related climbing decisions.
- **February Weather Profile**: Seasonal climate data for the NRG area — temperature, precipitation, wind, daylight. Historical patterns that set expectations for the trip week.
- **Area Weather Behavior**: Per-area microclimate characteristics — wind exposure, sun pattern, shelter, drying speed, best/worst conditions. One entry per bouldering area and trail system.
- **Daily Decision Framework**: A structured guide mapping weather conditions to activity and area recommendations. The "what do we do today?" tool.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A climber can determine whether it's safe to climb on Nuttall sandstone right now (yes/no/wait) within 30 seconds of consulting the guide.
- **SC-002**: A group member can estimate drying time for a specific wall angle under current conditions within 30 seconds.
- **SC-003**: The group can make a morning area-selection decision (which area today, based on weather) within 60 seconds of consulting the guide.
- **SC-004**: A first-time sandstone climber can understand the "don't climb wet rock" ethic and the reasoning behind it after reading the primer.
- **SC-005**: The guide covers at least 6 distinct weather scenarios (clear+cold, clear+warm, overcast, active rain, post-rain drying, freeze/thaw) with specific area recommendations for each.
- **SC-006**: All weather data and drying estimates are internally consistent with existing area profiles in `areas/` and trail profiles in `trails/`.

## Clarifications

### Session 2026-02-10

- Q: Should this be a single comprehensive file or multiple focused files? → A: Single file `conditions/README.md` with all 3 topics as sections (sandstone primer, February weather, per-area matrix). One-stop reference, compact, uses section anchors for direct linking.

## Assumptions

- The guide is a single file at `conditions/README.md` containing all 3 topics as sections: Nuttall sandstone primer, February weather patterns, and per-area weather matrix. Section anchors enable direct linking from area and trail profiles to specific sections. This mirrors the compact pattern used for bouldering pairings and rentals in `trails/README.md`.
- February weather data is based on historical averages for the Fayetteville, WV area. Actual trip conditions will vary.
- Drying time estimates are approximations based on sandstone behavior research and climbing community knowledge. They are not precise measurements.
- The guide consolidates and extends weather information already present in area profiles (Feature 001) and trail profiles (Feature 003). It is the authoritative weather reference; area/trail profiles contain area-specific summaries.
- Wind pattern data for the gorge is based on general Appalachian gorge geography and available weather station data. Gorge-floor microclimates are difficult to characterize precisely.
- The "do not climb wet sandstone" ethic is well-established in the NRG climbing community and is treated as a firm guideline, not a suggestion.

## Scope

### In Scope

- Nuttall sandstone rock behavior reference (friction, seepage, drying, freeze/thaw)
- February seasonal weather data for Fayetteville/NRG area
- Per-area weather behavior comparison (all 3 bouldering areas + trail systems)
- Wind patterns in the New River Gorge
- Daily decision framework (weather → activity → area)
- Cross-references to existing area and trail profiles

### Out of Scope

- Real-time weather forecasting or automated condition updates
- Weather behavior for areas outside the 45-minute drive radius from Fayetteville
- Detailed geological survey of Nuttall sandstone (this is a practical climbing reference, not a geology textbook)
- Weather data for months other than February (the trip is February 14-21)
- Route climbing conditions (bouldering only per constitution)
