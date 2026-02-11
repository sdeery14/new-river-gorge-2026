# Data Model: Sean's Personal Trip Guide

**Feature**: 007-seans-trip-guide | **Date**: 2026-02-11

## Entities

### Decision Matrix Row

A row in the daily decision table mapping weather/energy conditions to Sean's recommended activity and destination.

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| Scenario | Yes | Weather + energy condition | Clear + Cold + High Energy |
| Activity | Yes | Boulder, Bike, or Rest | Bike AM → Boulder PM |
| Destination | Yes | Specific area/trail name | Arrowhead → Meadow River |
| Time Window | Yes | When to go | Ride 7-10 AM, climb 12-4 PM |
| Why This | Yes | One-line rationale tuned to Sean's goals | Frozen trails + best beginner problems |
| Rain Fallback | Conditional | Alternative if rain starts | Gorge Boulders cliff-base overhang |

**Validation rules**:
- Must cover at least 6 distinct weather scenarios (clear/cold, clear/warm, rain, freeze/thaw, wind, extended wet)
- Every scenario must have a specific destination, not "check area profiles"
- Rain fallback required for all outdoor activity scenarios

### Hit List Entry

A curated V1-V3 problem in Sean's bouldering hit list.

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| Problem Name | Yes | Name from Feature 002 | The Warm-Up |
| Grade | Yes | V-scale grade | V1 |
| Style | Yes | One-word climb style | Overhang / jug |
| Area | Yes | Which bouldering area | Meadow River |
| Shelter | Yes | Sheltered / Partial / Exposed | Sheltered |
| Quality Note | Yes | One-line personal recommendation | ⭐ Your first climb of any session — obvious jug ladder |
| Conditions | Conditional | When this problem is best/worst | Works in all conditions |
| Profile Link | Yes | Link to full area profile | [Meadow River](../areas/meadow-river.md) |

**Validation rules**:
- At least 3 problems per area where available (Summersville has most, Gorge has fewest)
- Classic problems (⭐) must be highlighted
- Sheltered problems must be identified for rain-day planning
- If an area has <3 usable V1-V3 problems, include an honest note

### Trail Priority Entry

A ranked trail system in Sean's mountain biking priority stack.

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| Rank | Yes | Priority order (1, 2, 3) | 1 |
| Trail System | Yes | Name | Arrowhead Trails |
| Drive Time | Yes | From rental house | 5-10 min |
| Conditions Gate | Yes | What conditions must be true to ride | Frozen ground, ride before 10 AM |
| Access Risk | Yes | None / Medium / High | None |
| Best For | Yes | One-line description | Default ride, pairs with afternoon bouldering |
| Fallback | Yes | What to do instead | Boulder Meadow River or Gorge |
| Profile Link | Yes | Link to full trail profile | [Arrowhead](../trails/arrowhead.md) |

**Validation rules**:
- All 3 trail systems must be ranked
- Each must have a conditions gate and a fallback
- Must include the "don't ride" scenario (all trails too wet/soft)

### Personal Pick

A curated restaurant, brewery, or rest-day activity from Sean's favorites.

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| Name | Yes | Venue/activity name | Cathedral Cafe |
| Type | Yes | Restaurant / Brewery / Activity | Restaurant |
| Personal Note | Yes | Why Sean wants to go, what to try | Unique church setting — try the breakfast burrito |
| Best For | Yes | When/why to go here | Rest-day brunch, arrival morning |
| Hours Note | Conditional | February hours if uncertain | Closed Wed; weekends 7:30a-3p |
| Group Friendly | Yes | Yes / No / Varies | Yes (seats 5-6 easily) |
| Source Link | Yes | Link to full rest-day guide entry | [Rest-Day Guide](../rest-day/README.md#cathedral-cafe) |

**Validation rules**:
- At least 3 dining picks and 2 activity picks
- Each must have a personal note (not just a repeat of Feature 005 description)
- February hours should be flagged [UNVERIFIED] if uncertain

### Sample Day

A day in Sean's sample week itinerary.

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| Day | Yes | Day of week + date | Sunday Feb 15 |
| Weather | Yes | Assumed weather scenario | Clear, 38°F, dry |
| Morning | Yes | Morning activity + destination | Ride Arrowhead (frozen ground, 7-9 AM) |
| Afternoon | Yes | Afternoon activity + destination | Boulder Summersville Lake (12-4 PM) |
| Evening | Yes | Dinner plan | Pies & Pints (group dinner) |
| Notes | Conditional | Special logistics or weather notes | First full day — explore + settle in |

**Validation rules**:
- Must cover all 7 days (Sun Feb 15 through Sat Feb 21; arrival Sat Feb 14 is partial)
- Must include at least 2 weather variations (rain, freeze/thaw, clear)
- Wednesday (Feb 18) must note roster change
- At least 1 rest day and 1 bike day included

### Packing Item

An item in Sean's personal packing checklist.

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| Item | Yes | Gear/clothing item | Microspikes |
| Category | Yes | Bouldering / Biking / Weather / General | Weather |
| Why | Yes | Why Sean specifically needs this | Icy gorge approaches in February |
| Priority | Yes | Essential / Recommended / Nice-to-have | Essential |

**Validation rules**:
- Must include gear for all 3 activity types (bouldering, biking, rest-day)
- Must include February-specific weather gear
- Must be specific to Sean's activities (not a generic trip list)

## Relationships

```
Decision Matrix Row → Hit List Entry     (scenarios reference specific problems at destinations)
Decision Matrix Row → Trail Priority     (scenarios reference specific trails)
Decision Matrix Row → Personal Pick      (rain/rest scenarios reference dining picks)
Hit List Entry → Area Profile            (links to Feature 001 area profiles)
Trail Priority → Trail Profile           (links to Feature 003 trail profiles)
Personal Pick → Rest-Day Guide           (links to Feature 005 entries)
Sample Day → Decision Matrix Row         (each day follows the decision matrix logic)
```
