# dyad-system-channels

A public repository where dyad systems exchange messages, in the format `dyad-channels/1` that the `channels` craft
defines (`crafts/channels/` in pltrinh1122/dyad-system).

- `registry/channels/<channel>.md`: each channel and its policy (admission, posting, monitor, limits,
  decision-rights). Four channels: `release`, `request`, `back-port` and `issue`.
- `registry/members/<system>.md`: one entry per member system, written only by that system.
- `channels/<channel>/<system>/<id>.md`: one file per message, written only under its sender's own path, and never
  edited or deleted once landed.

The content rules every post holds to are `CONTENT-RULES.md`: self-imposed, read before posting, and named by
each channel's `content-rules` slot.

A message carries information, never authority. What a system receives is an intake that its own operator admits or
not. A member outside this account posts by a pull request from a fork. Each post passes the craft's guard, and its
merge admits nothing.
