# Writing Style Findings From Issue #8 Pattern

This report is read-only review output. It does not fix or rewrite chapter content.

## Issue #8 Reference Pattern

Issue #8 pointed to:

```text
book/chapters/06-mcp-skill-subagent.md - line 15
```

Original problem style:

```text
လက်စွဲစာအုပ်သည်လုပ်နည်းပြသည်။
```

Suggested direction from issue:

```text
လက်စွဲစာအုပ်သည်နည်းပြလုပ်သည်။
```

Interpretation:

The issue is not only missing spacing. The bigger problem is word-position and meaning clarity. The sentence has the right idea, but the Burmese action phrase feels compressed and unnatural. This report looks for similar cases where the idea is present, but the wording may be unclear, cramped, or may require further clarification.

## What Was Scanned

Target files:

```text
book/chapters/*.md
```

Focus:

- Sentences where subject/action/object order may be unclear.
- Burmese technical explanation that feels compressed.
- Metaphor sentences where the relationship may need clarification.
- Lines that are understandable to the author, but may slow down beginner readers.

Not the focus:

- Generic spelling-only issues.
- Every missing space.
- Full prose rewrite suggestions.
- Automatic chapter edits.

## Script Context 1: Re-read Issue #8

Command used:

```bash
gh issue view 8 --json number,title,body,state,url
```

Purpose:

To confirm the issue reporter's actual complaint and suggested direction before scanning other chapters.

Relevant issue body:

```text
File or chapter link: book/chapters/06-mcp-skill-subagent.md - Line 15

Short explanation: wrong position

Suggested fix:
လက်စွဲစာအုပ်သည်လုပ်နည်းပြသည်။ -> လက်စွဲစာအုပ်သည်နည်းပြလုပ်သည်။

Notes:
Please keep chapter voice intact. Large rewrites should be discussed first.
```

## Script Context 2: Broad Read-only Candidate Scan

This script was used to identify broad candidates. It produced many noisy results, so it was not used directly as the final report.

```python
from pathlib import Path
import re

root = Path("book/chapters")

patterns = [
    ("issue8_shape_thi_joined", re.compile(r"သည်(?=[\u1000-\u109F])")),
    ("compressed_ko_joined", re.compile(r"ကို(?=[\u1000-\u109F])")),
    ("compressed_hmar_joined", re.compile(r"မှာ(?=[\u1000-\u109F])")),
    ("compressed_atwet_joined", re.compile(r"အတွက်(?=[\u1000-\u109F])")),
    ("unclear_does_action", re.compile(r"သည်[^။\n]{0,45}(လုပ်|ပြ|ဖတ်|သုံး|ထား|ထိန်း|ခွဲ|ဆက်|ရပ်|စစ်|ရေး|ဖြေ)[^။\n]{0,20}သည်")),
    ("dense_metaphor_or_tech", re.compile(r"(လမ်းတံတား|စာရေးတော်|လက်ထောက်|စက်ခန်း|မြို့|လက်|ဦးနှောက်|boundary|scope|runtime|tool|agent|Agent|Tool|Loop|Harness|Memory|Context|State)")),
]

for p in sorted(root.glob("*.md")):
    for i, line in enumerate(p.read_text(encoding="utf-8").splitlines(), 1):
        s = line.strip()
        if not s or s.startswith("#") or s.startswith("|") or s.startswith("```") or s.startswith("- `"):
            continue
        if "http://" in s or "https://" in s:
            continue
        hits = [name for name, rx in patterns if rx.search(s)]
        if hits and (
            ("issue8_shape_thi_joined" in hits or "compressed_ko_joined" in hits or "unclear_does_action" in hits)
            and ("dense_metaphor_or_tech" in hits or "unclear_does_action" in hits)
        ):
            print(f"{p}:{i}: {','.join(hits)}: {s[:260]}")
```

Result:

This caught too many normal sentences. It was useful for finding patterns, but too noisy for final decision-making.

## Script Context 3: Tightened Human-review Candidate Scan

This was used to narrow the scan toward issue-8-like wording mutants.

```python
from pathlib import Path
import re

root = Path("book/chapters")

priority = [
    re.compile(r"သည်[^။]{0,40}(လုပ်|ပြ|ဖတ်|သုံး|ထိန်း|ခွဲ|ဆက်|ရပ်|စစ်|ရေး|သင်|ခိုင်း|ဖြေ)[^။]{0,25}သည်"),
    re.compile(r"(Loop|Harness|Tool|Agent|Model|Memory|Context|State|Browser|runtime|boundary|scope|စာရေးတော်|လက်|လမ်းတံတား|မြို့|စက်ခန်း|ဦးနှောက်)[^။]{0,80}(သည်(?=[\u1000-\u109F])|ကို(?=[\u1000-\u109F])|အတွက်(?=[\u1000-\u109F]))"),
    re.compile(r"(သည်(?=[\u1000-\u109F]).{0,40}(မဟုတ်|ဖြစ်|သင်|လို|ရ|လုပ်|ဖတ်|မြင်|ထိန်း)|ကို(?=[\u1000-\u109F]).{0,40}(ဖတ်|မြင်|ခွဲ|စစ်|သင်|ထား|လုပ်))"),
]

for p in sorted(root.glob("*.md")):
    items = []
    for i, line in enumerate(p.read_text(encoding="utf-8").splitlines(), 1):
        s = line.strip()
        if not s or s.startswith("#") or s.startswith("|") or s.startswith("```") or s.startswith("- `"):
            continue
        if "http://" in s or "https://" in s:
            continue
        if any(rx.search(s) for rx in priority):
            if p.name == "06-mcp-skill-subagent.md" and i == 15:
                continue
            items.append((i, s))

    if items:
        print(f"## {p}")
        for i, s in items[:5]:
            print(f"{i}: {s[:240]}")
        if len(items) > 5:
            print(f"... +{len(items) - 5} more candidates")
        print()
```

