---
name: living-story
description: Create or refresh a markdown-first living story for active projects. Use when asked to maintain an evidence-based project story, compile project state from repos, carry open threads forward, verify recent wins, or run the Living Story loop.
---

# Living Story

Maintain a markdown-first project story rooted in verifiable evidence.

## Workflow

1. Resolve the story directory, defaulting to `~/story`.
2. Resolve repo roots, defaulting to `~/repos` unless the user gives another
   path.
3. Create missing first-run files from the templates in this repo:
   `config.md`, `about-me.md`, `goals.md`, `STORY.md`, `CHANGELOG.md`, and
   `projects/`.
4. Discover git repositories under the configured roots.
5. For each repository, collect recent git activity for the requested window:
   commits, changed files, current branch, ahead/behind status, last activity,
   and likely shipped evidence.
6. Create or update `projects/[repo].md`.
7. Read the previous `STORY.md`, refreshed project files, `about-me.md`, and
   `goals.md`.
8. Write a new `STORY.md` with:
   - `STORY`
   - `FOCUS`
   - `DEADLINES`
   - `OPEN THREADS`
   - `RECENT WINS`
9. Verify:
   - Every recent win cites evidence.
   - Every prior open thread is carried forward, completed with proof, or
     marked `STALE` or `NEEDS-REVIEW`.
   - Nothing unresolved disappears silently.
10. Append the final story to `history/[date].md`.
11. Prepend a one-line change summary to `CHANGELOG.md`.
12. Return the updated story, project files touched, and change summary.

## Rules

- Do not claim "shipped" unless the work was released, deployed, sent, or
  otherwise delivered.
- If personal context or goals are empty templates, say the story is thin and
  continue from activity evidence.
- Prefer concrete file paths, commit hashes, release links, task IDs, or
  artifact paths as evidence.
- Keep the story interpretive, not a commit list.
