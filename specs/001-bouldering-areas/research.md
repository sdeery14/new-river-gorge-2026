# Research: Primary Bouldering Areas

**Feature**: 001-bouldering-areas
**Date**: 2026-02-10
**Sources**: Training data (cutoff May 2025), Mountain Project references, NPS publications, NRAC, USACE. Web verification was limited; items flagged per Constitution Principle VI.

---

## Decision 1: Which Areas to Profile

**Decision**: Profile 3 primary areas + 1 supplementary area within 45 minutes of Fayetteville.

**Areas included**:

| Area | Drive Time | Rationale |
|------|-----------|-----------|
| **Meadow River** | ~25-35 min | Most developed NRG bouldering area. Best all-around option. |
| **Summersville Lake** | ~35-40 min | Best problem density in region. Winter drawdown exposes additional boulders. Best beginner area. |
| **Gorge Boulders (NRG proper)** | 5-15 min | Closest to Fayetteville. Best wet-weather sheltered bouldering (cliff-base overhangs). Multiple sub-locations. |
| **Bridge Buttress area** | 5 min | Profiled as a distinct quick-access option within the gorge, not a separate area. Shortest approach in the region. |

**Areas excluded**:

| Area | Drive Time | Reason for Exclusion |
|------|-----------|---------------------|
| Coopers Rock | 2.5-3 hours | Too far — outside 45-min radius |
| Cranberry Wilderness | 45-60 min | Marginally outside radius, high elevation (snowier), minimally developed [UNVERIFIED] |
| Hawks Nest State Park | 15-20 min | No documented bouldering problems |
| Gauley Bridge / Kanawha Falls | 20-25 min | No documented bouldering problems |
| Babcock State Park | 20-25 min | No documented bouldering; state park may restrict climbing |
| Carnifex Ferry | 40-50 min | No confirmed bouldering [UNVERIFIED] |

**Alternatives considered**: Including all areas within radius regardless of problem count. Rejected because areas with zero documented bouldering add noise without value, violating Constitution Principle I (Decision-Support First).

---

## Decision 2: Gorge Boulders — One Area or Multiple

**Decision**: Profile "Gorge Boulders" as a single area with multiple sectors, not as separate areas.

**Rationale**: The gorge locations (Endless Wall, Fern Creek, Nuttall, Bridge Buttress, Kaymoor) share the same land manager (NPS), same rock type, same general access pattern (drive to rim trailhead, descend into gorge), and same weather behavior. They differ in approach length, shelter quality, and problem density — which maps perfectly to the sector model from the spec clarification.

**Sectors within Gorge Boulders**:
1. Endless Wall / Fern Creek — best shelter, moderate approach
2. Nuttall / Fern Buttress — good shelter, moderate approach
3. Bridge Buttress — shortest approach, moderate shelter
4. Kaymoor — long approach, dangerous when icy, not recommended for February primary use

---

## Decision 3: Rain Resilience Ratings

**Decision**: Assign ratings based on composite assessment of shelter, seepage, drying, and wind.

| Area | Rating | Primary Factor |
|------|--------|---------------|
| Meadow River | **Good** | Overhanging problems stay dry; forest canopy shelter |
| Gorge Boulders (Endless Wall / Nuttall sectors) | **Good** | Cliff-base overhangs provide natural roof coverage |
| Gorge Boulders (Bridge Buttress) | **Fair** | Some cliff shelter but more exposed than deep gorge sectors |
| Gorge Boulders (Kaymoor) | **Fair** | Some shelter but approach is dangerous when icy/wet |
| Summersville Lake | **Poor** | Lakeshore boulders are exposed; wind aids drying but no overhead shelter |

---

## Decision 4: Nuttall Sandstone Drying Time Reference

**Decision**: Include a standardized drying time table in the area overview, not repeated per-area.

| Condition | Overhanging | Vertical | Slab |
|-----------|------------|----------|------|
| Light rain → sun + wind | Already dry | 1-3 hours | 2-4 hours |
| Heavy rain → sun + wind | Already dry (seepage possible) | 3-6 hours | 4-8 hours |
| Heavy rain → overcast, no wind | Dry except seep lines | 6-12 hours | 12-24 hours |
| Multi-day soaking | Seepage on cracks/breaks | 12-24+ hours | 24-48+ hours |

**Source**: General Nuttall sandstone behavior from NRG climbing community. Cold February temperatures slow evaporation. [UNVERIFIED — drying times are estimates]

**Important community ethic**: NRAC and the NRG climbing community strongly discourage climbing on wet Nuttall sandstone. The stone is more friable when saturated. This is a rock-preservation concern, not just a friction issue.

---

## Decision 5: NPS Regulations Summary for Bouldering

**Decision**: Include a concise NPS bouldering regulations summary in the area overview (applies to all gorge sectors). Not repeated per-sector.

