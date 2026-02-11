# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **trip planning documentation repository** for a New River Gorge (West Virginia) bouldering trip, February 14-21, 2026. It serves as a rain-contingency alternative to a Chattanooga bouldering trip. The repo contains no application code -- it produces structured Markdown documents using the Specify (Spec-Kit) workflow.

A companion repo exists at `https://github.com/sdeery14/chattanooga-2026` with the same format.

## Specify (Spec-Kit) Workflow

All features follow this pipeline, invoked via slash commands:

```
/speckit.specify → /speckit.clarify → /speckit.plan → /speckit.tasks → /speckit.implement → /speckit.checklist
```

- **specify**: Create feature spec from natural language description
- **clarify**: Ask up to 5 targeted clarification questions, encode answers into spec
- **plan**: Generate implementation plan from spec
- **tasks**: Generate dependency-ordered tasks.md
- **implement**: Execute all tasks in tasks.md
- **checklist**: Generate quality checklist for the feature
- **analyze**: Cross-artifact consistency check (non-destructive)
- **constitution**: Create/update project constitution from principles

Templates live in `.specify/templates/`. Feature artifacts (spec.md, plan.md, tasks.md) are generated per-feature into feature directories.

## Feature Roadmap (from vision.md)

Features are sequenced with explicit dependencies:

1. **001 - Primary Bouldering Areas** (foundation, no deps)
2. **002 - Problem Clusters** (depends on 001)
3. **003 - Mountain Biking Trails** (depends on 001)
4. **004 - Conditions, Weather & Drying Guide** (depends on 001, 002)
5. **005 - Rest-Day & Low-Energy Pack** (no deps)
6. **006 - Logistics & Access Cheat Sheets** (depends on 001, 003)
7. **007 - Sean's Personal Trip Guide** (depends on all prior)
8. **008 - Interactive Area Maps** (depends on all prior)
9. **009 - Decision Trigger Playbook** (stretch, depends on 004)
10. **010 - Bike Rentals** (stretch, depends on 003)

## Content Principles (Constitution Seeds)

These govern all generated documents:

- **Decision-Support First**: Every document serves rapid in-the-moment decisions at the crag
- **Bouldering Only (NON-NEGOTIABLE)**: 100% bouldering. No sport, trad, or route climbing content
- **Hard-Climbing Priority**: V10 objectives come first; V6 and V1-V3 noted where they exist
- **Mountain Biking as First-Class Activity**: Equal research rigor to climbing
- **Weather-Resilience as Core Value**: Rain behavior, shelter, and drying characteristics required for every area (this is why the trip exists)
- **Source Accuracy**: Cite sources; flag unverified claims with `[UNVERIFIED]`

## Group Context

Three ability bands (Hard ~V10, Intermediate ~V6, Beginner V1-V3). Mid-week roster change: one member departs Wednesday, another arrives Wednesday. This affects lodging, car logistics, and daily planning. Documents should flag where roster composition matters.

## Document Style

- Skimmable, searchable, usable on a phone at the crag
- Quick-reference tables at the top, details below
- Every climbing area profile must include: grade spread across bands, rain resilience rating, shelter/drying characteristics, approach/access info
- Every bouldering day plan needs both a dry-weather option AND a wet-weather option
