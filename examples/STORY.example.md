# Story

## STORY

You have four real threads moving at once, and the shape is clearer than it was
yesterday. The client portal is closest to shipping: the authentication cleanup
landed, the billing table regression was fixed, and the remaining work is now
mostly release discipline rather than discovery. The research digest is moving
too, but it is still in the messy middle: the importer works, the summary pass
is useful, and the review queue is now the part that decides whether this turns
into a dependable weekly workflow or stays as a promising prototype.

The pattern across the scan is that your best progress came from turning fuzzy
systems into receipts: release notes, generated reports, artifact paths, and
project files that can be checked later. The risk is split attention. The mobile
capture app has not moved in six days and is now stale, while the data cleanup
tool has a shipped CLI but no documented handoff. Today should be less about
starting something new and more about closing the two loops that already have
evidence behind them.

## FOCUS

- Prepare the client portal release after the billing regression fix.
- Finish the research digest review queue so the weekly run can be trusted.
- Write the data cleanup handoff while the CLI behavior is still fresh.
- Decide whether the stale mobile capture app still belongs in this week's
  active set.

## DEADLINES

- 2026-06-21 Client portal release candidate review.
- 2026-06-22 Research digest weekly run.
- 2026-06-24 Data cleanup handoff note.

## OPEN THREADS

- Client portal release checklist: 2 days open.
- Research digest review queue: 3 days open.
- Data cleanup handoff: 1 day open.
- Mobile capture offline sync decision: 6 days open, STALE.

## RECENT WINS

- Fixed the client portal billing table regression. Evidence: commit
  `8d14c2a` in `client-portal`.
- Added the research digest importer and generated a sample report. Evidence:
  commit `4f92b11` and artifact `reports/research-digest-2026-06-20.html`.
- Shipped the first data cleanup CLI build. Evidence: release
  `data-cleanup-cli/v0.1.0`.
