# Impact Model & RICE Scoring

**Framework:** RICE (Reach × Impact × Confidence ÷ Effort)  
**Purpose:** Prioritize checkout interventions by expected return  
**Owner:** Product Manager  

---

## RICE Framework Explained

| Variable | Definition | Scale |
|----------|------------|-------|
| Reach | How many users are affected per month | Out of 10 |
| Impact | Effect on the primary metric (CR or NPS) | 1 = minimal, 2 = moderate, 3 = significant |
| Confidence | How sure are we this will work | % (based on research strength) |
| Effort | Engineering + design weeks to ship | Weeks |

**Formula:** `RICE Score = (Reach × Impact × Confidence) ÷ Effort`

---

## RICE Scoring Table

| Opportunity | Reach | Impact | Confidence | Effort | RICE Score | Priority |
|-------------|-------|--------|------------|--------|------------|----------|
| Single contextual upsell + Skip CTA | 10 | 3 | 85% | 2 | 1,275 | P0 |
| Geo-aware address ranking | 8 | 3 | 80% | 2 | 960 | P0 |
| Smart Payment Recovery flow | 7 | 3 | 70% | 3 | 490 | P1 |
| Live ETA component | 9 | 2 | 75% | 4 | 337 | P1 |
| One-tap checkout (returning users) | 6 | 3 | 65% | 5 | 234 | P2 |
| Auto-apply best coupon | 7 | 2 | 70% | 3 | 326 | P2 |
| Substitution UX on out-of-stock | 5 | 2 | 60% | 4 | 150 | P3 |

---

## P0 Interventions (Ship in Sprint 1)

### 1. Single Contextual Upsell + Skip CTA
**RICE Score: 1,275**

- **Reach:** 10/10 — affects every single checkout session
- **Impact:** 3 — directly reduces abandonment at the highest drop-off point
- **Confidence:** 85% — proven pattern from Blinkit, strong user research signal (16/18 participants frustrated by upsells)
- **Effort:** 2 weeks — UI change only, no backend work required

**Expected outcome:**
- CR lift: +6%
- TTC reduction: −28 seconds
- AOV impact: Monitor carefully — guardrail is max −2% AOV drop

**A/B test plan:**
- Control: Current 3-carousel upsell
- Treatment: Single 3-item strip + "Skip & Pay" CTA
- Sample size: 100,000 sessions
- Confidence target: 95%
- Runtime: 2 weeks

---

### 2. Geo-Aware Address Ranking
**RICE Score: 960**

- **Reach:** 8/10 — affects users with 2+ saved addresses (estimated 80% of repeat users)
- **Impact:** 3 — reduces decision time and re-selection at address step
- **Confidence:** 80% — 12/18 interview participants expressed address confusion; GPS ranking is proven pattern
- **Effort:** 2 weeks — requires GPS permission check + ranking logic on address API

**Expected outcome:**
- CR lift: +4%
- TTC reduction: −18 seconds on address step
- Re-selection rate: Target −50% reduction

**A/B test plan:**
- Control: Current alphabetical/recency address list
- Treatment: GPS-ranked list with top address shown as "Delivering here?" confirmation card
- Sample size: 50,000 sessions
- Confidence target: 95%
- Runtime: 2 weeks

---

## P1 Interventions (Ship in Sprint 2)

### 3. Smart Payment Recovery Flow
**RICE Score: 490**

- **Reach:** 7/10 — affects all users who attempt UPI payment (majority of Indian users)
- **Impact:** 3 — directly recovers lost transactions that currently result in full abandonment
- **Confidence:** 70% — strong qualitative signal (4/4 test participants abandoned on UPI failure); moderate confidence on exact recovery rate
- **Effort:** 3 weeks — requires payment gateway webhook integration + new bottom sheet UI

**Expected outcome:**
- Payment failure recovery rate: 40% of failed UPI transactions recovered
- Net CR lift: +2.8%
- Requires: UPI timeout detection (10s threshold), bottom sheet with Card/Zepto Pay/COD tiles

**A/B test plan:**
- Control: Current "Payment failed" dead end
- Treatment: Auto-surface recovery bottom sheet after 10s UPI timeout
- Sample size: 30,000 sessions
- Confidence target: 95%
- Runtime: 3 weeks

---

### 4. Live ETA Component
**RICE Score: 337**

- **Reach:** 9/10 — visible to all users post-order
- **Impact:** 2 — primarily a trust/retention metric, not direct CR impact
- **Confidence:** 75% — 8/18 participants cited ETA disappointment; NPS correlation is strong
- **Effort:** 4 weeks — requires dispatch API integration and real-time polling logic

**Expected outcome:**
- NPS lift: +12 points among users who see accurate ETA
- Reorder rate: Estimated +5% among previously disappointed users
- Requires: Dispatch API with 30s polling, "Why this estimate?" tooltip

---

## Guardrail Metrics

These metrics must be monitored across all experiments. If any guardrail is breached, pause the experiment immediately.

| Guardrail | Threshold | Action if breached |
|-----------|-----------|-------------------|
| Avg. Order Value (AOV) | Max −2% drop | Pause upsell experiment, investigate |
| App crash rate | No increase | Roll back immediately |
| Payment success rate | No decrease | Pause payment experiment |
| Customer support contacts | Max +5% increase | Investigate root cause |

---

## Total Projected Impact (All P0 + P1)

| Metric | Current | After P0+P1 |
|--------|---------|-------------|
| Checkout CR | ~64% | ~72.4% (+8.4%) |
| Avg. Time-to-Checkout | ~118s | ~76s (−42s) |
| Payment failure drop-off | 14% | ~8.4% (−40% recovery) |
| Post-order NPS | Baseline | +12 points |
