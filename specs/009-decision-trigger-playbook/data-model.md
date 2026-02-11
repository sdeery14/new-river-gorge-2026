# Data Model: Decision Trigger Playbook

## Entities

### Decision Window

A defined checkpoint before the trip where the group evaluates forecasts and makes a go/no-go decision.

| Field | Description |
|-------|-------------|
| Name | Human-readable label (e.g., "7-Day Window") |
| Date | Calendar date for Feb 2026 trip (Feb 7, Feb 11, Feb 13) |
| Forecast Reliability | Low / Moderate / High — how trustworthy is the forecast at this range |
| Booking Flexibility | High / Medium / Low — how many reservations are still changeable |
| Decision Type | Preliminary / Firm / Final — what level of commitment this window represents |
| Trigger Criteria | List of Weather Triggers evaluated at this window |
| Available Actions | What the group can do at this window (watch, switch, confirm) |

### Weather Trigger

A specific, measurable weather condition that drives a destination recommendation.

| Field | Description |
|-------|-------------|
| Condition | What to check (e.g., "consecutive rain days in Chattanooga forecast") |
| Threshold | Numeric boundary (e.g., "3+ days") |
| Applies To | Which destination's forecast to check (Chattanooga, NRG, or both) |
| Recommendation | What to do if triggered (pivot to NRG, stay with Chattanooga, consult contingency) |
| Confidence | How reliable this trigger is at the given decision window |

### Booking Commitment

A reservation with cancellation constraints that affect decision flexibility.

| Field | Description |
|-------|-------------|
| Type | Flight / Lodging / Rental Car |
| Destination | Chattanooga or NRG (may have bookings for both) |
| Cancellation Policy | Policy tier name (e.g., "Southwest free cancel", "Airbnb Strict") |
| Free Cancel Deadline | Last date/time for penalty-free cancellation |
| Partial Refund Window | Date range for partial refund (if applicable) |
| Sunk Cost | Estimated amount lost if cancelled after deadline |

### Contingency Path

An alternative plan for when the primary decision tree doesn't yield a clear answer.

| Field | Description |
|-------|-------------|
| Scenario | What triggered this path (e.g., "both destinations have 3+ rain days") |
| Assessment | How to evaluate the degraded scenario (e.g., "compare shelter count") |
| Recommendation | What to do (e.g., "pick NRG for better rain shelter") |
| Cross-Reference | Link to relevant existing document (conditions/, logistics/) |

## Relationships

```
Decision Window (3 instances: 7-day, 3-day, 1-day)
  └── evaluates → Weather Triggers (multiple per window)
  └── constrained by → Booking Commitments (what's still flexible)
  └── may invoke → Contingency Paths (if no clear trigger fires)

Weather Trigger
  └── references → Forecast data (external, not stored)
  └── produces → Recommendation (pivot / stay / consult contingency)

Booking Commitment
  └── limits → Decision Window actions (can't pivot if flights non-refundable)

Contingency Path
  └── references → Conditions Guide (Feature 004)
  └── references → Logistics Guide (Feature 006)
  └── references → Chattanooga repo (companion)
```

## Document Structure Mapping

Each entity maps to a section in `playbook/README.md`:

| Entity | Playbook Section |
|--------|-----------------|
| Decision Window | "Decision Windows" — one subsection per window (7-day, 3-day, 1-day) |
| Weather Trigger | Embedded in each Decision Window subsection as trigger criteria tables |
| Booking Commitment | "Booking & Cancellation Timeline" — countdown table |
| Contingency Path | "Contingency Paths" — scenario-based recommendations |
