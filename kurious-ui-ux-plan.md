# Kurious — UI/UX Plan

> Owned by Shivangi Mishra · Draft v1 · March 2026

---

## Design Principles

1. **Business user first** — if a non-technical person cannot use it without training, it is too complex
2. **Answer is the product** — every UI decision should make the answer faster and more trustworthy
3. **Show your work** — always show how Kurious found the answer, never just return a result
4. **Speed as a feeling** — the interface should feel instant even when retrieval takes a moment
5. **Trust by design** — data privacy, source citations, and transparency should be visible, not buried in docs

---

## The Two Products

Kurious has two distinct interfaces that share the same engine but serve different users.

### Product 1 — Kurious for Business Users
Simple, fast, conversational. Ask a question, get an answer with sources. No setup required by the user.

### Product 2 — Kurious for Developers / Engineers
API access, algorithm selection (Vibe-Discovery), pipeline builder, evaluation tools. Full control.

This document focuses primarily on **Product 1 — the business user experience**, as that is what drives enterprise adoption.

---

## User Journey — Enterprise Business User

```
Invited by admin
       ↓
First login — welcome screen
       ↓
Onboarding — connect to their data sources (admin does this, not user)
       ↓
Home — search interface
       ↓
Ask a question
       ↓
See thinking steps (retrieval in progress)
       ↓
Get answer with sources
       ↓
Explore sources if needed
       ↓
Ask follow-up or start new query
       ↓
Over time — Kurious learns patterns, surfaces proactive insights
```

---

## Key Screens

---

### 1. Home / Search Interface

**The most important screen. Everything starts here.**

**Idle state:**
- Clean, minimal. Search bar centred.
- Greeting: "Good morning, Shivangi. What do you need to know today?"
- 2–3 suggested queries based on recent activity or common queries in the organisation
- Subtle indication of what data Kurious has access to: "Connected to: Legal database · Contract archive · Board minutes · 4 more sources"

**Typing state:**
- Greeting slides up and out
- Real-time suggestions appear below the search bar
- Suggestions are drawn from actual organisational patterns — not generic

**Thinking state:**
- Search bar locks, query visible
- Live step trace builds trust:
  - ✓ Understood your question
  - ✓ Searching across [X] sources
  - ✓ Scanning documents, contracts, and data
  - ⟳ Connecting insights...
- No spinner — the steps themselves show progress

**Answer state:**
- Answer text — direct, clean, no chat bubbles
- Source strip — always visible, shows modality icons and retrieval time
- "View Sources" expandable — shows exact document, page, timestamp, or row used
- Feedback bar — "Was this helpful?" thumbs up/down
- Follow-up suggestions — 2 cards relevant to the answer just given

---

### 2. Answer Card Structure

Every answer follows the same structure — consistency builds trust.

```
┌─────────────────────────────────────────────┐
│ ⚡ Quick Answer                              │
│                                             │
│ [Answer text — direct, 2–4 sentences]       │
│                                             │
│ ─────────────────────────────────────────── │
│ 📄 ×3  📊 ×1  🎥 ×1  · Retrieved in 0.8s  │
│ ▸ View Sources                              │
│ ─────────────────────────────────────────── │
│ Was this helpful?  👍  👎                   │
└─────────────────────────────────────────────┘
```

**Sources panel (expanded):**
- Grouped: PRIMARY SOURCES / SUPPORTING / ADDITIONAL
- Each source: icon + file name + "Used for: [specific contribution]" + ↗ link
- ↗ opens to exact location — highlighted passage, timestamp, row

---

### 3. Admin Dashboard

For the person at the enterprise who sets up and manages Kurious.

**Key sections:**
- **Connected Sources** — all data sources Kurious has access to, status, last indexed
- **Usage** — who is asking what, most common queries, unanswered questions
- **Insights** — patterns Kurious has identified (most searched topics, information gaps)
- **Access Management** — who has access, roles, permissions
- **Integration Settings** — add/remove data sources

