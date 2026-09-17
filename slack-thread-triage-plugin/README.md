# Slack Thread Triage (Claude Code plugin)

Analyzes Slack/Teams conversation threads to detect consensus, unresolved questions, and next steps, then drafts the minimum viable reply to move the thread forward.

This plugin packages the `slack-thread-triage` skill. It **drafts** a reply. It does not post to Slack or Teams, and it does not require Slack MCP, tokens, or environment variables. Paste the thread into the session.

## Install from this marketplace

The marketplace catalog is `slack-thread-triage-plugin/.claude-plugin/marketplace.json`. From the Claude-Skillers repo root (or any clone that contains this folder):

In Claude Code:

```text
/plugin marketplace add ./slack-thread-triage-plugin
/plugin install slack-thread-triage@claude-skillers
/reload-plugins
```

From the CLI:

```bash
claude plugin marketplace add ./slack-thread-triage-plugin
claude plugin install slack-thread-triage@claude-skillers
```

If the repo is on GitHub, you can add the marketplace from the git remote instead of a local path (same `marketplace.json` inside this plugin folder). After install, confirm the skill with `/` or `/skills`. Plugin skills are namespaced:

```text
/slack-thread-triage:slack-thread-triage
```

## Load the plugin directory directly

From the Claude-Skillers repo root:

```bash
claude --plugin-dir ./slack-thread-triage-plugin
```

Then invoke `/slack-thread-triage:slack-thread-triage` and paste the thread.

## What the skill does

Before drafting, it runs four checks:

1. **Consensus Check** — Has agreement already been reached?
2. **Alignment Check** — Are participants genuinely aligned?
3. **Next Steps & Ownership** — Are action items assigned and clear?
4. **Pending Ask** — Is there a direct unanswered question?

Output is always:

- **Thread Status**: Aligned & Settled | Action Items Pending | Misaligned / Clarification Needed
- **Key Consensus**: one sentence, or `None`
- **Minimal Reply**: a 1–2 sentence draft in a blockquote

## Usage examples

Settled thread:

```text
/slack-thread-triage:slack-thread-triage

I'm Alex. Here's the thread:

Alex: Can we ship the billing fix in Friday's cut?
Sam: +1 if QA is done by Thursday.
Jordan: QA will finish Thursday noon.
Sam: sounds good
```

Pending question:

```text
Triage this Slack thread and draft the minimum reply I should send.

Priya: Who owns the migration runbook?
Lee: I can take it if someone reviews the rollback section.
Priya: What's the rollback target — staging or last prod snapshot?
Lee: (no reply)
```

Misalignment:

```text
/slack-thread-triage:slack-thread-triage

A: Let's use the new API for v1.
B: No, v1 should stay on the old API; new API is v2 only.
A: I thought we agreed last week to cut over now.
```

## License

MIT. Copyright (c) 2026 Venkatesh Peri.
