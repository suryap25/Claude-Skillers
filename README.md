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

This repository is public so Claude Code can clone it over HTTPS from the Add marketplace dialog.

From a local clone of this repo:

```text
/plugin marketplace add .
```