| Topic | Status | Confidence |
|-------|--------|------------|
| Bouldering permitted | Yes, year-round | [UNVERIFIED] |
| Entrance fee | None | [UNVERIFIED] |
| Crash pads | Permitted | [UNVERIFIED] |
| Chalk | Permitted (brush tick marks) | [UNVERIFIED] |
| Brushing | Nylon/boar's hair only. No wire brushes. | [UNVERIFIED — community standard, not confirmed NPS regulation] |
| Group size | No specific climbing limit; 5-6 person group is fine | [UNVERIFIED] |
| Peregrine closures | March-July only. February is unaffected. | [UNVERIFIED] |
| Permits | Not required for recreational bouldering | [UNVERIFIED] |

**Key distinction**: Meadow River and Summersville Lake are NOT within NPS boundaries. Only gorge boulders are subject to NPS regulations. Summersville Lake is managed by USACE.

**Pre-trip verification**: Call NPS Canyon Rim Visitor Center at (304) 574-2115 or check nps.gov/neri/planyourvisit/climbing.htm closer to the trip date.

---

## Decision 6: Summersville Lake Winter Drawdown

**Decision**: Highlight the winter drawdown as a key advantage for February bouldering.

The USACE draws Summersville Lake down ~77 feet from summer pool (~1,652 ft) to winter pool (~1,575 ft). February is at or near maximum drawdown, exposing lakeshore boulders that are submerged in summer. The exposed lakebed provides flat sandstone landing zones.

**Verification**: Check USACE Huntington District for 2026 drawdown schedule. Call (304) 872-3459.

**February access concern**: Some USACE access roads and boat ramp parking areas are gated November through April. Long Point trailhead off WV Rt. 129 is the most reliably accessible year-round. [UNVERIFIED — gate dates may vary by year]

---

## Decision 7: Document Structure

**Decision**: Produce one overview document (README.md) plus one area profile per primary area. Gorge boulders treated as one area with sector subsections.

```
areas/
├── README.md                  # Area overview with quick-reference table
├── meadow-river.md            # Full area profile
├── summersville-lake.md       # Full area profile
└── gorge-boulders.md          # Full area profile (with sector breakdowns)
```

**Rationale**: Three area profiles keeps the scope manageable. Gorge boulders as one document with sectors (Endless Wall, Nuttall, Bridge Buttress, Kaymoor) matches how climbers think about "going to the gorge" — they pick a sector once they're there, not before.

---

## Verified Data: Meadow River

**Date**: 2026-02-10
**Source**: Training data (cutoff May 2025) derived from Mountain Project, NRAC community knowledge, local guidebook references, and general NRG climbing knowledge. **Web verification was attempted but limited in this session.** All items flagged per Constitution Principle VI.

### Overview

Meadow River is the most developed dedicated bouldering area in the New River Gorge region. Located along the Meadow River corridor near Meadow Bridge, WV, it offers concentrated Nuttall sandstone bouldering on steep, overhanging rock. The area is NOT within NPS boundaries — it sits on a mix of private land and state/county road rights-of-way. [UNVERIFIED — land ownership details should be confirmed with NRAC]

### Sectors

Research identified the following general sectors along the Meadow River corridor [UNVERIFIED — sector names may differ in local usage]:

1. **Main Area / Roadside** — The most accessible boulders, visible from or near the road. Concentrated problems on freestanding blocks and roadcut boulders.
2. **River Boulders** — Boulders along the Meadow River bank, short walk from road pulloffs. Some require creek crossing in high water.
3. **Upstream / Upper Meadow** — Less developed area further upstream with additional bouldering potential.

### Problem Counts

| Grade Band | Estimated Count | Density | Style Notes |
|-----------|----------------|---------|-------------|
| V0-V3 | 15-30 | Some | Jugs, easy overhangs, traverses [UNVERIFIED] |
| V4-V6 | 20-40 | Many | Overhanging faces, compression, pinches [UNVERIFIED] |
| V7-V10+ | 10-25 | Some | Steep compression, roof pulls, powerful sequences [UNVERIFIED] |
| **Total** | **50-100** | — | Range reflects documentation gaps [UNVERIFIED] |

**Note**: Meadow River bouldering is a developing scene. Many problems are documented only in local guidebooks or word-of-mouth. The actual count may be higher than Mountain Project listings suggest.

### Parking & GPS

| Location | GPS (approx.) | Notes |
|----------|--------------|-------|
| Main pulloff / roadside parking | 38.0210 N, -80.8590 W | Gravel pulloff along Rt. 60/Meadow River Rd [UNVERIFIED] |
| Upper area pulloff | 38.0240 N, -80.8550 W | Secondary pulloff ~0.5 mi upstream [UNVERIFIED] |

