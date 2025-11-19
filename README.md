# Spend Coach — Real-Time Coaching UI (Block AI Fellowship Demo)

**Live Demo:** [Framer or Lovable link]  
**Case Study:** [Notion or site link]  
**Figma File:** [Figma link]  
**Demo Video:** [`assets/demo.mp4`]  
**Hero GIF:** [`assets/hero.gif`]

---

## Overview

Spend Coach explores how **real-time model feedback** can coach users toward healthier money habits inside Cash App.  
The prototype shows:
- A **Thinking → Result → Undo** loop with visible latency
- **Confidence + rationale chips** for transparency
- **Guardrails** (low-confidence state, slow fallback, error)
- **Controls** (Accept, Tweak, Undo)

> Goal: design for **trust, not magic** — every suggestion is explainable and reversible.

---

## How to Use (No Code)

1. Open the **Live Demo** link.  
2. On the Spend Coach screen, use the **Sample Events**:
   - Groceries high
   - Delivery streak
   - Paycheck deposit
   - Slow fallback
   - Error
3. Watch the **Thinking** state for ~300–500 ms, then the **Result** state.
4. Try **Accept / Tweak / Undo**.
5. Notice the small chip: *Model v0.2 · ~320 ms · confidence 0.82*.

Screenshots are in `/assets/`.

---

## Scenarios & Messages

This prototype uses pre-baked responses to simulate model output.  
See `/data/model_responses.json` and `/data/transactions.json`.

- **Groceries high** → high-confidence suggestion with rationale chips  
- **Delivery streak** → low-confidence suggestion + “Why this?”  
- **Paycheck deposit** → “Pay yourself first” nudge  
- **Slow fallback** (>800ms) → safe default with clear copy  
- **Error** → suggestions disabled; manual controls visible

---

## Design Notes

- **Latency & Confidence** are visible to set expectations.  
- **Rationale chips** (“3 trips in 5 days”) replace long explanations.  
- **Undo** and **Tweak** make suggestions safe and teachable.  
- **Modes:** Conservative / Balanced / Bold adjust thresholds (simulated).

---

## Responsible AI

- **Transparency:** version, latency, confidence shown inline.  
- **Safety rails:** graceful fallback when slow/uncertain.  
- **User agency:** accept, tweak, or undo any suggestion.  
- **Limitations:** demo uses simulated data and responses.

---

## File Map

