# Feature Specification: Primary Bouldering Areas

**Feature Branch**: `001-bouldering-areas`
**Created**: 2026-02-10
**Status**: Draft
**Input**: User description: "Primary Bouldering Areas from the vision.md doc"

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Quick Area Selection at the Trailhead (Priority: P1)

A climber checks the weather on a February morning in Fayetteville and needs to pick the best bouldering area for the day within 60 seconds. They open the area overview document on their phone and use the quick-reference summary table to compare areas by drive time, grade spread, and rain resilience rating. They select the area that best fits today's weather, group energy, and ability-band mix.

**Why this priority**: This is the core decision the group makes every morning. If the document doesn't serve this rapid lookup, nothing else matters. Directly implements Constitution Principle I (Decision-Support First).

**Independent Test**: Open the area overview document on a phone. Without scrolling past the first screen, a reader can identify which area to visit based on today's weather and group composition.

**Acceptance Scenarios**:

1. **Given** a dry, cold February morning, **When** a climber views the area overview, **Then** they can identify the best area for the full group (all three ability bands) within one screen of content.
2. **Given** active rain, **When** a climber views the area overview, **Then** they can identify which areas have shelter and are climbable in wet conditions, with a clear rain resilience rating visible in the summary table.
3. **Given** the second-half roster (post-Wednesday swap), **When** the ability-band mix changes, **Then** the area profiles clearly indicate whether each area still works for the revised group composition.

---

### User Story 2 - Detailed Area Scouting (Priority: P2)

A climber has selected an area from the overview and now needs logistics: driving directions from Fayetteville, parking situation, approach trail description, NPS or land-management considerations, and a grade-spread breakdown. They open the individual area profile and find all of this in a consistent, predictable format.

**Why this priority**: Once the group picks an area, they need to actually get there and know what to expect. Consistent formatting across all area profiles means climbers learn the layout once and can find information in any area document instantly.

**Independent Test**: Pick any area profile document. A first-time reader can extract driving directions, parking, approach, grade spread, and weather-resilience details without reading the entire document end-to-end.

**Acceptance Scenarios**:

1. **Given** a climber has chosen Meadow River, **When** they open the Meadow River area profile, **Then** they find drive time, parking notes, approach description, grade-band table (V0-V3 | V4-V6 | V7-V10+), and rain resilience rating in predictable locations.
2. **Given** a climber is visiting Summersville Lake for the first time, **When** they read the area profile, **Then** they find access warnings (road conditions, winter closures, fees) and land-management notes clearly stated.
3. **Given** an area is within NPS boundaries, **When** a climber reads that area's profile, **Then** relevant NPS climbing regulations are noted (crash pads, chalk, group size, seasonal closures).

---

### User Story 3 - Wet-Weather Fallback Planning (Priority: P3)

It's raining and has been raining for 12+ hours. The group needs to find climbable rock. A climber opens the area overview and filters mentally by rain resilience. They find which specific areas (or sub-areas/sectors within areas) have overhanging problems that stay dry during active rain, and which areas will dry fastest once rain stops.

**Why this priority**: Weather resilience is the reason this trip exists (Constitution Principle V). This scenario directly tests whether the documents fulfill the plan's core purpose.

**Independent Test**: Simulate a rainy-day decision. Using only the area documents, identify at least one area with problems climbable during active rain, and estimate when other areas will become climbable after rain stops.

**Acceptance Scenarios**:

1. **Given** continuous rain, **When** a climber reviews area profiles, **Then** they find at least one area with explicitly identified sheltered/overhanging problems that remain dry during rain.
2. **Given** rain stopped 3 hours ago with sun and wind, **When** a climber checks drying estimates, **Then** they can determine which areas and problem types (overhanging vs. vertical vs. slab) are likely dry.
3. **Given** multi-day soaking rain, **When** a climber reviews area profiles, **Then** seepage patterns and drying timelines are documented so the group can estimate when climbing becomes viable.

---

### User Story 4 - Hard-Climbing Objective Targeting (Priority: P4)

The two V10 climbers in the group want to identify their primary objectives for the week. They need to know which areas have the highest concentration of quality hard problems (V7-V10+), whether those problems are overhanging or face, and whether they're accessible in bad weather.

**Why this priority**: Constitution Principle III prioritizes hard-climbing objectives in area selection. This story ensures V10 climbers can plan their week's tick list.

**Independent Test**: A V10 climber can identify the top 3 areas ranked by hard-problem density and quality by reading the overview document.

**Acceptance Scenarios**:

1. **Given** a V10 climber reviewing area profiles, **When** they look at grade-band tables, **Then** they can compare V7-V10+ problem counts across all areas at a glance.
2. **Given** the group is choosing between two areas, **When** the hard climbers check profiles, **Then** they find notes on whether hard problems are sheltered or exposed, aiding weather-dependent decisions.

---

### Edge Cases

- What if an area has zero documented problems in one ability band (e.g., no V7+ at a beginner-friendly area)? The profile MUST state "No documented problems in this grade range" rather than omitting the band.
- What if access to an area is seasonally restricted or uncertain in February? The profile MUST flag this prominently with a warning, not buried in prose.
- What if information about an area is sparse or unverified? The profile MUST flag unverified claims with `[UNVERIFIED]` per Constitution Principle VI.
- What if an area straddles NPS and non-NPS land? Both jurisdictions' regulations MUST be noted.

