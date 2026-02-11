<!--
  Sync Impact Report
  ==================
  Version change: N/A → 1.0.0 (initial ratification)
  Added principles:
    - I. Decision-Support First
    - II. Bouldering Scope Boundary (NON-NEGOTIABLE)
    - III. Ability-Aware, Hard-Climbing Priority
    - IV. Mountain Biking as First-Class Activity
    - V. Weather-Resilience as Core Value
    - VI. Source Accuracy & Recency
  Added sections:
    - Document Standards
    - Group & Logistics Awareness
    - Governance
  Removed sections: None
  Templates requiring updates:
    - .specify/templates/plan-template.md — ✅ No update needed
      (Constitution Check section is generic; populated at plan time)
    - .specify/templates/spec-template.md — ✅ No update needed
      (Template structure supports all required sections)
    - .specify/templates/tasks-template.md — ✅ No update needed
      (Phase structure accommodates documentation-only features)
    - .specify/templates/checklist-template.md — ✅ No update needed
    - .specify/templates/agent-file-template.md — ✅ No update needed
    - CLAUDE.md — ✅ Already aligned with constitution seeds
  Follow-up TODOs: None
-->

# New River Gorge 2026 Constitution

## Core Principles

### I. Decision-Support First

Every document produced by this project MUST serve rapid,
in-the-moment decisions. A climber standing at a trailhead in
February rain, phone in hand, MUST be able to find actionable
guidance within seconds.

- Quick-reference tables MUST appear at the top of every document
- Detail sections follow below for deeper reading
- Documents MUST be skimmable, searchable, and legible on a phone
- No document exists solely for organizational purposes; every
  artifact MUST answer a question someone will actually ask on the trip

### II. Bouldering Scope Boundary (NON-NEGOTIABLE)

This project covers 100% bouldering. No sport climbing, trad
climbing, or route climbing content of any kind.

- All climbing references MUST be bouldering problems, not routes
- Grade references use the V-scale exclusively
- Area profiles MUST NOT include route counts, pitch descriptions,
  or gear lists for roped climbing
- If an area is primarily known for routes (e.g., Kaymoor, Endless
  Wall sport/trad), it is only included if it has documented
  bouldering problems

### III. Ability-Aware, Hard-Climbing Priority

The group spans three ability bands: Hard (~V10), Intermediate
(~V6), and Beginner (V1-V3). Area selection and problem curation
MUST prioritize hard climbing while remaining inclusive.

- V10 objectives are the primary driver for area selection
- Every area profile MUST note grade distribution across all three
  bands: V0-V3, V4-V6, V7-V10+
- Flag areas where beginners will run out of problems quickly
- Flag areas where hard climbers will lack enough quality lines
- Problem lists MUST be organized by grade band with hard problems
  listed first

### IV. Mountain Biking as First-Class Activity

Mountain biking receives equal research rigor to bouldering. It is
not a rest-day afterthought.

- Trail profiles MUST include: difficulty rating, distance, climb,
  February trail conditions, and estimated ride time
- Trail systems MUST be evaluated for pairing with nearby bouldering
  areas (morning ride + afternoon climb, or vice versa)
- Rental and logistics information MUST be documented where relevant

### V. Weather-Resilience as Core Value

This trip exists because Chattanooga sandstone fails in rain. Every
piece of content MUST address weather resilience. This is the reason
the plan exists.

- Every bouldering area profile MUST include: shelter availability,
  seepage patterns, drying time estimates, and wind exposure
- Every climbing day MUST have both a dry-weather plan AND a
  wet-weather plan
- Nuttall sandstone behavior in rain (friction loss, seepage,
  drying characteristics) MUST be documented
- Areas with natural shelter (overhanging boulders, gorge walls,
  forest canopy) MUST be explicitly identified and prioritized

### VI. Source Accuracy & Recency

All factual claims MUST be sourced. Unverified information MUST be
flagged.

- Cite guidebooks, Mountain Project, local beta sources, or
  firsthand accounts
- Flag any unverified claim with `[UNVERIFIED]`
- Note the recency of source material — NRG bouldering is developing;
  areas and access may change
- Prefer primary sources (guidebook authors, local climbers, NPS
  publications) over aggregated or secondhand information

## Document Standards

All documents produced under this constitution MUST follow these
formatting and structural rules:

- **Phone-first layout**: Tables and key facts at top, prose below
- **Optionality over itinerary**: Curate high-quality options; do not
  build a fixed schedule. The group decides each morning
- **Consistent area profiles**: Every bouldering area uses the same
  structure — location, approach, grade spread, rain resilience
  rating, shelter notes, parking, and NPS access considerations
- **Grade band tables**: Use three columns (V0-V3 | V4-V6 | V7-V10+)
  for problem density at a glance
- **Rain resilience rating**: Every area MUST receive a rating
  (e.g., Good / Fair / Poor) based on shelter, drainage, and drying
  characteristics
- **Markdown only**: All content is GitHub-flavored Markdown. No
  external tools, PDFs, or proprietary formats

## Group & Logistics Awareness

The group composition changes mid-week. Documents MUST account for
this where relevant.

- **Roster shift**: One member departs ~Wednesday Feb 18, another
  arrives ~Wednesday Feb 18. Flag where this affects lodging
  headcount, car capacity, or ability-band ratios
- **Lodging**: Note capacity changes at the midpoint
- **Transportation**: Note when car count or seating changes affect
  area access (e.g., areas requiring multiple vehicles or long
  one-way approaches)
- **Ability-band ratio shift**: If the first-half and second-half
  groups have different band compositions, note how daily area
  selection should adjust

## Governance

This constitution is the governing document for all content produced
in this repository. It supersedes informal preferences or ad-hoc
decisions.

- All feature specs, plans, and implementations MUST pass a
  Constitution Check verifying compliance with the six Core
  Principles
- Amendments require: (1) a stated rationale, (2) update to this
  file, and (3) propagation to any affected templates or existing
  documents
- Version follows semantic versioning: MAJOR for principle removals
  or redefinitions, MINOR for new principles or material expansions,
  PATCH for clarifications and wording fixes
- The vision.md file defines the project's feature roadmap and trip
  parameters; this constitution governs how those features are built

**Version**: 1.0.0 | **Ratified**: 2026-02-10 | **Last Amended**: 2026-02-10
