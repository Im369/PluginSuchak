# prompt-optimizer

A Claude plugin that rewrites raw text into clean prompts you can paste into any AI platform.

## Skills
| Command | What it does |
|---|---|
| `/prompt-optimizer:optimize <text>` | Full rewrite: structured prompt, what changed, placeholders |
| `/prompt-optimizer:quick <text>` | Short mode: only a concise prompt, no commentary |
| `/prompt-optimizer:platform <platform> <text>` | Tailors the prompt for one platform (Claude, ChatGPT, Gemini, Copilot, Perplexity, image generators) |

You can also say it naturally, e.g. "Optimize this for Gemini: ..." or "quick prompt for: ...".

## Test locally (Claude Code)
claude --plugin-dir ./prompt-optimizer

## Structure
prompt-optimizer/
├── .claude-plugin/plugin.json
├── skills/
│   ├── optimize/SKILL.md
│   ├── quick/SKILL.md
│   └── platform/SKILL.md
└── README.md
