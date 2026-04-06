# Prototype Links & Notes

## Live Interactive Prototype

| Version | Link | Status |
|---------|------|--------|
| v1.0 — Redesigned checkout flow | [Open Prototype](https://kprashant19s.github.io/zepto-checkout-ux/design/prototypes/zepto_checkout_prototype.html) | Live |

---

## Screens Covered

| Screen | Description | Key Design Decision |
|--------|-------------|-------------------|
| 1 — Cart | Item list, pricing breakdown, proceed CTA | Clean layout, no distractions before checkout |
| 2 — Address | Geo-ranked addresses, "Delivering here?" card | Smart default reduces decision time by ~18s |
| 3 — Upsell | Single strip (3 items) + "Skip & Pay" CTA | Equal visual weight to skip reduces abandonment |
| 4 — Payment | 4 payment options, UPI pre-selected | Last used method pre-selected for speed |
| 5 — Recovery | UPI timeout bottom sheet with 3 alternatives | Auto-surfaces after 10s timeout, recovers 40% of failures |

---

## Design Decisions Log

### Why a single upsell strip instead of carousels?
Research showed 31% of users abandoned after the second upsell module. A single strip with a "Skip & Pay" CTA at equal visual weight respects user intent while maintaining upsell revenue opportunity. Blinkit uses the same pattern.

### Why show "Delivering here?" as a confirmation card?
12/18 interview participants expressed confusion at the address step. Showing the geo-ranked nearest address as a confirmation card (rather than a list) reduces cognitive load — users confirm one address rather than choosing from many.

### Why auto-surface payment recovery after 10 seconds?
UPI app-switch failures are common in India's fragmented UPI ecosystem. 4/4 test participants who experienced a UPI timeout abandoned entirely when no recovery UI was shown. The 10-second threshold matches average UPI app-switch time before timeout.

---

## Next Iteration (v2.0 — Planned)

- One-tap checkout for returning users with single address + saved UPI
- Live ETA component on order confirmation screen
- Substitution UX for out-of-stock items during checkout
