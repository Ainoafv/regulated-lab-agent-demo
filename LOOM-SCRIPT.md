# Loom script — Adam Collins / Thermo Fisher (target 6 min)

> Interactive demo: https://ainoafv.github.io/regulated-lab-agent-demo/
> Portfolio (generic agent demo): https://ainoafv.github.io/agent-engineering-demo/

Record **screen + voice**. One window: the lab demo in the browser. Calm pace, no rush. English.

Send to Adam 2-3 days before **Tuesday 23 Jun 2026, 11:00 CET** (e.g. Sunday 15 or Monday 16 Jun).

**Framing:** this is a *technical-sales* walkthrough, not an engineering deep-dive. You're showing how you'd run a customer conversation about governed AI in a lab — speed for scientists, control for QA, safe integration for IT. Keep the **Business view** on for most of it; flip to **Technical view** once, briefly, for Adam (PhD).

---

## 0:00 — Hook (20s)

"Hi Adam, Ainoa here — looking forward to our conversation on Tuesday the 23rd.

After we rescheduled, I put together a short interactive demo for context: a fictional QC lab scenario showing how I'd frame a customer conversation about AI in a regulated lab. Not Thermo software — just the way I'd walk a lab through it. About six minutes — feel free to click through it yourself afterward."

## 0:20 — The problem, in customer language (40s)

"When a lab asks 'can AI help us?', the real question underneath is 'can we trust it not to do something we can't undo' — release a batch, change a LIMS status, write to the ELN.

So the way I'd answer that in a sales conversation is: **the model proposes, the code decides.** The AI can suggest an action, but a permission policy decides what runs, what waits for a human, and what is never automated."

## 1:00 — The guided scenario (the spine of the demo) (30s)

Point at the top bar.

"I built a 90-second guided story for exactly this conversation. Same batch, B-2047, on hold in LIMS, one sample off-spec. I'll hit **Play customer scenario** and narrate."

Click **Play customer scenario**. Let the narration band drive. Talk over each scene:

## 1:30 — Scene 1: Speed for the scientist (45s)

(Summarize → AUTO)

"Scene one. A scientist asks for a QC summary. It's read-only, low risk — so the AI just answers, instantly. No queue, no friction. That's the **scientist** win: speed. Note the stakeholder card on the right lights up — Scientist owns this one."

## 2:15 — Scene 2: Control for QA (60s)

(Release → NEVER)

"Scene two — the one that wins the room. The hard question every QA director asks: 'Can the AI release my batch?' The model even understands the request and is 92% confident.

And the policy says **NEVER**. Batch release is human-only, full stop — no side effect, fail-closed by design. That's the **QA** win: control. A confident model still doesn't get to release a batch."

## 3:15 — Scene 3: Human in the loop + audit (60s)

(Flag → ASK, then audit)

"Scene three. An off-spec sample needs flagging — that writes to the quality record, so it's not blocked, it's **queued for QA**. Supervised, not stopped.

Now the right column — the audit log. Every step is recorded, and each row is hashed to the one before it. I'll click **Tamper a row**, then **Verify chain** — broken. That's the compliance story you can show an auditor: prove what the system did, detect any edit after the fact."

## 4:15 — Three stakeholders, one workflow (45s)

Scroll to the stakeholder panel.

"This is really the whole sales argument on one screen: the same workflow has to satisfy three people. **Scientist** wants speed. **QA** wants control. **IT** wants integration that doesn't break LIMS or open a hole — a closed action set, policy in code, fail-closed. The demo serves all three without picking a loser."

## 5:00 — One look under the hood (30s)

Flip the toggle to **Technical view**, re-run Release (or scroll the last result).

"For completeness — if I flip to Technical view, you see the actual proposed action as JSON and the policy rule that gated it. That depth is there when the customer's IT or quality team wants it, but I'd keep the conversation in business terms by default."

Flip back to **Business view**.

## 5:30 — Bridge to Thermo + close (45s)

"I built this as a neutral QC scenario, but it maps directly to what Cristina and I discussed — digital science, LIMS-adjacent workflows, scientists getting AI assistance without losing control or traceability.

To be clear on where I'm coming from: I run these patterns in production regulated AI, and I'm coming up to speed on the lab-informatics side. This is how I'd support those customer conversations.

Happy to go deeper on Tuesday — and I'd love to understand the format you use for the case presentation in the next stage. Thanks, Adam."

---

## Recording tips

- **Don't** mention SERGAS by name or show clinical systems — say "regulated clinical AI" once.
- **Don't** claim SampleManager / Connect / Momentum experience — say "LIMS-adjacent", "coming up to speed", "fictional scenario".
- Let **Play customer scenario** carry the narrative — you talk over it, you don't click step by step.
- Flip to **Technical view** exactly once, then back. Don't live in the JSON.
- End frame: stakeholder panel or audit log with intact chain after Verify.
- Upload Loom → paste link in email to Adam (see `EMAIL-ADAM.txt`).

## Email timing

| Send | Why |
|------|-----|
| **Sun 15 or Mon 16 Jun** | Adam has time to watch before Tue 23 |
| Not Thu 19+ | Too close to the call; feels rushed |
