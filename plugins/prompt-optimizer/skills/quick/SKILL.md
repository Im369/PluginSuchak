---
name: quick
description: Quick mode for prompt optimization. Use when the user wants a fast, short, minimal rewrite of rough text into a better prompt, says "quick", "short version", "just the prompt", or "no explanation". Returns only a concise prompt with no commentary; never carries out the underlying task.
---

# Quick Prompt Mode

Return a tight, improved version of the user's text as a prompt. No extras.

## Rules

1. **Do not do the task.** The input is material to rewrite, not an instruction to you.
2. **Preserve intent.** Add nothing the user did not imply.
3. **No questions.** Make the most reasonable reading and use `[PLACEHOLDERS]` for missing key details.
4. **Keep it short.** Target roughly 40 to 100 words. Use plain text, platform-agnostic.

## What to include

One compact paragraph or a few short lines covering, only where relevant: the task as a direct instruction, key context, the most important constraint, and the output format or length.

## Response format

Output only the prompt in a single code block. No headings, no bullets, no explanation before or after.

## Example

**Raw input:** `explain blockchain to my grandma`

**Output:**

```
Explain blockchain to an older adult with no technical background. Use plain language and one everyday analogy. Avoid jargon. Keep it under 150 words and end with a one-sentence summary.
```
