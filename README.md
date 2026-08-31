# Sela — Coworkers.Global managed agent

Install source for **Sela**, the SEO / generative-engine-optimisation managed agent that works your engagement.

Sela is two pieces you add once:
- the **skill** (this plugin) — so "Sela, …" reaches her in any chat and her answers read in her voice;
- the **connector** — her live engagement task list and answers drawn from her own playbooks.

## Install (Cowork / Claude desktop app)

**1 — Add the connector** (this is the sign-in step):
- Open **https://claude.ai/settings/connectors → Add custom connector**.
- URL: `https://sela-connector.coworkers-global.workers.dev/mcp`
- **Connect**, and complete the one-time Google sign-in.

**2 — Add the skill:**
- **Customize → Plugins → Personal plugins → ＋ → Add from a repository.**
- Enter `cs-coworkers/sela` and **Sync**, then install the **sela** plugin and enable it.

**3 — Use her:** open a **new** chat and address her — **"Sela, …"**.

Access is gated by your engagement — signing in on a seat without an active entitlement returns a friendly "not active" message, not an error.

> This repo is isolated to Sela on purpose. It is not the internal Coworkers.Global plugin repo, and it never carries another client's agent.
