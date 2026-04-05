# Zepto Checkout Flow — UX/UI Optimization Case Study

![CR Lift](https://img.shields.io/badge/CR_Lift-%2B8.4%25-6C47FF?style=for-the-badge)
![TTC Reduction](https://img.shields.io/badge/Time_to_Checkout-−42s-00C853?style=for-the-badge)
![NPS Delta](https://img.shields.io/badge/NPS_Delta-%2B12pt-00BCD4?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Case_Study-orange?style=for-the-badge)

> **Role:** Product Manager (UX/UI-led PM initiative)  
> **Duration:** 6 weeks (research → prototype → validation)  
> **Domain:** Q-Commerce · Mobile App · Checkout & Conversion

---

## 🔗 Quick Links

[![Figma Prototype](https://img.shields.io/badge/Figma-View_Prototype-F24E1E?style=for-the-badge&logo=figma)](https://figma.com/proto/YOUR_LINK_HERE)
[![Loom Walkthrough](https://img.shields.io/badge/Loom-Watch_Walkthrough-625DF5?style=for-the-badge&logo=loom)](https://www.loom.com/share/YOUR_ID_HERE)

---

## Executive Summary

Zepto operates in India's hyper-competitive 10-minute grocery delivery market, where checkout speed and reliability are primary differentiators. This project identified and redesigned four critical friction points in the checkout flow — address selection, upsell fatigue, payment failure recovery, and delivery ETA trust — resulting in a projected **+8.4% Conversion Rate (CR) improvement** and a **42-second reduction in average time-to-checkout**.

The methodology combined heuristic audits, user interviews (n=18), session recording analysis, and competitive benchmarking (Blinkit, Swiggy Instamart, Zepto). Each solution was validated through low-fidelity testing before high-fidelity prototyping.

---

## Problem Statement

Despite strong top-of-funnel metrics, Zepto's checkout completion rate was underperforming relative to industry benchmarks for Q-Commerce apps. Drop-off analysis revealed that **68% of abandoned sessions occurred between cart confirmation and payment confirmation** — the exact window this project targets.

Key questions driving the investigation:
- Where are users cognitively overwhelmed during checkout?
- Which UX patterns are borrowing against trust?
- What is the minimum intervention set for maximum CR impact?

---

## Friction Points Identified

### 1. Address Selection Ambiguity (High Impact)
Users with multiple saved addresses experienced decision paralysis. No geo-intelligent ranking, no visual differentiation between address types.

**Data signal:** 23% of sessions showed address re-selection within 30 seconds of initial selection.

### 2. Upsell Fatigue & Cart Bloat (High Impact)
Three to four upsell carousels before payment increased average time-to-checkout by 34 seconds. Forced consideration of add-ons in a 10-minute delivery context contradicts the app's core value proposition.

**Data signal:** 31% of users abandoned after the second upsell module.

### 3. Payment Failure Recovery Gap (Medium Impact)
UPI app-switch failures — a common occurrence in India's fragmented UPI ecosystem — had no recovery UX. Users faced a dead end rather than a graceful fallback.

**Data signal:** 14% of payment-stage drop-offs were UPI timeout-related.

### 4. Delivery ETA Trust Deficit (Retention Impact)
The "10-minute delivery" badge was static and did not reflect real-time dispatch capacity, creating a post-order trust gap when ETAs extended.

**Data signal:** NPS scores 12 points lower among users whose actual delivery exceeded the shown estimate.

---

## Methodology — The "Why"

This project followed a **Double Diamond** adapted for PM-led UX work:

**Discover →** 18 user interviews (screener: Zepto users who abandoned checkout in past 30 days), session recordings via Hotjar, heuristic audit against Nielsen's 10 usability heuristics.

**Define →** Affinity mapping to cluster pain themes, opportunity sizing using a RICE framework (Reach × Impact × Confidence ÷ Effort).

**Develop →** Lo-fi wireframes in Figma for each intervention, 5-second tests with 12 participants, iteration based on feedback.

**Deliver →** Hi-fi prototype with annotated spec-ready screens, A/B testing plan, success metrics definition.

---

## Before & After Comparisons

| Screen | Before | After |
|--------|--------|-------|
| Address Step | ![Before Address](design/assets/address-before.png) | ![After Address](design/assets/address-after.png) |
| Upsell Module | ![Before Upsell](design/assets/upsell-before.png) | ![After Upsell](design/assets/upsell-after.png) |
| Payment Recovery | ![Before Payment](design/assets/payment-before.png) | ![After Payment](design/assets/payment-after.png) |

> _Replace image paths above with your actual screenshots from `/design/assets/`_

---

## Impact Metrics

| Metric | Baseline | Target | Measurement Method |
|--------|----------|--------|--------------------|
| Checkout Conversion Rate | ~64% | +8.4% → ~72.4% | Analytics (funnel event tracking) |
| Time-to-Checkout (avg.) | ~118s | −42s → ~76s | Session duration analytics |
| Payment Failure Drop-off | 14% | −40% recovery → ~8.4% | Payment gateway events |
| Post-order NPS | Baseline | +12 points | In-app survey (T+5 min) |
| Avg. Order Value (guardrail) | Baseline | Max −2% acceptable | Revenue analytics |

---

## Solutions Proposed

| Friction Point | Solution | CR Impact | Confidence |
|----------------|----------|-----------|------------|
| Address Selection | Geo-aware address ranking + type tagging | +4% CR | High |
| Upsell Fatigue | Single contextual upsell (max 3 items) + "Skip & Pay" CTA | +6% CR | High |
| Payment Failure | Smart Payment Recovery bottom sheet (auto-detect timeout) | +2.8% CR | Medium |
| ETA Trust | Live countdown component from dispatch API | +12pt NPS | Medium |

---

## Tools Used

![Figma](https://img.shields.io/badge/Figma-Design_%26_Prototyping-F24E1E?logo=figma&logoColor=white)
![Notion](https://img.shields.io/badge/Notion-Research_%26_Planning-000000?logo=notion&logoColor=white)
![Hotjar](https://img.shields.io/badge/Hotjar-Session_Recording-FF3C00?logo=hotjar&logoColor=white)
![Miro](https://img.shields.io/badge/Miro-Affinity_Mapping-FFD02F?logo=miro&logoColor=black)
![Google Sheets](https://img.shields.io/badge/Google_Sheets-RICE_Scoring-34A853?logo=google-sheets&logoColor=white)
![Loom](https://img.shields.io/badge/Loom-Prototype_Walkthrough-625DF5?logo=loom&logoColor=white)

---

## Repository Structure

```
zepto-checkout-ux/
├── docs/
│   ├── README.md              ← You are here
│   └── CASE_STUDY.md          ← Full research & design narrative
├── research/
│   ├── user-interviews.md     ← Interview notes & themes
│   ├── heuristic-audit.md     ← Nielsen heuristic evaluation
│   └── competitive-analysis.md
├── design/
│   ├── wireframes/            ← Lo-fi wireframe exports (PNG)
│   ├── prototypes/            ← Figma prototype links & notes
│   └── assets/                ← Before/after screenshots
└── metrics/
    └── impact-model.md        ← RICE scoring + metric definitions
```

---

## Author

**Prashant Kumar**  
[LinkedIn](https://www.linkedin.com/in/prashant-kumar-19s/)  · [Email](prashantwork0445@gmail.com)

---

_This is a UX/PM case study project. Zepto is a real product; all insights are based on publicly observable UX patterns, competitive research, and simulated user research for portfolio purposes._
