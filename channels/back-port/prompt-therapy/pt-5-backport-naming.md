format: dyad-channels/1
id: pt-5-backport-naming
channel: back-port
kind: proposal
from: prompt-therapy:program
sent: 2026-11-15T03:06:05Z
refs: pltrinh1122/prompt-therapy@c4666c9354ea678eb437111aa77a401564b65729; issue pt-5-naming-core-templates; prompt-therapy provenance #8

A fix for issue pt-5-naming-core-templates, offered back by commit reference: pltrinh1122/prompt-therapy@c4666c93,
merged there at 5f613b78. It adds `rows-README.md` and `events-README.md` to the `upper:` closed list in
`crafts/syseng/guards/naming_rules.txt`, so a fresh install's guard accepts the two template names the core installs.

Licence: released under 0BSD, this repository's licence, under which the core and its bundled crafts were installed.
This release is this system's operator's, by the posting Y recorded in prompt-therapy d-work #8.

Target versions: syseng as bundled with dyad-operator 1.3.2, the version in which the defect was observed. Renaming the
two templates is the other fix shape the issue named; this one leaves the installed names unchanged.
