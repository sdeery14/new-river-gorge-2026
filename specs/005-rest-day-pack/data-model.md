# Data Model: Rest-Day & Low-Energy Pack

**Feature**: 005-rest-day-pack | **Date**: 2026-02-11

## Entities

### Activity

The top-level entity representing any rest-day option. Every item in the guide is an Activity.

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| name | text | Yes | Venue or activity name |
| category | enum | Yes | One of: dining, brewery, hot-springs, hiking, sightseeing, indoor, grocery |
| energy_tier | enum | Yes | One of: Low, Medium, High |
| location | text | Yes | Town name (Fayetteville, Oak Hill, etc.) |
| drive_time | text | Yes | Drive time from Fayetteville (e.g., "In town", "~15 min") |
| duration | text | Yes | Estimated time to spend (e.g., "1-2 hrs", "30 min") |
| indoor_outdoor | enum | Yes | One of: Indoor, Outdoor, Both |
| cost | text | Yes | Price indicator: $, $$, $$$, or Free |
| february_available | enum | Yes | One of: Yes, Likely, Seasonal (verify), Closed |
| reservation_required | boolean | Yes | Whether advance booking is needed |
| source | text | Yes | Citation for hours/pricing claims, or `[UNVERIFIED]` |

### Venue (extends Activity for dining, brewery, grocery)

Additional fields for business-type activities.

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| address | text | Yes | Street address |
| phone | text | Recommended | Phone number for reservations or verification |
| winter_hours | text | Yes | Operating hours in February (or `[UNVERIFIED]`) |
| cuisine_or_type | text | Yes | Cuisine type, beer style, or store type |
| price_range | enum | Yes | $, $$, or $$$ per the scale in spec ($ <$15, $$ $15-30, $$$ >$30) |
| group_suitability | text | Yes | Max party size, "call ahead", or general suitability note |

### Brewery (extends Venue)

Additional fields specific to brewery profiles (FR-004).

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| food_menu | text | Yes | Description of food availability (kitchen, food truck, none) |
| outdoor_seating | text | Yes | Whether outdoor seating exists and February relevance |
| atmosphere | text | Yes | Brief description of vibe/setting |
| beer_style | text | Yes | Brewery focus or notable beers |

### Trail (extends Activity for hiking, sightseeing)

Additional fields for hiking and sightseeing entries (FR-006).

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| distance | text | Yes | Round-trip distance (e.g., "2.2 miles RT") |
| elevation_gain | text | Recommended | Elevation gain if applicable |
| difficulty | enum | Yes | One of: Easy, Easy-Moderate, Moderate, Strenuous |
| february_conditions | text | Yes | Trail conditions note or `[UNVERIFIED]` |
| trailhead | text | Recommended | Trailhead name or location |
| features | text | Yes | Brief description of what makes this trail notable |

### Grocery (extends Venue)

Additional fields for grocery store entries (FR-008).

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| selection_quality | text | Yes | e.g., "Full-service supermarket", "Regional grocery", "Convenience" |
| pickup_available | boolean | Recommended | Whether online order + pickup is offered |

### Sample Itinerary

A pre-built day plan combining activities from the reference listings (FR-013).

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| name | text | Yes | Itinerary title (e.g., "Low-Energy Rainy Day") |
| energy_tier | enum | Yes | Target energy level: Low, Medium, or High |
| activities | list | Yes | Ordered list of activities with approximate times |
| weather_assumption | text | Yes | Weather scenario this itinerary is designed for |
| total_duration | text | Yes | Approximate total time for the itinerary |

## Relationships

```
Activity (base)
├── Venue (dining, brewery, grocery)
│   ├── Brewery (extends Venue with beer-specific fields)
│   └── Grocery (extends Venue with selection fields)
└── Trail (hiking, sightseeing)

Sample Itinerary
└── references multiple Activities by name
```

## Validation Rules

- Every Activity MUST have all required fields populated (no blank cells in the quick-reference table)
- Every Venue MUST have winter_hours populated or flagged `[UNVERIFIED]`
- Every cost claim MUST cite a source or be flagged `[UNVERIFIED]`
- Every Trail MUST have february_conditions populated (even if `[UNVERIFIED]`)
- Energy tier assignment MUST follow the definitions in FR-002:
  - Low: Minimal physical effort
  - Medium: Moderate effort (hikes under 3 miles)
  - High: Significant effort (hikes 3+ miles)
- Quick-reference table MUST contain every Activity in the guide (no orphaned listings)
- Sample itineraries MUST only reference Activities that appear in the guide listings
