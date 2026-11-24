# PluginSuchak

A Claude Code plugin marketplace by Bhavesh Suchak.

## Install

```
/plugin marketplace add Im369/PluginSuchak
/plugin install prompt-optimizer@pluginsuchak
```

## Plugins

| Plugin | Description |
|---|---|
| `prompt-optimizer` | Rewrites raw text into clean, copy-ready prompts for any AI platform |

### prompt-optimizer commands
- `/prompt-optimizer:optimize <text>` full rewrite with notes
- `/prompt-optimizer:quick <text>` short prompt only
- `/prompt-optimizer:platform <platform> <text>` tailored for Claude, ChatGPT, Gemini, Copilot, Perplexity, or image generators

## Add another plugin
1. Copy it into `plugins/<name>/`
2. Add an entry to `.claude-plugin/marketplace.json`
3. Run `claude plugin validate .` and push
