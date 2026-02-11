# Interactive Area Maps — New River Gorge 2026

> Visual overview of all bouldering areas, trail systems, and town amenities. Maps render on GitHub — click markers for details.
> **These maps require GitHub rendering** — for offline use at the crag, download [Google Maps offline](https://support.google.com/maps/answer/6291838) for the Fayetteville/NRG area.

---

## Regional Overview

All bouldering areas, mountain biking trail systems, and Fayetteville on one map.

```geojson
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "title": "Summersville Lake",
        "description": "Best beginner area — 13 V0-V3 problems, flat landings. 35-40 min from Fayetteville. Rain resilience: Poor (exposed). [UNVERIFIED]",
        "marker-color": "#e74c3c",
        "marker-size": "large",
        "category": "bouldering-area"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-80.8920, 38.1350]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Meadow River",
        "description": "Rain-day backup — sheltered overhangs, short approaches. 35-40 min from Fayetteville. Rain resilience: Good. [UNVERIFIED]",
        "marker-color": "#e74c3c",
        "marker-size": "large",
        "category": "bouldering-area"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-80.8590, 38.0210]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Gorge Boulders",
        "description": "Best rain shelter — cliff-base overhangs stay dry. 5-15 min from Fayetteville. Rain resilience: Good-Fair. [UNVERIFIED]",
        "marker-color": "#e74c3c",
        "marker-size": "large",
        "category": "bouldering-area"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.0785, 38.0670]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Arrowhead Trails",
        "description": "Primary MTB — 10-13 mi singletrack, green to black. 5-10 min from Fayetteville. Free access. [UNVERIFIED]",
        "marker-color": "#2ecc71",
        "marker-size": "large",
        "category": "trail-system"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.0837, 38.0393]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Summit Bechtel Reserve",
        "description": "Premium MTB — 30-40 mi trail, green to double black. 12-18 min from Fayetteville. ⚠️ MUST call (304) 465-2800 — access NOT guaranteed. [UNVERIFIED]",
        "marker-color": "#2ecc71",
        "marker-size": "large",
        "category": "trail-system"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.11, 38.02]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Babcock State Park",
        "description": "Scenic backup MTB — 5-10 mi old roads and railroad grades. 30-35 min from Fayetteville. Call (304) 438-3004 for road access. [UNVERIFIED]",
        "marker-color": "#2ecc71",
        "marker-size": "large",
        "category": "trail-system"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-80.95, 38.02]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Fayetteville",
        "description": "Base town — lodging, dining, gear shops, groceries. All drives measured from here.",
        "marker-color": "#1abc9c",
        "marker-size": "large",
        "category": "town"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.1035, 38.0520]
      }
    }
  ]
}
```

**Legend**: 🔴 Bouldering area · 🟢 Trail system · 🟦 Town center

| Color | Category | Markers |
|-------|----------|---------|
| Red | Bouldering area | Summersville Lake, Meadow River, Gorge Boulders |
| Green | Trail system | Arrowhead, Summit Bechtel, Babcock |
| Teal | Town center | Fayetteville |

**Detailed maps**: Each area and trail profile contains a sector-level map — see [Bouldering Areas](../areas/README.md) and [Trail Systems](../trails/README.md).

---

## Town Amenities — Fayetteville

Curated dining, breweries, gear shops, and supplies from the [Rest-Day Guide](../rest-day/README.md).

```geojson
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "title": "Cathedral Cafe",
        "description": "Breakfast/brunch in a converted church. Try the breakfast burrito. Closed Wednesdays. February hours [UNVERIFIED].",
        "marker-color": "#9b59b6",
        "marker-size": "medium",
        "category": "dining"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.1032, 38.0524]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Pies & Pints",
        "description": "Craft pizza + beer. Happy hour Mon-Fri 3-6p. Group-friendly. February hours [UNVERIFIED].",
        "marker-color": "#9b59b6",
        "marker-size": "medium",
        "category": "dining"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.1040, 38.0529]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Secret Sandwich Society",
        "description": "Thoughtful sandwiches + cocktails. Homemade pickles, chips. February hours [UNVERIFIED].",
        "marker-color": "#9b59b6",
        "marker-size": "medium",
        "category": "dining"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.1046, 38.0555]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "The Handle Bar + Kitchen",
        "description": "Beer garden at Arrowhead Bike Farm. WV craft beer, vegan-friendly. Perfect post-ride. February hours [UNVERIFIED].",
        "marker-color": "#9b59b6",
        "marker-size": "medium",
        "category": "dining"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.0806, 38.0403]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Firecreek BBQ & Steaks",
        "description": "Best BBQ locally — smoked ribs and brisket. February hours [UNVERIFIED].",
        "marker-color": "#9b59b6",
        "marker-size": "medium",
        "category": "dining"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.1047, 38.0555]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Bridge Brew Works",
        "description": "Dog-friendly craft brewery. Indoor tasting room, pizza/tacos on-site. February hours [UNVERIFIED].",
        "marker-color": "#f1c40f",
        "marker-size": "medium",
        "category": "brewery"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.1056, 38.0516]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Southside Junction Tap House",
        "description": "12 rotating WV craft taps + full restaurant menu. Group-friendly. February hours [UNVERIFIED].",
        "marker-color": "#f1c40f",
        "marker-size": "medium",
        "category": "brewery"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.1020, 38.0517]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Water Stone Outdoors",
        "description": "Local gear shop — guidebooks, trail beta, bike service. (304) 574-2425. February hours [UNVERIFIED].",
        "marker-color": "#3498db",
        "marker-size": "medium",
        "category": "gear-shop"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.0974, 38.0518]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Walmart Supercenter",
        "description": "Best grocery selection in area. 204 Town Center Rd. Hours: 6a-11p daily [UNVERIFIED].",
        "marker-color": "#7f8c8d",
        "marker-size": "small",
        "category": "supply"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.1198, 38.0343]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "title": "Sheetz",
        "description": "24-hour fuel + food + snacks. 27 Whitewater Ave. [UNVERIFIED]",
        "marker-color": "#7f8c8d",
        "marker-size": "small",
        "category": "supply"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-81.1114, 38.0339]
      }
    }
  ]
}
```

**Legend**: 🟣 Dining · 🟡 Brewery · 🔵 Gear shop · ⚪ Supply

| Color | Category | Markers |
|-------|----------|---------|
| Purple | Dining | Cathedral Cafe, Pies & Pints, Secret Sandwich Society, The Handle Bar, Firecreek BBQ |
| Gold | Brewery | Bridge Brew Works, Southside Junction Tap House |
| Blue | Gear shop | Water Stone Outdoors |
| Gray | Supply | Walmart, Sheetz |

All February hours [UNVERIFIED] — call ahead. Full details: [Rest-Day Guide](../rest-day/README.md).

---

*Last updated: 2026-02-11*
*All coordinates [UNVERIFIED] — verify before navigating. If maps don't render, view `.geojson` files directly or paste into [geojson.io](https://geojson.io) for guaranteed rendering.*
*For daily planning, start with your [Conditions Guide](../conditions/README.md).*
