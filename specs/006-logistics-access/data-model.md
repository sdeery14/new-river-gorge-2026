# Data Model: Logistics & Access Cheat Sheets

**Feature**: 006-logistics-access | **Date**: 2026-02-11

## Entities

### Access Point

An entry in the master access table representing a parking/trailhead location for a bouldering area or trail system.

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| Name | Yes | Location name (area or trail system) | Meadow River |
| Type | Yes | `Bouldering` or `Trail` | Bouldering |
| Drive Time | Yes | From Fayetteville | ~30 min |
| Route Summary | Yes | Short text directions | US-60 E, 30 min |
| GPS Link | Yes | Tappable Google Maps link to parking | [Maps link] |
| Parking Note | Yes | One-line: lot type, capacity, winter status | Gravel pulloffs, 5-10 cars, plowed |
| Approach Note | Yes | One-line: distance, time, difficulty | 200 yds, 5 min, flat |
| Access Warning | Conditional | One-line warning if Feb hazard exists | ⚠️ Road may close in ice |
| Profile Link | Yes | Link to full area/trail profile | [Meadow River](../areas/meadow-river.md) |
| Land Manager | Yes | NPS / USACE / State Parks / Private | Private / County ROW |

**Validation rules**:
- Every bouldering area and trail system from Features 001 and 003 MUST have at least one Access Point row
- GPS Link MUST be a tappable Google Maps URL
- Access Warning is required if any February-specific hazard exists (FR-004)
- Gorge Boulders has multiple Access Points (one per sector with distinct parking)

### Regulation Set

A collection of land-management rules applicable to one or more bouldering areas.

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| Land Manager | Yes | Authority name | NPS — New River Gorge National Park |
| Applicable Areas | Yes | Which areas this covers | Gorge Boulders (all sectors) |
| Crash Pads | Yes | Permitted / Prohibited / Unknown | Permitted |
| Chalk | Yes | Permitted / Prohibited / Conditions | Permitted (brush tick marks) |
| Brushing | Conditional | Material restrictions if applicable | Nylon/boar's hair only — no wire |
| Group Size | Yes | Limit or guidance | No formal limit [UNVERIFIED] |
| Seasonal Closures | Yes | February-relevant closures | None (peregrine closures Mar-Jul) |
| Fees | Yes | Entry/parking fees | None |
| Source | Yes | Citation | NPS nps.gov/neri |
| Verify Contact | Yes | Phone/URL for pre-trip confirmation | (304) 574-2115 |

**Validation rules**:
- Every distinct land manager with bouldering areas MUST have a Regulation Set
- Known land managers: NPS (Gorge Boulders), USACE (Summersville Lake), Private/County (Meadow River)
- Trail system land managers: Active SWV (Arrowhead), WV State Parks (Babcock), BSA (Summit Bechtel)

### Carpooling Scenario

A sample plan showing how the car fleet handles a specific daily activity split.

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| Scenario Name | Yes | Descriptive label | Full Group — Same Area |
| Group Split | Yes | Who goes where | All 6 to Meadow River |
| Cars Needed | Yes | Number of cars deployed | 1-2 (carpool) |
| Car A Assignment | Yes | Where Car A goes | Meadow River (all pax) |
| Car B Assignment | Conditional | Where Car B goes (if split) | Stays at house |
| Car C Assignment | Conditional | Where Car C goes (if 3-car fleet) | Stays at house |
| Departure Note | Yes | Timing guidance | Leave by 8:00 AM |
| Parking Note | Conditional | Capacity concern if applicable | Pulloffs fit 5-10 cars — OK |

**Validation rules**:
- At least 3 scenarios required (SC-004): full group same destination, split activities, bad weather day
- Each scenario MUST work for both 2-car and 3-car fleet sizes
- Mid-week scenarios (after roster change) MUST account for reduced/changed fleet

### Roster Transition Plan

Template for the Wednesday mid-week member swap, using role-based placeholders.

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| Departing Member Role | Yes | Placeholder label | Departing Member |
| Departure Time | Yes | Estimated morning departure | ~8-9 AM Wednesday |
| Car Handoff | Yes | Does departing member take a car or leave one? | Scenario A: Takes car (fleet drops to 2) / Scenario B: Carpooled in, no car change |
| Arriving Member Role | Yes | Placeholder label | Arriving Member |
| Arrival Airport | Yes | Recommended airport | CRW (Charleston, ~1.5 hr drive) |
| Arrival Time | Yes | Estimated afternoon arrival | ~2-4 PM Wednesday |
| Pickup Plan | Yes | How arriving member gets to Fayetteville | Option 1: Rent car at CRW / Option 2: Group pickup (~3 hr round trip) |
| Lodging Adjustment | Yes | Room assignment change notes | Departing Member's room → Arriving Member |
| Fleet Impact | Yes | How car count changes | If departing takes car: fleet -1 until arriving adds rental |

**Validation rules**:
- Must cover both scenarios: departing member has a car vs. carpooled in
- Must cover both scenarios: arriving member rents a car vs. gets picked up
- Must note impact on car fleet for remainder of week

### Verification Item

An entry in the pre-trip checklist for confirming access, closures, or regulations.

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| Item | Yes | What to verify | Summit Bechtel public access |
| Contact | Yes | Phone number, URL, or both | (304) 465-2800 / summitbsa.org |
| Why | Yes | Why this needs verification | Private facility — access not guaranteed |
| When | Yes | When to check | 2-4 weeks before trip |

**Validation rules**:
- Every location with `[UNVERIFIED]` access data SHOULD have a Verification Item
- Every location with potential February closures MUST have a Verification Item

## Relationships

```
Access Point ←→ Regulation Set    (many-to-one: multiple access points share a land manager's rules)
Access Point  → Profile Link      (one-to-one: links to Feature 001 area or Feature 003 trail profile)
Carpooling Scenario → Access Point (references parking capacity from access points)
Roster Transition → Car Fleet     (impacts fleet size and carpooling scenarios)
Verification Item → Access Point  (verifies access conditions for specific locations)
```
