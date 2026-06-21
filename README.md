# Living Story

Living Story is a prompt-first workflow for giving agents a durable,
evidence-based understanding of a person and the work around them.

It keeps more than project status. It maintains the context agents usually lose
between sessions:

- what someone is building
- what they care about
- what their goals are
- what motivates them
- what counts as real progress
- which projects are moving, stalled, shipped, or unresolved

The result is a living operating picture that agents can read before helping.
Instead of starting every session from scattered repo activity and stale memory,
an agent gets a current story of the work, the person behind it, and the next
things that actually deserve attention.

## Why It Matters

Most agent workflows are task-scoped. They can inspect a repo, answer a prompt,
or finish a ticket, but they rarely understand the broader arc: why this work
matters, what the person is trying to become, which commitments are real, and
where attention is getting fragmented.

Living Story turns that broader context into a small markdown system:

- one `about-me.md` for personal operating context
- one `goals.md` for targets, dates, and motivation
- one markdown file per project
- one synthesized `STORY.md`
- one history snapshot per run
- one changelog line per update
- verification rules that keep wins and open threads tied to evidence

The point is not to summarize commits. The point is to keep an honest,
inspectable narrative of what is moving, what is stalled, what shipped, what is
at stake, and what should happen next.

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

Run it once per day, or whenever you want a refreshed operating picture.

## What It Checks

Living Story asks the agent to:

- discover configured repository roots
- scan each git repository for recent activity
- update per-project state files
- read personal context and goals
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

- Personal context is part of the work context.
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
