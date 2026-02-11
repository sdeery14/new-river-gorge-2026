# Feature Specification: Problem Clusters

**Feature Branch**: `002-problem-clusters`
**Created**: 2026-02-10
**Status**: Draft
**Input**: User description: "Problem Clusters from the vision.md doc"
**Depends On**: Feature 001 (Primary Bouldering Areas)

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Grade-Band Problem Selection (Priority: P1)

A climber arrives at an area and wants to quickly find quality problems at their grade level. They open the problem cluster document for that area on their phone and scan their grade band for curated problems. Each entry shows the problem name, grade, style, shelter status, and landing quality — enough to walk up to a boulder and try it without consulting another source.

**Why this priority**: This is the core value of the feature. Without grade-band-organized problem lists, climbers either need a guidebook or waste time wandering between boulders. Constitution Principle III (Hard-Climbing Priority) requires that V7-V10+ problems are prominently listed.

**Independent Test**: Open any area's problem cluster document on a phone. A V6 climber can identify 3+ quality problems at their grade within 30 seconds of opening the document.

**Acceptance Scenarios**:

1. **Given** a climber at Meadow River, **When** they open the problem cluster document and look at the V4-V6 section, **Then** they find curated problems listed with name, grade, style, shelter status, and landing quality.
2. **Given** a V10 climber reviewing the V7-V10+ section for any area, **Then** each problem includes style description detailed enough to assess conditions needed (e.g., "steep compression — needs dry cold" vs. "overhang jug-haul — works in humidity").
3. **Given** an area with no documented problems in a grade band, **Then** the document explicitly states "No documented problems in this grade range" rather than omitting the band.

---

### User Story 2 - Rainy-Day Sheltered Problem List (Priority: P2)

It's raining. The group needs to find problems they can climb right now. They want a quick-reference list of sheltered problems across all areas — problems under overhangs, roofs, or cliff shelter that stay dry during active rain. This list should be accessible without reading through each area's full problem cluster document.

**Why this priority**: This trip exists because of rain. Constitution Principle V (Weather-Resilience) demands that shelter information is front-and-center. A cross-area sheltered problem list is the rain-day decision tool.

**Independent Test**: Simulate active rain. Using only the problem cluster documents, find at least 5 sheltered problems across all areas within 60 seconds, with grades spanning all three ability bands.

**Acceptance Scenarios**:

1. **Given** active rain, **When** a climber opens the cross-area sheltered classics summary, **Then** they find sheltered problems organized by area with grade, style, and specific location (enough to navigate to the boulder).
2. **Given** the sheltered classics list, **Then** it includes problems across all three ability bands (V0-V3, V4-V6, V7-V10+) so the entire group can climb.
3. **Given** a problem marked "sheltered," **Then** the shelter type is specified (e.g., "cliff-base overhang," "roof," "cave") so climbers can assess whether it's truly dry or just partially covered.

---

### User Story 3 - Hard-Climbing Week Planner (Priority: P3)

The two V10 climbers want to build a prioritized tick list for the week. They need all V7-V10+ problems across all areas in one view, ranked by quality, with style descriptions, shelter status, and which area/sector each problem is in. This lets them plan which areas to prioritize on which days based on weather and conditions.

**Why this priority**: Constitution Principle III gives hard-climbing objectives first priority in area selection. This story extends that to problem-level planning. The V10 climbers are the trip anchors — their objectives drive daily area choice.

**Independent Test**: A V10 climber can build a ranked list of their top 10 objectives for the week by scanning the hard-climbing summary, without reading every area's full problem cluster document.

**Acceptance Scenarios**:

1. **Given** a V10 climber planning the week, **When** they review the cross-area V7-V10+ summary, **Then** they find all hard problems listed with area, grade, style, shelter status, and a quality indicator (classic/recommended/standard).
2. **Given** a rainy day, **When** the V10 climber checks the hard-climbing summary, **Then** they can identify which hard problems are sheltered and at which area, without cross-referencing the rain-day list separately.

---

### User Story 4 - Mixed-Ability Session Planning (Priority: P4)

The full group (V1-V3, V6, and V10 climbers) is choosing an area for the day. They want to know which areas have problems for everyone — enough V0-V3 to keep beginners engaged, enough V4-V6 for intermediate climbers, and quality V7-V10+ for the hard climbers. The problem cluster documents should make it obvious whether an area supports a mixed-ability session.

**Why this priority**: Constitution Principle III requires ability-aware documentation. This story ensures the group can pick areas where nobody is left without problems. Especially relevant in the first half of the trip when beginners are present.

**Independent Test**: The group can compare problem cluster density across areas and choose one where all three ability bands have at least 3 curated problems.

**Acceptance Scenarios**:

1. **Given** a mixed-ability group, **When** they compare problem cluster summaries across areas, **Then** each area's document shows a quick-reference count of curated problems per grade band at the top.
2. **Given** Summersville Lake (best beginner area per Feature 001), **When** the group reviews its problem clusters, **Then** the V0-V3 section has the most curated problems of any area.

---

### Edge Cases

