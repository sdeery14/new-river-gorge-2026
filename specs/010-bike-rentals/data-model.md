# Data Model: Bike Rentals

## Entities

### Rental Shop

A business that rents mountain bikes near New River Gorge.

| Field | Description |
|-------|-------------|
| Name | Business name (e.g., "New River Bikes") |
| Location | Town and address |
| Distance from Fayetteville | Drive time / miles from downtown Fayetteville |
| Phone | Primary contact number |
| Website | URL or social media link |
| Estimated Pricing | Daily rate range (e.g., "$40/day") flagged [UNVERIFIED] |
| Bike Types | Categories available (hardtail, full-suspension, e-bike) |
| February Status | Likelihood of being open: Open / Likely Open / Unlikely / Unknown |
| Hours | Operating hours, noting any winter schedule changes |
| Reservation Policy | Advance notice, deposit, ID requirements |
| Rental Durations | Half-day, full-day options |
| Damage Policy | Waiver, liability, credit card hold |
| Notes | Special features (shuttle service, on-site trails, etc.) |

### Bike Type

A category of rental bike with suitability assessment for NRG trails.

| Field | Description |
|-------|-------------|
| Type Name | Category label (hardtail, full-suspension, e-bike) |
| Best For | Trail difficulty and rider level (e.g., "beginners on green/blue trails") |
| Typical Cost | Relative price tier (budget, mid-range, premium) |
| Pros | Advantages for NRG trails |
| Cons | Disadvantages or limitations |

### Fallback Option

An alternative strategy when local bike rental is unavailable.

| Field | Description |
|-------|-------------|
| Strategy Name | Label (e.g., "Rent Out-of-Town", "Bring Your Own") |
| Description | How it works |
| Logistics | What the group needs to do (transport, timing, cost) |
| Pros | Why this works |
| Cons | Drawbacks and effort required |

## Relationships

```
Rental Shop (4 local + 2 out-of-town)
  └── offers → Bike Types (1+ per shop)
  └── has → Reservation Policy
  └── has → February Status

Bike Type (3: hardtail, full-suspension, e-bike)
  └── suited for → Trail difficulty level
  └── available at → Rental Shops

Fallback Option (3: out-of-town rental, bring-your-own, skip riding)
  └── references → Out-of-town Rental Shops (if applicable)
  └── cross-references → Trail Profiles (Feature 003)
```

## Document Structure Mapping

Each entity maps to a section in `trails/bike-rentals.md`:

| Entity | Guide Section |
|--------|--------------|
| Rental Shop | "Quick-Reference Shop Table" (summary) + "Shop Details" (expanded) |
| Bike Type | "Beginner Rental Guidance" — bike type recommendations |
| Fallback Option | "Out-of-Town Alternatives" + "Bring Your Own Bike" |
