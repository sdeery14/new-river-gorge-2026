# Data Model: Primary Bouldering Areas

**Feature**: 001-bouldering-areas
**Date**: 2026-02-10

This document defines the standardized structure for area profile documents. Every area profile MUST follow this schema to satisfy FR-002 (consistent structure) and Constitution Principle I (decision-support first).

---

## Entity: Bouldering Area

Each area profile is a Markdown document with the following sections in order.

### Quick Reference Header (required)

A table at the very top of the document — must fit on one phone screen.

| Field | Type | Example |
|-------|------|---------|
| Area name | Text | Meadow River |
| Drive time | Text | ~30 min from Fayetteville |
| Rain resilience | Good / Fair / Poor | Good |
| Rock type | Text | Nuttall sandstone |
| Estimated problems | Number or range | ~50-100 |
| Land manager | Text | National Forest [UNVERIFIED] |
| Google Maps link | URL | [Parking](https://maps.google.com/...) |
| Route summary | Text | US-19 N to WV-20 S |

### Grade Band Table (required)

Three-column table per FR-005.

| Field | Description |
|-------|-------------|
| V0-V3 (Beginner) | Count or density indicator + brief style note |
| V4-V6 (Intermediate) | Count or density indicator + brief style note |
| V7-V10+ (Hard) | Count or density indicator + brief style note |

Density indicators when exact counts are unavailable: Many (20+), Some (5-19), Few (1-4), None (0).

### Group Suitability (required)

Per FR-008. One-paragraph assessment answering:
- Does this area work for all three ability bands?
- Which band will run out of problems first?
- Is this better for a full day or a half day?

### Weather Resilience (required)

Per FR-004. Structured as:

| Field | Description |
|-------|-------------|
| Rating | Good / Fair / Poor |
| Shelter | Description of natural shelter (overhangs, canopy, gorge walls) |
| Seepage | Where water migrates after rain |
| Drying estimate | Time to climbable after rain stops (by face angle) |
| Wind exposure | Sheltered / Moderate / Exposed |
| Wet-weather verdict | Can you climb here during active rain? If so, what type of problems? |

### Approach & Access (required)

Per FR-010 and FR-011.

| Field | Description |
|-------|-------------|
| Google Maps link | Tappable link to primary parking |
| Route summary | Short text (e.g., "US-19 N, 25 min") |
| Parking | Formal lot / pulloff / gated. Capacity estimate. |
| Approach | Distance, time, elevation change, trail quality |
| February hazards | Ice, snow, mud, steep sections. Microspikes needed? |
| Winter access | Are roads/lots maintained? Gated? Plowed? |

### Land Management & Regulations (required)

Per FR-009.

| Field | Description |
|-------|-------------|
| Land manager | NPS / USACE / USFS / State / Private |
| Crash pads | Permitted? |
| Chalk | Permitted? |
| Seasonal closures | Any affecting February? |
| Fees | Any? |
| Special notes | Wire brush restrictions, group size, etc. |

### Climbing Style (required)

Brief description of predominant styles: overhanging, vertical, slab, roof, compression, arete. What type of climbing should the group expect?

---

## Entity: Sector (sub-entity of Bouldering Area)

Per the clarification session: where distinct sectors exist within an area, include per-sector breakdowns. Not all areas have sectors.

### Sector Quick Reference

| Field | Type |
|-------|------|
| Sector name | Text |
| Rain resilience | Good / Fair / Poor |
| Grade band breakdown | V0-V3 / V4-V6 / V7-V10+ counts |
| Shelter notes | Brief description |
| Approach from main parking | Additional time/distance |

---

## Entity: Area Overview (README.md)

The overview document contains ONE summary table covering all areas.

### Summary Table Schema

Per FR-003, columns are:

| Column | Description |
|--------|-------------|
| Area | Area name (linked to profile) |
| Drive | Time from Fayetteville |
| Rain Resilience | Good / Fair / Poor |
| V0-V3 | Density indicator |
| V4-V6 | Density indicator |
| V7-V10+ | Density indicator |
| Best For | One-line suitability note |

### Additional Overview Content

- Nuttall sandstone drying time reference table (one instance, not per-area)
- NPS bouldering regulations summary (one instance, applies to gorge sectors)
- Quick decision guide: "If it's raining, go to X. If it's dry, go to Y."
