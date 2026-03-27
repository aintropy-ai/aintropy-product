# Kurious — Product Strategy

> Owned by Shivangi Mishra, Lead PM · Draft v1 · March 2026
> Status: In discussion — pending Kunal and Nirmit review

---

## Product Vision

**Kurious is the first AI that can read everything an organisation knows — across every source, every format, every silo — and give anyone the exact answer they need, instantly.**

Not a summary. Not a guess. The actual answer, with the source, in seconds.

Over time Kurious learns the patterns — it understands how the organisation thinks, what it needs, where the gaps are. It becomes less of a search tool and more of an organisational brain.

---

## The Problem

People inside large organisations lose days, weeks, sometimes months looking for information they know exists somewhere. The data is there. The problem is getting to it.

**What people do today instead of having Kurious:**
- Ask IT and wait days for a report
- Search manually across disconnected systems for hours
- Make decisions with incomplete information
- Hire consultants to dig through data for them
- Give up and move on with the wrong answer

The cost is not just time. It is wrong decisions, missed opportunities, delayed action, and billions of dollars of data that nobody can actually use.

**This is the default state of every large organisation on the planet.**

---

## Why Kurious Solves It Uniquely

| The problem | How Kurious solves it |
|-------------|----------------------|
| Data is in 10 different systems | Kurious integrates with all of them simultaneously |
| Data is in different formats | Kurious reads documents, spreadsheets, databases, video, images |
| Answers require connecting data across silos | Kurious retrieves across all sources in a single query |
| Business users cannot use technical tools | Kurious works in plain language — no training required |
| Enterprises cannot send data to third parties | Kurious integrates where the data lives — nothing ever moves |
| AI tools hallucinate | Every Kurious answer comes with the exact source — verifiable in one click |

---

## The Two Users

### Primary — The Business User
A busy person inside a large organisation. Strategy, operations, finance, legal, compliance, consulting. Not technical. Does not have time. Needs an answer, not a tool.

**Their day today:** Ask someone, wait. Search manually, get lost. Use incomplete data, make a risky decision.

**Their day with Kurious:** Ask in plain language. Get the answer in seconds. See exactly where it came from. Move on.

### Secondary — The Engineer / Developer
Builds on top of Kurious. Uses the API, selects retrieval algorithms (Vibe-Discovery), integrates into existing workflows. Wants control, transparency, and performance.

---

## Target Customers — In Priority Order

### Why enterprise, not consumer
Kurious is at its best when the data is massive, fragmented, and multimodal. That is an enterprise problem. Only enterprises have millions of records across formats and systems. Consumer users do not have this problem at this scale — enterprise is the primary customer, always.

| Priority | Vertical | Why | Sales speed |
|----------|----------|-----|-------------|
| 🥇 **Consulting firms** | Strategy, management, research | Their business *is* finding and synthesising information. Immediate value. Fast decisions. | Weeks |
| 🥈 **Legal** | Mid-size law firms | Lawyers bill by the hour. Finding precedents, contracts, case history costs real money. Data privacy is critical. | 4–6 weeks |
| 🥉 **Finance** | Asset managers, risk, compliance | Drowning in data. Wrong decisions are extremely costly. | 6–8 weeks |
| 4 | **Government** | Proven by NJ demo. Highest pain but longest procurement cycle. | Months |
| 5 | **Enterprise at scale** | PayPal-scale companies. Biggest budget. Hardest to close fast. | Months |

---

## Phase 1 — The Product Today

**What Kurious does:**
- Integrates with existing enterprise data sources
- Reads across every format: documents, spreadsheets, databases, video, images
- Returns answers in plain language with exact source citations
- Never moves, copies, or trains on customer data
- Works for non-technical business users

**What needs to be built for Phase 1 enterprise launch:**
- [ ] Clean onboarding flow for admin (connect data source → test → invite team)
- [ ] Business user interface (search → thinking steps → answer → sources)
- [ ] SSO login (Google Workspace, Microsoft)
- [ ] Access permissions (role-based, department-level)
- [ ] Usage dashboard for admin

---

## Phase 2 — The Intelligence Layer

This is where Kurious becomes something no competitor can copy quickly.

Once Kurious is embedded in an organisation, it starts to learn:

