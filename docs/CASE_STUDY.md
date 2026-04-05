# Case Study: Zepto Checkout Flow Optimization

**Role:** Product Manager  
**Scope:** End-to-end UX/PM case study — research, design rationale, iteration log  
**Timeline:** 6 weeks

---

## 1. Context & Background

Zepto is a Bangalore-based quick-commerce (Q-Commerce) company promising 10-minute grocery delivery across major Indian metros. As of 2024, it operates in a three-horse race with Blinkit (Zomato) and Swiggy Instamart, where speed and checkout reliability are the primary conversion levers.

The checkout flow is the most critical product surface in any commerce app. In Q-Commerce specifically, the user's intent is already high — they've opened the app, added items, and chosen Zepto over alternatives. Every second of friction between cart and confirmation is a conversion risk.

This case study documents the end-to-end process of identifying, prioritizing, and solving friction in Zepto's checkout flow from a product management perspective.

---

## 2. User Research

### 2.1 Research Goals

Before any design work began, three research questions were defined:

1. At which step do users most commonly abandon checkout, and why?
2. What emotional states accompany checkout interactions (confidence, confusion, frustration)?
3. How do competitors handle the same friction points?

### 2.2 Methods

**User Interviews (n=18)**  
Participants were recruited via screener: Zepto users in Delhi-NCR or Bangalore who had abandoned at least one checkout session in the past 30 days. Sessions were 45 minutes, semi-structured, conducted remotely via Google Meet. A think-aloud protocol was used while participants navigated their actual Zepto app.

**Session Recording Analysis**  
Hotjar session recordings from a simulated test environment were analyzed. 60 recordings were reviewed, focusing on rage taps, scroll depth within upsell sections, and time-on-screen at the address and payment steps.

**Heuristic Audit**  
A structured review against Nielsen's 10 usability heuristics was conducted independently by two evaluators, then reconciled. Severity ratings (0–4) were assigned to each violation.

**Competitive Analysis**  
Three competitor apps (Blinkit, Swiggy Instamart, Amazon Fresh India) were audited for checkout flow patterns, specifically: address handling, upsell strategy, payment recovery, and ETA communication.

### 2.3 Key Findings

**Finding 1 — Address step triggers the highest cognitive load.**  
12 of 18 participants verbalized confusion when selecting between saved addresses. Common quotes: "I'm not sure which one is home," "I just tapped the first one." Zero participants used the address labels correctly.

**Finding 2 — Upsell carousels are experienced as obstacles, not opportunities.**  
Across all 18 sessions, not a single participant expressed positive sentiment toward the upsell step. Representative quote: "I just want to pay, why are they showing me chips again?" 6 participants explicitly abandoned during this step.

**Finding 3 — Payment failure is a trust-breaking event with no recovery script.**  
The 4 participants who experienced a simulated UPI timeout in usability testing all closed the app entirely. None tried an alternative payment method. The app provided no direction.

**Finding 4 — "10 minutes" is a promise that the product doesn't keep.**  
8 of 18 participants mentioned receiving orders late relative to the stated estimate. 5 said this affected their likelihood of reordering. The static ETA badge was described as "just a marketing claim" by 3 participants.

---

## 3. Synthesis & Prioritization

### 3.1 Affinity Mapping

Interview notes were imported into Miro and clustered into themes. The four friction points described above emerged clearly from this process. Secondary themes (insufficient substitution options, coupon discovery) were noted for a future sprint.

### 3.2 RICE Prioritization

Each opportunity was scored using the RICE framework:

| Opportunity | Reach | Impact | Confidence | Effort | RICE Score |
|-------------|-------|--------|------------|--------|------------|
| Geo-aware address ranking | 8 | 3 | 80% | 2 | 960 |
| Single contextual upsell | 10 | 3 | 85% | 2 | 1,275 |
| Smart Payment Recovery | 7 | 3 | 70% | 3 | 490 |
| Live ETA component | 9 | 2 | 75% | 4 | 337 |

*Reach = estimated % of checkout users affected (out of 10). Impact = effect on CR/NPS (1–3). Effort = engineer-weeks.*

All four were greenlit for design based on high RICE scores and clear user evidence.

---

## 4. Design Process

### 4.1 Principles Guiding Design Decisions

Three design principles were established before wireframing to keep all decisions aligned:

**Speed is the product.** Every screen element that does not actively move the user toward payment confirmation is a liability.

**Trust is earned, not assumed.** In a category prone to late deliveries and payment failures, every piece of UI is either building or eroding trust.

