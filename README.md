# Living Story

Living Story is a prompt-first workflow for keeping a daily, evidence-based
picture of active projects.

It turns repo activity into a durable project memory:

- one markdown file per project
- one synthesized `STORY.md`
- one history snapshot per run
- one changelog line per update
- verification rules that prevent wins and open threads from drifting away from
  evidence

The point is not to summarize commits. The point is to keep an honest operating
picture of what is moving, what is stalled, what shipped, and what still needs
attention.

## Use

Copy the prompt in [`loop.md`](loop.md) into an agent session that can inspect
your local repositories.

The agent will create a story directory with this shape:

```text
story/
  config.md
  about-me.md
  goals.md
  STORY.md
  CHANGELOG.md
  history/
    2026-06-20.md
  projects/
    example-project.md
```

Run it once per day, or whenever you want a refreshed project picture.

## What It Checks

Living Story asks the agent to:

- discover configured repository roots
- scan each git repository for recent activity
- update per-project state files
- carry open threads forward from the previous story
- verify recent wins against real evidence
- snapshot the finished story

Recent wins require proof such as a commit, release, deployed artifact, closed
task, sent deliverable, or generated output path. If a claim cannot be proven,
the agent must relabel it or keep it under review.

## Files

- [`loop.md`](loop.md) - the reusable loop prompt
- [`submission.txt`](submission.txt) - short form-ready text for sharing the
  loop
- [`templates/`](templates) - starting files for the story directory
- [`examples/`](examples) - neutral example output
- [`skills/living-story/SKILL.md`](skills/living-story/SKILL.md) - optional
  agent skill packaging

## Design Principles

- Evidence over vibes.
- Markdown over hidden state.
- Project files before global synthesis.
- Carry forward every unresolved thread.
- Do not call something shipped unless it was released, deployed, sent, or
  otherwise delivered.

## Future CLI

This first version is prompt-first on purpose. A future CLI could make the
workflow deterministic around setup, git scanning, verification, and snapshots
while leaving interpretation to an agent.
