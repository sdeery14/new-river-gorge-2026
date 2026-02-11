# Data Model: Problem Clusters

**Feature**: 002-problem-clusters
**Date**: 2026-02-10

## Problem Entry Schema

Each problem entry in a problem cluster document follows this schema. All fields are required unless marked optional.

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| **Name** | Text | Yes | Problem name. If unnamed, use descriptive identifier (e.g., "Unnamed overhang, River Boulder, river-left") |
| **Grade** | V-scale | Yes | V-grade. If disputed, show consensus grade with range: "V7 (V6-V8)" |
| **Style** | Enum | Yes | Primary climbing style. Values: overhang, slab, compression, crimp, arete, roof, traverse, vertical face, mantle. May combine (e.g., "overhang / compression") |
| **Shelter** | Enum | Yes | Shelter status. Values: Sheltered, Partial, Exposed |
| **Shelter Type** | Text | If Sheltered/Partial | Type of shelter: cliff-base overhang, roof, cave, tree canopy, boulder overhang |
| **Landing** | Enum | Yes | Landing quality. Values: Flat (pad-friendly, level), Uneven (careful pad placement, talus/slope), Poor (dangerous, spotter + multiple pads) |
| **Location** | Text | Yes | Descriptive text directions to find the boulder (e.g., "Tall block 50m left of trail junction, river-left"). No GPS. |
| **Classic** | Boolean | No | Star/classic marker. True if Mountain Project 3+ stars, guidebook highlight, or community consensus classic |
| **Conditions** | Text | V7-V10+ only | Conditions notes for projecting: needs dry/cold, works in humidity, wind-sensitive, etc. |
| **MP Link** | URL | If available | Mountain Project problem page URL (tappable on phone) |
| **Source** | Text | Yes | Where the data came from: Mountain Project, guidebook name, local beta, etc. |
| **Verified** | Boolean | Yes | True if confirmed from a primary source. False → flagged with [UNVERIFIED] |

## Problem Cluster Document Schema

Each per-area problem cluster document has this structure:

```
Document Header
├── Area name + link to parent profile
├── Quick-reference summary (curated count per grade band + classic count)
│
├── V7-V10+ (Hard) — listed FIRST per Constitution Principle III
│   ├── Band summary: "X curated problems, Y classics"
│   └── Problem entries (table or list)
│
├── V4-V6 (Intermediate)
│   ├── Band summary
│   └── Problem entries
│
├── V0-V3 (Beginner)
│   ├── Band summary
│   └── Problem entries
│
└── Sources
```

### Grade Band Order

Per Constitution Principle III (Hard-Climbing Priority), grade bands are listed in descending order: V7-V10+ first, then V4-V6, then V0-V3. This ensures V10 climbers see their problems first when opening the document.

### Quick-Reference Summary

At the top of each document, a summary table shows:

| Grade Band | Curated | Classics | Sheltered |
|-----------|---------|----------|-----------|
| V7-V10+   | [count] | [count]  | [count]   |
| V4-V6     | [count] | [count]  | [count]   |
| V0-V3     | [count] | [count]  | [count]   |

This enables SC-001 (30-second identification) and supports US4 (mixed-ability comparison).

## Cross-Area Summary Schema

### Sheltered Classics (FR-008)

Aggregates all sheltered quality problems across all areas:

```
Document Header
├── How to use this document (rain-day decision flow)
│
├── By Area
│   ├── [Area Name] — link to area profile
│   │   ├── V7-V10+ sheltered problems
│   │   ├── V4-V6 sheltered problems
│   │   └── V0-V3 sheltered problems
│   └── [repeat per area]
│
└── Sources
```

### Hard-Climbing Summary (FR-009)

Aggregates all V7-V10+ problems across all areas:

```
Document Header
├── How to use this document (week planning flow)
│
├── All V7-V10+ Problems (single table)
│   Columns: Area | Sector | Name | Grade | Style | Shelter | Classic | Conditions
│   Sorted by: Grade (descending), then quality (classics first)
│
└── Sources
```

## Relationships

```
Feature 001 Area Profile (existing)
  └── links to → Problem Cluster Document (new, FR-011)
       └── problems aggregated into → Cross-Area Sheltered Classics (new, FR-008)
       └── V7-V10+ problems aggregated into → Cross-Area Hard-Climbing Summary (new, FR-009)
```

## Conventions

- **Density terms**: Many (20+), Some (5-19), Few (1-4), None (0) — same as Feature 001
- **Classic marker**: Star symbol (⭐) before problem name in tables
- **[UNVERIFIED]**: Appended to any field not confirmed from a primary source
- **Empty grade bands**: Explicit "No documented problems in this grade range" — never omit a band
- **Mountain Project links**: Inline markdown links `[MP](url)` — tappable on phone
