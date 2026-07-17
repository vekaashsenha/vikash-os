# Codex Production Prompt

Use this only after a post is marked `Approved for production`.

## Reusable Prompt

```text
Work only inside the current valid VikashOS Git worktree.

Create the standard asset package for this approved LinkedIn post:

[TARGET SERIES FOLDER]/[POST ID]/
  POST.md
  CAROUSEL.md
  IMAGE_BRIEF.md
  VIDEO_SCRIPT.md
  PERFORMANCE.md

Approved post:
[PASTE EXACT APPROVED WORDING]

Requirements:
- Preserve the approved post wording exactly unless I explicitly request a change.
- Do not invent facts, claims, numbers, people, quotations, events, emotions, results, or achievements.
- Keep all supporting assets aligned with the approved post.
- Use a concise seven-slide carousel unless another length is explicitly approved.
- Create a minimal static-image brief; Canva remains optional.
- Create a natural 45–60 second first-person video script.
- Create a performance-review template with no fabricated results.
- Protect confidentiality.
- Check existing folders first and do not duplicate a post, series, or template.

Do not:
- Modify published or scheduled posts.
- Commit or push.
- Use Canva.
- Create a Supergrow draft.
- Publish or schedule anything.

After creation, show:
1. Full POST.md.
2. Full supporting files.
3. Git status.
4. A no-index diff summary if files are untracked.
5. Assumptions.

Stop for human approval.
```

## Expected Package

| File | Purpose |
| --- | --- |
| `POST.md` | Exact approved LinkedIn copy |
| `CAROUSEL.md` | Slide copy and structure |
| `IMAGE_BRIEF.md` | Optional static visual direction |
| `VIDEO_SCRIPT.md` | Short spoken version |
| `PERFORMANCE.md` | Readiness, production metadata, and later results |
