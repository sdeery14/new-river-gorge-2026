# Research: Interactive Area Maps

**Feature**: 008-interactive-area-maps | **Date**: 2026-02-11

## Section 1: GitHub GeoJSON Rendering Capabilities

### Decision: Use inline `geojson` code blocks + canonical `.geojson` files

**Rationale**: GitHub natively renders both inline `geojson` fenced code blocks in Markdown and standalone `.geojson` files as interactive maps. Inline blocks provide zero-click map access within profile documents. Canonical files in `maps/` provide standalone viewing and a fallback if inline rendering fails.

**Alternatives considered**:
- Linked `.geojson` files only → Requires click-through; worse UX per Principle I
- Inline code blocks only → No standalone files for direct viewing/download
- External map service (geojson.io embed) → Violates FR-007 (no external dependencies)

### Rendering Syntax

Inline code block in Markdown:

````markdown
```geojson
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "title": "Location Name",
        "description": "Details here",
        "marker-color": "#e74c3c",
        "marker-size": "large",
        "marker-symbol": ""
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.0785, 38.0670]
      }
    }
  ]
}
```
````

**Critical note**: GeoJSON uses `[longitude, latitude]` order (NOT `[lat, lng]`).

### Simplestyle Spec v1.1.0 (Supported by GitHub)

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `title` | string | `""` | Popup heading text (use this, NOT `name`) |
| `description` | string | `""` | Popup body text |
| `marker-color` | hex | `#7e7e7e` | Marker fill color (`#RGB` or `#RRGGBB`) |
| `marker-size` | string | `"medium"` | `"small"`, `"medium"`, or `"large"` |
| `marker-symbol` | string | `""` | Maki icon ID, digit `0`-`9`, or letter `a`-`z` |

### Known Limitations

