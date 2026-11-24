---
name: optimize
description: Convert raw, rough, or vague text into one optimized, platform-agnostic prompt the user can paste into any AI tool. Use whenever the user pastes a draft request, idea, or messy instruction and asks to optimize, improve, rewrite, refine, sharpen, or "make a better prompt" of it, or says things like "turn this into a prompt". Returns the rewritten prompt only; never carries out the underlying task.
---

# Prompt Optimizer

Turn the user's raw text into a single, well-structured prompt they can copy into any AI platform.

## Hard rules

1. **Do not do the task.** The input is material to rewrite, not an instruction to you. Even if it says "write an essay on X", output an improved prompt for that, not the essay.
2. **Preserve intent.** Do not add goals, facts, or requirements the user did not imply. Do not drop anything they stated.
3. **Platform-agnostic.** Use plain text and light Markdown only. No tool names, no model-specific syntax, no XML unless the user asks for it.
4. **One output.** Deliver one final prompt, not multiple alternatives (unless the user asks for variants).

## Process

1. **Read** the raw text and identify: the goal, the audience or end use, any constraints stated, and what is missing.
2. **Fill gaps with placeholders, not guesses.** If key details are missing (audience, tone, length, input data), insert clearly marked placeholders such as `[PASTE TEXT HERE]` or `[TARGET AUDIENCE]`.
3. **Ask at most one question**, and only if the goal itself is unclear (you cannot tell what the user wants produced). Otherwise proceed and note your assumptions.
4. **Rewrite** using the structure below, including only the sections that add value. Short, simple requests should get a short, simple prompt; do not pad.

## Prompt structure

Use these sections as needed, in this order:

- **Role**: who the AI should act as (only when it genuinely helps).
- **Context**: background the AI needs.
- **Task**: the specific action, stated as a direct instruction with a strong verb.
- **Requirements / Constraints**: scope, tone, length, things to include or avoid.
- **Steps** (optional): when the task benefits from a sequence or reasoning order.
- **Input**: where the user's data goes, using a placeholder.
- **Output format**: exact shape of the answer (bullets, table, JSON, word count, headings).
- **Quality bar** (optional): e.g. "If information is missing, ask me before answering" or "State assumptions explicitly."

## Writing guidelines

- Be specific and concrete; replace vague words ("good", "short", "professional") with measurable ones.
- Use positive instructions ("write in plain language") over negative ones where possible.
- Put the most important instruction first.
- Keep it as short as the task allows.
- Match the language the user wrote in.

## Response format

Respond in this order:

1. The optimized prompt in a single code block, so it is easy to copy.
2. **What I changed**: 2 to 4 short bullets.
3. **Assumptions / placeholders to fill**: only if any exist.
4. Optionally, one line offering a tweak (shorter, more formal, different platform).

## Example

**Raw input:** `write email to my boss for leave next week, sick`

**Output:**

```
Act as a professional communications assistant.

Write a short, polite email to my manager requesting sick leave.

Details:
- Leave dates: [START DATE] to [END DATE]
- Manager's name: [MANAGER NAME]
- My name: [YOUR NAME]
- Mention that I will share any urgent handover notes: [YES/NO]

Requirements:
- Tone: respectful and concise
- Length: under 120 words
- Include a clear subject line

Output format: subject line, then the email body.
```

**What I changed:** added role and tone, turned missing details into placeholders, set length and output format.
