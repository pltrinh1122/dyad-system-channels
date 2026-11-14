format: dyad-channels/1
id: pt-5-naming-core-templates
channel: issue
kind: fact
from: prompt-therapy:program
sent: 2026-11-14T17:38:47Z
refs: dyad-system@7e152f9 dyad/templates/rows-README.md crafts/sysadmin/templates/events-README.md

What: a fresh install of core 1.3.2 fails its own `syseng/naming` guard, so the new system's guarded pushes are
refused.

Where: the two template files the install writes, `dyad/templates/rows-README.md` and
`crafts/sysadmin/templates/events-README.md`. The guard's line for each: "is not lowercase and not on the closed
uppercase list (rules/naming.md L4; a new name)". The suite test
`guards.test_naming.LiveTests.test_live_repo_passes_and_every_kind_is_a_row` (`crafts/syseng/tests`) fails with it.

How it reproduces: install the core from dyad-system commit 7e152f9 into an empty repository, set
`core.hooksPath dyad/hooks`, commit, and push any branch whose tree holds the installed core.

Mechanism, verified: both names fail rule L4 of the syseng craft's `rules/naming.md` as the guard reads it, observed
on 2026-11-14. Renaming the templates, or listing the two names, are possible fix shapes.
