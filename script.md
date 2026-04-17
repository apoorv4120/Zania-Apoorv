# Zania Deliverable — Design Script & Decisions

## What We're Building

A single hosted URL that is both the prototype AND the case study. No separate attachments. Shruti opens one link and gets the full story.

---

## Entry Flow

### 1. Intro Screen (before the prototype)
Three sections, in this order:
1. **Problem** — the UX pain points the brief identified (cognitive overload, data density, complex round histories, chat-dominant layout)
2. **UX Strategy** — how the redesign solves those problems (phase navigator, 3-layer IA, ambient AI, phase-specific detail views)
3. **AI Workflow** — how Claude was used as a collaborative design + prototyping partner (not just code generation — UX thinking, iteration, decision-making)

After reading all three sections, Shruti gets two CTAs:
- **"Take the guided tour →"** — enters walkthrough mode
- **"Explore freely →"** — enters the prototype with no annotations

---

## Two Modes Inside the Prototype

### Guided Tour Mode
- A linear, scripted walkthrough — she is being *shown* the prototype, not free-exploring
- A collapsible bottom drawer (LinkedIn message drawer pattern) advances through scripted stops
- Each stop: a designer's note explaining the decision for that view/moment
- A **"Next →"** button moves her forward through the narrative
- She never has to make navigation decisions — the tour handles it
- Drawer is collapsible if she wants to look at a screen without the panel in the way

### Explore Freely Mode
- Completely clean prototype — zero annotations, zero panels
- Exactly as designed, no distractions
- The prototype speaks for itself

---

## Why This Approach

- Mirrors a portfolio case study structure (problem → solution → process) but as a live product
- Two modes solve the core tension: guided narrative requires interruption; clean prototype requires none. Separate them.
- The CTA choice itself demonstrates UX thinking — Apoorv treated the reviewer's experience as a design problem
- Shruti can check off the brief's eval criteria (UX strategy + AI workflow) from the intro screen, then verify them by interacting with the prototype

---

## Scripted Tour Stops (to be written)

Key moments to cover in the guided tour — rough list, needs to be written out:

1. **AI Briefing (default landing)** — why the analyst arrives informed, not mid-story
2. **Phase Navigator** — why a phase-based structure instead of a chat/list
3. **Phase 0 — External Scan** — how dense data is organized into scannable cards
4. **Phase 3 — Questionnaire** — the coverage chart approach to high data density
5. **Phase 4 — Vendor Outreach** — the bundle card + countdown, removing send chaos
6. **Phase 5 — Response Review** — inline AI judgment + resolution mechanics
7. **Risk Assessment** — streaming AI chat + progressive reveal instead of a loading state

---

## Remaining Work

1. **Intro screen** — build the 3-section case study landing page
2. **Mode selector** — two CTAs after the intro sections
3. **Guided tour engine** — bottom drawer component + scripted stops
4. **Scripted tour copy** — write the designer's notes for each stop
5. **Hosting** — publish to a shareable URL

---

## What NOT to change

- The prototype itself (prototype-v3.html) — it's done
- The 3-layer IA, color tokens, typography — all locked
- The AI Briefing as default landing state
