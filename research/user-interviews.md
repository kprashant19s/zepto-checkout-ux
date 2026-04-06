# User Research — Interview Notes & Themes

**Method:** Semi-structured interviews  
**Participants:** 18 users  
**Screener:** Zepto users who abandoned checkout at least once in the past 30 days  
**Duration:** 45 minutes per session  
**Format:** Remote via Google Meet + think-aloud protocol  

---

## Participant Demographics

| # | Age | City | Zepto Usage | Abandoned Step |
|---|-----|------|-------------|----------------|
| P1 | 24 | Bangalore | Daily | Payment |
| P2 | 31 | Delhi | 3x/week | Upsell |
| P3 | 27 | Mumbai | Daily | Address |
| P4 | 29 | Hyderabad | 2x/week | Payment |
| P5 | 22 | Bangalore | Daily | Upsell |
| P6 | 35 | Delhi | Weekly | Address |
| P7 | 28 | Pune | 3x/week | Upsell |
| P8 | 33 | Mumbai | Daily | Payment |
| P9 | 26 | Bangalore | Daily | Address |
| P10 | 30 | Chennai | 2x/week | Upsell |
| P11 | 25 | Delhi | 3x/week | Payment |
| P12 | 32 | Hyderabad | Weekly | Address |
| P13 | 27 | Bangalore | Daily | Upsell |
| P14 | 29 | Mumbai | 3x/week | Payment |
| P15 | 24 | Delhi | Daily | Address |
| P16 | 31 | Pune | 2x/week | Upsell |
| P17 | 28 | Bangalore | Daily | Payment |
| P18 | 26 | Chennai | 3x/week | Upsell |

---

## Key Themes from Affinity Mapping

### Theme 1 — Address Confusion (12/18 participants)

**Representative quotes:**
- P3: *"I have 3 addresses saved — home, office, and my parents' place. I can never remember which one I set last."*
- P6: *"I just tap the first one and hope it's correct. Half the time it's not."*
- P9: *"Why doesn't it just know I'm at home right now?"*
- P15: *"I've ordered to my office at 11pm by mistake. The app should be smarter."*

**Observed behaviour:** Users spent average 28 seconds on the address step. 23% re-selected their address at least once.

**Root cause:** No geo-intelligent ranking, no contextual default, no visual tag differentiation between Home/Work/Other.

---

### Theme 2 — Upsell Fatigue (16/18 participants)

**Representative quotes:**
- P2: *"I just want to pay. Why are they showing me chips again?"*
- P5: *"There are like 3 or 4 screens of 'you might also want' before I can pay. It's annoying."*
- P7: *"I know what I came to buy. I don't need suggestions right before checkout."*
- P13: *"The whole point of Zepto is speed. These upsells completely kill that."*
- P18: *"I've literally just closed the app because of how many upsell screens there are."*

**Observed behaviour:** 31% of users abandoned during the upsell step. Average time spent on upsell screens: 34 seconds.

**Root cause:** 3-4 upsell carousels with 8-10 items each. No clear "skip" option at equal visual weight to "add items."

---

### Theme 3 — Payment Failure (8/18 participants)

**Representative quotes:**
- P1: *"The UPI just spun and then nothing happened. I didn't know if my order went through or not."*
- P4: *"When PhonePe didn't open, I panicked and closed the app. I didn't want to be charged twice."*
- P8: *"There was no button to try again. I had to start my whole cart from scratch."*
- P11: *"I would have paid by card but the app never suggested it. It just failed."*

**Observed behaviour:** 4 out of 4 participants who experienced a simulated UPI timeout abandoned entirely. None tried an alternative payment method.

**Root cause:** No recovery UX after UPI timeout. No fallback suggestion. No retry mechanism.

---

### Theme 4 — ETA Trust Gap (8/18 participants)

**Representative quotes:**
- P3: *"It always says 10 minutes but it never actually comes in 10 minutes."*
- P9: *"I've stopped believing the delivery time. It feels like marketing."*
- P14: *"If they just told me the real time I'd be fine with it. The lying is what bothers me."*
- P17: *"I ordered for a dinner party and it came 25 minutes late. The app said 10 minutes."*

**Observed behaviour:** 8 participants mentioned receiving orders later than the shown estimate. NPS 12 points lower among this group.

**Root cause:** Static "10 min" badge not connected to real-time dispatch data.

---

## Secondary Themes (Future Sprints)

- **Substitution UX** — 6 participants frustrated when items go out of stock mid-checkout with no smart replacement
- **Coupon discovery** — 5 participants didn't know coupons existed; found them only by accident
- **Order tracking anxiety** — 4 participants opened the app repeatedly after ordering to check status

---

## Research Methodology Notes

- Think-aloud protocol used throughout — participants narrated their actions in real time
- Sessions recorded with participant consent
- Hotjar session recordings analyzed for rage taps, scroll depth, and time-on-screen
- Affinity mapping conducted in Miro — 3 rounds of clustering to identify themes