- Google Maps link: [Main area](https://maps.google.com/?q=38.0210,-80.8590) [UNVERIFIED]
- **All GPS coordinates are approximate** and should be verified against Google Maps satellite view
- Route from Fayetteville: Take US-19 S to US-60 E toward Meadow Bridge. ~25-35 min. [UNVERIFIED — verify exact route]

### Approach

- Distance from parking to boulders: **50-200 yards** (roadside sector) to **0.25 miles** (river boulders) [UNVERIFIED]
- Elevation change: Minimal — boulders are near road level or a short walk to the river
- Approach time: **2-10 minutes** for most problems
- Trail quality: Informal paths from road pulloffs, some bushwhacking to river boulders

### February Conditions

- **Winter road access**: US-60 is a state highway, plowed and maintained year-round. Road pulloffs may have snow/ice accumulation but are generally accessible. [UNVERIFIED]
- **Approach hazards**: Minimal — short, mostly flat approaches. River boulders may require crossing a shallow creek (water level varies). Ice on rocks near the river.
- **Microspikes**: Generally not needed for the approach (unlike gorge descents)

### Weather Resilience

| Factor | Detail |
|--------|--------|
| **Rating** | **Good** |
| **Shelter** | Many problems are on heavily overhanging faces and roofs — these stay dry during rain |
| **Seepage** | Some seepage on crack systems and horizontal breaks after heavy/prolonged rain [UNVERIFIED] |
| **Drying** | Overhanging problems: already dry. Vertical: 1-3 hrs (sun+wind). Steep nature means faster drying overall. |
| **Wind** | Moderate — river corridor funnels wind, aiding drying |
| **Rain verdict** | **Yes — overhanging problems climbable during active rain.** The steep nature of Meadow River rock means a significant portion of problems stay dry. Best rain-day bouldering option in the region. |

### Land Management

- **NOT NPS land** — Meadow River is outside the NRG National Park boundary [UNVERIFIED — confirm exact jurisdiction]
- Land ownership: Mix of private land and public road right-of-way [UNVERIFIED]
- **Access**: NRAC monitors access. Check newriverclimbing.net for alerts before visiting.
- No entrance fees, no permits required [UNVERIFIED]
- Crash pads permitted, chalk permitted [UNVERIFIED]
- **Leave No Trace**: Pack out all trash. Respect private property boundaries.

---

## Verified Data: Summersville Lake

**Date**: 2026-02-10
**Source**: Training data (cutoff May 2025) derived from Mountain Project, USACE Huntington District publications, local guidebooks, and general NRG climbing knowledge. **Web verification was attempted but limited in this session.** All items flagged per Constitution Principle VI.

### Overview

Summersville Lake is a USACE (U.S. Army Corps of Engineers) reservoir on the Gauley River, approximately 35 minutes north of Fayetteville. The lake is famous for its clear water and sandstone cliffs. In winter, the USACE draws the lake down ~77 feet from summer pool (~1,652 ft elevation) to winter pool (~1,575 ft), exposing extensive lakeshore sandstone boulders that are submerged in summer. February is at or near maximum drawdown, making it the prime time for lakeshore bouldering. The exposed lake bed provides flat sandstone landing zones — some of the best landings in the region.

### Sectors

| Sector | Description | Winter Access |
|--------|-------------|--------------|
| **Long Point** | Most reliable winter access. Boulders along the lakeshore below Long Point trail. Best documented sector. | Open year-round via WV Rt. 129 [UNVERIFIED] |
| **Pirates Cove** | Lakeshore bouldering west of Long Point. Good beginner problems on low-angle exposed blocks. | Access road may be gated Nov-Apr [UNVERIFIED] |
| **Orange Oswald Wall area** | Cliff-base boulders below the Orange Oswald Wall. More developed sport climbing area, but cliff-base blocks have bouldering. | Access via Long Point or lake road [UNVERIFIED] |
| **Dam area / Salmon Run** | Boulders near the dam outflow on the Gauley River side. Less documented. | May require alternate access in winter [UNVERIFIED] |

### Problem Counts

| Grade Band | Estimated Count | Density | Style Notes |
|-----------|----------------|---------|-------------|
| V0-V3 | 60-100 | Many | Slabs, easy traverses, low-angle faces on lakeshore blocks. Best beginner bouldering in the region. [UNVERIFIED] |
| V4-V6 | 50-90 | Many | Vertical faces, crimps, technical footwork on sandstone [UNVERIFIED] |
| V7-V10+ | 15-40 | Some | Steeper faces and overhangs, typically on larger cliff-base blocks [UNVERIFIED] |
| **Total** | **150-250** | — | Highest problem density in the region. Winter drawdown exposes additional problems. [UNVERIFIED] |

**Note**: Problem counts include both year-round accessible boulders and winter-drawdown-exposed boulders. The drawdown-exposed problems are only available roughly November through April.

### Parking & GPS

| Location | GPS (approx.) | Notes |
|----------|--------------|-------|
| Long Point Trailhead | 38.1350 N, -80.8920 W | Off WV Rt. 129. Small gravel lot, ~10-15 vehicles. Most reliable winter access. [UNVERIFIED] |
| Summersville Lake boat ramp (main) | 38.1420 N, -80.8800 W | USACE boat ramp. May be gated Nov-Apr. [UNVERIFIED] |

- Google Maps link: [Long Point](https://maps.google.com/?q=38.1350,-80.8920) [UNVERIFIED]
- Route from Fayetteville: Take US-19 N ~20 mi, exit toward Summersville Lake / WV Rt. 129. ~35-40 min. [UNVERIFIED]
- **Long Point trailhead is the recommended winter access point** — other access roads and boat ramp parking may be gated.

### Approach

- **From Long Point Trailhead**: ~0.5-1.0 mile hike to lakeshore boulders [UNVERIFIED]
- Elevation change: ~150-250 ft descent to lake level [UNVERIFIED]
- Approach time: 15-25 minutes
- Trail quality: NPS/USACE-maintained trail to Long Point overlook; climber trails descend to lakeshore

### February Conditions

- **Winter gate status**: Some USACE access roads are gated November through April. Long Point trailhead off WV Rt. 129 is the most reliably open. [UNVERIFIED — call USACE (304) 872-3459 to confirm]
- **Lake level**: At or near maximum winter drawdown (~1,575 ft). Extensive lakeshore exposed. [UNVERIFIED — verify 2026 schedule with USACE]
- **Approach hazards**: Trail to lakeshore can be muddy/icy. The exposed lake bed is generally flat sandstone but can be slippery when wet or icy.
- **Landing zones**: Flat exposed lakebed sandstone provides excellent pad placement and natural flat landings.

### Weather Resilience

| Factor | Detail |
|--------|--------|
| **Rating** | **Poor** |
| **Shelter** | Very little — most boulders are freestanding on exposed lakeshore with no overhead canopy or cliff shelter |
| **Seepage** | Minimal seepage (freestanding blocks), but surface water pools on flat lakebed after rain |
| **Drying** | Slow for vertical/slab. Exposed lakeshore gets good wind and sun, but lack of overhang means rain hits all surfaces. 3-6+ hrs for vertical after rain. |
| **Wind** | Exposed — lakeshore is open with significant wind exposure. Aids drying but uncomfortable in cold. |
| **Rain verdict** | **No — not recommended during active rain.** Virtually all problems are exposed. Wait for dry conditions. The wind and open sun exposure mean it dries faster than sheltered gorge areas in direct sunlight, but still needs several hours. |

### Land Management

- **USACE (U.S. Army Corps of Engineers)** manages Summersville Lake and surrounding land
- **NOT NPS land** — different regulations than gorge boulders
- No climbing-specific permit required [UNVERIFIED]
- No entrance fee for lakeshore access [UNVERIFIED]
- Crash pads permitted [UNVERIFIED]
- USACE rules: No bolting, no fixed gear on USACE property. Does not affect bouldering. [UNVERIFIED]
- **Pre-trip verification**: Call USACE Summersville Lake at (304) 872-3459

---

## Verified Data: NPS Bouldering Regulations

**Date**: 2026-02-10
**Source**: Training data (cutoff May 2025) derived from NPS publications, nps.gov/neri, Superintendent's Compendium references, and NRAC community knowledge. **Web verification was attempted but limited.** All items flagged per Constitution Principle VI.

NPS regulations apply ONLY to the Gorge Boulders area (Endless Wall, Nuttall, Bridge Buttress, Kaymoor). Meadow River and Summersville Lake are NOT NPS land.

| Topic | Status | Source | Confidence |
|-------|--------|--------|------------|
| Bouldering permitted | Yes, year-round | NPS climbing management plan | [UNVERIFIED] |
| Entrance fee | None for NRG National Park | NPS general info | [UNVERIFIED] |
| Crash pads | Permitted | NPS climbing page | [UNVERIFIED] |
| Chalk | Permitted; brush tick marks after climbing | NPS climbing page / community standard | [UNVERIFIED] |
| Brushing | Nylon/boar's hair brushes ONLY — no wire brushes | NPS / NRAC community standard | [UNVERIFIED] |
| Group size limit | No climbing-specific limit. General NPS group size limits may apply for organized events (>25 people). Our group of 5-8 is fine. | NPS Superintendent's Compendium | [UNVERIFIED] |
| Peregrine falcon closures | Seasonal (typically March 15 - July 15). **February is NOT affected.** | NPS annual closure notices | [UNVERIFIED] |
| Permits | Not required for recreational bouldering or climbing | NPS climbing page | [UNVERIFIED] |
| Fixed hardware | Not relevant to bouldering. Bolting rules apply to routes only. | NPS climbing management plan | [UNVERIFIED] |
| Fayette Station Road winter status | Road descends steeply into gorge. May be closed or restricted in icy/snowy conditions. Check with NPS before relying on it for Bridge Buttress access. | NPS / local knowledge | [UNVERIFIED] |
| Winter parking hours | Canyon Rim Visitor Center lot is open year-round. Hours may be reduced in winter (check NPS). Other trailhead lots are generally open 24/7. | NPS | [UNVERIFIED] |

**Pre-trip verification contacts**:
- NPS Canyon Rim Visitor Center: (304) 574-2115
- NPS website: nps.gov/neri/planyourvisit/climbing.htm
- Superintendent's Compendium: nps.gov/neri/learn/management/superintendents-compendium.htm

---

## Verified Data: Gorge Boulders — Per-Sector Research

**Date**: 2026-02-10
**Source**: Training data (cutoff May 2025) derived from Mountain Project listings, NPS publications (nps.gov/neri), the New River Gorge climbing guidebook series (Mike Williams / Rick Thompson editions), NRAC community knowledge, and widely published GPS/trailhead data. **Web verification was attempted but WebSearch and WebFetch tools were denied in this session.** All items are flagged per Constitution Principle VI.

**Web sources that should be checked manually before implementation**:
- Mountain Project NRG Bouldering: https://www.mountainproject.com/area/105855991/new-river-gorge (search "bouldering" filter)
- NPS Climbing Page: https://www.nps.gov/neri/planyourvisit/climbing.htm
- NPS Superintendent's Compendium: https://www.nps.gov/neri/learn/management/superintendents-compendium.htm
- NRAC: https://newriverclimbing.net
- 27 Crags NRG: https://27crags.com (search "New River Gorge bouldering")
- SendAge / theCrag NRG listings

---

### Sector 1: Endless Wall / Fern Creek

**Overview**: Endless Wall is the most iconic cliff line at NRG, running roughly 1.5 miles along the gorge rim and cliff base on the north side of the gorge. Fern Creek is a drainage area at the eastern end of the Endless Wall trail system. While Endless Wall is overwhelmingly known for its sport and trad routes (400+ routes), cliff-base talus boulders and freestanding blocks at the base provide bouldering opportunities. Fern Creek has some of the more concentrated cliff-base bouldering.

**Problem counts**:
- Estimated total bouldering problems: **15-30** [UNVERIFIED — NRG gorge bouldering is sparsely documented; Mountain Project likely lists fewer than 20 specific boulder problems in this area]
- V0-V3: Few (5-10) [UNVERIFIED]
- V4-V6: Few (5-12) [UNVERIFIED]
- V7-V10+: Few (3-8) — predominantly overhanging compression and roof problems on cliff-base boulders [UNVERIFIED]
- Style: Overhanging faces, roofs, compression, aretes on Nuttall sandstone blocks. Steep terrain. Landings are uneven talus in many spots — crash pad placement matters.

**Trailhead / Parking GPS**:
- **Endless Wall Trailhead parking lot**: 38.0670 N, -81.0785 W [UNVERIFIED — approximate, derived from known NPS trailhead location on Lansing-Edmond Road]
- Google Maps link: https://maps.google.com/?q=38.0670,-81.0785 [UNVERIFIED]
- Parking lot is paved, NPS-maintained, ~15-20 vehicle capacity
- Access road: From Fayetteville, take US-19 N to Lansing-Edmond Road (CR 82), turn right, follow signs to Endless Wall trailhead. ~10 min from town. [UNVERIFIED — verify road name/number]

**Approach**:
- Distance: ~0.7-1.0 miles from parking to cliff-base bouldering areas [UNVERIFIED]
- Elevation change: ~250-350 ft descent from rim to gorge floor (steep in sections) [UNVERIFIED]
- Trail quality: Well-maintained NPS trail along the rim; descent to cliff base uses climber-maintained spur trails that are steeper, less maintained, and rooty/rocky
- Approach time: 20-35 minutes depending on which boulders are targeted

**February trail hazards**:
- **Ice is the primary hazard.** The descent trail from the rim to cliff base is north-facing and shaded, meaning ice persists for days after a freeze. Steel ladder/steps on some descent sections become treacherous when iced. [UNVERIFIED — verify if steel steps exist on this particular trail or only at Kaymoor]
- Wooden boardwalk sections along the rim trail can be icy when wet/frozen
- Microspikes strongly recommended for the descent
- Mud on the cliff-base trail after rain/snowmelt
- Fallen leaves over ice obscure slippery spots

**Shelter / rain info**:
- **Rain resilience: Good** — The cliff line overhangs significantly in many places, creating natural rain shelter at the cliff base. Some boulders sit directly under overhanging cliff bands with essentially zero rain exposure.
- Specific sheltered boulders: The large cliff-base boulders beneath the overhanging headwall sections of Endless Wall stay dry during rain. Problems on the underside of these roof-like formations are fully sheltered. [UNVERIFIED — specific boulder names not confirmed; the guidebook may name these individually]
- Fern Creek drainage area may have seepage issues during/after heavy rain — water flows through the creek gully
- Wind: Sheltered — deep in the gorge, wind is minimal at cliff base

---

### Sector 2: Nuttall / Fern Buttress

**Overview**: The Nuttall area (sometimes "Nuttall Slab" area) and Fern Buttress are located along the gorge, accessed from near the south side of the New River Gorge Bridge or via the Fern Creek / Kaymoor area trails. Fern Buttress is a distinct cliff section with some cliff-base talus bouldering. This sector is less trafficked for bouldering than Endless Wall.

**Problem counts**:
- Estimated total bouldering problems: **10-20** [UNVERIFIED — this sector has less documented bouldering than Endless Wall]
- V0-V3: Few (3-6) [UNVERIFIED]
- V4-V6: Few (3-8) [UNVERIFIED]
- V7-V10+: Few (2-5) [UNVERIFIED]
- Style: Similar to Endless Wall — overhanging Nuttall sandstone, compression, some vertical face problems on talus blocks

**Trailhead / Parking GPS**:
- Primary access is typically from the **Fayette Station Road / Tunney Hunsaker Convention Center area** or from the Long Point trailhead on the south rim
- **Long Point Trailhead** (south rim access): 38.0710 N, -81.0835 W [UNVERIFIED — approximate]
- Google Maps link: https://maps.google.com/?q=38.0710,-81.0835 [UNVERIFIED]
- Alternatively accessed from the **Fern Creek Trailhead** near Endless Wall: same parking as Sector 1 above [UNVERIFIED]
- Parking: Varies by access point. Long Point has a small NPS lot (~10 vehicles). [UNVERIFIED]

**Approach**:
- Distance: ~0.5-1.0 miles from nearest parking [UNVERIFIED]
- Elevation change: ~200-300 ft descent [UNVERIFIED]
- Approach time: 15-30 minutes
- Trail quality: Combination of NPS-maintained trail and climber spur trails

**February trail hazards**:
- Similar to Endless Wall: icy descent sections, especially on north-facing shaded slopes
- Microspikes recommended
- Less foot traffic than Endless Wall means less packed/maintained trail in winter

**Shelter / rain info**:
- **Rain resilience: Good** — Cliff-base overhangs provide shelter similar to Endless Wall
- Fern Buttress has some sizeable overhanging cliff bands that shelter boulders beneath
- Less documentation on specific sheltered boulders than Endless Wall [UNVERIFIED]
- Wind: Sheltered (gorge interior)

---

### Sector 3: Bridge Buttress

**Overview**: Bridge Buttress is the cliff area immediately adjacent to the New River Gorge Bridge on the north side, accessed from the Fayette Station Road. This is one of the most accessible cliff areas in the gorge — the approach from the parking area near the NPS Bridge Walk parking / Fayette Station area is the shortest in the gorge. While primarily known for sport climbing (classic routes like "The Entertainer" 5.12a and "New Yosemite" 5.11c), cliff-base boulders provide some bouldering.

**Problem counts**:
- Estimated total bouldering problems: **10-20** [UNVERIFIED]
- V0-V3: Few (3-7) — some easy traverses and slab problems on lower-angle blocks [UNVERIFIED]
- V4-V6: Few (4-8) [UNVERIFIED]
- V7-V10+: Few (2-5) — overhanging cliff-base blocks [UNVERIFIED]
- Style: Mixed — some vertical face, some overhanging. The talus field below Bridge Buttress has freestanding blocks and cliff-base boulders.

**Trailhead / Parking GPS**:
- **Bridge Buttress / Fayette Station area parking**: 38.0705 N, -81.0830 W [UNVERIFIED — approximate, near the NPS Canyon Rim Visitor Center / Fayette Station Road descent area]
- Alternative: Park at the **Canyon Rim Visitor Center** (NPS): 38.0700 N, -81.0750 W [UNVERIFIED]
- Google Maps link: https://maps.google.com/?q=38.0705,-81.0830 [UNVERIFIED]
- Parking: Paved NPS lots. Canyon Rim Visitor Center lot is large (50+ vehicles) and plowed in winter.

**Approach**:
- Distance: **~0.2-0.4 miles** — the shortest approach in the gorge [UNVERIFIED]
- Elevation change: ~100-200 ft descent (short but steep) [UNVERIFIED]
- Approach time: **5-15 minutes** — fastest access to gorge bouldering
- Trail quality: NPS-maintained trail. Stairs in places.

**February trail hazards**:
- Short approach reduces exposure to icy conditions, but the descent steps can ice up
- Fayette Station Road itself may be closed or restricted in winter conditions — it descends steeply into the gorge and is not always plowed/maintained [UNVERIFIED — verify winter status of Fayette Station Road with NPS]
- **IMPORTANT**: If Fayette Station Road is closed in winter, approach changes to rim-side trail from Canyon Rim Visitor Center, which is longer (~0.5-0.7 miles) [UNVERIFIED]
- Microspikes still recommended for the descent trail

**Shelter / rain info**:
- **Rain resilience: Fair** — Some cliff-base shelter exists but the area is more open and exposed than the deeper gorge sectors (Endless Wall / Nuttall). The cliff line here is less consistently overhanging.
- Some boulders beneath overhanging sections stay dry, but a smaller percentage of problems are fully sheltered compared to Endless Wall
- The bridge itself does NOT provide useful rain shelter for bouldering (boulders are not directly under the bridge span)
- Wind: Moderate — closer to the gorge rim and bridge opening, more wind exposure than deep-gorge sectors
- Seepage: Moderate after heavy rain, particularly on problems near crack systems in the cliff band

---

### Sector 4: Kaymoor

**Overview**: Kaymoor is a historic coal mining area on the south side of the gorge, known for its extremely steep and overhanging sport climbing (famous routes like "Flight of the Gumby" 5.11b). Access involves a long approach including the famous Kaymoor miners' steel staircase. While bouldering exists on cliff-base blocks, Kaymoor is primarily a roped climbing destination.

**Problem counts**:
- Estimated total bouldering problems: **5-15** [UNVERIFIED — least documented bouldering of the four sectors]
- V0-V3: Few (1-4) [UNVERIFIED]
- V4-V6: Few (2-5) [UNVERIFIED]
- V7-V10+: Few (2-6) — the overhanging cliff character suggests harder problems dominate what exists [UNVERIFIED]
- Style: Predominantly overhanging and roof problems on cliff-base blocks, matching the character of the main cliff (extremely overhanging Nuttall sandstone)

**Trailhead / Parking GPS**:
- **Kaymoor Trailhead (upper)**: 38.0580 N, -81.0690 W [UNVERIFIED — approximate, off Kaymoor Road south of the gorge]
- Google Maps link: https://maps.google.com/?q=38.0580,-81.0690 [UNVERIFIED]
- Parking: Small NPS lot at Kaymoor trailhead, ~8-12 vehicles [UNVERIFIED]
- Access road: From Fayetteville, cross the bridge, turn onto Kaymoor Road. ~10 min drive. [UNVERIFIED — verify road name]

**Approach — the steel staircase**:
- Distance: **~1.0-1.5 miles** from parking to cliff base [UNVERIFIED]
- Elevation change: **~600-800 ft descent** (one of the largest approach descents in the gorge) [UNVERIFIED]
- Approach time: **30-50 minutes** one way
- **The Kaymoor Miners Trail features a historic steel staircase** — over 800 steps descending the gorge wall. This is a maintained NPS historic structure, originally built for coal miners accessing the mines. The stairs are steel grate construction.
- The staircase is the defining feature of the Kaymoor approach and is both an attraction and a hazard.

**February trail hazards — CRITICAL**:
- **The steel staircase becomes extremely dangerous when iced or snow-covered.** Steel grate steps are inherently slippery when wet or icy. In February, shaded sections of the staircase may be iced for extended periods.
- **Recommendation: Do NOT use Kaymoor as a primary bouldering destination in February unless conditions have been dry and above freezing for several consecutive days.** [UNVERIFIED — this is a safety-based conservative recommendation]
- Microspikes are ESSENTIAL if attempting the Kaymoor approach in winter. Even with microspikes, steel grate steps provide poor traction compared to rock/soil trails.
- The long approach means more exposure time to icy conditions, and the return hike (800+ steps ascending) is strenuous
- Handrails exist on portions of the staircase but may not be continuous [UNVERIFIED]

**Shelter / rain info**:
- **Rain resilience: Fair** — The cliff base is extremely overhanging (Kaymoor is known for its steepness), so cliff-base boulders are well-sheltered from rain. However, the approach hazard in wet/icy conditions severely limits practical rain-day usability.
- The rock itself may offer the best overhang shelter of any sector, but the approach negates this advantage in February
- Wind: Moderate — south-facing aspect gets more sun but also more wind in certain conditions [UNVERIFIED]

---

### Mountain Project NRG Bouldering References

The following Mountain Project URLs are the expected listing pages for NRG bouldering. **These should be manually verified** as web access was denied during this research session:

| Resource | URL | Expected Content |
|----------|-----|-----------------|
| NRG Main Area | https://www.mountainproject.com/area/105855991/new-river-gorge | Parent area; filter by "Boulder" type to see all bouldering |
| Endless Wall | https://www.mountainproject.com/area/106031227/endless-wall | Route/problem listings; filter for boulders |
| Bridge Buttress | https://www.mountainproject.com/area/105855995/bridge-buttress | Route/problem listings; filter for boulders |
| Kaymoor | https://www.mountainproject.com/area/105856053/kaymoor | Route/problem listings; filter for boulders |
| Fern Buttress | https://www.mountainproject.com/area/105856009/fern-buttress | Route/problem listings; filter for boulders [UNVERIFIED — URL may differ] |
| NRG Bouldering (if separate area) | Search: "New River Gorge bouldering" on mountainproject.com | Some areas list bouldering under a separate sub-area |

**Note**: Mountain Project's NRG listings are heavily weighted toward sport/trad routes. Bouldering may be listed as sub-areas within cliff areas or may require filtering by "Boulder" type. Problem counts on Mountain Project may significantly undercount actual bouldering because (a) NRG bouldering is a developing scene, (b) many problems are documented only in local guidebooks or word-of-mouth, and (c) the gorge boulder problems often live under route-climbing area pages where they are easy to miss.

**Alternative bouldering databases to check**:
- **27crags.com**: Sometimes has NRG bouldering listed separately
- **theCrag.com**: May have user-submitted NRG boulder problems
- **8a.nu**: May have logged NRG boulder ascents
- **NRAC (newriverclimbing.net)**: Local access coalition, may have area-specific info
- **Guidebooks**: "New River Rock" by Mike Williams has historically been the definitive NRG climbing guide; later editions may include bouldering sections. "Bouldering in West Virginia" (if it exists) would be the most relevant. [UNVERIFIED — confirm guidebook title/availability at Water Stone Outdoors in Fayetteville]

---

### Gorge Boulders — Composite Summary Table

| Sector | Est. Problems | V0-V3 | V4-V6 | V7-V10+ | Rain | Approach | Feb Risk |
|--------|--------------|-------|-------|---------|------|----------|----------|
| Endless Wall / Fern Creek | 15-30 | Few | Few | Few | Good | 20-35 min, 300 ft desc. | Moderate (icy descent) |
| Nuttall / Fern Buttress | 10-20 | Few | Few | Few | Good | 15-30 min, 250 ft desc. | Moderate (icy descent) |
| Bridge Buttress | 10-20 | Few | Few | Few | Fair | 5-15 min, 150 ft desc. | Low-Moderate |
| Kaymoor | 5-15 | Few | Few | Few | Fair* | 30-50 min, 700 ft desc. | **HIGH (steel stairs + ice)** |

*Kaymoor cliff-base shelter is excellent but approach hazard makes it impractical for February wet weather.

**All problem counts are [UNVERIFIED].** The gorge bouldering scene is developing and sparsely documented. Actual problem counts may be higher (locals know problems not on Mountain Project) or lower (some listed "problems" may be contrived eliminates at route bases).

---

### GPS Coordinates Summary (All [UNVERIFIED])

| Sector | Parking Lot GPS | Google Maps Link |
|--------|----------------|-----------------|
| Endless Wall | 38.0670, -81.0785 | [Map](https://maps.google.com/?q=38.0670,-81.0785) |
| Nuttall / Long Point | 38.0710, -81.0835 | [Map](https://maps.google.com/?q=38.0710,-81.0835) |
| Bridge Buttress | 38.0705, -81.0830 | [Map](https://maps.google.com/?q=38.0705,-81.0830) |
| Kaymoor | 38.0580, -81.0690 | [Map](https://maps.google.com/?q=38.0580,-81.0690) |

**IMPORTANT**: These GPS coordinates are approximate and derived from training data knowledge of NPS trailhead locations. They should be verified against Google Maps satellite view and NPS trail maps before use for navigation. Errors of up to 0.005 degrees (~500 meters) are possible.

---

## Critical Data Gaps

These items require live web verification before implementation and should be flagged with `[UNVERIFIED]` in area profiles:

1. **Meadow River**: Exact parking GPS, sector names, verified problem counts, land ownership
2. **Summersville Lake**: Exact 2026 drawdown schedule, winter gate status, verified V7-V10+ problem count
3. **Gorge Boulders**: Per-sector verified problem counts (current estimates are from training data, not live Mountain Project queries); specific sheltered boulder NAMES (e.g., "The Whale," "The Ship" — if these exist); Fayette Station Road winter closure status; steel staircase condition
4. **NPS Regulations**: All items marked [UNVERIFIED] should be re-confirmed via NPS website or phone call
5. **GPS Coordinates**: All parking lot coordinates are approximate and must be verified against Google Maps / NPS maps
6. **Mountain Project listings**: The MP URLs listed above should be visited and filtered for "Boulder" type problems to get accurate counts and specific problem names/grades

---

## Web Access Limitation Notice

**This research session was unable to perform live web lookups.** Both WebSearch and WebFetch tools were denied. All data in the "Verified Data: Gorge Boulders" section above comes from the model's training data (cutoff May 2025) and general knowledge of the NRG climbing area. This data has NOT been cross-referenced against live Mountain Project pages, the NPS website, or Google Maps.

**Before writing area profile documents (tasks T009-T011), the following manual verification steps are recommended**:

1. Visit each Mountain Project URL above and count boulder problems by grade
2. Visit Google Maps to verify parking lot GPS coordinates
3. Check nps.gov/neri for current winter road/trail status
4. Call Water Stone Outdoors (304-574-2425) for current local bouldering beta
5. Check NRAC (newriverclimbing.net) for any access alerts

---

## Key Contacts for Verification

| Contact | Phone | Use For |
|---------|-------|---------|
| NPS Canyon Rim Visitor Center | (304) 574-2115 | Winter trail conditions, parking, regulations |
| NPS Main Office | (304) 465-0508 | Climbing management plan, regulations |
| USACE Summersville Lake | (304) 872-3459 | Lake level, drawdown schedule, winter gate status |
| Water Stone Outdoors (Fayetteville) | (304) 574-2425 | Local beta, guidebooks, Meadow River access |
| NRAC | newriverclimbing.net | Access alerts, area updates, ethics |
