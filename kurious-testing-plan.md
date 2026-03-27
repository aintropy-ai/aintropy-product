# Kurious — Testing Plan

> Owned by Shivangi Mishra · Draft v1 · March 2026

---

## Why Testing Matters More for Kurious Than Most Products

Kurious makes a very specific promise: **the exact answer, from your data, with the source.**

That promise is either kept or it is not. There is no "mostly right" in enterprise. A wrong answer cited with confidence is worse than no answer at all — it destroys trust immediately and permanently.

Testing is therefore not a phase at the end. It is built into every step of building and selling Kurious.

---

## Testing Layers

```
Layer 1 — Does it retrieve correctly?          (Technical)
Layer 2 — Does it answer correctly?            (Quality)
Layer 3 — Does a business user trust it?       (UX)
Layer 4 — Does it work on real customer data?  (Pilot)
Layer 5 — Does it keep working over time?      (Reliability)
```

---

## Layer 1 — Retrieval Testing

**What we are testing:** Does Kurious find the right document, chunk, timestamp, or row when given a query?

### Metrics
| Metric | Target | Why |
|--------|--------|-----|
| Recall@10 | >90% | The right source appears in the top 10 results |
| Precision@3 | >80% | Top 3 results are all relevant |
| Retrieval time | <1 second | Speed is a core brand promise |
| Null result rate | <5% | How often Kurious returns nothing when something exists |

### Test Types
- **Known answer tests** — queries where the correct source is already known. Does Kurious find it?
- **Cross-source tests** — queries that require connecting information from two or more sources. Does Kurious bridge them?
- **Format tests** — test retrieval across each modality: PDF, spreadsheet, database, video, image
- **Edge case tests** — ambiguous queries, partial information, questions with no answer in the data

### Dataset for Testing
- NJ Open Data — 85M records, 23 agencies, 8 formats. Already indexed. Use this as the primary benchmark.
- Build a curated test set of 100 questions with known correct answers across different query types.

---

## Layer 2 — Answer Quality Testing

**What we are testing:** Is the answer Kurious returns correct, complete, and appropriately scoped?

### The Three Failure Modes

| Failure | Description | Severity |
|---------|-------------|----------|
| **Hallucination** | Kurious returns an answer not supported by any source | Critical — kills trust |
| **Incomplete answer** | Kurious finds part of the answer but misses key information | High |
| **Wrong attribution** | Answer is correct but attributed to the wrong source | High |

### Test Protocol
1. Write 50 benchmark questions per vertical (legal, finance, consulting, government)
2. For each question: record expected answer + correct source
3. Run Kurious on all 200 questions
4. Score each answer: Correct / Partially correct / Wrong / Hallucinated
5. Track hallucination rate — must be <1%

### Red Team Testing
Before any pilot: dedicate one week to deliberately trying to break Kurious.
- Ask trick questions designed to provoke hallucination
- Ask questions where the answer is not in the data
- Ask ambiguous questions that could have multiple valid answers
- Ask questions that require synthesising conflicting information from different sources

Document every failure. Fix before pilot.

---

## Layer 3 — UX and Trust Testing

**What we are testing:** Does a non-technical business user understand, trust, and successfully use Kurious?

### The Key Questions
- Can a business user find an answer without any training?
- Do they trust the answer they get?
- Do they understand where the answer came from?
- Would they use it again tomorrow?

### Test Method — Usability Sessions
Run 5 usability sessions before any pilot launch.

**Participant profile:** Business users — strategy, legal, finance, operations. No engineers.

**Session structure:**
1. Give them a task: "Find the answer to [specific question] using Kurious"
2. Watch without helping — note where they get confused or hesitate
3. After task: "Do you trust this answer? Why or why not?"
4. After task: "Would you use this every day?"
5. Note exactly what they say when they see the source attribution — do they check it?

### Success Criteria
- 4 out of 5 users complete the task without assistance
- 4 out of 5 users say they trust the answer
- 4 out of 5 users say they would use it regularly
- Zero users feel their data is at risk

---

## Layer 4 — Pilot Testing (First Customer)

**What we are testing:** Does Kurious work on real customer data, solve a real business problem, and create measurable value?

### Pilot Structure

**Duration:** 2 weeks

**Scope:** One department. One use case. Not the whole organisation.

**Participants:** 5–10 business users within that department.

**The Pilot Query Set:**
Before the pilot starts, the customer identifies:
- 10 questions they currently cannot answer quickly
- 5 questions they already know the answer to (for verification)
- 3 questions that require connecting information from two different sources

Kurious must answer the verification questions correctly before the pilot begins. Non-negotiable.

### What to Measure

| Metric | How to measure |
|--------|---------------|
| Time to answer (before Kurious) | Ask users: how long does it currently take to find this type of information? |
| Time to answer (with Kurious) | Time the actual queries during pilot |
| Answer accuracy | User verifies each answer against their own knowledge |
| User adoption | How many of the 5–10 users actively use Kurious by end of week 2 |
| Net Promoter Score | Single question at end: "Would you recommend Kurious to a colleague?" |
| Unanswered questions | How many queries returned no result — and were those correct null results? |

### Pilot Success Criteria
- Time to answer reduced by >70%
- Answer accuracy >95% on verified queries
- Zero hallucinations
- >4/5 users still actively using by end of week 2
- Customer agrees to continue beyond pilot

### What Happens If the Pilot Fails
- Document every failure in detail
- Identify whether failure is retrieval (Layer 1), answer quality (Layer 2), or UX (Layer 3)
- Fix before starting next pilot
- Never paper over a failure — one bad enterprise reference kills the next 10 conversations

---

## Layer 5 — Reliability Testing

**What we are testing:** Does Kurious keep working accurately as data grows, changes, and as more users query simultaneously?

### Tests
- **Scale test** — does retrieval quality hold as the data source grows from 10K to 10M documents?
- **Concurrency test** — does response time hold when 50 users query simultaneously?
- **Data freshness test** — when a document is updated, does Kurious return the new version?
- **Source removed test** — when a data source is disconnected, does Kurious handle gracefully?
- **Long-running test** — does accuracy hold after 30 days of continuous use?

---

## Testing Cadence

| Phase | Testing Focus | Timing |
|-------|--------------|--------|
| Pre-pilot | Layers 1, 2, 3 | Before any customer conversation |
| Pilot setup | Layer 4 setup — verification queries | Week before pilot starts |
| During pilot | Layer 4 — daily monitoring | Every day of the 2-week pilot |
| Post-pilot | Layer 5 — reliability | Ongoing after pilot ends |
| Pre-scale | All layers | Before expanding to full organisation |

---

## What a "Pass" Looks Like

Kurious is ready for its first enterprise pilot when:

- [ ] Hallucination rate <1% on benchmark test set
- [ ] Recall@10 >90% on benchmark test set
- [ ] Retrieval time <1 second on benchmark data
- [ ] 4/5 usability session participants complete task without assistance
- [ ] 4/5 usability session participants trust the answer
- [ ] Red team testing complete — all critical failures fixed
- [ ] Verification queries for first customer answered correctly

---

## Open Questions for Engineering

- [ ] Do we have an eval framework already? (aintropy-ai/eval-framework repo exists — what is its current state?)
- [ ] What is our current hallucination rate on NJ Open Data benchmark queries?
- [ ] Can we run concurrent user load testing on the current infrastructure?
- [ ] How are data source updates handled — real-time re-indexing or scheduled?

---

*Authored by Shivangi Mishra — March 2026*
