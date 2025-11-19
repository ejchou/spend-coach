# Spend Coach — Real-Time Coaching UI (Block AI Fellowship Demo)

**Live Demo:** https://spendcoach.framer.website/  
**Case Study:** [Notion or site link]  
**Figma File:** https://www.figma.com/design/zn0belzO8kskqc87FpOrUe/Spend-Coach?node-id=0-1&t=wOQ8htkGa449UuFD-1  
**Demo Video:** [`assets/demo.mp4`]  
**Hero GIF:** [`assets/hero.gif`]

---

## Overview

Spend Coach explores how **real-time model feedback** can coach users toward healthier money habits.  
The prototype shows:
- A **Thinking → Result → Dismiss/Undo** loop with visible latency
- **Confidence + rationale chips** for transparency
- **Guardrails** (low-confidence state, slow fallback, error)
- **Controls** (Confirm, Edit, Dismiss/Undo)

> Goal: design for **trust, not magic** — every suggestion is explainable and reversible.

---

## How to Use (No Code)

1. Open the **Live Demo** link.  
2. On the Spend Coach screen, use the **Sample Events**:
   - Dining high
   - Shopping streak
   - Paycheck
   - Slow analysis
   - Analysis error
3. Watch the **Thinking** state for ~300–500 ms, then the **Result** state.
4. Try **Confirm / Edit / Undo**.
5. Notice the small chip: *Model v0.2 · ~320 ms · confidence 0.82*.

Screenshots are in `/assets/`.

---

## Scenarios & Messages

This prototype uses pre-baked responses to simulate model output.  
See `/data/model_responses.json` and `/data/transactions.json`.

- **Dining high** → high-confidence suggestion with rationale chips  
- **Shopping streak** → low-confidence suggestion with rationale chips 
- **Paycheck deposit** → “Pay yourself first” nudge  
- **Slow fallback** (>800ms) → safe default with clear copy  
- **Error** → suggestions disabled; manual controls visible

---

## Design Notes

- **Latency & Confidence** are visible to set expectations.  
- **Rationale chips** (“Weeknight increase”) replace long explanations.  
- **Undo** and **Edit** make suggestions safe and teachable.  
- **Modes:** Conservative / Balanced / Bold adjust thresholds (simulated).

---

## Responsible AI

- **Transparency:** version, latency, confidence shown inline.  
- **Safety rails:** graceful fallback when slow/uncertain.  
- **User agency:** accept, tweak, or undo any suggestion.  
- **Limitations:** demo uses simulated data and responses.

---

## File Map

/assets  
hero.gif  
demo.mp4  
spendcoach_home.png  
spendcoach_analysis.png  
/data  
transactions.json  
model_responses.json  
README.md  

---

## What I’d Explore Next

- Hooking telemetry to measure **accept**, **override**, and **dismiss** rates  
- **Multi-model routing** for budgeting vs. saving vs. cash-flow predictions  
- Creating **design system primitives** for “intelligent states” (thinking, rationale, uncertainty)

---

## License

MIT © Eileen Chou

---

# Spend Coach v0.2 — Model Card  
*(Simulated AI for the Block AI Fellowship Prototype)*  

---

## Overview
Spend Coach v0.2 is a **simulated real-time classification and nudging model** designed to demonstrate how a budgeting app might deliver transparent, explainable financial insights in-app.  
It does not process live data; all inputs and outputs are synthetic, built to illustrate latency, confidence, and rationale feedback loops for responsible AI design.

---

## Intended Use
Spend Coach generates short, contextual messages that help users understand and manage spending trends.  
It is meant to:
- Detect patterns in recent transactions (e.g., spending spikes, recurring deposits).  
- Provide supportive, human-readable nudges (“You’re trending 20 % above average”).  
- Expose model states — confidence, rationale, latency — to build user trust.  

**Not intended for:** real financial advice, autonomous fund transfers, or risk scoring.

---

## Inputs & Outputs
| Type | Example | Description |
|------|----------|-------------|
| **Input** | `amount`, `merchant`, `timestamp`, `category` | Synthetic transaction data. |
| **Output** | `message`, `confidence`, `latency_ms`, `rationale[]` | Pre-baked JSON simulating model behavior. |

---

## How It Works
- The prototype simulates a model call that returns:  
  `{ prediction, confidence, rationale, latency_ms }`.  
- Responses are static JSON objects representing **High**, **Low**, **Fallback**, and **Error** scenarios.  
- Latency (250–1100 ms) is used to demonstrate real-time responsiveness and fallback design.  

---

## Evaluation & Success Signals
Although no real model inference occurs, evaluation is guided by:  
- **User Comprehension:** clarity of rationale and transparency chips.  
- **Action Rate:** how often users accept, tweak, or undo suggestions.  
- **Trust Indicators:** qualitative feedback on whether the AI feels “understandable and in-control.”

---

## Ethical & Safety Considerations
| Risk | Mitigation |
|------|-------------|
| Misinterpretation of “advice” | Frame as *insight* not instruction; include Undo & manual control. |
| Overconfidence in uncertain data | Low-confidence results display visually muted and include “Low Data” rationale. |
| Latency / failure | Fallback and Error states provide graceful degradation and transparency (“Model offline · manual mode”). |
| Bias from limited inputs | Only synthetic, de-identified data used; future real models would require bias audits and human oversight. |

---

## Limitations
- Uses **mock data only** — no predictive accuracy.  
- Does **not learn or adapt**; all responses are pre-defined.  
- Cannot infer nuanced financial behaviors or intent.  
- Should not be deployed in production without privacy and fairness reviews.

---

## Transparency & Versioning
Each interface surface shows: *Model v0.2 · ~320 ms · confidence 0.78*.  
Visible version, latency, and confidence remind users that the system is probabilistic and time-bounded.

---

## Responsible AI Notes
- **Explainability:** Short rationale chips replace long texts and opaque scores.  
- **User Agency:** every suggestion is reversible (“Undo”) and optional.  
- **Accessibility:** confidence indicators do not rely on color alone.  
- **Privacy:** demo contains no personal or financial data.  

---

## Future Work
If developed beyond simulation:
- Integrate real transaction telemetry with opt-in consent.  
- Add continual evaluation for precision, recall, fairness, and transparency.  
- Embed standardized *Model Card JSON Schema* for automated audits.

---

© 2025 Eileen Chou · For Block AI Fellowship Application


