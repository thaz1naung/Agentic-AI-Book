# Agentic AI Book

မြန်မာ Developer များအတွက် Agentic AI ကို လက်တွေ့အခြေခံနဲ့ နားလည်အောင် ရေးထားသော open-source book project ဖြစ်ပါတယ်။

ဒီ repo ရဲ့ အဓိကရည်ရွယ်ချက်က Agent, Tool Calling, RAG, MCP, Context Engineering, Coding Agent, DevOps Automation စတာတွေကို "ဘယ်လိုစဉ်းစားရမလဲ" ဆိုတဲ့ angle ကနေ ရှင်းပြဖို့ပါ။ Framework documentation ကို တိုက်ရိုက်ဘာသာပြန်ထားတာ မဟုတ်ပါ။ Production manual လည်း မဟုတ်ပါ။ Beginner ကနေ intermediate developer အထိ ဖတ်လို့ရအောင် practical thinking guide အနေနဲ့ ပြင်ဆင်ထားပါတယ်။

## What This Book Is

Agentic AI Book က AI agent system တွေကို developer mindset နဲ့ လေ့လာနိုင်အောင် စုစည်းထားတဲ့ manuscript project ပါ။

ဖတ်ရန်အစမှာ `book/chapters/00-license.md` နှင့် `book/chapters/00-preface.md` ဖြစ်သည်။ Chapter 12 မှ 15 အထိသည် repo-backed case study လေးခုဖြစ်သည်။

ဒီစာအုပ်မှာ theory တစ်ခုတည်းမဟုတ်ဘဲ:

- Agent loop ကို ဘယ်လိုမြင်ရမလဲ
- Tool တစ်ခုကို agent က သုံးတဲ့အခါ risk ဘယ်လိုစဉ်းစားရမလဲ
- Context, memory, RAG တို့က ဘာကွာလဲ
- MCP, skill, subagent ဆိုတာတွေကို beginner အနေနဲ့ ဘယ်လိုစတင်နားလည်ရမလဲ
- Coding agent နဲ့ DevOps automation ကို လုံခြုံစိတ်ချစွာ ဘယ်လိုသုံးမလဲ

ဆိုတာတွေကို တဖြည်းဖြည်းရှင်းပြဖို့ ရည်ရွယ်ထားပါတယ်။

## Who Should Read This

ဒီစာအုပ်က အောက်ပါသူတွေအတွက် ရေးထားပါတယ်။

- မြန်မာ developer များ
- AI agent / automation စတင်လေ့လာနေသူများ
- RAG, MCP, LangGraph, Coding Agent စတာတွေကို concept အနေနဲ့ နားလည်ချင်သူများ
- DevOps automation မှာ AI agent ထည့်သုံးဖို့ စဉ်းစားနေသူများ
- English technical docs ဖတ်နိုင်ပေမယ့် Burmese explanation နဲ့ ပိုမြန်မြန်နားလည်ချင်သူများ

## What Readers Will Learn

စာအုပ်ကို ဖတ်ပြီးရင် reader အနေနဲ့ အောက်ပါအရာတွေကို ပိုရှင်းရှင်းလင်းလင်းမြင်လာဖို့ မျှော်လင့်ပါတယ်။

- Agentic AI ဆိုတာ chatbot တစ်ခုထက် ဘာပိုလဲ
- Agent, workflow, automation တို့ကို ဘယ်လိုခွဲမလဲ
- Tool Calling / Function Calling ကို ဘယ်လိုအသုံးချမလဲ
- Context Engineering, Memory, RAG တို့ရဲ့ role
- Planner / Worker / Critic style agent pattern
- Guardrails, sandbox, permission, prompt injection စတဲ့ safety concerns
- Coding agent နဲ့ DevOps automation examples တွေကို ဘယ်လိုအကဲဖြတ်မလဲ

## Start Here

Recommended reading order:

1. [License](book/chapters/00-license.md)
2. [Preface](book/chapters/00-preface.md)
3. [Agentic AI Basics](book/chapters/01-agentic-ai-basics.md)
4. [Agent vs Workflow vs Automation](book/chapters/02-agent-vs-workflow-vs-automation.md)
5. Continue chapter-by-chapter from the table of contents below.

If you are new to AI agents, start from Chapter 01. If you already know tool calling and RAG, you can jump to Chapter 06 or Chapter 07, then come back later.

## Table Of Contents

All links below point to existing manuscript files. Chapter prose is author-owned and should not be rewritten directly without prior discussion.

