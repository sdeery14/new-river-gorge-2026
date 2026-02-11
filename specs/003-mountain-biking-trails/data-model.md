# Data Model: Mountain Biking Trails

**Feature**: 003-mountain-biking-trails

---

## Entity: Trail System

A named collection of trails at a single location. Each system gets its own file in `trails/`.

### Attributes

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| name | string | Yes | Trail system name (e.g., "Arrowhead Trails") |
| location | string | Yes | Town/area and state |
| drive_time | string | Yes | Drive time from Fayetteville (e.g., "~5-10 min") |
| gps | string | Yes | Approximate GPS coordinates for trailhead/parking |
| total_mileage | string | Yes | Approximate total trail mileage (e.g., "~10-13 mi") |
| trail_count | integer | Yes | Number of individual named trails |
| difficulty_range | string | Yes | IMBA range (e.g., "Green Circle — Black Diamond") |
| trail_style | string | Yes | Primary style (e.g., "Cross-country, flow trail, stacked loop") |
| surface | string | Yes | Primary surface type (e.g., "Dirt singletrack, rocky/rooty") |
| land_manager | string | Yes | Who manages the land (e.g., "Active SWV", "WV State Parks") |
| fees | string | Yes | Cost or "Free" |
| february_viability | enum | Yes | One of: Good, Fair, Poor, Uncertain |
| february_notes | string | Yes | Detailed February conditions: freeze/thaw, mud, ice, closures |
| tier | enum | Yes | One of: Primary, Conditional, Supplementary |
| parking | string | Yes | Parking description (location, capacity, surface) |
| access_notes | string | No | February-specific access warnings (road closures, gates, etc.) |
| condition_sources | list[string] | Yes | Where to check real-time conditions (Trailforks, phone numbers, etc.) |
| google_maps_link | string | No | Google Maps link to trailhead |
| source | string | Yes | Data source(s) |
| verified | boolean | Yes | Whether data has been verified (all currently false) |

### Relationships

- Contains 1..N **Trail** entities
- Pairs with 1..N **Bouldering Area** entities (via Bouldering Pairing)

---

## Entity: Trail

An individual named trail within a system.

### Attributes

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| name | string | Yes | Trail name |
| difficulty | enum | Yes | IMBA rating: Green Circle, Blue Square, Black Diamond, Double Black Diamond |
| distance | string | Yes | Trail distance (e.g., "2.3 mi") |
| elevation_gain | string | Yes | Total elevation gain (e.g., "350 ft") |
| estimated_ride_time | string | Yes | Estimated ride time at intermediate pace |
| surface | string | Yes | Surface type (e.g., "Dirt singletrack", "Gravel road") |
| features | string | No | Notable features (e.g., "Berms, tabletop jumps, rock garden") |
| february_notes | string | No | Trail-specific February condition notes |
| source | string | Yes | Data source |
| verified | boolean | Yes | Whether data has been verified |

### Relationships

- Belongs to exactly 1 **Trail System**

### Validation Rules

- difficulty MUST be one of the 4 IMBA ratings
- distance MUST include unit (mi or km)
- elevation_gain MUST include unit (ft or m)

---

## Entity: Bouldering Pairing

A suggested combination of trail system + bouldering area for a single day.

### Attributes

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| trail_system | ref(Trail System) | Yes | Which trail system |
| bouldering_area | string | Yes | Bouldering area name (from Feature 001) |
| trail_to_boulder_drive | string | Yes | Drive time between trail and boulder parking |
| total_day_drive | string | Yes | Total driving for the day (home → trail → boulder → home) |
| suggested_schedule | string | Yes | "Ride AM + Boulder PM" or "Boulder AM + Ride PM" |
| weather_scenario | string | No | When this pairing works best (e.g., "Rain clearing by afternoon") |
| notes | string | No | Additional pairing notes |

### Relationships

- References 1 **Trail System**
- References 1 **Bouldering Area** (from Feature 001, `areas/` directory)

---

## Entity: Rental Shop

A bike rental business near Fayetteville.

### Attributes

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| name | string | Yes | Shop name |
| location | string | Yes | Address or area description |
| phone | string | No | Phone number |
| website | string | No | Website URL |
| price_range | string | Yes | Daily rental price range (e.g., "$40-75/day hardtail") |
| bike_types | string | Yes | Types available (e.g., "Hardtail, full suspension") |
| hours | string | Yes | Operating hours (note if seasonal) |
| february_available | enum | Yes | One of: Yes, Likely, Unlikely, Unknown |
| reservation_required | string | Yes | Whether advance booking is needed |
| notes | string | No | Additional info (guide services, etc.) |
| source | string | Yes | Data source |
| verified | boolean | Yes | Whether data has been verified |

### Relationships

- Standalone entity (no foreign keys)

---

## Document Schema

### Trail Overview (`trails/README.md`)

| Section | Content | Maps To |
|---------|---------|---------|
| Summary table | All systems with key attributes | Trail System (summary) |
| Quick decision guide | Condition-based recommendations | Trail System.february_viability |
| Bouldering pairings | Ride+boulder day combinations | Bouldering Pairing |
| Bike rentals | Shop listings | Rental Shop |
| Sources | Citations and verification notes | All entities.source |

### Trail System Profile (`trails/{system-name}.md`)

| Section | Content | Maps To |
|---------|---------|---------|
| Header banner | Name, drive time, viability, land manager | Trail System (top-level) |
| Trail table | Individual trails with stats | Trail |
| February conditions | Detailed winter assessment | Trail System.february_notes |
| Access & parking | Logistics | Trail System.parking, access_notes |
| Condition sources | Where to check real-time status | Trail System.condition_sources |
| Sources | Citations | Trail System.source |
