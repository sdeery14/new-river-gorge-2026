# Feature Specification: Rest-Day & Low-Energy Pack

**Feature Branch**: `005-rest-day-pack`
**Created**: 2026-02-11
**Status**: Draft
**Input**: User description: "feature 005 | Rest-Day & Low-Energy Pack from vision.md"

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Quick Rest-Day Decision (Priority: P1)

The group wakes up and collectively decides today is a rest day — either because they're physically spent, the weather is terrible for climbing, or both. They need to open one document on a phone and within 60 seconds identify what to do with their day, filtered by how much energy the group has left.

**Why this priority**: Rest days happen on every trip. The core value of this feature is rapid decision-support when the group is tired and unmotivated to research. Without this, the group wastes the morning debating options on their phones individually.

**Independent Test**: Can be fully tested by opening the document on a phone, scanning the quick-reference table, and selecting an energy-appropriate activity within 60 seconds.

**Acceptance Scenarios**:

1. **Given** a group member opens the rest-day guide on their phone, **When** they look at the quick-reference table, **Then** they can identify at least 3 activity options within their energy tier in under 60 seconds.
2. **Given** a rainy February day with low group energy, **When** a member scans the guide, **Then** they find at least 2 indoor or low-energy options that don't require good weather.
3. **Given** a rest day with mixed energy levels in the group, **When** they consult the energy-tier breakdown, **Then** they can identify activities that accommodate splitting into subgroups by energy level.
4. **Given** a tired group that doesn't want to assemble their own plan, **When** they scroll to the sample itineraries, **Then** they find a pre-built day plan matching their energy level that they can follow without further decisions.

---

### User Story 2 - Dining & Brewery Planning (Priority: P2)

A group member wants to find a place to eat or drink in Fayetteville. They need to quickly see what's available, what kind of food/drink it is, approximate price range, and whether it's open in February (winter hours). This is the most frequently used rest-day information — the group eats out every night regardless of whether it's a climbing day or rest day.

**Why this priority**: Dining happens every single day of the trip, not just rest days. This is the highest-frequency use case in the feature, but ranks P2 because the quick-reference table (P1) is the entry point that makes dining info discoverable.

**Independent Test**: Can be fully tested by looking up dinner options for a group of 5-6 on a Tuesday in February and confirming hours, cuisine type, and price range are present for each listing.

**Acceptance Scenarios**:

1. **Given** the group wants dinner, **When** a member checks the dining section, **Then** they find a list of restaurants with cuisine type, price range, and winter hours for each.
2. **Given** a group of 6 looking for a brewery after climbing, **When** they check the brewery listings, **Then** they find at least 2 breweries with info on food availability, group seating, and winter hours.
3. **Given** a member with dietary restrictions, **When** they scan the dining list, **Then** cuisine types are clear enough to identify likely-compatible options without further research.

---

### User Story 3 - Medium-Energy Activity Selection (Priority: P3)

It's a partial rest day — some members want to do something active but not climb. They want to find a casual hike, scenic viewpoint, or sightseeing activity that requires moderate effort. They need to know the basics: how long it takes, how strenuous it is, and whether February conditions make it viable.

**Why this priority**: Medium-energy activities fill the gap between "lying on the couch" and "climbing all day." They're especially valuable on travel days, roster-change day (Wednesday), or when weather clears in the afternoon.

**Independent Test**: Can be fully tested by selecting a medium-energy activity from the guide and confirming it includes duration, effort level, and February-specific notes.

**Acceptance Scenarios**:

1. **Given** a member wants a casual hike, **When** they check the medium-energy section, **Then** they find options with estimated duration, difficulty, and February trail conditions noted.
2. **Given** the afternoon clears up after morning rain, **When** a member scans medium-energy options, **Then** they can identify an activity doable in 2-3 hours that doesn't require dry rock.
3. **Given** a scenic viewpoint is listed, **When** a member reads its entry, **Then** they find directions, parking info, and any February access restrictions.

---

### User Story 4 - Roster-Change Day Planning (Priority: P4)

Wednesday is the mid-week roster transition — one member departs and another arrives. The group needs activity ideas that work around travel logistics: airport/meetup timing, smaller group size during the transition window, and social activities for welcoming the new arrival.

**Why this priority**: This is a specific one-day scenario, but it affects logistics and social dynamics. A well-planned roster-change day prevents wasted time and awkward "what do we do now?" moments.

**Independent Test**: Can be fully tested by consulting the guide for Wednesday-specific suggestions and confirming it addresses the transition logistics.

**Acceptance Scenarios**:

1. **Given** Wednesday arrives with one member departing in the morning and another arriving in the afternoon, **When** the group checks the rest-day guide, **Then** they find suggestions that account for the split-day logistics.
2. **Given** the new arrival wants to meet the group for dinner, **When** they check the dining section, **Then** they can identify a welcoming group-friendly dinner spot.

---

### Edge Cases

- What happens when a listed restaurant or business is closed for the season or has reduced February hours? Each listing must note winter/February operating status and flag seasonal closures.
- How does the guide handle activities that require reservations or advance booking? Any activity requiring advance booking must flag this prominently.
- What if the group wants to split — some rest, some climb? The energy-tier system must support subgroup planning without requiring the full group to commit to one activity.
- What happens on arrival day (Saturday) or departure day (Saturday) when time is limited? Travel-day-friendly activities should be flagged as such.

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: The guide MUST include a quick-reference summary table at the top listing all rest-day activities with: activity name, energy tier, estimated duration, indoor/outdoor, cost indicator, and February availability.
- **FR-002**: All activities MUST be categorized into three energy tiers:
  - **Low Energy**: Minimal physical effort (dining, breweries, hot springs, indoor lounging, shopping)
  - **Medium Energy**: Moderate physical effort (casual hikes under 3 miles, scenic viewpoints, town exploration)
  - **High Energy**: Significant effort but not climbing (longer hikes 3+ miles, mountain biking crossover suggestions referencing Feature 003)