Result:

This was still not perfect, but it helped identify where human review should focus.

## Findings By Chapter

### `00-license.md`

Lines to review:

- 27
- 29
- 31

Finding:

License wording is understandable, but some clauses are compressed. Examples include version/license scope explanation and `publication clarity အတွက်ဖြစ်သည်`. This is lower priority, but may be clearer for non-legal readers if lightly polished.

### `00-preface.md`

Lines to review:

- 3
- 5
- 7
- 9
- 15

Finding:

Several sentences stack many ideas into one paragraph. The author voice is important here, so avoid full rewrite. A light clarity pass may help where long phrases combine personal note, motivation, and technical disclaimer.

### `01-agentic-ai-basics.md`

Lines to review:

- 13
- 15
- 25
- 31
- 35
- 37
- 41

Finding:

This chapter uses strong metaphors such as `ကြက်တူရွေး`, `စာရေးတော်`, `ဦးနှောက်`, and `လက်`. Some lines combine metaphor and technical explanation in one sentence. These may need clarification so beginners do not miss the exact technical meaning.

### `02-agent-vs-workflow-vs-automation.md`

Lines to review:

- 7
- 9
- 13
- 15
- 19
- 23

Finding:

Train/ship/workflow metaphors are useful, but some paragraphs combine metaphor, definition, and warning together. The key distinction between automation, workflow, and agent may benefit from clearer action ordering.

### `03-llm-tool-calling-function-calling.md`

Lines to review:

- 7
- 9
- 13
- 17
- 45

Finding:

Tool-calling explanation uses `စာ`, `အမိန့်စာ`, `လက်`, and `စာချုပ်` metaphors. It is mostly clear, but a few lines may need clearer object/action ordering, especially where model output, runtime action, and security risk are discussed together.

### `04-agent-loop.md`

Lines to review:

- 7
- 9
- 13
- 31
- 49

Finding:

Agent Loop explanation has issue-8-like compressed metaphor phrases around `စာရေးတော်` becoming `ပြဿနာ ဖြေရှင်းသူ`. Worth checking whether beginner readers can follow the transition from loop mechanics to reasoning behavior.

### `05-agent-harness.md`

Lines to review:

- 5
- 7
- 9
- 13
- 15

Finding:

High priority. Harness is abstract, and many sentences use compact `ဘာကို... ဘယ်လို... ဘယ်အချိန်...` structures. Meaning is correct, but readers may need clearer separation between permission, memory, tool access, stop condition, and human approval.

### `06-mcp-skill-subagent.md`

Lines to review:

- 5
- 21
- 23
- 25
- 27

Finding:

Besides the fixed issue #8 line, this chapter still has compressed MCP/Skill/Sub-agent distinction lines. Since this chapter introduces three new terms, clarity matters more than density.

### `07-context-engineering-memory-rag.md`

Finding:

High priority. Context, Memory, and RAG are abstract concepts. Several lines combine metaphor, technical term, and warning in one sentence. A reader may understand each word but still miss the relationship between them.

Recommended review style:

- Check lines that define `Context`.
- Check lines that explain `Memory`.
- Check lines that distinguish `RAG` from normal model answering.
- Check warning lines about stale or wrong retrieved context.

### `08-planner-worker-verifier.md`

Finding:

Planner/Worker/Verifier roles are conceptually clear, but role boundaries may need simpler wording where multiple agents are compared in the same sentence.

Recommended review style:

- Look for lines where Planner, Worker, and Verifier appear together.
- Split role definition from warning if the sentence feels dense.

### `09-tool-broker-permission-mutation-scope.md`

Finding:

Permission and mutation wording is technical and compact. Similar to issue #8, the correct terms are present, but the relationship between tool broker, permission, and mutation scope may need clearer phrasing.

Recommended review style:

- Look for lines containing `scope`, `permission`, `mutation`, and `Tool Broker`.
- Prefer concrete phrasing like "ဘာကို ဖတ်ခွင့်ရှိလဲ" and "ဘာကို ပြောင်းခွင့်ရှိလဲ".

### `10-observability-trajectory-reflection.md`

Finding:

Observability, Trajectory, and Reflection are hard terms. Some explanations may need clearer Burmese+English phrasing so readers do not confuse log/history/reflection with the same thing.

Recommended review style:

- Check lines defining `Trajectory`.
- Check lines explaining why logs are not enough.
- Check lines distinguishing Reflection from retry.

### `11-safety-sandbox-prompt-injection-tool-output.md`

Lines to review:

- 5
- 7
- 21 and nearby lines

Finding:

High priority. Security chapter has many compressed sentences where `Tool output`, `instruction`, `untrusted`, and `context` appear together. Since misunderstanding safety can be risky, this chapter should get a careful clarity pass.

### `12-p2-zero-trust-multi-agent-bridge.md`

Lines to review:

- 17
- 19
- 21
- 25
- 27

Finding:

High priority. Hidden-room/guest/bridge metaphor is strong, but line 21 especially maps many roles in one paragraph. The metaphor may need clearer step-by-step explanation.

### `13-travis2-controlled-runtime.md`

Lines to review:

- 4
- 7
- 10
- 17 and nearby lines

Finding:

High priority. Controlled runtime explanation is technical and has many `X သည် Y ကို Z လုပ်သည်` style lines. Needs careful clarity pass around generated code, sandbox, runtime control, and policy signal.

### `14-browsersurfer-browser-tool-agent-security.md`

Lines to review:

- 4
- 7
- 10
- 13
- 17 and nearby lines

Finding:

High priority. Browser-as-city metaphor is useful but dense. Several lines may need clarification around trusted/untrusted page content, browser action risk, and session state.

### `15-appv22-emerging-runtime-recovery-lab.md`

Lines to review:

- 4
- 7
- 10
- 13
- 15 and nearby lines

Finding:

High priority. This chapter has many technical caveats and source relationship notes. Sentences about Pi, Hermes, OpenClaw, runtime recovery, and prototype status should stay cautious but may need clearer ordering.

### `16-devops-agent-thinking.md`

Lines to review:

- 5
- 7
- 9
- 11
- 15
- 295
- 297

Finding:

High priority. DevOps safety wording is important. Lines mixing `Terraform`, `Cloud`, `read-only`, `mutation`, `approval`, and `audit log` should be clarified carefully because wrong interpretation could be dangerous.

### `17-mini-labs.md`

Lines to review:

- 5
- 13
- 105
- 270
- 338
- 340

Finding:

Lab instruction wording sometimes compresses action and reason. Line 13 is similar to issue #8: `Build သည်...`, `Fix သည်...`, `Reflect သည်...`. Meaning is good, but the phrasing may be more natural if each role is explained as an action.

### `18-myanmar-developer-roadmap.md`

Lines to review:

- 5
- 7
- 11
- 13
- 17
- 23
- 25
- 31
- 35
- 83

Finding:

High priority. Roadmap has many compact guidance lines. Line 25 is especially similar to issue #8:

```text
Loop သည်အလုပ်လုပ်စေသည်။ Harness သည်အလုပ်ကိုဘောင်ထဲတွင်ထားသည်။
```

The meaning is good, but wording can be more natural and clearer for beginner readers.

### `19-references.md`

Lines to review:

- 3
- 5
- 20
- 33
- 41
- 67

Finding:

Mostly minor. Reference/source explanation can be clearer where repo evidence, source map, and license notes are compressed.

## Highest-priority Chapters

Recommended order for issue-style review:

1. `05-agent-harness.md`
2. `07-context-engineering-memory-rag.md`
3. `11-safety-sandbox-prompt-injection-tool-output.md`
4. `12-p2-zero-trust-multi-agent-bridge.md`
5. `13-travis2-controlled-runtime.md`
6. `14-browsersurfer-browser-tool-agent-security.md`
7. `15-appv22-emerging-runtime-recovery-lab.md`
8. `16-devops-agent-thinking.md`
9. `18-myanmar-developer-roadmap.md`

## Suggested Issue Template Wording

Use this if opening GitHub issues:

```text
Title:
Chapter clarity pass: issue #8 style wording review in <chapter>

Description:
This chapter may contain issue #8-like wording problems: the idea is present, but some Burmese technical phrases are compressed or word order may make the sentence less clear for beginner readers.

Please keep author voice intact. Do not rewrite the full chapter. Suggest small line-level improvements only.

Focus:
- unclear subject/action/object ordering
- compressed Burmese+English technical explanation
- metaphors that need one extra clarifying phrase
- risky technical wording where misunderstanding matters
```

## Editing Rule If Fixing Later

When fixing later, avoid mass rewriting.

Good fix style:

```text
Before: လက်စွဲစာအုပ်သည်လုပ်နည်းပြသည်။
After: လက်စွဲစာအုပ်သည် နည်းပြ လုပ်ပေးသည်။
```

Principle:

- Keep the author voice.
- Add natural spacing where it helps.
- Reorder words only when the meaning is muddy.
- Prefer small line-level fixes.
- Avoid making Burmese too formal or dictionary-like.
