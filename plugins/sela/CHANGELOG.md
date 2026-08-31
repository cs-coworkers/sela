# Sela plugin — changelog

## v0.2.0 — 2026-08-31 (v2 skill split; branch `v2-skill-split`, ships with the v2 cutover, not before)

- **The SKILL.md split lands (Cody; v2 PRD §2a, ruled by Charlie 2026-08-31).** Composition moves
  client-side under v2, and the skill mirrors `agent.config.ts`'s seam: the agent-INVARIANT
  composition contract now lives at `skills/sela/references/composition-contract.md` — byte-
  identical across every agent plugin, canonical at `shared/composition-contract.md`, verified by
  `scripts/check-contract-identity.mjs` (exits 1 on divergence; run before tagging any release
  that bundles it) — and `SKILL.md` keeps only what is Sela's alone: name, lane, tool names,
  voice. The contract governs the v2 envelope's fields, what her answers may draw on, the
  degrade-flag phrasing table (`menu`/`frameRefused`/`nonEnglish`/`noMatch`/`selfScope`/
  `outOfScope`, plus `back_reference`), and the three `flag_feedback` triggers with the
  `posited_improvement` rule. Sam's Style section carried over untouched.
- **`plugin_version` now passed on originated `ask_sela` calls** (§8b rule 2, previously unmet in
  this skill): the tool table states `plugin_version: "0.2.0"`. Two homes for the version string
  (this file's heading, plugin.json, the tool table) — bump all on release.
- **VERSION GATE: this plugin version pairs with the v2 Worker return shape** (`v2-thin-connector`
  branch). Against the live v1 Worker its composition instructions have no envelope to read —
  do not register it for a real client seat until the v2 cutover gate (PRD §5) clears.

## Unreleased

- **Fixed (Clarice, 2026-08-30, PR #5, `c1cce03`):** `skills/sela/SKILL.md` tool table advertised
  `repurpose_post`, `reddit_reply_drafter`, `naming_and_claims_check` — all three removed from the
  worker at PRD v0.13. Verified against live `src/agent.config.ts`; rewrote to route through
  `ask_sela` and state playbook-release status plainly. Install-checklist P4's tool-table half is
  now clear. Still open: Sam's voice pass (§ Style still placeholder), Block 3 routing test.

## v0.1.0 — 2026-08-25

Initial build (Clarice, client-connector PRD v0.9 §3a.7 / Block 6). Bundles:
- `.mcp.json` — the Sela connector (OAuth MCP, entitlement-gated), pointed at the renamed
  `sela-connector` Worker.
- `skills/sela/SKILL.md` — account-wide skill so Sela is reachable by name in every chat,
  mirroring the pattern that gave Chet a "worked every time" record on name-addressing.
- `commands/sela.md` — the `/sela` slash command, the one deterministic address rung.

**Deliberately unregistered** (`metadata.status: "experimental"`, per `plugins/README.md`'s
registration-parity rule) — not yet in `.claude-plugin/marketplace.json`, so not installable by
anyone until registered.

**Open before first client install (HireBoost/Jodi, targeted 2026-09-01):**
- Verify the live `sela-connector` Worker hostname against Cloudflare directly — this build
  infers it from `wrangler.toml`'s account-subdomain comment and Cody's 08-25 401-probe
  confirmation that the renamed URL is serving, but no tool call this session read the
  Cloudflare dashboard itself.
- Sam's voice pass on `SKILL.md` § Style (placeholder as shipped).
- Block 3's routing test (10/10 "Sela,"-prefixed messages, Chet connected and disconnected) —
  not yet run against this plugin specifically.
- Register in `.claude-plugin/marketplace.json` once the above clear.
