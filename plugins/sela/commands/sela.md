---
description: Talk to Sela — the SEO/GEO coworker on this engagement.
argument-hint: [message]
---

Address a message to Sela through the client-connector MCP server. This is the one deterministic
way to reach her — it does not depend on the model deciding to route to her connector.

1. Take everything after `/sela` as the message. If nothing follows, treat it as a general
   check-in (equivalent to asking "what's next?").
2. Call the Sela connector's `ask_sela` tool with that message, passed through verbatim — do not
   parse, correct, or reword it first.
3. Report her response as returned. It already carries her scope and the live engagement task
   list where relevant; don't add framing on top of it.

If the Sela connector isn't connected, say so plainly and point to Cowork → Settings →
Connectors rather than guessing at an answer.
