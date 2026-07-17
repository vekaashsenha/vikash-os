# Failure Recovery Guide

Use this guide when a production workflow stops. Do not keep retrying without understanding the failure.

## Wrong Worktree

**Signal:** The repository path is not the expected current VikashOS worktree.

1. Stop before editing or committing.
2. Run a read-only worktree check.
3. Return to the correct Codex task or worktree.
4. Confirm the intended path with Vikash if more than one valid worktree exists.

## Detached HEAD

**Signal:** Git says `Not currently on any branch`.

- Detached HEAD is not automatically an error in a Codex worktree.
- Confirm the intended base and `origin/main` before committing.
- Push only with the explicitly approved target.
- Never create or switch branches merely to hide the condition.

## Dirty Worktree

**Signal:** Git lists modified or untracked files before the task begins.

1. Identify which changes belong to the current task.
2. Preserve unrelated user changes.
3. Stage only explicitly approved paths.
4. Stop if changes overlap the requested files and ownership is unclear.

## Merge Conflict

1. Stop production and external publishing actions.
2. List conflicted files.
3. Explain which versions conflict.
4. Ask Vikash which content should win when approved wording is involved.
5. Resume only after the conflict is resolved and reviewed.

## Push Rejected

1. Do not force-push.
2. Read the rejection and compare local and remote history.
3. Fetch only when appropriate and authorized.
4. Stop if integrating remote changes could affect approved content.

## Missing Folder

1. Confirm the series and post ID.
2. Search for naming aliases before creating anything.
3. Create the folder only if it is genuinely new.
4. Record naming inconsistencies in the audit rather than improvising a new convention.

## Duplicate Post

1. Search by post ID, title, opening line, and core lesson.
2. Do not create a second folder.
3. Link the Story Bank entry to the existing source.
4. Decide whether the new idea is a distinct angle or should be archived.

## Canva Unavailable

1. Stop repeated retries.
2. Mark Canva `Pending – generation failed` in `PERFORMANCE.md`.
3. Continue with the approved text post if all other approvals exist.
4. Retry Canva in a later, separate task.

## Supergrow Unavailable

1. Do not claim a draft, score, or schedule exists.
2. Preserve the GitHub content commit.
3. Record the failure clearly.
4. Retry later; do not manually invent IDs or status.

## Low Supergrow Score

1. Read the criterion-level feedback.
2. Keep the approved wording unchanged unless revision authority is explicit.
3. Present necessary revisions to Vikash if the threshold is not met.
4. Rescore only after an approved change.

## Wrong Scheduled Date or Time

1. Unschedule if the tool supports a safe reversal.
2. Confirm day, date, year, time, and timezone together.
3. Reschedule only with explicit confirmation.
4. Update `PERFORMANCE.md` after external state is verified.

## Wrong Timezone

- Treat `IST` as `Asia/Calcutta` only when the workspace confirms it.
- Do not convert a local-time scheduling API to UTC unless its documentation requires it.
- Always repeat the final local schedule in the confirmation.

## Incomplete Metadata

1. Check the content commit, score, draft ID, external link, schedule, and optional Canva status.
2. Use `Pending` for unavailable facts.
3. Commit metadata separately from approved content.

## Approved Content Changed Accidentally

1. Stop before commit, Supergrow, or scheduling.
2. Compare the file against the approved version or prior commit.
3. Restore only the affected approved wording; preserve unrelated work.
4. Show the corrected diff and obtain approval again.

## Recovery Rule

Prefer a clear pending state over an unverified success. Never use destructive Git commands or silent assumptions to make the workflow look complete.