## Clarifications

### Session 2026-02-10

- Q: Should area profiles break down weather-resilience and grade-spread data by sector? → A: Yes — include sector-level breakdowns for both weather resilience and grade spread where distinct sectors exist within an area.
- Q: Should area profiles include tappable Google Maps links or text-only directions? → A: Include a Google Maps link to parking/trailhead plus a short text route summary (e.g., "US-19 N, 25 min").

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: The feature MUST produce an area overview document with a quick-reference summary table covering all bouldering areas within reasonable driving distance (~45 minutes) of Fayetteville, WV.
- **FR-002**: Each bouldering area MUST have an individual area profile document following a consistent structure: location, drive time, parking, approach, rock type, grade-band table (V0-V3 | V4-V6 | V7-V10+), problem density estimate, climbing style notes, rain resilience rating (Good / Fair / Poor), shelter and drying characteristics, seepage patterns, wind exposure, and land-management/NPS notes. Where an area contains distinct sectors, the profile MUST include per-sector breakdowns for weather resilience and grade spread.
- **FR-003**: The area overview summary table MUST include at minimum: area name, drive time from Fayetteville, rain resilience rating, grade spread indicator for all three ability bands, and a one-line suitability note.
- **FR-004**: Every area profile MUST include a rain resilience rating (Good / Fair / Poor) derived from documented shelter availability, seepage patterns, drying time estimates, and wind exposure.
- **FR-005**: Grade-band tables MUST use three columns (V0-V3 | V4-V6 | V7-V10+) showing estimated problem counts or density indicators for each band.
- **FR-006**: All factual claims MUST cite sources (guidebooks, Mountain Project, NPS publications, local beta). Unverified claims MUST be flagged with `[UNVERIFIED]`.
- **FR-007**: Areas primarily known for roped climbing (sport/trad) MUST only be included if they have documented bouldering problems. No sport or trad climbing content.
- **FR-008**: Each area profile MUST note group suitability — whether the area works for all three ability bands or skews toward a subset, and whether beginners will run out of problems quickly.
- **FR-009**: NPS-managed areas MUST include relevant climbing regulations (crash pad policy, chalk use, group size limits, seasonal closures relevant to February).
- **FR-010**: Each area profile MUST include February-specific considerations: winter access road conditions, approach trail hazards (ice, snow), and whether parking areas are maintained in winter.
- **FR-011**: Each area profile MUST include a Google Maps link to the primary parking/trailhead location alongside a short text route summary (e.g., "US-19 N, 25 min") for at-a-glance context.

### Key Entities

- **Bouldering Area**: A geographically distinct zone with a concentration of bouldering problems. Attributes: name, location description, drive time from Fayetteville, rock type, estimated problem count, grade distribution across three bands, predominant climbing style, rain resilience rating, shelter description, drying characteristics, seepage patterns, wind exposure, approach description, parking description, land management authority, access notes, February-specific conditions, group suitability assessment. Where distinct sectors exist, sector-level attributes include: sector name, sector-specific rain resilience rating, sector-specific grade-band breakdown, and shelter/exposure notes.
- **Sector**: A sub-zone within a Bouldering Area with distinct characteristics (e.g., different aspect, shelter level, or climbing style). Not all areas have sectors — only defined where meaningful differences exist within a single area.
- **Grade Band**: One of three standardized ability categories used throughout the project: V0-V3 (Beginner), V4-V6 (Intermediate), V7-V10+ (Hard). Each area's problem inventory is assessed against these bands.
- **Rain Resilience Rating**: A three-tier assessment (Good / Fair / Poor) applied to each area based on shelter availability, drainage, drying speed, and seepage behavior.

### Assumptions

- "Reasonable driving distance" is defined as ~45 minutes or less from Fayetteville, WV. Areas beyond this threshold are excluded (e.g., Coopers Rock at 2.5-3 hours is out of scope).
- Areas with fewer than ~10 documented problems are included if they serve a specific purpose (e.g., wet-weather shelter) but flagged as low-density.
- February 2026 NPS regulations are assumed to match the most recent available information; the spec will note where regulations should be re-verified closer to the trip date.
- Bouldering in the NRG region is a developing scene with less documentation than established destinations. Problem counts are estimates and the spec acknowledges this uncertainty.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A climber can select the best bouldering area for today's conditions (weather + group composition) within 60 seconds using only the area overview document on a phone.
- **SC-002**: Every bouldering area within 45 minutes of Fayetteville with 10+ documented problems is profiled.
- **SC-003**: 100% of area profiles include all required fields: drive time, grade-band table, rain resilience rating, shelter notes, approach description, and land-management notes.
- **SC-004**: On a rainy day, the group can identify at least one climbable area (with sheltered problems) using only the area documents, without needing external research.
- **SC-005**: The two V10 climbers can rank areas by hard-problem concentration using grade-band tables, identifying their top objectives for the week within 5 minutes.
- **SC-006**: All factual claims in area profiles are sourced, with zero unsourced assertions (unverified claims are explicitly flagged with `[UNVERIFIED]`).
