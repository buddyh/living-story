# Living Story Loop

Keep a daily, evidence-based picture of everything I am building, stored in a
home folder called `[story dir]`.

On the first run, create what is missing:

- `config.md` with repo roots, defaulting to `~/repos` unless I provide another
  path, plus discovered repositories and optional non-git sources such as notes,
  task exports, or calendar exports.
- `about-me.md` with a short template for who I am, how I work, what drives me,
  and what counts as real progress.
- `goals.md` with goals, targets, dates, status, and notes.

If `about-me.md` or `goals.md` are still empty templates, build the best story
you can from activity alone and say plainly that the story will be thin until
those files are filled in.

Then, once per `[window, e.g. day]`:

1. Activity log: inspect every git repository under the configured roots and
   collect `git log --since`, files changed, current branch, ahead/behind
   status, and last meaningful activity.
2. Project state: update `[story dir]/projects/[repo].md` with status
   (`active`, `stalled`, or `shipped`), current branch, what moved this window,
   what is in progress, when it last shipped, and a `STALE` flag if it had no
   activity in `[stale=5]` days.
3. Synthesis: read `about-me.md`, `goals.md`, the previous `STORY.md`, and all
   refreshed project files. Write a fresh `STORY.md` addressed to me in second
   person with five sections:
   - `STORY`: one or two interpretive paragraphs, not a list.
   - `FOCUS`: three to five things demanding attention now.
   - `DEADLINES`: dated `YYYY-MM-DD`.
   - `OPEN THREADS`: in-progress work and open questions with days-open and
     `STALE` or `NEEDS-REVIEW` flags where appropriate.
   - `RECENT WINS`: honest wording. `Shipped` means released, deployed, sent,
     or otherwise delivered; work that is only coded or generated should be
     described that way.
4. Verify:
   - Every recent win must cite real evidence such as a commit, release, closed
     task, deployed artifact, sent deliverable, or generated artifact path.
   - Every open thread from the previous story must be accounted for: carried
     forward, moved to recent wins with proof, or marked `STALE` or
     `NEEDS-REVIEW`.
   - No unresolved thread may be silently dropped.
5. Snapshot: append the final `STORY.md` to
   `[story dir]/history/[date].md` and prepend a one-line "what changed since
   last time" entry to `[story dir]/CHANGELOG.md`.

Stop when the window's snapshot is written and the verify step passes. Finish
with the updated `STORY.md`, the project files touched, and the one-line change
summary.