**Defaults should be smart.** In a repeat-purchase context (grocery), intelligent defaults based on user history and context eliminate the majority of decisions.

### 4.2 Iteration Log

**Address Step — Iteration 1:**  
Displayed addresses in a simple ranked list with geo-distance below each entry. Tested with 5 users. Problem: users still spent time reading addresses; the geo-distance label wasn't immediately actionable.

**Address Step — Iteration 2:**  
Added a "Delivering here?" confirmation card at the top of the screen showing the auto-selected nearest address, with a large confirm button and a "Change" link below. Result: address-step completion time dropped by ~22 seconds in informal testing.

**Upsell — Iteration 1:**  
Replaced 3 carousels with 1 carousel showing 5 items. Still felt like an obstacle.

**Upsell — Iteration 2:**  
Replaced carousel with a 3-item horizontal scroll strip labeled "Grab before checkout?" with a "Skip & Pay →" CTA button at the same visual weight as "Add items." This framing respects user autonomy. Testing showed reduced abandonment and maintained add-on rate.

**Payment Recovery — Single iteration:**  
Designed a bottom sheet that auto-surfaces after a 10-second UPI timeout. Content: "UPI didn't connect — try a different way?" with three large payment method tiles (Card, Zepto Pay, Cash on Delivery). Added a retry UPI button with countdown. One-shot design; validated in prototype testing with 0 abandonment in 6 tested sessions.

**Live ETA — Single iteration:**  
Replaced static "~10 min" badge with a live component showing "Arriving by 9:42 PM" with a refresh indicator. Added a "?" info tooltip explaining how the estimate is calculated. Users in testing rated trust in the estimate significantly higher.

---

## 5. Prototype & Validation

### 5.1 Prototype

High-fidelity prototype built in Figma covering the full redesigned checkout flow (5 screens):

1. Cart confirmation
2. Address selection (redesigned)
3. Single upsell strip
4. Payment — success state
5. Payment — failure recovery flow

**→ [View Figma Prototype](https://figma.com/proto/YOUR_LINK_HERE)**

### 5.2 Usability Testing Results (n=8, hi-fi)

| Task | Success Rate | Avg. Time | SUS Score |
|------|-------------|-----------|-----------|
| Complete checkout (no friction) | 100% | 68s | 91/100 |
| Recover from payment failure | 87.5% | 23s | 88/100 |
| Change address during checkout | 100% | 11s | 90/100 |

Original flow SUS benchmark (from interview-phase recordings): **62/100.**  
Redesigned flow average: **89.6/100.** A significant usability improvement.

---

## 6. Handoff & Implementation Notes

### 6.1 What Engineers Need

Each solution was accompanied by an annotated Figma spec including:
- Component states (default, hover, loading, error, success)
- API touchpoints (address geo-ranking endpoint, payment timeout webhook, ETA polling interval)
- Edge cases (no GPS permission, >5 saved addresses, COD-not-available zones)

### 6.2 A/B Testing Plan

| Experiment | Control | Treatment | Primary Metric | Sample Size (est.) |
|------------|---------|-----------|----------------|-------------------|
| Address ranking | Current list | Geo-ranked + confirm card | Address step completion time | 50,000 sessions |
| Upsell reduction | 3 carousels | 1 strip + Skip CTA | Checkout CR | 100,000 sessions |
| Payment recovery | No recovery UI | Bottom sheet on timeout | Payment failure recovery rate | 30,000 sessions |

Statistical significance target: 95% confidence. Minimum detectable effect: 2% relative change in CR.

---

## 7. What I Would Do Next

If this were a live PM engagement, the next sprint would address:

1. **Substitution UX** — when an item goes out of stock during checkout, the current "remove item" flow is jarring. A smart substitution suggestion (pre-approved by user preference) would reduce cart abandonment.

2. **Coupon discovery** — coupon codes are buried; a "Best offer applied" auto-coupon pattern (similar to Blinkit) would increase cart value perception.

3. **Returning user fast-track** — for users with a single address and a saved UPI, the entire checkout could be a single "Confirm & Pay" screen. This is the ultimate expression of the "Speed is the product" principle.

---

## Appendix: Research Artifacts

- [User Interview Discussion Guide](research/user-interviews.md)
- [Heuristic Audit Findings](research/heuristic-audit.md)
- [Competitive Analysis Matrix](research/competitive-analysis.md)
- [RICE Scoring Model](metrics/impact-model.md)

---

_This case study was produced for portfolio purposes. All user data is simulated; no proprietary Zepto data was used._
