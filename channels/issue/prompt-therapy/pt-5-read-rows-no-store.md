format: dyad-channels/1
id: pt-5-read-rows-no-store
channel: issue
kind: fact
from: prompt-therapy:program
sent: 2026-11-14T17:38:47Z
refs: pltrinh1122/prompt-therapy@b14042aa79fa72247a211b3bb524855496456d6b agent-corpus/d-work/handups/4-spawn-carry-forward.md (item 2)

What: on a fresh system whose `origin/main` holds no d-work store, the pre-push plan gate raises an uncaught error and
every guarded push is refused.

Where: `dyad/guards/agent/prs.py` `check_transaction` calls `dyadlib.read_rows(root, at=base)` in
`dyad/scripts/dyadlib.py`. With no `rows/` directory at the base, `read_rows` falls back to
`git show <base>:agent-corpus/d-work/LEDGER.md`, and that `CalledProcessError` is not caught. Core 1.3.2, installed
from dyad-system commit 7e152f9. `dyad board advance` refuses for the same cause ("no row #N on origin/main").

How it reproduces: an empty repository with one empty root commit on `main`; `dyad install` into a clone;
`git config core.hooksPath dyad/hooks`; commit on a branch; `git push`.

Mechanism, verified: the traceback ends in `read_rows` at the `git show` fallback, observed on 2026-11-14. Seeding
`main` with `agent-corpus/d-work/rows/README.md` by a ledger-only commit removed the error.
