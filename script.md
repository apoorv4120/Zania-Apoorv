# Zania Deliverable — Design Script & Decisions

## What We're Building

A single hosted URL that is both the prototype AND the case study. No separate attachments. Shruti opens one link and gets the full story.

---

## Entry Flow

### Intro Screen (before the prototype)

Three sections in CAR format — context, action, result. Reads like a senior designer's portfolio case study. Prototype is the centerpiece; copy is a preamble, not the main event.

**Section 1 — The Challenge**
Brief summary of the assignment + what deeper analysis surfaced as the specific failures:
- Interface treats evidence collection as a conversation feed, not a process — phases blur, status is invisible
- AI is visually dominant but not decision-relevant — chat fills the screen without guiding the next action
- Data rendered in flat lists regardless of type — security scores, documents, questionnaire coverage, vendor conversations all get the same treatment

**Section 2 — Design Approach**
How the redesign addresses those problems:
- Phase navigator replaces chat stream as primary orientation layer — analysts arrive informed, not mid-story
- Each of the 6 phases gets a view built for its specific data type
- AI repositioned from dominant to ambient — always present at point of decision, never competing with the work
- Design system: IBM Plex Sans + IBM Plex Mono for typographic hierarchy, Lucide icons for consistent status language, semantic color token system (positive / caution / critical) applied throughout — documented in Claude Code across all sessions

**Section 3 — AI Workflow**
How Claude Code was used as a design collaborator, not a code generator:
- Implementation planning against the brief before any interface work began
- Persistent Superpowers skill created from the brief so design context carried across sessions
- Memory files tracked every major decision, fix, and iteration — updated after each session
- Two structured critique passes: Claude simulating a UX director (IA specialist), then a compliance analyst as end user — both surfaced specific issues acted on in subsequent sessions

**CTAs after intro:**
- "Take the guided walkthrough →" — enters tour mode
- "Explore freely →" — clean prototype, no annotations

---

## Two Modes Inside the Prototype

### Guided Tour Mode
- Linear scripted walkthrough — Shruti is being shown the prototype, not free-exploring
- Collapsible bottom drawer (LinkedIn message drawer pattern) advances through scripted stops
- Each stop: a designer's note explaining the decision for that view/moment
- "Next →" button moves forward through the narrative
- Drawer is collapsible so she can look at a screen without the panel in the way

### Explore Freely Mode
- Clean prototype — zero annotations, zero panels
- Exactly as designed, no distractions

---

## Why This Approach

- Mirrors a portfolio case study structure (problem → solution → process) but as a live product
- Two modes solve the core tension: guided narrative requires interruption; clean prototype requires none
- The CTA choice itself demonstrates UX thinking — the reviewer's experience treated as a design problem
- Shruti can check the eval criteria (UX strategy + AI workflow) from the intro, then verify them by interacting

---

## Scripted Tour Stops

7 stops. Each stop is ~3–5 sentences: one sharp insight + what was changed and why.

---

### Stop 1 — AI Briefing (default landing)

**What's here:** Evidence Summary header with key stats (7 docs / 142 of 186 Qs / 2 rounds / 3 items to review) + "Select a phase to explore" placeholder.

**Designer's note:**
Most tools open a vendor assessment to a wall of documents — the analyst reconstructs the story themselves. This redesign flips that: the AI Briefing is the default landing state. Before touching anything, the analyst can see that collection is complete across all phases, what the AI found, and what needs their attention. The stats at the top of the phase nav — Coverage, Open Gaps, Pending Review, Round — give a one-glance health check. Everything is oriented before a single phase is opened.

---

### Stop 2 — Phase Navigator

**What's here:** Left-panel phase nav with 2 groups (Evidence: 4 phases / Vendor Communication: 2 phases), live status badges, stats grid, AI activity log.

