# Quickstart: Interactive Area Maps

**Feature**: 008-interactive-area-maps | **Date**: 2026-02-11

## What This Feature Produces

GeoJSON maps embedded in existing Markdown documents + canonical `.geojson` files in a new `maps/` directory. 8 map files, ~50-60 point markers total.

## Deliverables

```
maps/                              ← New directory
├── README.md                      ← Regional overview with inline map + town amenities map
├── regional-overview.geojson      ← All areas, trails, town center (7 markers)
├── summersville-lake.geojson      ← Sectors + parking (4-5 markers)
├── meadow-river.geojson           ← Sectors + parking (3-4 markers)
├── gorge-boulders.geojson         ← Sectors + parking + trailheads (7-9 markers)
├── arrowhead.geojson              ← Trail system + parking (2-3 markers)
├── summit-bechtel.geojson         ← Trail system + parking (2-3 markers)
├── babcock.geojson                ← Trail system + parking (2-3 markers)
└── town-amenities.geojson         ← Dining, breweries, shops, supplies (10-12 markers)

Modified existing files:
├── areas/summersville-lake.md     ← Add inline map + legend
├── areas/meadow-river.md         ← Add inline map + legend
├── areas/gorge-boulders.md       ← Add inline map + legend
├── trails/arrowhead.md           ← Add inline map + legend
├── trails/summit-bechtel.md      ← Add inline map + legend
└── trails/babcock.md             ← Add inline map + legend
```

## Implementation Order

1. **Create `maps/` directory** — establish new directory structure
2. **Research GPS coordinates** — look up lat/lng for all town amenities and verify/improve existing coordinates from Features 001-006
3. **Build regional overview map** (US1 MVP) — 7-marker GeoJSON with all areas + trails + town center
4. **Write `maps/README.md`** — regional overview with inline map, legend, and offline maps note
5. **Build bouldering area maps** (US2) — one `.geojson` per area with sectors, parking, trailheads
6. **Embed inline maps in area profiles** — add `geojson` code blocks to `areas/*.md` files
7. **Build trail system maps** (US3) — one `.geojson` per trail system with parking and access
8. **Embed inline maps in trail profiles** — add `geojson` code blocks to `trails/*.md` files
9. **Build town amenities map** (US4) — dining, breweries, gear shops, supplies
10. **Embed town map in `maps/README.md`** — add second inline map for town amenities
11. **Source verification pass** — verify all coordinates flagged [UNVERIFIED] or sourced
12. **Scope compliance check** — zero sport/trad/route climbing references
13. **Rendering verification** — push to GitHub, verify all inline maps and .geojson files render

## Key Files to Reference During Implementation

| File | Purpose |
|------|---------|
| `specs/008-interactive-area-maps/spec.md` | Requirements and acceptance criteria |
| `specs/008-interactive-area-maps/research.md` | GPS inventory and GeoJSON rendering research |
| `specs/008-interactive-area-maps/data-model.md` | Feature schema and color scheme |
| `specs/008-interactive-area-maps/contracts/geojson-feature-schema.md` | GeoJSON templates per category |
| `areas/summersville-lake.md` | Source for Summersville sectors and parking |
| `areas/meadow-river.md` | Source for Meadow River sectors and parking |
| `areas/gorge-boulders.md` | Source for Gorge sectors, parking, trailheads |
| `trails/arrowhead.md` | Source for Arrowhead trail system |
| `trails/summit-bechtel.md` | Source for Summit Bechtel trail system |
| `trails/babcock.md` | Source for Babcock trail system |
| `rest-day/README.md` | Source for dining, brewery, activity addresses |
| `logistics/README.md` | Source for parking GPS, drive times |
| `.specify/memory/constitution.md` | Constitution gates |

## Constitution Gates to Watch

- **Principle I (Decision-Support First)**: Inline maps provide zero-click spatial orientation
- **Principle II (Bouldering Scope)**: No roped climbing content in any map marker or description
- **Principle IV (MTB First-Class)**: Trail system maps receive equal treatment to area maps
- **Principle V (Weather-Resilience)**: Shelter status included in sector marker descriptions
- **Principle VI (Source Accuracy)**: All coordinates sourced or flagged `[UNVERIFIED]`

## Known Risks

- **GPS coordinate accuracy**: All existing coordinates are [UNVERIFIED]. Town amenity coordinates must be derived from addresses via Google Maps — also [UNVERIFIED]
- **GitHub rendering instability**: Intermittent issues reported with GeoJSON map rendering. Mitigated by dual storage (inline + canonical files) and fallback note directing users to geojson.io
- **Coordinate order**: GeoJSON uses [longitude, latitude] — easy to accidentally swap. Verify by checking that all points appear in West Virginia (~38°N, ~81°W)
- **Simplestyle marker-symbol**: May not render reliably. Use marker-color as primary visual differentiator, not marker-symbol
