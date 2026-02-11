# Feature Specification: Sean's Personal Trip Guide

**Feature Branch**: `007-seans-trip-guide`
**Created**: 2026-02-11
**Status**: Draft
**Input**: User description: "007 | Sean's Personal Trip Guide from the vision.md"

## Overview

Sean's Personal Trip Guide is a personalized layer that synthesizes all prior feature outputs (001-006) into a single document tailored to Sean's specific interests, ability level, and preferences. Sean climbs in the V1-V3 (beginner) range and prioritizes mountain biking as a first-class activity alongside bouldering. This guide provides Sean with a personalized daily decision framework, curated bouldering targets, a mountain biking priority stack, and a food & drink guide — all consolidated so he can make fast decisions without cross-referencing multiple documents.

**Adapted from Chattanooga format**: The companion repo at `chattanooga-2026` uses a similar personal guide structure. This guide follows the same pattern for consistency.

## Clarifications

### Session 2026-02-11

- Q: What voice/tone should the guide use? → A: Second-person practical ("Your top picks", "Check your stack", "You'll want to ride early") — advisory voice like a friend's cheat sheet written for Sean.
- Q: How much source content should be inlined vs. linked? → A: Curated inlining — problem names, grades, one-line style/quality notes inline in hit list and biking stack; link to full area/trail profiles for complete context. Guide target ~300-400 lines.

## User Scenarios & Testing

### User Story 1 - Sean's Daily Decision Framework (Priority: P1)

Sean wakes up and checks the weather. He needs to decide: boulder, bike, or rest? If boulder, which area? If bike, which trail? He opens his personal guide on his phone and within 30 seconds has a clear recommendation based on current conditions, his energy level, and what the rest of the group is doing.

**Why this priority**: This is the guide Sean will use every single morning of the trip. A personalized decision matrix tuned to his V1-V3 goals and biking preferences is the highest-value content — it directly reduces morning decision paralysis.

**Independent Test**: Open the guide on a phone, pick a weather scenario (e.g., "35°F, cloudy, rained last night"), and find Sean's recommended activity and destination within 30 seconds.

**Acceptance Scenarios**:

1. **Given** it's a clear cold morning (28°F, frozen ground), **When** Sean checks his daily decision framework, **Then** he finds a recommendation to ride Arrowhead Trails early (frozen ground window 7-10 AM) then boulder Gorge Boulders or Meadow River in the afternoon (best friction after noon thaw).
2. **Given** it rained overnight and is still drizzling, **When** Sean checks his framework, **Then** he finds a rain-day recommendation: Gorge Boulders cliff-base overhangs if motivated (stay dry under natural roof), otherwise rest-day options with his top restaurant picks.
3. **Given** it's a sunny dry day (45°F), **When** Sean checks his framework, **Then** he finds a recommendation to boulder Summersville Lake (best beginner area, sunny exposure, lakeshore boulders) or split day with biking if group wants.

---

### User Story 2 - Sean's Bouldering Hit List (Priority: P2)

Sean wants to know which specific problems to try at each bouldering area, filtered to his V1-V3 range. He opens his guide and finds a curated list of beginner-friendly problems organized by area, with notes on style, quality, and conditions requirements for each.

**Why this priority**: Sean's climbing goals are the core personal content. Without a curated hit list, he'd have to scan the full area profiles (which prioritize V10 objectives per the constitution) to find problems in his range.

**Independent Test**: Open the guide, pick an area (e.g., Summersville Lake), and find at least 3 specific V1-V3 problems with grade, style description, and conditions notes within 30 seconds.

**Acceptance Scenarios**:

1. **Given** Sean is at Meadow River, **When** he opens his bouldering hit list, **Then** he finds V1-V3 problems listed with name (if named), grade, style (overhang, slab, vertical), and a quality rating or highlight note.
2. **Given** Sean is at Summersville Lake, **When** he opens his hit list, **Then** he finds the area marked as his "best beginner area" with the most V1-V3 options, plus notes on February drawdown exposing flat landings.
3. **Given** Sean is at Gorge Boulders in the rain, **When** he opens his hit list, **Then** he finds any available V1-V3 problems near the cliff-base overhangs, or an honest note that this area has "Few" beginner problems and is better used as a shelter day.

---

