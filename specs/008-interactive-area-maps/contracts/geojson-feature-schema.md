# Contract: GeoJSON Feature Schema

**Feature**: 008-interactive-area-maps | **Date**: 2026-02-11

## GeoJSON Feature Template

Every map point MUST conform to this structure:

```json
{
  "type": "Feature",
  "properties": {
    "title": "Location Name",
    "description": "Contextual detail. [UNVERIFIED] if coordinates unconfirmed.",
    "marker-color": "#e74c3c",
    "marker-size": "large",
    "marker-symbol": "",
    "category": "sector"
  },
  "geometry": {
    "type": "Point",
    "coordinates": [-81.0785, 38.0670]
  }
}
```

## Property Requirements by Category

### Bouldering Sector (`category: "sector"`)

```json
{
  "title": "Long Point",
  "description": "Best beginner sector — 6 V0-V3 problems. Exposed (no shelter). Flat lakebed landings. [UNVERIFIED]",
  "marker-color": "#e74c3c",
  "marker-size": "large",
  "category": "sector"
}
```

**Required description content**: Grade density, shelter status, landing type

### Trail System (`category: "trail-system"`)

```json
{
  "title": "Arrowhead Trails",
  "description": "Primary MTB — 10-13 mi singletrack, green to black. 5-10 min from town. Free access. [UNVERIFIED]",
  "marker-color": "#2ecc71",
  "marker-size": "large",
  "category": "trail-system"
}
```

**Required description content**: Mileage, difficulty range, drive time, access status

### Parking (`category: "parking"`)

```json
{
  "title": "Endless Wall Trailhead Parking",
  "description": "Main parking for Endless Wall sector. NPS lot on Lansing-Edmond Rd. Free, no fee. [UNVERIFIED]",
  "marker-color": "#95a5a6",
  "marker-size": "small",
  "category": "parking"
}
```

**Required description content**: What it serves, road name, fee info if known

### Dining (`category: "dining"`)

```json
{
  "title": "Cathedral Cafe",
  "description": "Breakfast/brunch in a converted church. Try the breakfast burrito. February hours [UNVERIFIED].",
  "marker-color": "#9b59b6",
  "marker-size": "medium",
  "category": "dining"
}
```

**Required description content**: Cuisine type, one personal note, February hours flag

### Brewery (`category: "brewery"`)

```json
{
  "title": "Bridge Brew Works",
  "description": "Dog-friendly tasting room with pizza/tacos. WV craft beer focus. February hours [UNVERIFIED].",
  "marker-color": "#f1c40f",
  "marker-size": "medium",
  "category": "brewery"
}
```

**Required description content**: What's notable, food availability, February hours flag

### Supply (`category: "supply"`)

```json
{
  "title": "Walmart Supercenter",
  "description": "Best grocery selection in area. 204 Town Center Rd. Hours: 6a-11p daily [UNVERIFIED].",
  "marker-color": "#7f8c8d",
  "marker-size": "small",
  "category": "supply"
}
```

**Required description content**: What it provides, address or location, hours if known

## Inline Embed Template

Each Markdown document embeds its map using this structure:

````markdown
### Area Map

> Markers are approximate. All coordinates [UNVERIFIED]. See legend below.

```geojson
{
  "type": "FeatureCollection",
  "features": [
    ...
  ]
}
```

**Legend**: 🔴 Sector · 🟠 Trailhead · ⚪ Parking
````

## Map File Naming Convention

| File | Scope |
|------|-------|
| `maps/regional-overview.geojson` | All 7 key locations |
| `maps/summersville-lake.geojson` | Summersville sectors + parking |
| `maps/meadow-river.geojson` | Meadow River sectors + parking |
| `maps/gorge-boulders.geojson` | Gorge sectors + parking + trailheads |
| `maps/arrowhead.geojson` | Arrowhead trail system + parking |
| `maps/summit-bechtel.geojson` | Summit Bechtel + parking |
| `maps/babcock.geojson` | Babcock + parking |
| `maps/town-amenities.geojson` | Dining + breweries + shops + supplies |