- **FR-003**: Each restaurant and brewery listing MUST include: name, location (Fayetteville or nearby town with drive time), cuisine type or beer style, approximate price range ($ / $$ / $$$), group suitability (max party size or "call ahead" note), and February/winter hours. Coverage area extends to Fayetteville and nearby towns within a 20-minute drive.
- **FR-004**: The guide MUST include at least 2 brewery profiles (Bridge Brew Works, Fayetteville Brewing Co.) with details on food menu availability, outdoor seating (February relevance), and atmosphere.
- **FR-005**: The guide MUST include hot springs options within reasonable driving distance of Fayetteville, with: name, distance/drive time from Fayetteville, cost, reservation requirements, and February availability.
- **FR-006**: Each hiking/sightseeing entry MUST include: trail or site name, distance/duration, difficulty, February trail conditions or access notes, and brief description.
- **FR-007**: The guide MUST include indoor activity options for severe-weather days (e.g., gym, indoor recreation, museums, local shops).
- **FR-008**: The guide MUST include a brief grocery section listing key stores within the 20-minute coverage area, with: store name, location, drive time from Fayetteville, hours, and a note on selection quality (e.g., full-service vs. convenience).
- **FR-009**: Each activity listing MUST flag whether advance reservation or booking is required.
- **FR-010**: The guide MUST note roster-change day (Wednesday) as a natural rest-day candidate and suggest activities that accommodate the transition logistics.
- **FR-011**: All claims about business hours, pricing, and availability MUST cite sources; unverified information MUST be flagged with `[UNVERIFIED]`.
- **FR-012**: The guide MUST be formatted for phone readability: quick-reference table at top, skimmable sections, no table wider than 6 columns.
- **FR-013**: The guide MUST include 2-3 sample rest-day itineraries organized by energy level (e.g., "Low-Energy Rainy Day," "Medium-Energy Afternoon," "High-Energy Active Rest Day"). Each itinerary combines activities from the reference listings into a ready-made day plan with approximate timing.
- **FR-014**: The guide MUST be 100% bouldering-trip context — no sport climbing, trad climbing, or route-climbing references. Hiking and sightseeing are rest-day activities only.

### Key Entities

- **Activity**: A rest-day option with name, energy tier, category (dining / brewery / hot springs / hiking / sightseeing / indoor / grocery), duration, cost, and February availability status.
- **Energy Tier**: A classification (Low / Medium / High) indicating physical effort required, enabling the group to match activities to their collective or individual energy level.
- **Venue**: A specific business or location (restaurant, brewery, hot spring facility) with operating details, group suitability, and seasonal notes.
- **Trail/Viewpoint**: A hiking trail or scenic location with distance, difficulty, February conditions, and access information.

## Clarifications

### Session 2026-02-11

- Q: What is the geographic scope for dining and activities — Fayetteville only, or a broader radius? → A: Fayetteville + nearby towns within a 20-minute drive (Oak Hill, Route 19 corridor, etc.)
- Q: Should the guide include grocery store and self-catering information? → A: Yes — a brief grocery section covering key stores, locations, hours, and selection notes. No detailed meal planning or cooking tips.
- Q: Should the guide include sample rest-day itineraries or remain a pure reference listing? → A: Include 2-3 sample rest-day itineraries organized by energy level (e.g., low-energy rainy day, medium-energy afternoon, high-energy active rest day).

## Assumptions

- **Fayetteville is the base town**: All drive times and directions are relative to Fayetteville, WV. Dining, breweries, indoor options, and other activities cover Fayetteville plus nearby towns within a 20-minute drive (e.g., Oak Hill, Route 19 corridor). Hot springs may extend further (up to 90 minutes).
- **"Reasonable driving distance" for hot springs means under 90 minutes one-way**: The group won't want to spend 3+ hours round-trip driving on a rest day.
- **February hours are winter hours**: Many businesses in small Appalachian towns have reduced winter schedules. The guide assumes winter operating hours apply and flags any businesses that may be closed entirely in February.
- **Group size for dining is 5-6**: Restaurant suitability is assessed for a party of 5-6 unless the roster-change day reduces it.
- **Mountain biking details live in Feature 003**: This guide references Feature 003 for mountain biking as a high-energy rest-day option but does not duplicate trail profiles.
- **Price range uses a simple scale**: $ = under $15/person, $$ = $15-30/person, $$$ = over $30/person.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A group member can identify an energy-appropriate rest-day activity from the quick-reference table within 60 seconds on a phone screen.
- **SC-002**: Every dining and brewery listing includes cuisine/beer style, price range, group suitability, and February hours — no fields left blank or marked "unknown."
- **SC-003**: At least 2 activities are listed per energy tier (Low, Medium, High), providing meaningful choice at every energy level.
- **SC-004**: 100% of business listings cite a source for hours and pricing, or flag the information as `[UNVERIFIED]`.
- **SC-005**: The guide covers at least 6 distinct activity categories (dining, breweries, hot springs, hiking/sightseeing, indoor options, grocery).
- **SC-006**: All hot springs listings include drive time, cost, and reservation requirements — enough information to make a go/no-go decision without further research.
- **SC-007**: The roster-change day (Wednesday) is explicitly addressed with transition-friendly activity suggestions.