### User Story 3 - Sean's Mountain Biking Priority Stack (Priority: P3)

Sean wants a ranked list of trail systems in order of his preference, with conditions requirements for each. He opens his guide and finds his biking priority stack: which trail to try first, what conditions it needs, and what to ride instead if his first choice is unavailable.

**Why this priority**: Mountain biking is a first-class activity for Sean. A prioritized stack prevents him from defaulting to "just boulder" on days when riding is viable. The stack accounts for access uncertainty (Summit Bechtel is private) and February conditions.

**Independent Test**: Open the guide, find Sean's #1 trail pick, see what conditions it needs, and find the fallback trail if those conditions aren't met.

**Acceptance Scenarios**:

1. **Given** Sean checks his biking stack on a cold frozen morning, **When** he looks up trail #1 (Arrowhead), **Then** he finds it needs frozen ground (ride before 10 AM), is free, 5-10 min away, and pairs well with afternoon bouldering.
2. **Given** Summit Bechtel has confirmed public access (called ahead), **When** Sean checks his stack, **Then** he finds it ranked as the premium option with the most mileage and trail variety, with fee/waiver notes.
3. **Given** trails are all muddy (thaw + rain), **When** Sean checks his stack, **Then** he finds a clear "don't ride today" signal with the community ethic note (riding wet trails causes lasting damage) and a redirect to bouldering or rest-day activities.

---

### User Story 4 - Sean's Food, Drink & Rest-Day Picks (Priority: P4)

Sean wants a curated list of his personal restaurant, brewery, and rest-day activity picks — not the full Feature 005 catalog, but his "definitely want to hit" spots with personal notes on what to order, when to go, and what makes each place worth visiting.

**Why this priority**: Personal curation adds value beyond the generic rest-day guide. Sean can share this with the group as recommendations without everyone reading the full guide.

**Independent Test**: Open the guide, find Sean's top 3 dining picks, each with a personal note about what to order or why he wants to go.

**Acceptance Scenarios**:

1. **Given** the group wants dinner on arrival night (Saturday), **When** Sean checks his picks, **Then** he finds his recommended arrival dinner spot with hours, group-friendliness note, and what to order.
2. **Given** it's a rest day, **When** Sean checks his picks, **Then** he finds a curated rest-day itinerary combining his preferred dining and activity options (not just a list — a suggested flow for the day).
3. **Given** the group wants craft beer, **When** Sean checks his picks, **Then** he finds his brewery/taphouse priorities with notes on beer selection and food availability.

---

### Edge Cases

1. **Zero rideable days**: February conditions may prevent any mountain biking during the entire trip. Sean's guide must acknowledge this possibility and provide graceful fallback to bouldering-focused days without making the biking section feel wasted.
2. **All bouldering areas wet**: Extended rain could make all areas unclimbable for 1-2 days. Sean's guide needs a "nuclear rest day" plan that doesn't depend on outdoor climbing or biking.
3. **Sean arrives or departs mid-week**: If Sean is the arriving or departing member (not the full-week participant), his personal logistics section needs different content. (Assumed full-week — see Assumptions.)
4. **Group splits differently than expected**: Sean's daily framework assumes he can join either the climbing or biking subgroup. If the group splits 5-1, Sean may be solo for an activity — the guide should note which activities are solo-safe.

## Requirements

### Functional Requirements

- **FR-001**: The guide MUST provide a personalized daily decision matrix that recommends boulder, bike, or rest based on weather conditions and Sean's preferences
- **FR-002**: The guide MUST include a curated V1-V3 bouldering hit list for each bouldering area, sourced from Feature 002 problem clusters and area profiles
- **FR-003**: The guide MUST include a ranked mountain biking priority stack with conditions requirements and fallback order for each trail system
- **FR-004**: The guide MUST include Sean's curated food, drink, and rest-day picks with personal notes, sourced from Feature 005
- **FR-005**: The guide MUST use curated inlining for personal sections (problem names, grades, one-line notes inline in hit list and biking stack) and link to full area/trail profiles for complete context — abbreviated details inline, full profiles linked
- **FR-006**: The guide MUST include a personal packing checklist tailored to Sean's specific activities (bouldering V1-V3 + mountain biking + February conditions)
- **FR-007**: The guide MUST include Sean's personal logistics summary (arrival/departure info, car assignment, lodging notes, emergency contacts)
- **FR-008**: The guide MUST be usable on a phone with quick-reference sections at the top and detailed content below
- **FR-009**: Every factual claim MUST be sourced or flagged with `[UNVERIFIED]`, consistent with Features 001-006
- **FR-010**: The guide MUST contain zero sport climbing, trad climbing, or route climbing references (bouldering scope only)
- **FR-011**: The guide MUST include a sample week itinerary showing how Sean's preferences play out across 7 days with realistic weather variation

