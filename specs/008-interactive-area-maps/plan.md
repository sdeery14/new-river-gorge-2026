# Implementation Plan: Interactive Area Maps

**Branch**: `008-interactive-area-maps` | **Date**: 2026-02-11 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/008-interactive-area-maps/spec.md`

## Summary

Create GeoJSON maps for all bouldering areas, trail systems, and town amenities, embedded as inline `geojson` code blocks in existing Markdown profile documents and stored as canonical `.geojson` files in a new `maps/` directory. Maps render natively on GitHub using the simplestyle spec for marker color, size, and popup content. No external tools or build steps required.

## Technical Context

**Language/Version**: GeoJSON (RFC 7946) with Mapbox simplestyle-spec v1.1.0
**Primary Dependencies**: GitHub's built-in GeoJSON renderer (Leaflet.js-based)
**Storage**: Flat `.geojson` files in `maps/` directory + inline code blocks in Markdown
**Testing**: Manual — visual verification on GitHub after push
**Target Platform**: GitHub.com (web + mobile browser)
**Project Type**: Documentation-only (Markdown + GeoJSON)
**Performance Goals**: N/A — static files, no server
**Constraints**: GeoJSON files must be <10 MB; all coordinates WGS 84
**Scale/Scope**: ~8 map files, ~50-70 total point features

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| Principle | Status | Notes |
|-----------|--------|-------|
| I. Decision-Support First | PASS | Maps provide instant spatial orientation; inline rendering = zero extra clicks |
| II. Bouldering Scope Boundary | PASS | Maps show bouldering areas and sectors. MTB trails are separate category. No roped climbing content. FR-012 enforces this |
| III. Ability-Aware, Hard-Climbing Priority | PASS | Sector markers include grade density in descriptions. No change to priority order — maps are spatial, not grade-curated |
| IV. Mountain Biking as First-Class | PASS | Trail system maps have equal treatment (US3, dedicated map files, same styling rigor) |
| V. Weather-Resilience as Core Value | PASS | FR-009 requires shelter vs. exposed visual distinction on bouldering maps. Marker descriptions include rain resilience |
| VI. Source Accuracy & Recency | PASS | FR-006 requires all coordinates sourced or flagged [UNVERIFIED]. All existing GPS data inherits [UNVERIFIED] status from Features 001-006 |

**Post-design re-check**: All gates still PASS. No violations.

## Project Structure

### Documentation (this feature)

```text
specs/008-interactive-area-maps/
├── plan.md
├── research.md
├── data-model.md
├── quickstart.md
├── contracts/
│   └── geojson-feature-schema.md
└── tasks.md
```

### Source (repository root)

```text
maps/
├── README.md                  ← Regional overview (US1) with inline map + legend
├── regional-overview.geojson  ← Canonical file: all areas, trails, town center
├── summersville-lake.geojson  ← Canonical file: Summersville sectors + parking
├── meadow-river.geojson       ← Canonical file: Meadow River sectors + parking
├── gorge-boulders.geojson     ← Canonical file: Gorge sectors + parking + trailheads
├── arrowhead.geojson          ← Canonical file: Arrowhead trail system + parking
├── summit-bechtel.geojson     ← Canonical file: Summit Bechtel + parking
├── babcock.geojson            ← Canonical file: Babcock + parking
└── town-amenities.geojson     ← Canonical file: dining, breweries, shops, supplies

Modified existing files:
├── areas/summersville-lake.md ← Add inline geojson code block + legend
├── areas/meadow-river.md     ← Add inline geojson code block + legend
├── areas/gorge-boulders.md   ← Add inline geojson code block + legend
├── trails/arrowhead.md       ← Add inline geojson code block + legend
├── trails/summit-bechtel.md  ← Add inline geojson code block + legend
└── trails/babcock.md         ← Add inline geojson code block + legend
```

**Structure Decision**: Flat `maps/` directory at repo root. Each `.geojson` file named to match its parent document (e.g., `summersville-lake.geojson` → `areas/summersville-lake.md`). Inline code blocks duplicate the GeoJSON content in profile documents for in-place rendering.

## Key Research Findings

| Finding | Impact |
|---------|--------|
| GitHub renders ` ```geojson ` code blocks inline as interactive maps | Confirms inline embed strategy works |
| Simplestyle spec supported: `title`, `description`, `marker-color`, `marker-size`, `marker-symbol` | Use for popup content and visual category distinction |
| Use `title` (not `name`) for popup headings | Critical — `name` is not part of simplestyle spec |
| 10 MB file size limit; 750+ markers trigger clustering | No risk — our maps have ~50-70 total features |
| Intermittent rendering issues reported on GitHub | Mitigated by dual storage (inline + canonical .geojson files) |
| 8 existing GPS coordinates from Features 001-006 (parking/trailheads) | Good starting data; remaining locations need coordinate research |
| Addresses available for dining/breweries but not GPS coords | Will need to derive lat/lng from addresses via Google Maps |

## Color Scheme

| Category | Marker Color | Hex | Marker Size |
|----------|-------------|-----|-------------|
| Bouldering area / sector | Red | #e74c3c | large |
| Trail system | Green | #2ecc71 | large |
| Parking | Gray | #95a5a6 | small |
| Trailhead / approach | Orange | #f39c12 | small |
| Dining | Purple | #9b59b6 | medium |
| Brewery / taphouse | Gold | #f1c40f | medium |
| Gear shop | Blue | #3498db | medium |
| Supply (grocery/gas) | Dark gray | #7f8c8d | small |
| Town center | Teal | #1abc9c | large |

## Risk Assessment

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| GPS coordinates inaccurate | HIGH | LOW | All flagged [UNVERIFIED]; dual verification encouraged |
| GitHub GeoJSON rendering breaks | LOW | MEDIUM | Canonical .geojson files viewable directly; fallback to geojson.io |
| Inline code blocks make Markdown files large | MEDIUM | LOW | GeoJSON for point features is compact (~2-5 KB per map) |
| Simplestyle marker-symbol icons don't render | MEDIUM | LOW | Use marker-color as primary differentiator; symbols are secondary |
