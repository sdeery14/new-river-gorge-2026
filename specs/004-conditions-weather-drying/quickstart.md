# Quickstart: Conditions, Weather & Drying Guide

**Feature**: 004-conditions-weather-drying

---

## Workflow 1: Can I Climb Right Now? (US1)

**Scenario**: You're at the crag. It rained last night. The rock looks damp in places. Is it safe to climb?

1. Open `conditions/README.md` → "Can I Climb Right Now?" section
2. Check the quick decision table: match current rock state (dry / damp / wet / frozen / thawing)
3. If "wait" → check the Drying Reference table
4. Match your wall angle (overhang / vertical / slab) to current conditions (sun+wind / overcast / overcast+cold)
5. Estimate time until friction restored
6. If overhangs available → climb overhangs now, wait for vertical/slab to dry

**Success**: Climber makes a safe go/no-go decision in under 30 seconds.

---

## Workflow 2: How Long Until It Dries? (US1)

**Scenario**: Rain stopped 2 hours ago. Sun is out with moderate wind. When can we climb vertical faces?

1. Open `conditions/README.md` → Drying Reference section
2. Find "Vertical" row, "Sun + Wind" column
3. Read estimate: ~2-6 hours
4. Subtract 2 hours already elapsed → ~0-4 more hours
5. Note: "surface dry" comes first; "friction restored" takes longer
6. Check specific area drying modifier in Per-Area Weather Matrix

**Success**: Group estimates drying time within 30 seconds.

---

## Workflow 3: What Do We Do Today? (US2)

**Scenario**: It's 7 AM. The forecast shows 38°F, overcast, 30% chance of afternoon rain.

1. Open `conditions/README.md` → Daily Decision Framework
2. Match forecast to scenario: "Overcast + dry" → Climb in the morning
3. Check area recommendation: Meadow River (overhangs if rain develops)
4. Note time window: climb 10 AM - 2 PM before any afternoon rain
5. Plan rain contingency: if rain starts, drive to Gorge Boulders for cliff-base shelter

**Success**: Group makes a morning plan in under 60 seconds.

---

## Workflow 4: Which Area Today? (US3)

**Scenario**: It's a climbing day — sunny, cold, light wind. The group needs to pick an area.

1. Open `conditions/README.md` → Per-Area Weather Matrix
2. Scan the comparison table for today's conditions (clear+cold, light wind)
3. All areas viable on a clear dry day
4. Check "Best for" row: Summersville Lake (open sun, best friction), or Meadow River (default)
5. Cross-reference group ability needs in `areas/README.md`

**Success**: Area selected in under 30 seconds from weather conditions alone.

---

## Workflow 5: Post-Rain Recovery (US1 + US3)

**Scenario**: Two days of rain. Now it's clearing — sunny, 45°F, moderate wind. Which area recovers first?

1. Open `conditions/README.md` → Per-Area Weather Matrix → Drying Speed column
2. Meadow River = fastest drying (wind + sun + steep rock)
3. Summersville Lake = moderate (exposed but everything got wet)
4. Gorge Boulders = slowest (shade + low wind)
5. Decision: Head to Meadow River for overhangs (already dry), check vertical faces on arrival
6. If vertical still wet, climb overhangs for 2-3 hours, then reassess

**Success**: Group identifies fastest-recovering area and plans accordingly.

---

## Workflow 6: Freeze/Thaw Morning (US1 + US2)

**Scenario**: Overnight low was 22°F, high will reach 45°F. Classic freeze/thaw day.

1. Open `conditions/README.md` → Freeze/Thaw Guide
2. Check timeline: frozen until ~10 AM, thaw transition 10-11:30 AM, climbable by ~noon
3. Morning option: ride frozen trails at Arrowhead (7-9 AM on frozen ground)
4. Transition: DO NOT climb during thaw (invisible water film, dangerous)
5. Afternoon: climb from noon onward once rock has fully thawed and any meltwater dried

**Success**: Group uses both halves of the day and avoids the dangerous thaw window.

---

## Edge Case: Week of Rain

**Scenario**: 4+ consecutive rain days during the trip. When will anything be climbable?

1. Check `conditions/README.md` → Drying Reference for multi-day soak estimates
2. Overhangs: may still be dry at Gorge Boulders (Endless Wall cliff-base) and Meadow River
3. Vertical/slab: 24-48+ hours of dry weather needed in overcast+cold conditions
4. Consult `trails/README.md` → mountain biking is also likely unrideable (mud)
5. Pivot to rest-day activities until a dry+warm window appears
6. Check weather apps for the first clear day — plan to climb overhangs that morning

**This is expected in February.** The guide should set realistic expectations: 3-5 climbable days in a 7-day window is the most likely outcome.
