---
name: writing-deslop
description: Detect and fix 11 AI writing slop patterns in Korean/English prose, plus a meeting-minutes (회의록) profile for STT/summarizer output
---

# AI Writing Deslop

## Purpose

Detect and rewrite 11 common AI-generated writing patterns that make text feel robotic. This skill targets PROSE (blog posts, newsletters, LinkedIn posts, card news captions, social media copy) - not code.

These patterns originate from a viral Reddit r/ChatGPT post documenting writing formats ruined by AI overuse.

## Modes

- **Default (rewrite)**: Detect patterns, show each finding, suggest rewrites, output cleaned text
- **`--check`**: Report-only mode - list detected patterns without rewriting

## Usage

When the user says any of:
- "deslop", "anti-slop", "AI 글 교정", "AI체 교정", "슬롭 제거"
- "이거 AI가 쓴 것 같아", "AI 냄새 나", "로봇 같아"
- "회의록 교정", "회의록 deslop", "요약기 출력 정리해줘" → apply the **Meeting Minutes Profile** below in addition to the 11 patterns
- Or when reviewing any generated prose before publishing

## The 11 Patterns

### Pattern 1: Hostage Negotiation Reveal (인질 협상식 반전 공개)

Asking rhetorical questions one by one before revealing a simple answer.

**Detection signals:**
- 3+ consecutive question sentences before an answer
- "What if I told you..." / "만약 ~라면 어떨까요?" followed by reveal
- Questions that build suspense for a mundane conclusion

**Korean example (before):**
```
마케팅에서 가장 중요한 건 뭘까요?
광고? 아닙니다.
브랜딩? 그것도 아닙니다.
바로 '고객 이해'입니다.
```

**Rewrite:**
```
마케팅에서 가장 중요한 건 고객 이해다. 광고나 브랜딩보다 먼저, 고객이 뭘 원하는지 파악하는 게 우선이다.
```

**English example (before):**
```
What's the most important skill in 2024?
Is it coding? No.
Is it design? Not quite.
It's prompt engineering.
```

**Rewrite:**
```
Prompt engineering has become the most important skill in 2024 - more than coding or design.
```

---

### Pattern 2: "It's Not X. It's Y." (X가 아니다. Y다.)

Dramatic negation-then-reveal. Creates artificial tension for a straightforward point.

**Detection signals:**
- "X가 아니다" or "X이/가 아닙니다" immediately followed by "Y(이)다" or "Y입니다"
- "It's not X. It's Y." or "This isn't about X. It's about Y."
- The negated thing and the revealed thing are closely related concepts

**Korean example (before):**
```
이건 도구가 아니다. 무기다.
```

**Rewrite:**
```
이 도구는 제대로 쓰면 강력한 경쟁력이 된다.
```

**English example (before):**
```
This isn't a tool. It's a weapon.
```

**Rewrite:**
```
Used well, this tool becomes a serious competitive advantage.
```

---

### Pattern 3: "You Don't Need X. You Need Y." (필요한 건 X가 아니다. Y다.)

Prescriptive negation telling readers what they need. Condescending tone.

**Detection signals:**
- "필요한 건 X가 아니라 Y" or "X가 필요한 게 아니라 Y가 필요하다"
- "You don't need X. You need Y." or "What you really need isn't X - it's Y."
- Prescribing what the reader should want

**Korean example (before):**
```
당신에게 필요한 건 더 많은 정보가 아닙니다. 더 나은 판단력입니다.
```

**Rewrite:**
```
정보는 넘치는 시대다. 차이를 만드는 건 그 정보로 무엇을 결정하느냐다.
```

**English example (before):**
```
You don't need more data. You need better judgment.
```

**Rewrite:**
```
Data is abundant. What separates winners is the quality of decisions made from that data.
```

---

### Pattern 4: One Sentence Per Line (원룸 문장)

Every sentence gets its own paragraph for fake drama. Line breaks used for pacing instead of substance.

**Detection signals:**
- 5+ consecutive one-sentence paragraphs (each under 20 words)
- Short declarative sentences stacked with blank lines between them
- No logical reason for the separation (not a list, not dialogue)

