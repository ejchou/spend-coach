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