- What if an area has zero documented problems in a grade band? The document MUST explicitly state "No documented problems in this grade range" rather than omitting the band.
- What if a problem has no established name? Use a descriptive identifier (e.g., "Unnamed overhang, River Boulder, river-left" with enough location detail to find it).
- What if shelter status cannot be determined from available sources? Flag the shelter field as `[UNVERIFIED]` rather than guessing.
- What if a problem's grade is disputed or has a wide consensus range? List the most common grade with the range in parentheses (e.g., "V7 (V6-V8)").
- What if very few problems are documented for an area (e.g., Gorge Boulders has "Few" per band)? Include all known problems rather than curating down — note that the list represents the full known inventory.

## Clarifications

### Session 2026-02-10

- Q: How specific should problem location directions be? → A: Descriptive text location per problem (e.g., "Tall overhang 50m left of trail junction, river-left") — no GPS coordinates needed.
- Q: Should problem entries include Mountain Project links? → A: Yes — include a tappable Mountain Project link per problem where available.

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: Each bouldering area from Feature 001 (Meadow River, Summersville Lake, Gorge Boulders) MUST have a problem cluster document listing curated problems organized by grade band (V0-V3, V4-V6, V7-V10+).
- **FR-002**: Each problem entry MUST include: problem name, V-grade, style (e.g., overhang, slab, compression, crimp, arete, roof, traverse), shelter status (sheltered / partially sheltered / exposed), landing quality (flat / uneven / poor), a descriptive location (e.g., "Tall overhang 50m left of trail junction, river-left") sufficient to find the boulder without GPS, and a Mountain Project link where available (tappable on phone for photos, beta, and community grades).
- **FR-003**: Quality problems MUST be highlighted with a classic/recommended marker (e.g., star symbol) to differentiate must-do problems from the full list. Classic designation is based on Mountain Project star ratings, guidebook recommendations, or community consensus.
- **FR-004**: Every problem cluster document MUST clearly identify which problems are climbable during active rain by marking their shelter status. Sheltered problems MUST specify the shelter type (cliff-base overhang, roof, cave, tree canopy).
- **FR-005**: Each grade band section MUST display a summary count at the top (e.g., "V4-V6: 12 curated problems, 4 classics") so climbers can quickly assess density.
- **FR-006**: The V7-V10+ band MUST include conditions notes for each problem — whether it needs dry rock, cold temps for friction, specific wind conditions, or is climbable in a wider range of conditions.
- **FR-007**: All problem data MUST cite its source (Mountain Project, guidebook name/edition, local beta) and flag unverified entries with `[UNVERIFIED]` per Constitution Principle VI.
- **FR-008**: A cross-area sheltered classics summary MUST exist listing sheltered quality problems across all areas, organized by grade band, so rain-day decisions can be made from a single document.
- **FR-009**: A cross-area hard-climbing summary MUST exist listing all V7-V10+ problems across all areas with area/sector, grade, style, shelter status, and quality indicator.
- **FR-010**: Landing quality MUST use a consistent rating system across all areas: "Flat" (pad-friendly, level ground), "Uneven" (requires careful pad placement, talus or slope), "Poor" (dangerous landing, spotter recommended, multiple pads needed).
- **FR-011**: Each problem cluster document MUST link back to its parent area profile from Feature 001.
- **FR-012**: For areas with distinct sectors (Gorge Boulders), problems MUST be organized by sector within each grade band so climbers can find problems near each other.

### Key Entities

- **Problem**: A single boulder problem. Attributes: name, V-grade, style, shelter status, shelter type, landing quality, descriptive location (text directions to find the boulder — no GPS), sector, classic marker, conditions notes, Mountain Project link (where available), source, verified status.
- **Problem Cluster**: A curated grouping of problems for one grade band at one area. Contains problems, a summary count, and a classic count.
- **Cross-Area Summary**: An aggregated view of problems across all areas, filtered by a specific criterion (sheltered classics, hard climbing).

## Assumptions

- Problem data will come from the same sources as Feature 001: Mountain Project, guidebooks, NRAC, and community knowledge. Web access limitations may apply — all unverified data flagged per Constitution Principle VI.
- "Curated" means quality over exhaustive inventory. For well-documented areas, select the best problems per grade band. For sparsely documented areas, include all known problems.
- Problem cluster documents are separate files from the Feature 001 area profiles (avoids making profiles too long; allows independent reference).
- The number of problems per area varies significantly: Summersville Lake may have 50+ curated problems; Gorge Boulders may have 15-20.
- Classic/recommended designations are subjective and based on community consensus. When sources disagree, note the discrepancy.
- This feature produces phone-first Markdown documents following the same conventions as Feature 001.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A climber can identify 3+ quality problems at their grade level within 30 seconds of opening an area's problem cluster document.
- **SC-002**: During active rain, a climber can find all sheltered problems across all areas within 60 seconds using the cross-area sheltered classics summary.
- **SC-003**: Each curated problem entry contains enough information (name, grade, style, shelter, landing) to make a go/no-go decision without consulting an external source.
- **SC-004**: V10 climbers can build a prioritized week-long tick list from the cross-area hard-climbing summary in under 5 minutes.
- **SC-005**: 100% of curated problem entries cite at least one source or are flagged `[UNVERIFIED]`.
- **SC-006**: Problem cluster documents render readably on a phone screen with tables fitting within horizontal scroll.
