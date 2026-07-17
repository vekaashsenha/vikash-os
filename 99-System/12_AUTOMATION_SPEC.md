# Automation Specification

This document describes an automation-ready architecture. It does **not** claim that every connection or trigger already exists.

## System Boundary

### Inputs

- Weekly notes and raw ideas
- AGMP lessons approved for personal use
- Work observations safe to share
- Product and build updates
- Story Bank entries

### Processing

- Draft creation
- Human review
- Approval
- Asset creation
- Repository updates
- Scoring and scheduling

### Outputs

- GitHub repository records
- Supergrow drafts and schedules
- LinkedIn publishing schedule
- Performance records

## Automation Modes

- **Fully automated:** May run without a content decision, but must remain observable and reversible.
- **Semi-automated:** Tool performs work after a human-approved input or trigger.
- **Manual:** Human judgment is the action.
- **Optional:** May be skipped without breaking the core workflow.

## Stage Map

| Stage | Trigger | Input | Action | Tool | Human approval needed | Success condition | Failure condition | Recovery action | Mode |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Capture | Weekly session or real observation | Raw note | Record a structured idea | Markdown template | Vikash supplies facts | Story Bank entry exists | Idea remains in chat or memory only | Use the five-minute template | Manual |
| Select | Weekly planning | Active Story Bank | Choose 1–3 useful, safe ideas | Story Bank + Control Centre | Yes | Ideas marked `Selected` | Topic lacks evidence or repeats recent content | Return to `Captured` or `Needs evidence` | Manual |
| Draft | Selected idea | Facts, evidence, series, restrictions | Create draft options | ChatGPT prompt | Approval after drafting | Draft uses only supplied facts | Invented detail, weak voice, unclear lesson | Revise from source notes; do not patch facts | Semi-automated |
| Review | Draft ready | Draft + evidence | Check truth, confidentiality, voice, value | Review checklist | Yes | Status becomes `Approved for production` | Unsupported claim or confidentiality risk | Mark `Needs revision` or `Archived` | Manual |
| Asset package | Production approval | Exact approved post | Create five standard files | Codex | Yes before any external action | Package exists and diff is scoped | Duplicate folder, changed approved wording, wrong worktree | Stop, compare, and correct before approval | Semi-automated |
| Content commit | Publication approval | Approved package | Commit and push scoped files | Git + GitHub | Yes | `origin/main` contains content commit | Conflict, rejected push, unexpected staged file | Stop; resolve explicitly; do not publish | Semi-automated |
| Supergrow draft | Content commit pushed | Approved post text | Create and score draft | Supergrow | Yes for wording changes | Draft ID exists and score meets threshold | Service failure or score below threshold | Report; revise only with authority; retry later | Semi-automated |
| Canva assets | Approved brief | Carousel and image brief | Generate optional visual assets | Canva | Yes before selecting final asset | Reviewable Canva links exist | Service unavailable or design off-brief | Mark Pending; continue without blocking text post | Optional |
| Schedule | Exact schedule approved | Draft ID, date, time, timezone | Schedule the post | Supergrow | Yes | Schedule confirmation matches all fields | Any ambiguity or scheduling error | Stop or unschedule; confirm exact details | Semi-automated |
| Metadata commit | Production steps complete | Commit, score, draft ID, schedule, Canva status | Update `PERFORMANCE.md`, commit, push | Codex + GitHub | No new content approval if metadata is factual | Metadata commit is on `origin/main` | Missing or contradictory metadata | Verify external state, then correct | Semi-automated |
| Publication confirmation | Scheduled time has passed | Platform state | Confirm published status and URL | Supergrow / LinkedIn | No, read-only | Public URL recorded | Scheduled date passed but status unknown | Keep `Pending`; investigate without guessing | Semi-automated |
| Performance capture | Metrics available | LinkedIn metrics and comments | Record post and dashboard results | Supergrow / manual input / Codex | Vikash validates interpretation | Factual metrics and lessons recorded | Metrics unavailable or definitions changed | Use `Pending`; note definition changes | Semi-automated |
| Monthly review | Month end | Calendar, dashboard, Story Bank | Approve one evidence-based improvement | Monthly review | Yes | Decision record completed | Weekly redesign or tool proliferation | Defer changes until repeated bottleneck is documented | Manual |

## Future Semi-Automated Timing Process

This process is designed but should be enabled only when each step can read and write the documented repository fields safely.

| Step | Automated action | Human gate | Repository result |
| --- | --- | --- | --- |
| 1 | Read the next unused test window from the posting-time experiment. | No | Candidate experiment ID and window identified. |
| 2 | Recommend a posting date and time in Asia/Kolkata while considering the series and current calendar. | Yes | Proposal only; no schedule created. |
| 3 | Require Vikash's explicit approval of date, time, timezone, and experiment ID. | Required | Approved scheduling instruction. |
| 4 | Schedule the approved post through Supergrow. | Approval already recorded | Confirmed external schedule or clear failure. |
| 5 | Record the approved experiment slot, draft ID, and schedule in the calendar and `PERFORMANCE.md`. | No | GitHub metadata matches external state. |
| 6 | Collect or request results at 2 hours, 24 hours, 72 hours, and 7 days. | Vikash may supply unavailable data | Checkpoints recorded as values or `Pending`. |
| 7 | Update the content dashboard and timing experiment using medians and confirmed sample sizes. | No | Window summaries updated. |
| 8 | Recommend changes only after sufficient evidence. | Monthly approval required | Recommendation, sample size, and confidence recorded. |

The process remains **semi-automated** because scheduling and any default-time change require human approval.

## Source-of-Truth Flow

```text
Raw notes
  → Story Bank
  → Approved post files
  → GitHub content commit
  → Supergrow draft and schedule
  → PERFORMANCE.md metadata commit
  → Confirmed publication and metrics
  → Dashboard and monthly review
```

GitHub is the durable record. External tools may execute publishing tasks, but their IDs, statuses, and links must be written back to the repository.

## Approval Invariants

- Draft automation never equals publication approval.
- A score never overrides Vikash's wording approval.
- External writes require an explicit approved scope.
- Failed optional automation does not become a false success record.