- [00 - License](book/chapters/00-license.md)
- [00 - Preface](book/chapters/00-preface.md)
- [00 - Thank You Note](book/chapters/00-thankyou_note.md)
- [01 - Agentic AI Basics](book/chapters/01-agentic-ai-basics.md)
- [02 - Agent vs Workflow vs Automation](book/chapters/02-agent-vs-workflow-vs-automation.md)
- [03 - LLM Tool Calling / Function Calling](book/chapters/03-llm-tool-calling-function-calling.md)
- [04 - Agent Loop](book/chapters/04-agent-loop.md)
- [05 - Agent Harness](book/chapters/05-agent-harness.md)
- [06 - MCP, Skill, Subagent](book/chapters/06-mcp-skill-subagent.md)
- [07 - Context Engineering, Memory, RAG](book/chapters/07-context-engineering-memory-rag.md)
- [08 - Planner, Worker, Verifier](book/chapters/08-planner-worker-verifier.md)
- [09 - Tool Broker, Permission, Mutation Scope](book/chapters/09-tool-broker-permission-mutation-scope.md)
- [10 - Observability, Trajectory, Reflection](book/chapters/10-observability-trajectory-reflection.md)
- [11 - Safety, Sandbox, Prompt Injection, Tool Output](book/chapters/11-safety-sandbox-prompt-injection-tool-output.md)
- [12 - P-2 Zero-Trust Multi-Agent Bridge](book/chapters/12-p2-zero-trust-multi-agent-bridge.md)
- [13 - Travis-2 Controlled Runtime](book/chapters/13-travis2-controlled-runtime.md)
- [14 - BrowserSurfer Browser Tool Agent Security](book/chapters/14-browsersurfer-browser-tool-agent-security.md)
- [15 - appv22 Emerging Runtime Recovery Lab](book/chapters/15-appv22-emerging-runtime-recovery-lab.md)
- [16 - DevOps Agent Thinking](book/chapters/16-devops-agent-thinking.md)
- [17 - Mini Labs](book/chapters/17-mini-labs.md)
- [18 - Myanmar Developer Roadmap](book/chapters/18-myanmar-developer-roadmap.md)
- [19 - References](book/chapters/19-references.md)

## Repository Structure

```text
.
├── README.md
├── CONTRIBUTING.md
├── ROADMAP.md
├── SECURITY.md
├── GLOSSARY.md
├── STYLE_GUIDE.md
├── STARTER_ISSUES.md
├── LICENSE-NEEDS-DECISION.md
├── .github/
│   ├── ISSUE_TEMPLATE/
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── LABELS.md
├── book/
│   ├── README.md
│   ├── LICENSE.md
│   └── chapters/
├── repo_sources/
├── scripts/
├── models
└── prompts
```

`book/` and `book/chapters/` are manuscript areas. Treat them carefully.

Useful file references:

- [book/README.md](book/README.md)
- [book/chapters/00-license.md](book/chapters/00-license.md)
- [book/chapters/00-preface.md](book/chapters/00-preface.md)

Repo-backed case study links:

1. [`P-2`](https://github.com/htooayelwinict/P-2)
2. [`travis-2`](https://github.com/htooayelwinict/travis-2)
3. [`bot / BrowserSurfer Bot`](https://github.com/htooayelwinict/bot)
4. [`allthebest / appv22`](https://github.com/htooayelwinict/allthebest)

## How To Contribute

Contributions are welcome, especially small improvements that help readers.

Good contribution types:

- typo fixes
- broken link reports
- diagram suggestions
- glossary improvements
- terminology consistency notes
- beginner explanation suggestions
- technical corrections with source/context
- issue discussions

Important rule:

Please do not submit large manuscript/chapter rewrites directly. Open an issue first and discuss the change with the maintainer. The author voice matters, especially for Burmese + English explanation style.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide.

## Roadmap Summary

Current roadmap focus:

- improve diagrams
- strengthen glossary and terminology consistency
- add beginner-friendly examples
- expand MCP, RAG, memory, and LangGraph explanations
- add safer DevOps automation and tool-calling examples
- make contribution workflow easier for new readers

See [ROADMAP.md](ROADMAP.md).

## License Note

The manuscript currently includes a license note at [book/LICENSE.md](book/LICENSE.md).

There is no root-level `LICENSE` file yet. Before wider reuse, packaging, or distribution, the maintainer should choose and add a clear root repository license. See [LICENSE-NEEDS-DECISION.md](LICENSE-NEEDS-DECISION.md).

I am not choosing a license automatically here.

## Author Note

This project is written and maintained by Htoo Aye Lwin.

The goal is not to sound perfect. The goal is to make Agentic AI easier to understand for Myanmar developers, with practical language and real engineering caution.

If you find something confusing, please open an issue. A confused reader is useful feedback.
