# Data Model: Interactive Area Maps

**Feature**: 008-interactive-area-maps | **Date**: 2026-02-11

## Entities

### GeoJSON Feature (Map Point)

A single geographic point on a map, conforming to GeoJSON RFC 7946 with Mapbox simplestyle-spec v1.1.0 properties.

| Field | Required | Type | Description | Example |
|-------|----------|------|-------------|---------|
| type | Yes | string | Always "Feature" | "Feature" |
| geometry.type | Yes | string | Always "Point" | "Point" |
| geometry.coordinates | Yes | [lng, lat] | WGS 84 coordinates (longitude first!) | [-81.0785, 38.0670] |
| properties.title | Yes | string | Popup heading — location name | "Endless Wall Trailhead" |
| properties.description | Yes | string | Popup body — contextual detail | "Parking for Endless Wall sector. 5-15 min approach." |
| properties.marker-color | Yes | hex string | Category color per color scheme | "#e74c3c" |
| properties.marker-size | Yes | string | "small", "medium", or "large" | "large" |
| properties.marker-symbol | No | string | Maki icon ID (optional, may not render) | "" |
| properties.category | Yes | string | Internal category tag | "sector" |

**Validation rules**:
- Coordinates MUST be [longitude, latitude] order (GeoJSON standard)
- All coordinates MUST be flagged [UNVERIFIED] in the description unless sourced from official NPS/USACE data
- `title` is required (no bare markers)
- `description` MUST include at least one contextual detail
- `marker-color` MUST match the color scheme defined in plan.md

### GeoJSON FeatureCollection (Map File)

A collection of GeoJSON Features representing a complete map for a specific scope.

| Field | Required | Type | Description | Example |
|-------|----------|------|-------------|---------|
| type | Yes | string | Always "FeatureCollection" | "FeatureCollection" |
| features | Yes | array | Array of GeoJSON Feature objects | [...] |

**Validation rules**:
- Must be valid GeoJSON per RFC 7946
- File size MUST be under 10 MB (GitHub rendering limit)
- Feature count should be under 750 (GitHub clustering threshold)
- File MUST render correctly when viewed directly on GitHub

### Map Legend Entry

A row in the text legend table that accompanies each inline map in a Markdown document.

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| Marker Color | Yes | Visual color indicator + name | Red |
| Category | Yes | What this marker type represents | Bouldering sector |
| Count | Yes | How many markers of this type | 3 |
| Notes | No | Additional context | Shelter status in description |

**Validation rules**:
- Every marker category present in the inline map MUST have a legend entry
- Legend MUST appear immediately above or below the inline geojson code block

## Category Color Scheme

| Category | Hex | Use For |
|----------|-----|---------|
| sector | #e74c3c | Bouldering area sectors |
| trail-system | #2ecc71 | Mountain biking trail systems |
| parking | #95a5a6 | Parking lots and pulloffs |
| trailhead | #f39c12 | Approach start points |
| dining | #9b59b6 | Restaurants and cafes |
| brewery | #f1c40f | Breweries and taphouses |
| gear-shop | #3498db | Outdoor gear shops |
| supply | #7f8c8d | Grocery stores, gas stations |
| town | #1abc9c | Town center / reference point |
| bouldering-area | #e74c3c | Area-level marker on overview map |

## Relationships

```
Map File (FeatureCollection) → contains → GeoJSON Features (Map Points)
Map File → embedded in → Markdown Document (inline code block)
Map File → stored in → maps/ directory (canonical .geojson file)
GeoJSON Feature → references → Area Profile (via description links)
GeoJSON Feature → references → Trail Profile (via description links)
Map Legend Entry → describes → GeoJSON Feature categories in parent document
```
