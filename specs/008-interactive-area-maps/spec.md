# Feature Specification: Interactive Area Maps

**Feature Branch**: `008-interactive-area-maps`
**Created**: 2026-02-11
**Status**: Draft
**Input**: User description: "Interactive Area Maps from the vision.md — GeoJSON maps of boulder fields, trails, town amenities. Embedded in area READMEs for GitHub rendering."

## Clarifications

### Session 2026-02-11

- Q: What GeoJSON embed method should maps use — inline code blocks in Markdown, linked separate files, or inline-only? → A: Inline GeoJSON code blocks as the primary embed (renders maps in-place in profile documents), with `maps/` directory holding canonical `.geojson` copies for standalone viewing/download.

## User Scenarios & Testing *(mandatory)*

### User Story 1 — Regional Overview Map (Priority: P1)

The trip group opens the repo on their phone or laptop and immediately sees a single map showing all bouldering areas, trail systems, and the Fayetteville base town in relation to each other. They can visually understand drive distances and spatial relationships (e.g., "Summersville Lake is north, Arrowhead is right in town, the Gorge is between them"). This replaces the mental model they'd otherwise have to build from reading drive-time text in each profile.

**Why this priority**: Spatial orientation is the foundational value — every subsequent map (area sectors, trails, town) builds on understanding where things are relative to each other. This is the MVP: one map, all key locations.

**Independent Test**: Open `maps/README.md` on GitHub. A rendered map displays with labeled markers for all 3 bouldering areas, all 3 trail systems, and Fayetteville town center. Clicking a marker shows the location name and a link to its profile document.

**Acceptance Scenarios**:

1. **Given** the maps/README.md is open on GitHub, **When** the user views the embedded map, **Then** they see markers for Summersville Lake, Meadow River, Gorge Boulders, Arrowhead Trails, Summit Bechtel Reserve, Babcock State Park, and Fayetteville town center — all on a single map
2. **Given** a map marker is clicked/tapped, **When** the popup appears, **Then** it shows the location name, category (bouldering / trails / town), drive time from Fayetteville, and a link to the relevant profile document
3. **Given** the user is viewing the map on a phone, **When** they pinch-zoom or pan, **Then** the map remains usable and markers remain legible

---

### User Story 2 — Bouldering Area Sector Maps (Priority: P2)

For each bouldering area, the user sees a map showing individual sectors, parking locations, and trailhead/approach start points within that area. This helps with on-the-ground navigation — "which direction do I walk from the parking lot to reach Long Point sector?"

**Why this priority**: Once users understand regional geography (US1), the next need is within-area navigation. Bouldering is the primary trip activity, so area sector maps come before trail maps.

**Independent Test**: Open `areas/summersville-lake.md` on GitHub. A rendered map displays with markers for each sector (Long Point, Pirates Cove, Orange Oswald Wall Area), parking areas, and approach trailheads. Repeat for Meadow River and Gorge Boulders.

**Acceptance Scenarios**:

1. **Given** an area profile (e.g., `areas/summersville-lake.md`) is open on GitHub, **When** the user views the embedded map, **Then** they see markers for each sector, each parking area, and each approach trailhead within that area
2. **Given** a sector marker is clicked, **When** the popup appears, **Then** it shows the sector name, rain resilience rating, grade density summary, and shelter availability
3. **Given** the map is viewed after rain, **When** the user needs to find sheltered sectors, **Then** markers visually distinguish sheltered sectors from exposed sectors

---

### User Story 3 — Trail System Maps (Priority: P3)

For each mountain biking trail system, the user sees a map showing the trail network, parking, and access points. This helps answer "where do I park and where do the trails go?" for each riding destination.

**Why this priority**: Mountain biking is a first-class activity but secondary to bouldering in trip priority. Trail maps complete the spatial picture for all outdoor activities.

**Independent Test**: Open `trails/arrowhead.md` on GitHub. A rendered map displays with the trail network area, parking location, and access point. Repeat for Summit Bechtel and Babcock.

**Acceptance Scenarios**:

1. **Given** a trail profile (e.g., `trails/arrowhead.md`) is open on GitHub, **When** the user views the embedded map, **Then** they see the trail system area, parking location(s), and access road
2. **Given** the trail map for Summit Bechtel is viewed, **When** the user checks the marker, **Then** it includes the access note about calling ahead and the phone number

---

### User Story 4 — Town Amenities Map (Priority: P4)

The user sees a map of Fayetteville showing restaurant, brewery, gear shop, and grocery/gas locations curated from the rest-day guide (Feature 005). This helps with "where is Cathedral Cafe relative to Bridge Brew Works?" for planning rest days and evening outings.

**Why this priority**: Town navigation is lower urgency than crag/trail navigation (users can use Google Maps for town), but having curated pins for trip-relevant spots adds convenience and keeps everything in one repo.

**Independent Test**: Open `maps/town.geojson` on GitHub (or the town section in `maps/README.md`). A rendered map displays with markers for all curated dining, brewery, gear shop, and supply locations from the rest-day guide.

**Acceptance Scenarios**:

1. **Given** the town amenities map is viewed on GitHub, **When** the user scans the markers, **Then** they see pins for all dining picks (Cathedral Cafe, Pies & Pints, Secret Sandwich Society, The Handle Bar, Firecreek BBQ), breweries (Bridge Brew Works, Southside Junction Tap House), Water Stone Outdoors, Walmart, and Sheetz
2. **Given** a restaurant marker is clicked, **When** the popup appears, **Then** it shows the venue name, type, and a note about February hours being [UNVERIFIED]

---

### Edge Cases

