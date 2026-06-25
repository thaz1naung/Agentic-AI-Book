# Style Guide

This guide is for future contributors. Do not apply it by rewriting chapters without discussion.

## Burmese + English Technical Style

Use Burmese for explanation and flow. Keep common technical terms in English when translating them would make the sentence harder to understand.

Good style:

```text
Agent က tool ကိုခေါ်တဲ့အခါ permission scope ကို သေချာစဉ်းစားရမယ်။
```

Avoid forcing every English term into Burmese if the result sounds unnatural.

## Terms To Keep In English

Usually keep these in English:

- Agent
- Tool Calling
- Function Calling
- Context
- Context Engineering
- RAG
- MCP
- Memory
- Workflow
- Guardrails
- Sandbox
- Prompt Injection
- Coding Agent
- DevOps

You can explain them in Burmese after the English term.

## Avoid Robotic Burmese

Avoid sentences that sound like direct machine translation.

Prefer short, natural sentences. If a sentence becomes too long, split it.

Avoid overusing formal words when a normal developer phrase is clearer.

## Suggesting Chapter Edits

The author voice matters. For large prose changes:

1. Open an issue first.
2. Quote only the small sentence or section you want to discuss.
3. Explain why it is confusing.
4. Suggest a replacement in the same tone.
5. Wait for maintainer direction before opening a rewrite PR.

## Writing Examples

Examples should be:

- small
- safe by default
- realistic
- beginner-readable
- clear about assumptions

Avoid examples that mutate real systems unless clearly marked as lab-only.

## Beginner-Friendly Explanation

When explaining a hard concept:

- start with the problem
- give a simple mental model
- show one small example
- mention the risk or limitation
- avoid pretending the topic is easier than it is

## Pull Request Rule

Large prose rewrites need issue discussion first.

Small typo fixes and support-file improvements can go directly to PR.