**Korean example (before):**
```
AI가 바꾸고 있다.

모든 것을.

당신의 일도.

당신의 커리어도.

준비하지 않으면 뒤처진다.
```

**Rewrite:**
```
AI가 일과 커리어를 빠르게 바꾸고 있다. 준비하지 않으면 뒤처질 수밖에 없다.
```

**English example (before):**
```
AI is changing everything.

Your job.

Your career.

Your future.

And you're not ready.
```

**Rewrite:**
```
AI is reshaping jobs, careers, and futures faster than most people are preparing for.
```

---

### Pattern 5: Fake Profound Reversal (가짜 심오한 반전)

"X isn't about X-ing. It's about Y-ing." Pretends to reveal a hidden truth about something obvious.

**Detection signals:**
- "X는 X하는 게 아니다. Y하는 것이다" pattern
- "X isn't about X-ing. It's about Y-ing."
- Redefining something into a closely related concept as if it is a revelation

**Korean example (before):**
```
리더십은 이끄는 게 아니다. 경청하는 것이다.
```

**Rewrite:**
```
좋은 리더는 말하기보다 듣기에 시간을 더 쓴다.
```

**English example (before):**
```
Leadership isn't about leading. It's about listening.
```

**Rewrite:**
```
Good leaders spend more time listening than directing.
```

---

### Pattern 6: Good. Better. Best. (좋다. 더 좋다. 최고다.)

Three-tier escalation building to a climax. Often with single-word or short-phrase tiers.

**Detection signals:**
- Three short statements escalating in intensity
- "Good. Better. Best." or "X는 좋다. Y는 더 좋다. Z는 최고다."
- Tiered comparison with dramatic build-up

**Korean example (before):**
```
ChatGPT는 좋다.
Claude는 더 좋다.
둘 다 쓰는 게 최고다.
```

**Rewrite:**
```
ChatGPT와 Claude는 각각 장단점이 있어서, 상황에 맞게 골라 쓰는 게 가장 효과적이다.
```

**English example (before):**
```
Good marketers create content.
Great marketers create systems.
The best marketers create cultures.
```

**Rewrite:**
```
The best marketers go beyond individual content pieces - they build repeatable systems and eventually shape the culture around their brand.
```

---

### Pattern 7: "But the best part?" (그런데 가장 좋은 점은?)

Teasing with setup before a punchline. Creates artificial suspense.

**Detection signals:**
- "그런데 가장 좋은 점은?" or "근데 진짜 좋은 건?"
- "But the best part?" or "Want to know the best part?" or "But here's the kicker:"
- A question used as a dramatic bridge between setup and payoff

**Korean example (before):**
```
이 도구는 무료입니다. 설치도 필요 없습니다. 그런데 가장 좋은 점은? 한국어를 완벽하게 지원합니다.
```

**Rewrite:**
```
이 도구는 무료에 설치 불필요, 게다가 한국어까지 완벽 지원한다.
```

**English example (before):**
```
It's free. It's fast. But the best part? It works offline.
```

**Rewrite:**
```
It's free, fast, and works offline.
```

---

### Pattern 8: "The truth is?" (진실은?)

Using "truth" as a dramatic device to introduce an opinion or mundane fact.

**Detection signals:**
- "진실은" or "진짜는" or "사실은 이렇습니다"
- "The truth is" or "Here's the truth:" or "The real truth?"
- Framing a subjective opinion as a hidden truth being revealed

**Korean example (before):**
```
많은 사람이 AI를 두려워합니다. 하지만 진실은? AI는 당신의 적이 아니라 파트너입니다.
```

**Rewrite:**
```
AI를 두려워할 필요 없다. 잘 활용하면 일을 훨씬 효율적으로 할 수 있는 도구다.
```

**English example (before):**
```
Everyone fears AI. But here's the truth: AI isn't your enemy. It's your partner.
```

**Rewrite:**
```
AI works best as a productivity multiplier, not a replacement - the people using it well are getting more done, not getting replaced.
```

---

