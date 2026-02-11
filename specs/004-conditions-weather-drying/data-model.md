# Data Model: Conditions, Weather & Drying Guide

**Feature**: 004-conditions-weather-drying

---

## Entity: Rock Behavior Profile

The authoritative reference for Nuttall sandstone behavior. Single instance — one rock type covers the entire region.

### Attributes

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| rock_type | string | Yes | "Nuttall sandstone" |
| composition | string | Yes | Quartz content, cement type, hardness |
| friction_dry | string | Yes | Friction behavior when dry (excellent, "bitey") |
| friction_wet | string | Yes | Friction behavior when wet (dangerously low, chalk fails) |
| friction_frozen | string | Yes | Friction behavior when frozen dry (excellent — skin grips well) |
| seepage_sources | list[string] | Yes | Where water emerges: horizontal breaks, crack systems, formation contacts |
| seepage_lag | string | Yes | Time delay between rain stopping and seepage increasing (4-8 hrs) |
| drying_overhang | string | Yes | Drying time for overhangs (0-1 hr — already dry) |
| drying_vertical_fast | string | Yes | Drying time for vertical in sun+wind (2-6 hrs) |
| drying_vertical_slow | string | Yes | Drying time for vertical in overcast+cold (8-16 hrs) |
| drying_slab_fast | string | Yes | Drying time for slab in sun+wind (4-12 hrs) |
| drying_slab_slow | string | Yes | Drying time for slab in overcast+cold (24-48+ hrs) |
| surface_dry_vs_friction | string | Yes | Distinction between "surface dry" and "friction restored" |
| community_ethic | string | Yes | "Do not climb wet sandstone" — rock preservation reasoning |
| freeze_thaw_behavior | string | Yes | How rock transitions through frozen → thaw → wet → drying |
| comparison_notes | string | No | How Nuttall compares to Cumberland, Corbin, Font sandstones |

### Relationships

- Referenced by **Area Weather Behavior** entries (drying modifiers per area)

---

## Entity: February Weather Profile

Seasonal climate data for the Fayetteville/NRG area. Single instance for the trip region.

### Attributes

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| location | string | Yes | "Fayetteville, WV / New River Gorge area" |
| data_source | string | Yes | NOAA climate normals, nearest station (Beckley) |
| avg_high | string | Yes | Average February high temperature (42-45°F) |
| avg_low | string | Yes | Average February low temperature (23-27°F) |
| precip_monthly | string | Yes | Average February precipitation (~3.1 in) |
| precip_days | string | Yes | Number of precipitation days (~12-15) |
| precip_types | string | Yes | Rain, sleet, snow, mixed — frequency of each |
| wind_avg | string | Yes | Average wind speed (~6-7 mph) |
| wind_prevailing | string | Yes | Prevailing direction (west) |
| daylight_hours | string | Yes | Usable daylight (~10.5-11 hrs, gorge reduces to ~6-7 hrs direct sun) |
| sunrise | string | Yes | Approximate sunrise time (~7:06-7:15 AM) |
| sunset | string | Yes | Approximate sunset time (~6:02-6:09 PM) |
| freeze_thaw_days | string | Yes | Estimated freeze/thaw crossing days (~18-22 per Feb) |
| multi_day_rain_freq | string | Yes | How often multi-day rain events occur (~2-3 per Feb) |
| climbable_days_7day | string | Yes | Expected climbable days in a 7-day window (~3-5) |

### Relationships

- Referenced by **Daily Decision Framework** (weather → activity mapping)
- Cross-referenced with **Area Weather Behavior** (area-specific deviations)

---

## Entity: Area Weather Behavior

Per-area microclimate characteristics. One entry per bouldering area and trail system.

### Attributes

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| area_name | string | Yes | Area name (must match Feature 001/003 names exactly) |
| area_type | enum | Yes | "bouldering" or "trail_system" |
| wind_exposure | enum | Yes | LOW / MODERATE / HIGH |
| sun_pattern | string | Yes | Sun/shade characteristics (morning sun, gorge shade, etc.) |
| shelter_quality | enum | Yes | POOR / FAIR / GOOD / EXCELLENT |
| shelter_description | string | Yes | What provides shelter (cliff overhangs, canopy, etc.) |
| drying_speed_rank | integer | Yes | 1=fastest, 3=slowest (among bouldering areas) |
| drying_modifier | string | Yes | How this area differs from baseline drying times |
| humidity_relative | string | Yes | Higher/lower than baseline (gorge floor = higher) |
| best_conditions | string | Yes | Weather scenarios when this area is ideal |
| worst_conditions | string | Yes | Weather scenarios when this area should be avoided |
| profile_link | string | Yes | Relative link to area/trail profile document |

### Instances

| Area | Wind | Shelter | Drying Rank | Best For | Worst For |
|------|------|---------|-------------|----------|-----------|
| Meadow River | MODERATE | GOOD | 1 (fastest) | Post-rain (overhangs dry, wind aids) | Calm overcast (still good due to steep rock) |
| Summersville Lake | HIGH | POOR | 2 (moderate) | Clear+cold+dry (open sun, friction) | Active rain (no shelter at all) |
| Gorge Boulders | LOW | EXCELLENT | 3 (slowest) | Active rain (cliff-base shelter) | Post-rain overcast (slowest drying) |

### Relationships

- References **Rock Behavior Profile** for baseline drying times
- Links to Feature 001 area profiles (`areas/*.md`)
- Links to Feature 003 trail profiles (`trails/*.md`)

---

## Entity: Daily Decision Framework

Structured weather-to-activity mapping. One row per weather scenario.

### Attributes

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| scenario_name | string | Yes | Short description (e.g., "Clear + cold + frozen") |
| temperature_range | string | Yes | Approximate temp range for this scenario |
| precipitation | string | Yes | None / light / heavy / post-rain |
| wind | string | Yes | Calm / moderate / strong |
| activity_recommendation | string | Yes | Climb / ride / rest / mixed |
| area_recommendation | string | Yes | Which area(s) to prioritize |
| time_window | string | Yes | Best climbing/riding window for this scenario |
| notes | string | No | Additional guidance |

### Instances (minimum 6 per FR-005)

1. Clear + cold + frozen ground
2. Clear + warm (above freezing all day)
3. Overcast + dry
4. Active rain
5. Post-rain drying (sunny + wind)
6. Freeze/thaw transition day

### Relationships

- References **February Weather Profile** for climate context
- References **Area Weather Behavior** for area recommendations
- Cross-references trails for riding recommendations

---

## Document Schema

### Conditions Guide (`conditions/README.md`)

Single file with section anchors for direct linking.

| Section | Content | Maps To |
|---------|---------|---------|
| Quick Reference (top) | Can-I-climb-now decision tree + drying table | Rock Behavior Profile (summary) |
| Nuttall Sandstone Primer | Composition, friction, seepage, drying, ethic | Rock Behavior Profile |
| Drying Reference Table | Wall angle × conditions matrix | Rock Behavior Profile (drying fields) |
| February Weather | Seasonal data, temperature, precip, wind, daylight | February Weather Profile |
| Daily Decision Framework | Weather scenario → activity → area table | Daily Decision Framework |
| Per-Area Weather Matrix | Comparison of all areas by weather conditions | Area Weather Behavior |
| Freeze/Thaw Guide | Frozen rock behavior, thaw timeline, safety | Rock Behavior Profile (freeze fields) |
| Sources | Citations and verification notes | All entities |
