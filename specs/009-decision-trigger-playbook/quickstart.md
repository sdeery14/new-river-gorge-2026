# Quickstart: Decision Trigger Playbook

## Implementation Order

| Step | Task | File | Depends On |
|------|------|------|------------|
| 1 | Create `playbook/` directory | playbook/ | — |
| 2 | Write quick-reference decision tree | playbook/README.md | — |
| 3 | Write 7-day decision window section | playbook/README.md | Step 2 |
| 4 | Write 3-day decision window section | playbook/README.md | Step 3 |
| 5 | Write 1-day decision window section | playbook/README.md | Step 4 |
| 6 | Write weather comparison table (Chattanooga vs NRG) | playbook/README.md | Step 2 |
| 7 | Write booking & cancellation timeline | playbook/README.md | Step 2 |
| 8 | Write contingency paths section | playbook/README.md | Steps 3-5 |
| 9 | Write mid-week roster considerations | playbook/README.md | Step 7 |
| 10 | Add cross-references to conditions/logistics/Chattanooga | playbook/README.md | Steps 3-8 |
| 11 | Add playbook link to root README.md | README.md | Step 2 |
| 12 | Source verification pass | All files | Steps 2-11 |
| 13 | Scope compliance check | playbook/README.md | Step 12 |
| 14 | Phone readability check | playbook/README.md | Step 12 |

## File Reference

| File | Action | Description |
|------|--------|-------------|
| playbook/README.md | NEW | Decision Trigger Playbook — the full document |
| README.md | MODIFY | Add playbook to Quick Start table and What's in the Repo |

## Constitution Gates

All 6 principles PASS (see plan.md Constitution Check).

## Key Implementation Notes

- **Decision tree first**: The quick-reference decision tree at the top is the MVP. Everything below it supports and explains the tree.
- **Cross-reference, don't duplicate**: Weather data lives in conditions/README.md. Logistics data lives in logistics/README.md. The playbook links to these rather than copying.
- **Placeholder-friendly**: Booking details are not finalized. Use [UNVERIFIED] flags and design sections so actual booking terms can be dropped in later.
- **Chattanooga data**: Reference the companion repo by link. Don't copy conditions data — it may change.
- **Three windows, not more**: 7-day (preliminary), 3-day (firm decision), 1-day (final confirm). Morning-of decisions are Feature 004's job.

## Known Risks

1. Booking details are placeholders — playbook must work even with [UNVERIFIED] cost estimates
2. Chattanooga weather comparison uses researched data, not live forecasts — flag as [UNVERIFIED]
3. Cancellation policies may change before the trip — flag all as [UNVERIFIED]
