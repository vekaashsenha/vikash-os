# Publishing and Scheduling Prompt

Use this only after the post is marked `Approved for publication` and the date, time, and timezone are explicit.

## Reusable Prompt

```text
Work only inside the current valid VikashOS Git worktree.

The following post package is approved for publication:
[POST FOLDER]

Schedule:
- Date: [DAY, DD MONTH YYYY]
- Time: [HH:MM AM/PM]
- Timezone: [TIMEZONE]

Supergrow score threshold: [FOR EXAMPLE 9/10]
Canva: Optional

Production workflow:
1. Validate the worktree, package path, approved wording, and clean scope.
2. Commit only the approved post package with this message: [CONTENT COMMIT MESSAGE].
3. Push the commit to origin/main. Stop if the push is rejected or conflicts exist.
4. Create a Supergrow draft using the approved post wording.
5. Score the post. If it is below the agreed threshold, propose or apply revisions only within the authority given. Never silently change approved wording.
6. Schedule the confirmed date, time, and timezone.
7. Optionally create Canva assets. A Canva failure must not block an approved text post.
8. Update PERFORMANCE.md with the content commit, score, draft ID, schedule, Canva status, and any relevant links.
9. Commit only PERFORMANCE.md with this message: [METADATA COMMIT MESSAGE].
10. Push again.
11. Confirm that HEAD and origin/main match and the worktree is clean.

FAILURE POLICY
- Canva unavailable: mark Pending and continue.
- Supergrow unavailable: report the failure clearly; do not claim a draft or schedule exists.
- Git conflict, rejected push, or unexpected changes: stop before external publishing actions.
- Missing or ambiguous date, time, day, or timezone: stop and request clarification.
- Score below threshold: do not schedule until the approved revision path is clear.
- Never make silent assumptions about dates, times, timezones, branches, or approved wording.

Return:
- Commit hashes.
- GitHub status.
- Supergrow score and draft ID.
- Scheduled confirmation.
- Canva status.
```

## Human Approval Gates

1. Approved wording before the content commit.
2. Explicit score threshold.
3. Explicit schedule including timezone.
4. Approval for any wording change made after scoring.