### Pattern 9: Fake Contrarianism (가짜 반골주의)

"Everyone says X. They're wrong." Pretends to challenge consensus but delivers conventional wisdom.

**Detection signals:**
- "모두가 X라고 한다. 틀렸다." or "다들 X라고 하지만"
- "Everyone says X. They're wrong." or "Conventional wisdom says X. I disagree."
- The "contrarian" view is actually mainstream or obvious

**Korean example (before):**
```
모두가 AI 시대엔 코딩을 배워야 한다고 합니다. 틀렸습니다. 진짜 배워야 할 건 질문하는 법입니다.
```

**Rewrite:**
```
AI 시대에 코딩도 중요하지만, 좋은 질문을 던지는 능력이 더 핵심적인 경쟁력이 되고 있다.
```

**English example (before):**
```
Everyone says you need to learn to code. They're wrong. You need to learn to ask the right questions.
```

**Rewrite:**
```
Coding matters, but in the AI era, knowing how to ask precise questions is becoming the more valuable skill.
```

---

### Pattern 10: "Most people do X. Successful people do Y." (대부분의 사람들은 X. 성공한 사람들은 Y.)

False dichotomy between ordinary and successful people. Flatters the reader.

**Detection signals:**
- "대부분의 사람들은 X. 성공한 사람들은 Y." or "보통 사람들은 / 상위 1%는"
- "Most people X. Successful people Y." or "Average people X. Top performers Y."
- Binary split between "losers" and "winners" with reader implicitly on the winner side

**Korean example (before):**
```
대부분의 사람들은 뉴스를 소비합니다. 성공한 사람들은 뉴스를 만듭니다.
```

**Rewrite:**
```
뉴스를 읽기만 하는 것과 직접 콘텐츠를 만드는 것은 완전히 다른 학습 효과를 준다.
```

**English example (before):**
```
Most people consume content. Successful people create content.
```

**Rewrite:**
```
Creating content teaches you far more than consuming it - the act of writing forces clarity that reading alone never does.
```

---

### Pattern 11: "Stop X. Start Y." (X를 멈추고 Y를 시작하라)

Imperative stop/start commands. Bossy and oversimplified.

**Detection signals:**
- "X를 멈춰라" or "X 그만하고 Y 시작해라" or "X를 버려라. Y를 택해라."
- "Stop X. Start Y." or "Stop doing X and start doing Y."
- Imperative commands telling the reader to abandon one behavior for another

**Korean example (before):**
```
완벽을 추구하는 것을 멈춰라. 실행을 시작하라.
```

**Rewrite:**
```
완벽하게 준비되길 기다리면 아무것도 시작할 수 없다. 일단 해보면서 다듬는 게 낫다.
```

**English example (before):**
```
Stop chasing perfection. Start shipping.
```

**Rewrite:**
```
Waiting for perfection keeps you stuck. Shipping something imperfect and iterating gets you further, faster.
```

---

## Execution Protocol

### Step 1: Receive Text

Accept the full text to analyze. Identify the language (Korean, English, or mixed).

### Step 2: Scan for All 11 Patterns

Go through the text systematically checking for each pattern. For each detection:
1. Name the pattern (number + name)
2. Quote the exact offending passage
3. Explain why it triggers the pattern

### Step 3: Generate Rewrites (skip if `--check` mode)

For each detected pattern:
1. Rewrite the passage to convey the same information naturally
2. Preserve the author's actual insight - just remove the AI formatting trick
3. Match the surrounding tone and register (formal/informal, 존대/반말)

### Step 4: Output

**`--check` mode output:**
```
## AI Slop Detection Report

Found: N patterns in M passages

### Pattern X: [Name]
> [quoted passage]
Reason: [why this triggers the pattern]

### Pattern Y: [Name]
> [quoted passage]
Reason: [why this triggers the pattern]

---
Total: N slop patterns detected
```

**Default (rewrite) mode output:**
```
## AI Slop Detection & Rewrite Report

Found: N patterns in M passages

### Pattern X: [Name]
**Before:**
> [quoted passage]

**After:**
> [rewritten passage]

**Why:** [brief explanation of the change]

---

## Cleaned Text

[Full text with all rewrites applied]

---
Summary: Rewrote M passages across N pattern types.
```

