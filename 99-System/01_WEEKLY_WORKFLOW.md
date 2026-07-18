# Weekly Workflow

Use this workflow once per week. The target is 2–3 hours of Vikash's attention, with drafting and production work handled between approval gates.

## Weekly Time Budget

| Step | Owner | Vikash time | Output | Approval gate |
| --- | --- | ---: | --- | --- |
| Capture 3–5 raw ideas | Vikash | 20 min | New entries in the Story Bank | No |
| Select the strongest ideas | Vikash | 10 min | 1–3 ideas marked Selected | Yes: topic choice |
| Select the next unused timing window | Codex + Vikash | 5 min | Experiment ID and proposed window | Yes: exact date and time |
| Create first drafts | ChatGPT | 0–10 min | Draft posts based only on supplied facts | No |
| Review truth, voice, and value | Vikash | 30–45 min | Revision notes or approved wording | Yes: production approval |
| Build the asset package | Codex | 0–10 min | Post folder with five standard files | No publication action |
| Review assets and approve production | Vikash | 15–20 min | Approved post and optional assets | Yes: publishing approval |
| Commit and push approved files | Codex | 0–5 min | GitHub updated as source of truth | Only after explicit instruction |
| Score and prepare the draft | Supergrow + Codex | 0–10 min | Draft ID and agreed quality score | Yes if wording must change |
| Schedule | Codex + Supergrow | 5 min | Confirmed date, time, and timezone | Yes: exact schedule |
| Review recent performance and timing | Vikash + Codex | 20–30 min | Metrics, timing checkpoints, and lessons recorded | No |
| Carry unused ideas forward | Vikash | 5 min | Story Bank statuses updated | No |

Expected Vikash time: **105–145 minutes**. Keep the remaining time as a buffer for one difficult revision or a failed tool.

## The Workflow

### 1. Capture ideas

Open [the idea template](02_IDEA_CAPTURE_TEMPLATE.md). Capture three to five observations without trying to write finished posts. Each entry should take less than five minutes.

For AI Visibility Journal ideas, capture whether each claim is an observation, hypothesis, experiment, or confirmed evidence. Record the real problem before any QueryCite connection.

### 2. Select the week

Open [the Story Bank](08_STORY_BANK.md). Select ideas that are true, useful, sufficiently specific, safe to share, and different from recent posts. Carry unused ideas forward; do not discard them because they were not chosen.

Open [the Posting-Time Experiment](15_POSTING_TIME_EXPERIMENT.md). Select the next unused window for an eligible post and assign an experiment ID. Do not repeatedly use the same slot while another approved window remains unused, unless the current experiment phase requires replication.

AI Visibility Journal is a fortnightly rotation candidate, not an additional weekly slot. Select it only when it has the strongest genuine, evidence-backed story. Replace the least relevant or weakest pillar for that week without permanently removing that pillar. Do not assign Sunday as a mandatory posting day.

### 3. Draft with ChatGPT

Give ChatGPT the selected Story Bank entries and [the content-creation prompt](03_CONTENT_CREATION_PROMPT.md). ChatGPT may shape the writing but must not fill factual gaps with invented details.

For AI Visibility Journal, also use the [series rules](../01-LinkedIn/AI-Visibility-Journal/README.md): teach before promoting, put the customer problem before the product feature, and do not claim that AI replaced Google or that SEO is dead.

### 4. Review and approve

Use [the review checklist](04_CONTENT_REVIEW_CHECKLIST.md). Vikash owns truthfulness, confidentiality, personal voice, and whether an idea is worth publishing.

### 5. Produce with Codex

For each post marked `Approved for production`, give Codex [the production prompt](05_CODEX_PRODUCTION_PROMPT.md). Codex creates the standard five-file package and stops for review.

### 6. Publish and schedule

After approval, use [the publishing prompt](06_PUBLISHING_AND_SCHEDULING_PROMPT.md). GitHub is updated first. Supergrow scoring and scheduling follow. Record the approved experiment ID, window, and Asia/Kolkata timezone. Canva is optional and must not block a text post.

### 7. Review results

After publication data is available, update the post's `PERFORMANCE.md`, [the performance dashboard](10_PERFORMANCE_DASHBOARD.md), and experiment log. Collect available results at 2 hours, 24 hours, 72 hours, and 7 days. Record facts only.

For AI Visibility Journal, record QueryCite website visits or sign-ups only when reliable tracking exists. Do not attribute them to LinkedIn from timing or assumption alone.

### 8. Close the week

Update statuses in the Story Bank and [content calendar](09_CONTENT_CALENDAR.md). Move unused ideas to `Captured` or `Ready to develop`, then set one clear next action in the [Control Centre](../VIKASHOS_CONTROL_CENTRE.md).

Briefly review timing each week: confirm which checkpoints are due, which results are missing, and the next unused window. Do not change the default posting schedule from a single result. Timing recommendations and default-schedule changes are monthly-review decisions.

## Role Boundaries

### Vikash

- Supplies real experiences, observations, and evidence.
- Decides what is safe and worth sharing.
- Approves wording, production, and the exact schedule.
- Reviews performance and chooses system changes.

### ChatGPT

- Converts supplied ideas into draft options.
- Improves structure, clarity, and voice.
- Flags missing evidence or possible confidentiality issues.
- Does not publish or treat assumptions as facts.

### Codex

- Maintains repository files and the standard asset package.
- Checks Git state, scopes commits, pushes only when instructed, and records metadata.
- Uses connected tools only after approval.
- Stops on conflicts, ambiguity, or unauthorized content changes.

### Supergrow

- Stores drafts, scores approved copy, and schedules confirmed posts.
- Does not replace human approval.

### Optional: Canva

- Creates carousel or static-image assets after approval.
- A Canva failure never blocks an otherwise approved text post.

## Weekly Limit Rule

If the workflow exceeds three hours for two consecutive weeks, do not add more tools. Record the bottleneck in the Control Centre and simplify one step during the monthly review.
