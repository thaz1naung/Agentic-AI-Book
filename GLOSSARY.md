# Glossary / ဝေါဟာရရှင်းလင်းချက်

ဒီ glossary က dictionary translation မဟုတ်ပါ။ Repo ထဲမှာ Agentic AI အကြောင်းပြောတဲ့အခါ term တစ်ခုကို ဘယ်လိုနားလည်ထားရမလဲဆိုတာကို developer-friendly အနေနဲ့ ရှင်းထားတာပါ။

## Agent

Agent ဆိုတာ message တစ်ခုပဲ ပြန်ဖြေတဲ့ chatbot ထက် ပိုပါတယ်။ Goal ကိုကြည့်ပြီး next step စဉ်းစားနိုင်တယ်၊ tool ခေါ်နိုင်တယ်၊ result ကိုပြန်ကြည့်ပြီး ဆက်လုပ်မလား ရပ်မလား ဆုံးဖြတ်နိုင်တဲ့ AI system ကို ဆိုလိုပါတယ်။

## Agentic AI

Agentic AI ဆိုတာ model ကို တစ်ခါမေးပြီး တစ်ခါဖြေတဲ့ပုံစံမဟုတ်ဘဲ loop နဲ့အလုပ်လုပ်စေတဲ့ idea ပါ။ Think → act → observe → adjust ဆိုတဲ့ cycle ထဲမှာ model, tools, memory, rules တွေ ပေါင်းပြီး task တစ်ခုကို ပြီးအောင်လုပ်စေပါတယ်။

## Tool Calling

Tool Calling ဆိုတာ model က "ဒီ function/tool ကို run ပေးပါ" လို့ request လုပ်တာပါ။ Search, file read, browser action, API call, shell command စတာတွေ ဖြစ်နိုင်ပါတယ်။ Tool result က မှန်မမှန်၊ safe ဖြစ်မဖြစ်ကို system က ပြန်စစ်ရပါမယ်။

## Context

Context ဆိုတာ model ကို လက်ရှိ task အတွက် ပေးထားတဲ့ information အားလုံးပါ။ User message, system rules, conversation history, file content, retrieved docs, tool output စတာတွေ ပါနိုင်ပါတယ်။

## Context Engineering

Context Engineering ဆိုတာ model ကို ဘာတွေပြမလဲ၊ ဘယ်အစဉ်နဲ့ပြမလဲ၊ ဘာတွေဖယ်မလဲ ဆိုတာကို design လုပ်တာပါ။ Prompt ရေးတာတစ်ခုတည်းမဟုတ်ဘဲ memory, retrieval, tool output, instruction hierarchy အကုန်ပါပါတယ်။

## RAG

RAG က Retrieval-Augmented Generation ပါ။ Model ကို တိုက်ရိုက်မဖြေခိုင်းခင် relevant document/data ကို အရင်ရှာပြီး၊ ရလာတဲ့ context ပေါ်မူတည်ပြီး ဖြေခိုင်းတဲ့ pattern ပါ။

## MCP

MCP ဆိုတာ Model Context Protocol ပါ။ Model နဲ့ external tools/resources တွေကို standard client/server ပုံစံနဲ့ ချိတ်ဆက်ဖို့သုံးတဲ့ protocol အနေနဲ့ မြင်လို့ရပါတယ်။ Tool access ကို စနစ်တကျ expose လုပ်ချင်တဲ့အခါ အသုံးဝင်ပါတယ်။

## Memory

Memory ဆိုတာ conversation တစ်ကြိမ်ပြီးသွားလည်း နောက်ပိုင်းမှာ ပြန်သုံးနိုင်အောင် သိမ်းထားတဲ့ information ပါ။ User preference, project facts, previous decisions စတာတွေ ဖြစ်နိုင်ပါတယ်။ Memory မကောင်းရင် agent က context မှားသွားနိုင်ပါတယ်။

## Planner

Planner ဆိုတာ goal တစ်ခုကို step တွေအဖြစ် ခွဲပေးတဲ့ role ပါ။ ဥပမာ "repo ကို review လုပ်မယ်" ဆိုရင် inspect files, run tests, summarize risks ဆိုပြီး plan ခွဲနိုင်ပါတယ်။

## Worker Agent

Worker Agent ဆိုတာ planner က ခွဲထားတဲ့ task တစ်ခုကို တကယ်လုပ်တဲ့ agent/component ပါ။ Research worker, coding worker, test worker လိုမျိုး role သေးသေးလေးတွေ ဖြစ်နိုင်ပါတယ်။

## Critic Agent

Critic Agent ဆိုတာ output ကိုပြန်စစ်တဲ့ role ပါ။ Mistake ရှာတယ်၊ missing evidence ရှိမရှိ စစ်တယ်၊ unsafe step ပါမပါ ကြည့်တယ်။ Critic က final answer ကို ပိုယုံကြည်စေဖို့ကူညီပေမယ့် သူလည်းမှားနိုင်ပါတယ်။

## Workflow

Workflow ဆိုတာ fixed သို့မဟုတ် semi-fixed steps တွေနဲ့ သွားတဲ့ process ပါ။ AI ပါနိုင်ပေမယ့် agent လို လွတ်လွတ်လပ်လပ် next step ဆုံးဖြတ်တာမျိုး မဖြစ်ချင်လည်း ရပါတယ်။

## Guardrails

Guardrails ဆိုတာ agent ကို safe ဖြစ်အောင်ထားတဲ့ rules/checks တွေပါ။ Permission limit, output validation, human approval, sandbox, blocked action list စတာတွေ ပါနိုင်ပါတယ်။

## Coding Agent

Coding Agent ဆိုတာ codebase ကို inspect လုပ်နိုင်၊ file edit လုပ်နိုင်၊ command/test run လုပ်နိုင်တဲ့ AI assistant ပါ။ အားသာချက်က speed ဖြစ်ပြီး risk က wrong edit, unsafe command, hidden assumption တွေပါ။

## DevOps Automation

DevOps Automation ဆိုတာ CI/CD, deployment, infra scripts, monitoring, rollback, incident response စတဲ့ ops work တွေကို automate လုပ်တာပါ။ AI agent ထည့်သုံးမယ်ဆိုရင် dry-run, approval, logs, rollback plan တွေ အရေးကြီးပါတယ်။

## Human-in-the-loop

Human-in-the-loop ဆိုတာ risky step မလုပ်ခင် လူက review/approve လုပ်တဲ့ design ပါ။ Production deploy, secret rotation, destructive command, billing-related action စတာတွေမှာ အထူးလိုအပ်ပါတယ်။