- What happens when a location's GPS coordinates are inaccurate? All coordinates should be flagged `[UNVERIFIED]` and sourced where possible (Google Maps, NPS, AllTrails)
- What happens when GitHub changes GeoJSON rendering behavior? Maps must degrade gracefully — if rendering fails, the raw GeoJSON file remains browsable as structured data, and the profile documents still contain all textual information
- What happens when a user views the map offline? GeoJSON maps require GitHub's renderer and an internet connection. A note should direct users to download offline maps (Google Maps) for field use
- What happens for areas where precise sector boundaries are unknown? Use point markers (pins) rather than polygon boundaries. Only use polygons where boundaries are well-defined and sourced

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: Each bouldering area profile (`areas/*.md`) MUST embed an inline GeoJSON code block rendering a map of its sectors, parking areas, and approach trailheads directly in the document
- **FR-002**: Each trail system profile (`trails/*.md`) MUST embed an inline GeoJSON code block rendering a map of the trail system area, parking, and access points directly in the document
- **FR-003**: A regional overview map MUST show all bouldering areas, trail systems, and Fayetteville town center on a single map with labeled markers
- **FR-004**: A town amenities map MUST show curated dining, brewery, gear shop, and supply locations from the rest-day guide (Feature 005)
- **FR-005**: Every map marker MUST include at minimum: location name, category, and one contextual detail (drive time, rain resilience, or venue type)
- **FR-006**: All GPS coordinates MUST be sourced or flagged `[UNVERIFIED]` per constitution Principle VI
- **FR-007**: Maps MUST render natively on GitHub without requiring external tools, plugins, or build steps — using GitHub's built-in GeoJSON rendering
- **FR-008**: Maps MUST be usable on mobile devices (readable markers, zoomable, no horizontal scroll issues)
- **FR-009**: Sheltered vs. exposed sectors MUST be visually distinguishable on bouldering area maps (via marker properties or descriptions) to support rain-day decision-making per constitution Principle V
- **FR-010**: Canonical `.geojson` files MUST be stored in a dedicated `maps/` directory for standalone viewing and download, in addition to the inline code blocks embedded in profile documents
- **FR-011**: Each map file MUST include a text description or legend in its parent Markdown document explaining what the markers represent
- **FR-012**: No map content may reference sport climbing, trad climbing, or route climbing per constitution Principle II

### Key Entities

- **Map Point**: A geographic location with coordinates (lat/lng), name, category (bouldering-area / trail-system / sector / parking / trailhead / dining / brewery / gear-shop / supply), and contextual metadata (drive time, rain resilience, grade density, shelter status, venue type)
- **Map File**: A GeoJSON file containing a FeatureCollection of Map Points for a specific scope (regional overview, single area, single trail system, town)
- **Map Embed**: An inline ` ```geojson ` code block in a Markdown document that GitHub renders as an interactive map in-place, providing zero-click map access within profile documents

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: Users can identify the spatial relationship between any two locations (e.g., Summersville Lake and Arrowhead Trails) within 10 seconds of opening the regional overview map
- **SC-002**: Users can find parking and sector locations for any bouldering area within 15 seconds of opening that area's profile
- **SC-003**: 100% of GPS coordinates are either sourced or flagged `[UNVERIFIED]`
- **SC-004**: 100% of GeoJSON files render as interactive maps on GitHub without external dependencies
- **SC-005**: Zero references to sport climbing, trad climbing, or route climbing appear in any map file or map description
- **SC-006**: All map markers include at least a name and one contextual detail (no bare/unlabeled pins)
- **SC-007**: Every map file has a corresponding text legend in its parent Markdown document

## Scope

### In Scope

- GeoJSON point markers for all bouldering area sectors, parking lots, trailheads, trail systems, and curated town amenities
- Embedding maps in existing area profiles, trail profiles, and a new maps/ directory
- Marker metadata (name, category, contextual notes) rendered in GitHub popups
- Regional overview map and per-area/per-trail detail maps

### Out of Scope

- Custom web application or JavaScript map viewer (GitHub-native rendering only)
- Real-time data (weather, trail conditions, live occupancy)
- Turn-by-turn navigation or routing
- Polygon boundaries for climbing areas or trail networks (point markers only, unless well-sourced boundaries exist)
- Satellite/aerial imagery layers (GitHub GeoJSON renders on default basemap)
- Maps for locations outside the New River Gorge trip area

## Assumptions

1. GitHub renders inline ` ```geojson ` code blocks as interactive maps within Markdown documents, and renders `.geojson` files as maps when viewed directly — both are current GitHub features expected to remain stable
2. Point markers (not polygons or lines) are the primary geometry type, as precise sector boundaries and trail routes are not available from verified sources
3. GPS coordinates will be sourced from Google Maps, NPS resources, and AllTrails where available, with remaining coordinates flagged `[UNVERIFIED]`
4. GeoJSON marker popups on GitHub support basic text properties (name, description) but not rich HTML or images
5. The `maps/` directory is a new addition to the repo structure — no existing map files need to be migrated
6. Town amenity locations are curated from Feature 005 (Rest-Day Guide) — no new venue research is needed
7. All area sectors referenced in Features 001-002 will have corresponding map markers
8. Trail system maps show the general trail area and parking — not individual trail routes (which would require verified GPS tracks)

## Dependencies

- **Feature 001** (Primary Bouldering Areas): Provides sector names, parking locations, and approach descriptions for area maps
- **Feature 002** (Problem Clusters): Provides sector-level detail for marker metadata
- **Feature 003** (Mountain Biking Trails): Provides trail system locations, parking, and access information
- **Feature 004** (Conditions & Weather): Provides rain resilience ratings and shelter data for marker properties
- **Feature 005** (Rest-Day Guide): Provides curated town amenity list for town map
- **Feature 006** (Logistics & Access): Provides parking GPS coordinates and drive times
