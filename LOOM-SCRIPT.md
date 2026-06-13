# Loom script — Adam Collins / Thermo Fisher (target 6 min)

> Interactive demo: **DEPLOY_URL** (update after GitHub Pages deploy)
> Portfolio (generic agent demo): https://ainoafv.github.io/agent-engineering-demo/

Record **screen + voice**. One window: the lab demo in the browser. Calm pace, no rush. English.

Send to Adam 2–3 days before **Tuesday 23 Jun 2026, 11:00 CET** (e.g. Sunday 15 or Monday 16 Jun).

---

## 0:00 — Hook (20s)

"Hi Adam, Ainoa here — looking forward to our conversation on Tuesday the 23rd.

After we rescheduled, I put together a short interactive demo for context: a fictional QC lab scenario that shows how I'd approach AI in a regulated lab environment. Not Thermo software — just the architecture I'd bring to digital science workflows. About six minutes — feel free to click through the demo yourself afterward."

## 0:20 — The problem (40s)

"In labs — and in clinical AI, which is what I do day-to-day — the risk isn't the model being wrong once. It's the model triggering a side effect you can't undo: releasing a batch, writing to an ELN, changing LIMS status.

So the pattern I use is simple: **the model proposes, the code decides**. The LLM never touches LIMS, ELN, or batch release directly."

## 1:00 — Show the demo layout (30s)

Scroll the page briefly. Point at the context bar:

"QC lab, batch B-2047, on hold in LIMS, one sample off-spec. The scientist types a request — or uses a preset chip."

## 1:30 — Scenario 1: read-only AUTO (60s)

Click **Summarize batch** → **Run lab agent**.

Walk through the four steps:

1. Request received — analyst, batch ID logged  
2. LLM proposes `generate_summary` — label it **untrusted model output**  
3. Gate: `POLICY → AUTO`, confidence above floor  
4. Outcome: executed — read-only summary, no LIMS change  

"Summaries and LIMS queries are low risk — auto if confident. Still logged."

## 2:30 — Scenario 2: NEVER — batch release (60s)

Click **Release batch** → Run.

"This is the important one. The model correctly understands 'release for shipment' and proposes `release_batch` with high confidence — 0.92.

But the gate says **NEVER**. Batch release is human-only, full stop. No side effect. Queued/blocked. That's fail-closed by design — even a confident model doesn't get to release a batch."

## 3:30 — Scenario 3: ASK — anomaly flag (45s)

Click **Flag anomaly** → Run.

"Flagging an off-spec sample is a write to the quality record — so it's **ASK**: queue for QA before anything hits the ELN. Human in the loop, not because the model is dumb, but because the policy says so."

## 4:15 — Audit trail (60s)

Point at the audit log on the right.

"Every step — received, decided, gated, executed or queued — goes into an append-only log. Each row hashes the previous one.

Click **Tamper a row** — simulates someone editing history after the fact. Then **Verify chain** — broken. That's the compliance story: you can prove what the system did and detect tampering."

## 5:15 — Bridge to Thermo + close (45s)

"I built this as a neutral QC scenario, but the architecture maps directly to what you described — lab digitalization, LIMS-adjacent workflows, scientists getting AI assistance without losing control or traceability.

Same patterns I run in production regulated AI — closed action set, permission table in code not prompts, hash-chained audit.

Happy to go deeper on Tuesday — and I'd love to understand the format you use for the case presentation in the next stage. Thanks, Adam."

---

## Recording tips

- **Don't** mention SERGAS by name or show clinical systems — say "regulated clinical AI" once.  
- **Don't** claim SampleManager / Connect / Momentum experience — say "LIMS-adjacent" and "fictional scenario".  
- Run 3 presets in order (Summarize → Release → Flag) — that's the narrative arc.  
- Optional 4th: ELN entry (ASK) if you have time.  
- End frame: audit log with intact chain after Verify.  
- Upload Loom → paste link in email to Adam (see `EMAIL-ADAM.txt`).

## Email timing

| Send | Why |
|------|-----|
| **Sun 15 or Mon 16 Jun** | Adam has time to watch before Tue 23 |
| Not Thu 19+ | Too close to the call; feels rushed |
