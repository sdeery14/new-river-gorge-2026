# New River Gorge Climbing Trip — February 14–21, 2026

A decision-support guide for a week-long bouldering trip based in Fayetteville, WV. Rain-contingency alternative to the [Chattanooga 2026](https://github.com/sdeery14/chattanooga-2026) trip. Open any section, find what you need, go climb.

## Quick Start: Common Questions

| Question | Where to look |
|----------|---------------|
| **"Where should we climb today?"** | [Conditions guide](conditions/README.md) — match today's weather to the best area |
| **"How far is [area]?"** | [Logistics guide](logistics/README.md) — access quick reference table at the top |
| **"What can I climb at [area]?"** | [Area profiles](areas/README.md) — pick an area, then see its problem clusters |
| **"What do we need before going to [area]?"** | [Logistics guide](logistics/README.md) — regulations, parking, approach, warnings |
| **"It's a rest day — what do we do?"** | [Rest-day guide](rest-day/README.md) — options sorted by energy level |
| **"Can someone ride bikes instead?"** | [Trail profiles](trails/README.md) — 3 trail systems with February conditions |
| **"Where is everything on a map?"** | [Interactive maps](maps/README.md) — GeoJSON maps of areas, trails, and town amenities |
| **"When do we switch to NRG?"** | [Decision Trigger Playbook](playbook/README.md) — weather thresholds, booking deadlines, contingency paths |
| **"What's Sean's plan?"** | [Sean's guide](sean/README.md) — personal decision matrix, V1-V3 problems, food picks |

## What's in the Repo

### [Bouldering Areas](areas/README.md)

Area profiles for 3 bouldering zones within driving distance of Fayetteville. Each area has an overview (style, conditions, access, rain resilience), sector maps, and curated problem lists organized by grade band (V0-V3 / V4-V6 / V7-V10+). Comparison table and quick decision filters included.

- **Meadow River** — default day; best rain fallback (sheltered overhangs, short approaches)
- **Summersville Lake** — best for beginners and volume (13+ V0-V3 problems, flat landings)
- **Gorge Boulders** — closest to town; best rain shelter (cliff-base overhangs stay dry)

### [Conditions, Weather & Drying Guide](conditions/README.md)

"Given today's weather, which area?" Nuttall sandstone primer (friction, seepage, drying times), per-area weather behavior, February seasonal data, freeze/thaw guide, and the daily decision framework. The core reference for every morning.

### [Mountain Biking Trails](trails/README.md)

3 trail systems near Fayetteville with February conditions, difficulty ratings, and climbing-area pairings. Includes wet-weather guidance and a comparison table.

- **Arrowhead Trails** — primary; 10-13 mi singletrack, 5-10 min from town, free
- **Summit Bechtel Reserve** — premium; 30-40 mi trail, but private (must call ahead)
- **Babcock State Park** — scenic backup; old roads and railroad grades

### [Logistics & Access Cheat Sheets](logistics/README.md)

Drive times from the rental house, parking, approaches, NPS regulations, mid-week roster change logistics (lodging, cars), and a pre-trip verification checklist.

### [Rest Days & Low-Energy Options](rest-day/README.md)

Dining, breweries, hiking trails, hot springs, and indoor options — all with drive times, costs, and February availability. Energy-tiered from zero effort to full day trips.

### [Sean's Personal Trip Guide](sean/README.md)

Personalized decision matrix, V1-V3 bouldering tick list, mountain biking priority stack, food & drink picks, and daily logistics — all calibrated for Sean's ability band and preferences.

### [Decision Trigger Playbook](playbook/README.md)

"When do we switch from Chattanooga to NRG?" Weather-based decision tree, trigger thresholds at 7-day/3-day/1-day windows, side-by-side weather resilience comparison, booking & cancellation timeline with financial exposure, and contingency paths for degraded scenarios.

### [Interactive Area Maps](maps/README.md)

GeoJSON maps rendered on GitHub. Regional overview of all locations, sector-level maps embedded in each area and trail profile, and a town amenities map with curated dining, breweries, gear shops, and supplies.

## Before the Trip

1. Read the [regulations and access warnings](logistics/README.md) — NPS rules, gate closures, pre-trip calls
2. Run the [pre-trip verification checklist](logistics/README.md#pre-trip-verification-checklist) — lodging, calls, gear, downloads
3. Skim the [access quick reference](logistics/README.md#access-quick-reference) to build a mental map
4. Browse [area profiles](areas/README.md) to get familiar with the options
5. Check the [conditions guide](conditions/README.md) to understand weather-to-area logic

## During the Trip

1. Check the weather each morning (temperature, dew point, wind, rain)
2. Open the [conditions guide](conditions/README.md) — "Can I Climb Right Now?" table at the top
3. Check the [area quick decision guide](areas/README.md#quick-decision-guide) to pick the best area
4. Check that area's [access details](logistics/README.md#access-quick-reference) for parking, approach, and warnings
5. Check the [problem clusters](areas/README.md) for what to climb when you arrive

## The Group

- **V10 climbers** — primary trip focus; area selection prioritizes hard-climbing quality
- **~V6 climbers** — strong moderate options at most areas
- **V1-V3 climbers** — beginner-friendly problems identified; may split for biking or rest-day activities

**Mid-week roster change**: One member departs ~Wednesday, another arrives ~Wednesday. This affects lodging headcount, car capacity, and daily ability-band ratios. Documents flag where this matters.

## Key Warnings

- **Summit Bechtel is PRIVATE** — must call (304) 465-2800 before driving. Public access NOT guaranteed.
- **Summersville Lake gates** — USACE may close Long Point access Nov-Apr. Call (304) 872-3459 to verify.
- **Gorge trails are icy in February** — bring microspikes for Endless Wall boardwalk approach.
- **Kaymoor steps — SKIP ENTIRELY** — 800+ steel grate steps are dangerously icy in winter.
- **Babcock interior roads** — may be gated in winter. Call (304) 438-3004 for access.
- **Do not climb wet Nuttall sandstone** — weakened when saturated. Wait for the [drying reference](conditions/README.md#drying-reference).
- **Do not ride muddy trails** — causes lasting damage. Default to bouldering on wet days.

## Repo Structure

```
README.md                  ← You are here
areas/                     ← Bouldering area profiles + problem clusters
  README.md                ← Area comparison table and quick decision guide
  summersville-lake.md     ← Per-area profiles (with inline sector maps)
  meadow-river.md
  gorge-boulders.md
  problems-*.md            ← Curated problem lists by area
  hard-climbing.md         ← V7-V10+ cross-area reference
  sheltered-classics.md    ← Rain-resilient problems across all areas
conditions/
  README.md                ← Weather-to-area guide, sandstone primer, drying reference
logistics/
  README.md                ← Drive times, access sheets, regulations, roster logistics
trails/
  README.md                ← Trail comparison table and February conditions
  arrowhead.md             ← Per-trail profiles (with inline trail maps)
  summit-bechtel.md
  babcock.md
rest-day/
  README.md                ← Rest-day options by energy level
sean/
  README.md                ← Sean's personal trip guide
playbook/
  README.md                ← Decision Trigger Playbook (Chattanooga vs NRG)
maps/
  README.md                ← Regional overview + town amenities maps
  *.geojson                ← Canonical map files (8 total)
```

## Notes

- All drive times are from the rental house in Fayetteville, WV
- Items marked **[UNVERIFIED]** throughout the repo could not be confirmed from available sources — verify before relying on them
- This repo is a decision-support tool, not a fixed itinerary. Plans change — that's the point
- Companion repo: [Chattanooga 2026](https://github.com/sdeery14/chattanooga-2026) (same format, different rock)