- Which questions get asked most frequently
- Where information gaps exist — questions asked that had no answer
- What decisions are being delayed because data is hard to find
- Which departments are asking similar questions without knowing it
- What the workflow looks like before and after a key decision

**This transforms Kurious from a retrieval tool into an organisational intelligence layer.**

It stops waiting to be asked and starts proactively surfacing information:

> "Three people in your strategy team asked about the Johnson contract this week. Here is a summary with all relevant clauses — you may want to share this."

> "Your compliance team has asked 14 questions about GDPR requirements this month. Here is a gap in your documentation that may need attention."

This is the long-term moat. It is not just search. It is memory, pattern recognition, and proactive intelligence. No competitor is building this.

---

## The Product Roadmap

### Now — Weeks 1–4
- Lock the product vision with Kunal and Nirmit
- Define exactly what data sources Kurious connects to today
- Build the admin onboarding flow
- Build the business user search interface
- Identify first pilot customer

### Short term — Weeks 5–12
- Run first pilot with consulting or legal firm
- Gather real usage data — what do people ask? Where does Kurious fail?
- Ship improvements based on pilot feedback
- Write first case study

### Medium term — Months 3–6
- Expand to second vertical based on pilot learnings
- Build the intelligence layer — pattern recognition, proactive surfacing
- Self-serve pilot request on aintropy.ai
- 3 paying enterprise customers

### Long term — Months 6–12
- Intelligence layer in production
- 10+ enterprise customers across 3 verticals
- Published benchmarks establishing Kurious as the accuracy standard
- Kurious becomes the product AIntropy sells externally

---

## How We Get the First Customer — In Weeks

**Step 1:** Identify one consulting firm or law firm. One real organisation. One person Kunal or Nirmit already knows or can reach through one connection.

**Step 2:** Show them the NJ demo. Do not pitch. Show. Ask: "Is this the problem you have?" They will say yes.

**Step 3:** Propose a 2-week pilot. One department. One use case. We measure time-to-answer before and after. Zero risk to them — their data never leaves.

**Step 4:** Pilot runs. We monitor daily. We fix anything that breaks.

**Step 5:** Pilot succeeds. We write the case study together. They become a reference.

**Step 6:** The case study opens the next door. Repeat.

---

## What Kurious Is Not

- Not a chatbot
- Not a document summariser
- Not a generic AI assistant
- Not a tool that requires your data to leave your building
- Not only for technical users
- Not a competitor to ChatGPT or Google — it is built for the data they have never seen

---

## The Metric That Matters

**Time from question to verified answer — before Kurious vs after Kurious.**

That is the number that sells. That is the number in every case study, every LinkedIn post, every sales conversation, every board deck.

If a lawyer used to spend 4 hours finding a precedent and now spends 8 seconds — that is the story.

---

## Open Questions — To Discuss with Kunal and Nirmit

- [ ] What data sources can Kurious connect to today out of the box?
- [ ] How long does indexing take for a new enterprise data source?
- [ ] Is SSO (Google/Microsoft login) supported today?
- [ ] What is the pricing model — per seat, per query, per data source, or value-based?
- [ ] What is the one vertical Kunal and Nirmit feel most confident about for the first pilot?
- [ ] Is there anyone in their network at a consulting firm or law firm we can approach this week?
- [ ] What does the integration look like technically — how much engineering is required per customer?

---

## Related Documents

| Document | What it covers |
|----------|---------------|
| [kurious-brand.md](./kurious-brand.md) | Brand voice, positioning, visual direction |
| [kurious-ui-ux-plan.md](./kurious-ui-ux-plan.md) | Interface design, user flows, key screens |
| [kurious-testing-plan.md](./kurious-testing-plan.md) | How we validate before and during pilots |
| [kurious-product-marketing.md](./kurious-product-marketing.md) | Messaging, objection handling, demo strategy |
| [kurious-marketing-strategy.md](./kurious-marketing-strategy.md) | Category creation, flywheel, 90-day plan |
| [marketing-flywheel.md](./marketing-flywheel.md) | Original marketing flywheel document |

---

*Authored by Shivangi Mishra — March 2026*
*This is a living document — update as decisions are made*
