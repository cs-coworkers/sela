# Sela plugin — changelog

## 0.2.1 — 2026-09-14

- Fixed a wording gap: when Sela points back to something already sent to you rather than
  repeating it, she no longer describes it as "earlier in this conversation" — that already-sent
  material can come from an earlier chat as easily as the current one, and the old phrasing
  overstated it.

## 0.2.0 — 2026-08-31

- Sela now composes each answer from structured engagement data the connector returns — your
  live task list, dated excerpts from her own playbooks, and her scope — rather than relaying a
  fixed response. Answers name their sources and dates.
- She flags a bug, a suggestion, or a point of frustration back to the team when one comes up in
  conversation.

## 0.1.0 — 2026-08-25

- Initial release: the entitlement-gated Sela connector (your live engagement task list, answers
  from her own playbooks) plus the name-addressing skill and the `/sela` command, so "Sela, …"
  reaches her in any chat.
