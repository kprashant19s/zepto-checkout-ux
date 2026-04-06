# Heuristic Audit — Zepto Checkout Flow

**Method:** Nielsen's 10 Usability Heuristics  
**Evaluators:** 2 independent evaluators, findings reconciled  
**Severity Scale:** 0 (not a problem) → 4 (usability catastrophe)  
**Scope:** Checkout flow only — from cart confirmation to order confirmation  

---

## Severity Rating Scale

| Rating | Description |
|--------|-------------|
| 0 | Not a usability problem |
| 1 | Cosmetic problem only |
| 2 | Minor usability problem |
| 3 | Major usability problem — important to fix |
| 4 | Usability catastrophe — imperative to fix |

---

## Audit Findings

### H1 — Visibility of System Status
*"The system should always keep users informed about what is going on."*

| Issue | Severity | Screen |
|-------|----------|--------|
| UPI payment spinner has no timeout message — users don't know if it failed or is still processing | 4 | Payment |
| No progress indicator showing which step of checkout the user is on | 2 | All steps |
| Delivery ETA is static — does not update to reflect real-time dispatch capacity | 3 | Order confirmation |

---

### H2 — Match Between System and Real World
*"The system should speak the users' language."*

| Issue | Severity | Screen |
|-------|----------|--------|
| Address labels use internal naming ("Address 1", "Address 2") instead of user-defined names ("Home", "Office") | 3 | Address selection |
| "Proceed" CTA is vague — does not tell user what happens next | 2 | Cart |

---

### H3 — User Control and Freedom
*"Users often choose system functions by mistake and need a clearly marked emergency exit."*

| Issue | Severity | Screen |
|-------|----------|--------|
| No visible "Skip" option on upsell carousels — user must scroll past all items to reach payment | 4 | Upsell |
| Back button during payment flow takes user all the way back to cart, losing payment method selection | 3 | Payment |
| No way to edit cart items from the checkout screen | 2 | Checkout |

---

### H4 — Consistency and Standards
*"Users should not have to wonder whether different words, situations, or actions mean the same thing."*

| Issue | Severity | Screen |
|-------|----------|--------|
| "Add to cart" and "Add item" used interchangeably across upsell modules | 1 | Upsell |
| Primary CTA button changes color between checkout steps with no logical reason | 2 | All steps |

---

### H5 — Error Prevention
*"Even better than good error messages is a careful design which prevents a problem from occurring."*

| Issue | Severity | Screen |
|-------|----------|--------|
| No warning when selected address is far from current GPS location | 3 | Address selection |
| No confirmation step before final payment — users can accidentally place order | 2 | Payment |
| UPI app-switch has no fallback if app is not installed | 4 | Payment |

---

### H6 — Recognition Rather Than Recall
*"Minimize the user's memory load."*

| Issue | Severity | Screen |
|-------|----------|--------|
| Saved addresses show full text only — no map thumbnail or landmark to aid recognition | 3 | Address selection |
| Previously used payment method not highlighted or pre-selected | 2 | Payment |

---

### H7 — Flexibility and Efficiency of Use
*"Accelerators may often speed up the interaction for the expert user."*

| Issue | Severity | Screen |
|-------|----------|--------|
| No "Reorder last cart" shortcut for returning users | 2 | Cart |
| No one-tap checkout option for users with single address and saved UPI | 3 | All steps |

---

### H8 — Aesthetic and Minimalist Design
*"Dialogues should not contain irrelevant or rarely needed information."*

| Issue | Severity | Screen |
|-------|----------|--------|
| 3-4 upsell carousels add significant visual noise before payment | 4 | Upsell |
| Promotional banners compete with primary CTA for visual attention | 2 | Cart |

---

### H9 — Help Users Recognize, Diagnose and Recover from Errors
*"Error messages should be expressed in plain language."*

| Issue | Severity | Screen |
|-------|----------|--------|
| UPI failure shows only "Payment failed" with no explanation or next step | 4 | Payment |
| Address not serviceable error gives no alternative — no suggestion to change address | 3 | Address |

---

### H10 — Help and Documentation
*"Even though it is better if the system can be used without documentation, it may be necessary to provide help."*

| Issue | Severity | Screen |
|-------|----------|--------|
| No explanation of what "10 min delivery" means or how it is calculated | 2 | All screens |
| No tooltip explaining why certain payment methods are unavailable in some areas | 1 | Payment |

---

## Priority Summary

| Severity 4 (Fix immediately) | Screen |
|------------------------------|--------|
| UPI spinner — no timeout message | Payment |
| No skip option on upsells | Upsell |
| UPI fallback missing | Payment |
| Upsell visual noise | Upsell |
| Payment failed — no recovery | Payment |

| Severity 3 (Fix in next sprint) | Screen |
|---------------------------------|--------|
| Static ETA badge | Order confirmation |
| Address labels not user-defined | Address |
| Back button loses payment state | Payment |
| No GPS warning on address | Address |
| No map thumbnail on addresses | Address |
| No one-tap checkout | All steps |
| Address not serviceable — no alternative | Address |