---

## Meeting Minutes Profile (회의록 프로파일)

The 11 patterns rarely fire on meeting minutes (개조식 bullets, tables), but STT transcripts run through a summarizer produce a different kind of slop. Apply this profile whenever the input is a 회의록, 회의 요약, 녹취 정리, or summarizer output (signals: "Speaker N" labels, "Key Decisions / Action Items / Open Questions" template headers, "~했습니다/~되었습니다" on every sentence).

### What NOT to touch

- **Quoted speech is evidence, not slop.** "X가 아니라 Y다", "모두가 X라고 하지만" etc. inside a participant's actual remark (quoted or clearly attributed) stays as-is. Pattern 2/5/9 apply to the *writer's* voice, not the *speaker's*.
- **Bullets and tables are not Pattern 4.** 개조식 is the correct register for minutes.
- **Numbers, IDs, `[확인]` markers, dates** — never paraphrase away.

### MM-1. Speaker labels → organization/role

Summarizer output attributes by "Speaker 1/3/5". Replace with the organization or role (정책 측 / 플랫폼 측 / 에이전트 OS 측 / 회의 주재자 / 2-4 과제 측). If the mapping is uncertain, keep the role guess and append `[확인]`; list the Speaker→role mapping in the 용어 확인 table. Never invent a real name.

### MM-2. Reporting-verb tail

Every sentence ending in 강조했습니다 / 공유되었습니다 / 정리되었습니다 / 지적했습니다 / ~하기로 했습니다 / 판단하여 추후 논의하기로 했습니다 is summarizer filler. Convert to 개조식: drop the reporting verb, keep the content, end with a noun or 명사형 (~함 / ~필요 / ~합의 / ~미결).

**Before:** 참석자들은 '사번 부여'라는 표현이 특정 부서에 국한될 수 있다는 점에 동의하고, 더 포괄적인 '에이전트의 정의'로 용어를 변경하기로 합의했습니다.
**After:** '사번 부여'는 특정 부서 일로 읽힐 수 있음 → 「에이전트의 정의」로 용어 변경 합의

### MM-3. Rationale boilerplate

"(근거: … 때문입니다)" appended to every decision is a template artifact. Move decisions into a table with a short 비고 column; drop the rationale if the body already states it.

### MM-4. Emphasis inflation

Bold on every other phrase (or bold used as pseudo-headers) is the minutes equivalent of Pattern 4 — fake drama via formatting. When everything is bold, nothing is.

**Rule: at most one bold per paragraph.** Keep the phrase that carries the paragraph's point — the decision reached, the number that changes a judgment, or the term being defined. Everything else goes plain. A paragraph whose point is already clear from its first clause needs no bold at all.

Do not strip bold wholesale. Stripping everything flattens the text and forces the reader to re-derive the point from scratch; the fix is to choose, not to delete.

- Bold-only lines acting as section labels → promote to `###` headers
- Tables and 개조식 bullets keep their bold — that is the correct register, not prose
- Keep 「」 for defined terms, and do not bold them on top of the brackets
- Quoted remarks: bold at most the clause the speaker actually leaned on
- **Parallel items get no bold at all.** Two or more bolds that are enumerated or
  balanced options (① / ②, A vs B, 채찍 vs 당근) → drop every one of them. Bolding
  one side of a balanced pair invents weight the text does not have, and bolding both
  is the inflation this rule exists to stop. The enumeration itself already carries
  the structure.

**Before** (5 bolds in one paragraph)
```
제기된 딜레마: **자체 모델을 쓰는 조직**은 좋은 성과를 내면서도 **집계에서 빠짐**.
**열심히 했는데 빠져버리는 구조**. 따라서 **목적이 비용 타이트닝인지 퍼포먼스 체크인지**를
정해야 하며, 실제로는 **둘 다** 봐야 함.
```

