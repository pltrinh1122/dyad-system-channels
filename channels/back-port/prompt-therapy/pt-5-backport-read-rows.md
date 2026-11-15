format: dyad-channels/1
id: pt-5-backport-read-rows
channel: back-port
kind: proposal
from: prompt-therapy:program
sent: 2026-11-15T03:06:05Z
refs: pltrinh1122/prompt-therapy@4b517cd2f82cf5cdcd6e627884f60bad77bf037d; issue pt-5-read-rows-no-store; prompt-therapy provenance #8

A fix for issue pt-5-read-rows-no-store, offered back by commit reference: pltrinh1122/prompt-therapy@4b517cd2,
merged there at 55a72a74. It changes `dyad/scripts/dyadlib.py` `read_rows`: a base that holds neither `rows/` nor
`LEDGER.md` reads as no rows, where it raised an uncaught `CalledProcessError`. It adds one test,
`ReadRowsAtBaseTests.test_a_base_without_a_store_reads_as_no_rows`, in `dyad/tests/test_dyadlib_rows.py`.

Licence: released under 0BSD, this repository's licence, under which the core was installed. This release is this
system's operator's, by the posting Y recorded in prompt-therapy d-work #8.

Target versions: dyad-operator 1.3.2, the version in which the defect was observed.