### Key Entities

- **Personal Decision Matrix**: Weather-to-activity mapping tuned to Sean's preferences (V1-V3 bouldering, MTB priority, energy levels)
- **Bouldering Hit List Entry**: Problem name (if available), grade (V1-V3), area, style, quality note, conditions requirement
- **Trail Priority Entry**: Trail system name, rank, conditions requirement, access notes, fallback if unavailable
- **Personal Pick**: Restaurant/brewery/activity name, personal note (what to order/do), hours, group-friendliness
- **Sample Day**: Day number, weather scenario, recommended activity sequence, area/trail, dining plan

## Success Criteria

### Measurable Outcomes

- **SC-001**: Sean can determine his recommended activity for any weather scenario within 30 seconds of opening the guide
- **SC-002**: The bouldering hit list contains at least 3 V1-V3 problems per bouldering area (where available), or an honest note explaining limited options
- **SC-003**: The mountain biking priority stack covers all 3 trail systems with clear rank order, conditions gates, and fallback recommendations
- **SC-004**: 100% of factual claims are sourced or flagged `[UNVERIFIED]`
- **SC-005**: The guide contains zero references to sport, trad, or route climbing
- **SC-006**: The sample week itinerary covers all 7 days (Sat-Sat) with at least 2 weather variations (e.g., 3 dry days, 2 rain days, 1 freeze/thaw, 1 rest)
- **SC-007**: The personal packing checklist is specific to Sean's activities (not a generic trip packing list)

## Scope

### In Scope

- Personalized decision framework synthesizing Features 001-006 for Sean's specific needs
- Curated V1-V3 bouldering targets by area from Feature 002 problem clusters
- Ranked mountain biking trail preferences with conditions requirements
- Personal dining/brewery/rest-day curations from Feature 005
- Personal packing checklist (bouldering + MTB + February gear)
- Sample week itinerary with weather variation
- Personal logistics summary (arrival, car, lodging, contacts)

### Out of Scope

- Problems above V3 (those are in the main area profiles for other group members)
- Trail route details beyond what's in Feature 003 profiles (no new trail research)
- New restaurant research beyond Feature 005 content
- Group coordination documents (that's Feature 006)
- Real-time weather integration or dynamic content
- Content for other group members (this is Sean's guide only)

## Dependencies

- **Feature 001** (Bouldering Areas): Area profiles, grade distributions — Required
- **Feature 002** (Problem Clusters): V1-V3 problem curations per area — Required
- **Feature 003** (Mountain Biking Trails): Trail profiles, ride pairings, February viability — Required
- **Feature 004** (Conditions & Weather): Decision framework, drying reference, freeze/thaw guidance — Required
- **Feature 005** (Rest-Day Activities): Dining, breweries, hiking, indoor options — Required
- **Feature 006** (Logistics & Access): Drive times, parking, car strategy, roster change — Required

All six features are complete and merged to main.

## Assumptions

1. Sean is present for the full week (Saturday Feb 14 through Saturday Feb 21) — he is neither the departing nor arriving member in the mid-week roster change
2. Sean climbs in the V1-V3 range (beginner band) as stated in the vision
3. Sean prioritizes mountain biking as a first-class activity — he will ride whenever conditions allow
4. Sean has no specific dietary restrictions (curations are preference-based, not allergy-based)
5. The guide is a single Markdown file at `sean/README.md`, consistent with the single-file pattern used in Features 004, 005, and 006
6. The guide uses second-person practical voice ("Your top picks", "You'll want to ride early") — an advisory tone like a friend's cheat sheet, more personal than the group-facing documents but not first-person
7. The Chattanooga companion repo uses a similar personal guide format — this guide mirrors that structure where applicable
8. Sean has access to a car for the full trip (either his own or shared fleet)
