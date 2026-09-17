# Claude-Skillers

Collection of Claude Code skills and plugins.

The marketplace catalog is `.claude-plugin/marketplace.json` at the repository root. Claude Code clones the default branch (`main`) when you add this GitHub URL.

## Add the marketplace

In Claude Code (Add marketplace), use GitHub shorthand (recommended) or a git URL. Do not point at a subdirectory.

```text
suryap25/Claude-Skillers
```

```text
https://github.com/suryap25/Claude-Skillers.git
```

CLI:

```bash
claude plugin marketplace add suryap25/Claude-Skillers
claude plugin install slack-thread-triage@claude-skillers
```

This repository is private. Claude Code uses your existing git credentials. GitHub `owner/repo` shorthand clones over SSH by default.

From a local clone of this repo:

```text
/plugin marketplace add .
```