**Designer's note:**
The phase navigator is the core structural decision of this redesign. Evidence collection isn't a document list — it's a sequential process with distinct stages, each with its own data type and completion state. Splitting it into two groups (Evidence and Vendor Communication) reflects the actual workflow: the first four phases are AI-run, the last two are where the analyst is needed. Status badges make state visible at a glance without opening anything. The stats grid is clickable — each number navigates directly to the relevant phase.

---

### Stop 3 — Phase 1: External Security Scan

**What's here:** 3-column scan card grid (BitSight / SecurityScorecard / Shodan) + AI Summary box.

**Designer's note:**
External scan results come from three sources with different scoring systems. Rendering this as a list loses the comparative signal — you can't see at a glance whether the sources agree or conflict. The card grid makes them scannable side-by-side: score, grade, and sub-metrics per source. The AI Summary box at the bottom synthesises across all three so the analyst gets the verdict without reading every row.

---

### Stop 4 — Phase 3: Questionnaire Coverage

**What's here:** Hero number (142/186, 76.3%), overall progress bar, 11-section coverage chart with color-coded bars.

**Designer's note:**
A questionnaire with 186 questions across 11 domains can't be communicated as a single progress bar — the per-domain picture is what the analyst actually needs. Red bars (Business Continuity at 47%, HR Security at 57%) tell the analyst immediately which domains need vendor follow-up. The hero number gives the executive summary; the coverage chart gives the operational detail. These two layers serve two different decisions: the number tells you where you are, the chart tells you what to do next.

---

### Stop 5 — Phase 4: Vendor Outreach

**What's here:** Bundle card with 5 line items (each editable), countdown timer, email preview toggle, 3-state send flow (draft → sending → waiting + view CTA).

**Designer's note:**
Vendor outreach in most tools is: copy a gap list, paste into email, send manually. This redesign bundles all open items into a structured follow-up package — each item has a type badge (DOC or QUESTIONNAIRE), an editable message draft, and a round label. The countdown timer shows when auto-escalation kicks in. The email preview lets the analyst inspect what's going out before it does. After sending, the view transitions to a waiting state and reveals a "View Responses" CTA when Twilio responds — the analyst never has to manually navigate back.

---

### Stop 6 — Phase 5: Vendor Response Review

**What's here:** Split-pane layout — left shows 19 items across 3 filter tabs (Review / Awaiting / Resolved), right shows the selected item's full thread with R1→R2 conversation, AI analysis boxes, and analyst action buttons.

**Designer's note:**
Response Review is where the analyst makes binding decisions. The split pane separates the queue (what needs attention) from the detail (what happened and what to do). The thread view shows the full round history — outreach sent, vendor response, AI analysis — in chronological order so context is never lost. The AI analysis box at each round shows confidence level, the specific control being evaluated (SOC 2 CC7.2, ISO 27001 A.17.1.2), and a recommendation with reasoning. The analyst accepts, accepts with an exception note, or re-requests. Every decision is recorded for the audit trail.

---

### Stop 7 — Risk Assessment

**What's here:** Two states — Ready (evidence summary + begin button) → Report (streaming AI chat left + progressive right panel reveal: tier selector → confirm CTA → vendor profile → dimension bars).

**Designer's note:**
Most tools show a loading spinner while AI processes. This redesign turns the wait into a conversation. Three AI messages stream in progressively — each one revealing a new layer of the analysis. The tier selector appears after the second message, before the recommendation lands, so the analyst can start forming a view. After the third message, Tier 2 auto-selects with an AI RECOMMENDED badge. The dimension bars animate in on the right. The analyst can override at any point — the AI shows its work, the analyst confirms or corrects.

---

## Remaining Work

1. **Intro screen** — build the 3-section landing page (copy approved, now build)
2. **Mode selector** — two CTAs after intro sections
3. **Guided tour engine** — bottom drawer + scripted stop navigation
4. **Hosting** — publish to shareable URL

---

## What NOT to Change

- The prototype itself (prototype-v3.html) — it's done
- The 3-layer IA, color tokens, typography — locked
- The AI Briefing as default landing state
- Phase 5 split-pane layout — this is the current shipped state