---

### 4. Onboarding Flow — Admin Setup

This is the first thing an enterprise admin does after signing the contract.

```
Step 1 → Connect your first data source
         (Google Drive / SharePoint / Database / Upload files)
Step 2 → Select what Kurious can access
         (Department-level or organisation-wide)
Step 3 → Set access permissions
         (Who can ask what — role-based)
Step 4 → Test with a sample query
         (Kurious runs a demo query on their own data)
Step 5 → Invite your team
         (Email invites — they just click and start asking)
```

**Design principle for onboarding:** The admin should see Kurious working on their own data before they invite anyone. The "aha moment" must happen before rollout.

---

### 5. Onboarding Flow — End User (Business User)

When an employee gets their invite:

```
Step 1 → Click invite link → land on welcome screen
Step 2 → Sign in with company SSO (Google, Microsoft)
Step 3 → See what Kurious is connected to
         ("Kurious can search across: Legal · Finance · Board docs · 3 more")
Step 4 → Try your first query — suggested by Kurious
Step 5 → See the answer with sources → trust established
```

**Design principle:** First query must be answered correctly. The pilot query should be chosen by the admin during setup — a question they already know the answer to, so the user can immediately verify Kurious is right.

---

### 6. Mobile

Business users need answers on the go — in client meetings, on the way to a presentation.

**Mobile is not a scaled-down version. It is a different surface for the same engine.**

Mobile priority features:
- Voice input — ask by speaking
- Single answer view — no multi-column layout
- Saved answers — bookmark answers for offline reference
- Quick share — send an answer (with source) to a colleague instantly

---

## Navigation Structure

### Business User
- Home (search)
- Recent queries
- Saved answers
- Data sources (view only — what Kurious can access)
- Settings

### Admin
- Dashboard
- Connected sources
- Usage & insights
- Team access
- Settings

---

## Interaction Principles

**Speed:**
- Search results begin appearing within 0.3s of submission
- Thinking steps animate in real time — no blank waiting screens
- Transitions are fast (0.2–0.3s) — nothing lingers

**Trust:**
- Every answer shows retrieval time
- Every answer shows source count
- Sources are always one click away
- "Your data never leaves your systems" visible in footer of every page

**Clarity:**
- One primary action per screen
- No jargon in the UI — "sources" not "retrieved documents", "connected to" not "indexed"
- Error states are human: "I couldn't find anything on that — try rephrasing or check your connected sources"

---

## Design System

| Element | Spec |
|---------|------|
| Background | Near-black `#0D0D0D` or white `#FFFFFF` (light/dark modes both supported) |
| Primary accent | Cyan `#00D4FF` |
| Secondary | Teal `#0891B2` |
| Font | Inter — geometric, readable, modern |
| Border radius | 12px cards, 8px inputs, 6px buttons |
| Spacing unit | 4px base, 8/16/24/32px increments |
| Animation | 0.2–0.3s ease — fast and purposeful |

---

## What Kurious Should Never Look Like

- A chatbot with bubbles — Kurious is a knowledge engine, not a conversation
- A document management system — it is not a place to store files
- A dashboard full of charts — analytics are secondary, answers are primary
- Overwhelming on first load — one thing at a time

---

## Prototype Reference

The Kurious UI prototype already built:
- **Enterprise UI:** https://aintropy-ai.github.io/kurious_ui/
- **User-facing UI:** https://aintropy-ai.github.io/kuriousungateduserui/
- **NJ Open Data demo:** https://aintropy.ai/nj_demo

These are the starting point — not the final design.

---

## Open Questions for Engineering

- [ ] What data sources can Kurious connect to today out of the box?
- [ ] How long does indexing take for a new data source?
- [ ] Is SSO (Google/Microsoft login) supported?
- [ ] What is the maximum data size Kurious can handle per customer?
- [ ] Can permissions be set at the document level or only source level?

---

*Authored by Shivangi Mishra — March 2026*
