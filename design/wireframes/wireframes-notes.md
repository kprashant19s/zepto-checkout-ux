# Wireframes — Lo-Fi Design Process

## Overview

Low-fidelity wireframes were created before high-fidelity prototyping to validate layout and flow decisions quickly with minimal investment. Each wireframe went through at least 2 iterations based on user feedback.

---

## Wireframe Iterations

### Screen 1 — Cart Confirmation

**Iteration 1:**
- Simple list of items with total at bottom
- Single "Proceed" CTA button
- Feedback: Users wanted to see delivery fee clearly before proceeding

**Iteration 2 (Final):**
- Added pricing breakdown (subtotal, delivery fee, platform fee, total)
- "FREE delivery" highlighted in green to reinforce value
- Cleaner item cards with quantity display

---

### Screen 2 — Address Selection

**Iteration 1:**
- Standard list of all saved addresses
- No ranking or default selection
- Feedback: Users still confused about which address to pick, spent 25+ seconds on this screen

**Iteration 2:**
- Added "Delivering here?" confirmation card at top showing geo-ranked nearest address
- Remaining addresses shown below with distance labels
- Feedback: Much faster — users confirmed the top address in under 5 seconds in most cases

**Iteration 3 (Final):**
- Added Home/Work/Other color-coded tags for quick recognition
- Distance shown in km for all addresses
- Confirm button changed to green to signal "safe to proceed"

---

### Screen 3 — Upsell

**Iteration 1:**
- Removed all upsells entirely (control experiment)
- Feedback from PM review: Complete removal risks AOV drop beyond guardrail threshold

**Iteration 2:**
- Single horizontal scroll strip with 5 items
- No skip option
- Feedback: Still felt like an obstacle, users scrolled past without engaging

**Iteration 3 (Final):**
- Single strip reduced to 3 items (personalized)
- "Skip & Pay →" button added at equal visual weight to "Proceed to Payment"
- Label changed to "Grab before checkout?" — softer, less pushy tone
- Result: Reduced abandonment while maintaining add-on opportunity

---

### Screen 4 — Payment

**Iteration 1:**
- All payment methods shown as equal list
- No pre-selection
- Feedback: Users had to actively choose every time, even for repeat orders

**Iteration 2 (Final):**
- UPI pre-selected by default (most used method in India)
- Visual highlight on selected payment method
- Payment methods ordered by popularity: UPI → Card → Wallet → COD

---

### Screen 5 — Payment Recovery

**Iteration 1:**
- Simple "Payment failed. Try again?" message with retry button
- Feedback: Users didn't know what to retry with — still abandoned

**Iteration 2 (Final):**
- Clear error message: "UPI didn't connect"
- Three alternative payment tiles shown immediately
- Retry UPI option kept as secondary action
- Tone: Helpful and solution-focused, not alarming

---

## Wireframe Testing Method

Each iteration was tested using a **5-second test** — participants were shown the wireframe for 5 seconds and then asked:
1. What is the main action on this screen?
2. What would you tap first?
3. Did anything confuse you?

Results were used to iterate before moving to high-fidelity design.

---

## Tools Used

- **Sketching:** Paper and pen for first drafts
- **Digital wireframes:** Figma (lo-fi, grayscale)
- **Testing:** Maze for 5-second tests
- **Feedback collection:** Google Forms post-session survey
