# Evidence Collection Prototype — Master Fix List

Consolidated from three perspectives: Shruti (founder), UX Director (IA audit), and Compliance Analyst (usability test).

---

## P0 — Fix Before Any Demo
*These break credibility on inspection.*

1. **Fix impossible questionnaire data** — Access Control bar shows 28/24. Section bar totals don't add to 186. Numerators don't add to 142. All numbers must reconcile.
2. **Resolve Phase 4 state contradiction** — Header badge says SENT, bundle card says DRAFT. Pick one true state and make it consistent.
3. **Remove duplicate content across Phase 0 and Phase 2** — SEC EDGAR and Adverse Media appear in both. Each document needs one canonical home.
4. **Fix Phase 1 NDA status** — Pen test is still showing "blocked — NDA required" even though it was obtained and is in the Round 2 review. Phase 1 should reflect that this gap was resolved via outreach.
5. **Fix breadcrumb** — "New Vendor Assessment" → "Twilio Inc." The vendor name is known.
6. **Replace browser alert** — "Proceed to Risk Assessment" fires a native browser alert. Replace with an in-UI state change or summary screen.

---

## P1 — High Impact Design Improvements
*These address core evaluation criteria: AI story, analyst workflow, IA clarity.*

### AI Agency (Shruti's core ask)

7. **Surface AI gap identification as a visible moment** — Add a step or panel where the AI explains *why* it flagged the 5 gaps. What's missing, what framework clause it maps to, what the risk is. This is Zania's core value prop and it's currently invisible.
8. **Show AI reasoning at decision points** — In Response Review, the AI flags issues but doesn't explain its confidence or the rule it applied. Add: "AI flagged this because [X]. Confidence: high/medium. Recommended action: [Y]."
9. **Make auto-cleared items reviewable** — The green cleared box is a black box. Analysts need to be able to expand cleared items, see the AI's reasoning, and override if needed.

### Analyst Decision Layer

10. **Clarify Accept vs. Accept with note consequences** — Add one line per button explaining downstream impact. E.g., "Accept with note — flags this item in the final risk report."
11. **Make re-request queue transparent** — When an item is added to re-request, show: when Round 3 will be triggered, what will be sent, who it goes to.
12. **Add email preview in Vendor Outreach** — Show a draft of the actual email the vendor receives. This closes the loop on Shruti's brief ("compiled gaps sent via email") and demonstrates end-to-end thinking.
13. **Make "Proceed to Risk Assessment" a real handoff** — Replace the dead end with a brief summary: what evidence is being passed forward, what flags exist, what the analyst decided. Even a simple confirmation screen works.

### Navigation & IA Structure

14. **Add sequence numbers to phase steps** — Status and position are different things. Steps need both: a number (1–6) and a status indicator.
15. **Visually connect pipeline strip to phase nav** — Make it clear the phase nav is a drill-down of the current pipeline step. A label, an indent, or a connecting visual cue.
16. **Move "Round 2" context closer to where it's relevant** — Either remove from global topbar and put it only in Phase 4/5 headers, or add a tooltip explaining what "Round" means.
17. **Fix stats grid** — Replace "Sent" with a number (e.g., "5") and update the label to "Items Sent." All four stats must be the same data type.

---

## P2 — Usability & Polish
*These improve the experience but don't block submission.*

18. **Add expand affordance to clickable rows** — Chevron or arrow indicator on rows that expand. Currently no visual cue distinguishes expandable rows from static ones.
19. **Remove duplicate CTAs in Phase 1** — The bottom "Get from Trust Center" / "Request from Vendor" buttons duplicate the inline buttons in the expanded pen test row. Remove the bottom ones or scope them clearly.
20. **Fix "Skip" copy** — "Proceed to assessment with current evidence" navigates to Phase 5, not Risk Assessment. Copy should match destination.
21. **Standardize phase subtitle grammar** — All six phase descriptions should follow the same sentence pattern. Currently some describe tools, some describe processes, some describe states.
22. **Make AI activity log entries navigable** — Each log entry should be clickable and navigate to the relevant phase. "Flagged pen test: expired" should take you to Phase 5, item 1.
23. **Add send bundle transition signal** — After "Send All", show a brief "Navigating to Response Review…" state before auto-navigating. The current jump feels like a bug.
24. **Add timestamps to collected documents** — Phase 1 documents need collection dates. Evidence recency is critical for compliance.

---

## P3 — Missing Context (Stretch, High Value)
*These aren't in the current prototype but would significantly strengthen the analyst story.*

25. **Add assessment deadline/SLA** — Show the due date somewhere prominent. Every compliance workflow is deadline-driven.
26. **Add questionnaire drill-down** — Phase 3 needs one level deeper — let the analyst see individual questions, AI-filled answers, and override them. Even showing 3-4 sample questions per section would demonstrate the concept.
27. **Add policy guardrail on decisions** — When the AI flags something out of policy (e.g., pen test >12 months), surface the relevant policy rule inline so the analyst knows whether accepting is a policy exception.

---

## Deliverables (Non-Prototype)

28. **Write the Rationale & Strategy doc** — Required by Shruti's brief. UX strategy + AI workflow description.
29. **Publish to a hosted/shareable link** — Required for submission.

---

## Effort vs. Impact

| Priority | Count | Effort |
|---|---|---|
| P0 — Must fix | 6 | Low — data/copy corrections |
| P1 — High impact | 11 | Medium — interaction + content additions |
| P2 — Polish | 7 | Low — mostly copy and small UI |
| P3 — Stretch | 3 | Medium-High |
| Deliverables | 2 | High |