**After** (1)
```
제기된 딜레마: 자체 모델을 쓰는 조직은 좋은 성과를 내면서도 집계에서 빠짐.
따라서 **목적이 비용 타이트닝인지 퍼포먼스 체크인지**를 정해야 하며, 실제로는 둘 다 봐야 함.
```

The kept bold is the one that states what must be decided. The rest were description already carried by the sentence.

### MM-5. STT mis-recognition

Unfamiliar proper nouns in summarizer output are often mis-heard (사번제→사본/사법, 하이밸류→하이브리드, 폴라리스→플라디스, 토큰→ROT). Do not silently "correct" them. Mark inline with `[확인]` and collect them in a 「용어 · 원문 확인 필요」 table (표기 / 추정 / 사유). Also flag numbers that differ between transcript versions.

**The marker and the table are one unit.** An inline `[확인]` with no row to land on is
worse than no marker at all — it signals doubt without saying about what. So:

- Trimming the minutes? If the 「용어 · 원문 확인 필요」 table goes, every inline `[확인]`
  goes with it — either resolved into the sentence or deleted.
- Keeping only some rows? Keep exactly the rows the surviving markers point to. Two live
  markers need a two-row table, not the full original list.
- Before publishing, count them: inline `[확인]` occurrences must equal table rows.

### MM-6. Fixed skeleton

Normalize to this order so minutes across meetings line up:

1. 회의 성격 (2–3 lines: what, why, duration/date)
2. `[!warning] 정리 기준` — attribution rule, `[확인]` convention, date if inferred
3. Numbered topic sections, each 개조식; sub-blocks as `###`
4. 결정 사항 — table (# / 결정 / 비고)
5. 미결 사항 — table (# / 항목 / 내용)
6. 액션 아이템 — table (담당 / 내용 / 기한)
7. 향후 일정 or 기타 공유
8. 용어 · 원문 확인 필요 — table
9. `[!info] 정리 노트` — writer's own analysis, clearly labeled as not-a-remark

### MM-7. 정리 노트 (writer's analysis) is where the 11 patterns actually live

This is the only free-prose block, so scan it hardest. Typical hits: Pattern 7 ("그런데 이번 회의에서 사실상 답이 나왔습니다" — setup→reveal), Pattern 8 ("~이 정확한 진단입니다" — evaluative flourish), Pattern 2/5 in the writer's framing. Rewrite to lead with the conclusion, in the same 개조식-compatible 종결 (~다) as the body, no bold.

### Output for 회의록 mode

Skip the per-pattern report unless the user asks for `--check`. Deliver the full re-formatted minutes as a `.md` file, then a 3–5 line change summary: what was restructured, what was left untouched (quotes, numbers), and which `[확인]` items need the author's eyes.

## Rewrite Principles

1. **Preserve the insight** - The original author had a real point. Keep it. Remove only the AI packaging.
2. **Merge fragmented sentences** - Combine one-liners back into flowing paragraphs.
3. **Remove artificial suspense** - State the point directly. Let the content create interest, not the formatting.
4. **Keep the register** - If the original is casual, keep it casual. If formal, stay formal.
5. **Don't over-correct** - Not every short sentence is Pattern 4. Not every question is Pattern 1. Use judgment.
6. **Korean-specific** - Respect 존대말/반말 choice. Don't switch between them.

## Edge Cases

- **Intentional rhetorical questions** (e.g., essay openers in academic writing): Leave alone if genuinely rhetorical and not followed by a reveal pattern.
- **Lists**: Numbered/bulleted lists are not Pattern 4 even if each item is short.
- **Dialogue/quotes**: Patterns inside quoted speech from real people should be flagged but not rewritten. In meeting minutes, do not even flag them — see Meeting Minutes Profile.
- **Meeting minutes / summarizer output**: 개조식 bullets, tables, and reporting structure are the correct register. Apply the Meeting Minutes Profile (MM-1 … MM-7) instead of forcing the 11 patterns onto every bullet.
- **Headlines/titles**: Patterns in headlines may be acceptable for engagement. Flag but let the author decide.
- **Mixed patterns**: A single passage can trigger multiple patterns. Report all, but combine into one rewrite.