- **10 MB file size limit** — no risk for our maps (~2-5 KB each)
- **750+ markers** trigger automatic clustering — no risk (~50-70 total features)
- **WGS 84 projection only** — standard lat/lng coordinates (what Google Maps uses)
- **No external file references** — cannot link to a `.geojson` file and have it render inline; must embed full JSON
- **Intermittent rendering issues** reported on GitHub Community ([#58244](https://github.com/orgs/community/discussions/58244), [#19258](https://github.com/orgs/community/discussions/19258)) — mitigated by dual storage strategy

### Sources

- [GitHub Docs: Creating Diagrams](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-diagrams)
- [GitHub Docs: Mapping GeoJSON Files](https://docs.github.com/en/repositories/working-with-files/using-files/working-with-non-code-files)
- [Mapbox simplestyle-spec v1.1.0](https://github.com/mapbox/simplestyle-spec/blob/master/1.1.0/README.md)

---

## Section 2: GPS Coordinate Inventory

All coordinates extracted from Features 001-006 deliverables. All are [UNVERIFIED] unless noted.

### Bouldering Area Coordinates

| Location | Lat | Lng | Source | Status |
|----------|-----|-----|--------|--------|
| Summersville Lake — Long Point TH (parking) | 38.1350 | -80.8920 | areas/summersville-lake.md | [UNVERIFIED] |
| Meadow River — Main/Roadside Area | 38.0210 | -80.8590 | areas/meadow-river.md | [UNVERIFIED] |
| Gorge — Endless Wall TH (parking) | 38.0670 | -81.0785 | areas/gorge-boulders.md | [UNVERIFIED] |
| Gorge — Nuttall TH (parking) | 38.0710 | -81.0835 | areas/gorge-boulders.md | [UNVERIFIED] |
| Gorge — Bridge Buttress / Fayette Station (parking) | 38.0705 | -81.0830 | areas/gorge-boulders.md | [UNVERIFIED] |
| Gorge — Canyon Rim Visitor Center (parking) | 38.0700 | -81.0750 | areas/gorge-boulders.md | [UNVERIFIED] |
| Gorge — Kaymoor TH (parking) | 38.0580 | -81.0690 | areas/gorge-boulders.md | [UNVERIFIED] |

### Trail System Coordinates

| Location | Lat | Lng | Source | Status |
|----------|-----|-----|--------|--------|
| Arrowhead Trails (trailhead) | ~38.05 | ~-81.10 | trails/arrowhead.md | [UNVERIFIED] — approximate |
| Summit Bechtel Reserve (entrance) | ~38.02 | ~-81.11 | trails/summit-bechtel.md | [UNVERIFIED] — approximate |
| Babcock State Park (entrance) | ~38.02 | ~-80.95 | trails/babcock.md | [UNVERIFIED] — approximate |

### Town Amenities (Addresses — GPS needed)

| Location | Category | Address | GPS Status |
|----------|----------|---------|------------|
| Cathedral Cafe | dining | 134 S. Court Street, Fayetteville | Needs lookup |
| Pies & Pints | dining | 219 West Maple Avenue, Fayetteville | Needs lookup |
| Secret Sandwich Society | dining | 103 Keller Avenue, Fayetteville | Needs lookup |
| The Handle Bar + Kitchen | dining | 8263 Gatewood Rd, Fayetteville | Needs lookup |
| Firecreek BBQ & Steaks | dining | Fayetteville (in town) | Needs lookup |
| Bridge Brew Works | brewery | 335 Nick Rahall Greenway, Fayetteville | Needs lookup |
| Southside Junction Tap House | brewery | Fayetteville (in town) | Needs lookup |
| Water Stone Outdoors | gear-shop | Fayetteville (in town) | Needs lookup |
| Walmart Supercenter | supply | 204 Town Center Rd, Fayetteville | Needs lookup |
| Sheetz | supply | 27 Whitewater Ave, Fayetteville | Needs lookup |
| Fayetteville Town Center | town | Main St / Court St intersection | Needs lookup |

### Coordinate Gaps

**Bouldering sectors without individual coordinates** (will use parent area coordinate as approximate):
- Summersville Lake: Long Point, Pirates Cove, Orange Oswald Wall Area — all accessed from Long Point TH
- Meadow River: Main Area/Roadside, River Boulders, Upstream/Upper Meadow — all near roadside pulloffs
- Gorge: Endless Wall/Fern Creek sector, Nuttall/Fern Buttress sector — trailhead coords available

**Strategy**: Use parking/trailhead coordinates for sectors accessed from the same parking lot. Add offset descriptions in marker `description` field (e.g., "5-10 min walk from Endless Wall TH").

---

## Section 3: Map File Inventory

8 GeoJSON files to create:

| Map File | Scope | Est. Features | Parent Documents |
|----------|-------|---------------|------------------|
| regional-overview.geojson | All areas + trails + town center | 7 | maps/README.md |
| summersville-lake.geojson | Sectors + parking | 4-5 | areas/summersville-lake.md |
| meadow-river.geojson | Sectors + parking | 3-4 | areas/meadow-river.md |
| gorge-boulders.geojson | Sectors + parking + trailheads | 7-9 | areas/gorge-boulders.md |
| arrowhead.geojson | Trail area + parking | 2-3 | trails/arrowhead.md |
| summit-bechtel.geojson | Trail area + parking | 2-3 | trails/summit-bechtel.md |
| babcock.geojson | Trail area + parking + Glade Creek | 2-3 | trails/babcock.md |
| town-amenities.geojson | All dining + breweries + shops + supplies | 10-12 | maps/README.md |

**Total estimated features**: ~50-60 point markers

---

## Section 4: Sources

- Features 001-006 deliverable documents (areas/, trails/, conditions/, rest-day/, logistics/)
- GitHub GeoJSON documentation (docs.github.com)
- Mapbox simplestyle-spec v1.1.0 (github.com/mapbox/simplestyle-spec)
- Google Maps (for address → coordinate conversion during implementation)
