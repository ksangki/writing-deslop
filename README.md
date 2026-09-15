# AI Writing Deslop - AI 글쓰기 패턴 교정기

[![Claude Code Skill](https://img.shields.io/badge/Claude_Code-Skill-blue?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cGF0aCBkPSJNMTIgMkM2LjQ4IDIgMiA2LjQ4IDIgMTJzNC40OCAxMCAxMCAxMCAxMC00LjQ4IDEwLTEwUzE3LjUyIDIgMTIgMnoiIGZpbGw9IiNmZmYiLz48L3N2Zz4=)](https://docs.anthropic.com/en/docs/claude-code)

A Claude Code skill that detects and fixes 11 common AI-generated writing patterns that make text feel robotic and unnatural. Works with both Korean and English prose. Includes a **Meeting Minutes Profile** for cleaning up STT/summarizer-generated 회의록.

AI 글쓰기에서 자주 나타나는 11가지 '슬롭' 패턴을 감지하고 자연스러운 문장으로 교정하는 Claude Code 스킬입니다. 한국어와 영어 모두 지원하며, STT·요약기가 생성한 회의록을 정리하는 **회의록 프로파일**도 포함합니다.

---

## Why this exists

AI writing tools produce text that follows predictable dramatic patterns - rhetorical buildups, fake contrarianism, one-sentence-per-line drama. Individually they seem fine. But when every LinkedIn post, blog, and newsletter uses the same tricks, readers develop an instinct for "this was written by AI" and tune out.

This skill catches those patterns and suggests rewrites that keep the original insight but lose the robotic packaging.

Inspired by [this Reddit post](https://www.reddit.com/r/ChatGPT/comments/1kqe0ph/writing_formats_ruined_by_chatgpt/) documenting writing formats ruined by ChatGPT.

> **회의록·녹취 정리라면 11패턴보다 [Meeting Minutes Profile](#meeting-minutes-profile-회의록-프로파일)을 먼저 보십시오.**
> 실제로 걸리는 것은 대부분 그쪽입니다. 한 건의 실사용에서 산문 183블록 기준 11패턴은 1건(그마저 발언 인용이라 대상 제외),
> MM 규칙은 5건이 나왔습니다.

---

## The 11 Patterns

### 1. Hostage Negotiation Reveal (인질 협상식 반전 공개)

Asking rhetorical questions one by one before revealing a simple answer.

| Before | After |
|--------|-------|
| What's the #1 skill for 2024? Is it coding? No. Design? No. It's prompt engineering. | Prompt engineering has become the most important skill in 2024 - more than coding or design. |
| 마케팅에서 가장 중요한 건 뭘까요? 광고? 아닙니다. 브랜딩? 그것도 아닙니다. 바로 '고객 이해'입니다. | 마케팅에서 가장 중요한 건 고객 이해다. 광고나 브랜딩보다 먼저, 고객이 뭘 원하는지 파악하는 게 우선이다. |

### 2. "It's Not X. It's Y." (X가 아니다. Y다.)

Dramatic negation-then-reveal for a straightforward point.

| Before | After |
|--------|-------|
| This isn't a tool. It's a weapon. | Used well, this tool becomes a serious competitive advantage. |
| 이건 도구가 아니다. 무기다. | 이 도구는 제대로 쓰면 강력한 경쟁력이 된다. |

### 3. "You Don't Need X. You Need Y." (필요한 건 X가 아니다. Y다.)

Prescriptive negation telling readers what they need. Condescending tone.

| Before | After |
|--------|-------|
| You don't need more data. You need better judgment. | Data is abundant. What separates winners is the quality of decisions made from that data. |
| 당신에게 필요한 건 더 많은 정보가 아닙니다. 더 나은 판단력입니다. | 정보는 넘치는 시대다. 차이를 만드는 건 그 정보로 무엇을 결정하느냐다. |

### 4. One Sentence Per Line (원룸 문장)

Every sentence gets its own paragraph for fake drama.

| Before | After |
|--------|-------|
| AI is changing everything.<br><br>Your job.<br><br>Your career.<br><br>Your future.<br><br>And you're not ready. | AI is reshaping jobs, careers, and futures faster than most people are preparing for. |
| AI가 바꾸고 있다.<br><br>모든 것을.<br><br>당신의 일도.<br><br>당신의 커리어도. | AI가 일과 커리어를 빠르게 바꾸고 있다. 준비하지 않으면 뒤처질 수밖에 없다. |

### 5. Fake Profound Reversal (가짜 심오한 반전)

"X isn't about X-ing. It's about Y-ing." Redefining something obvious as if revealing a hidden truth.

| Before | After |
|--------|-------|
| Leadership isn't about leading. It's about listening. | Good leaders spend more time listening than directing. |
| 리더십은 이끄는 게 아니다. 경청하는 것이다. | 좋은 리더는 말하기보다 듣기에 시간을 더 쓴다. |

### 6. Good. Better. Best. (좋다. 더 좋다. 최고다.)

Three-tier escalation building to a climax.

| Before | After |
|--------|-------|
| Good marketers create content. Great marketers create systems. The best marketers create cultures. | The best marketers go beyond individual content pieces - they build repeatable systems and eventually shape the culture around their brand. |
| ChatGPT는 좋다. Claude는 더 좋다. 둘 다 쓰는 게 최고다. | ChatGPT와 Claude는 각각 장단점이 있어서, 상황에 맞게 골라 쓰는 게 가장 효과적이다. |

### 7. "But the best part?" (그런데 가장 좋은 점은?)

Teasing with setup before a punchline. Artificial suspense.

| Before | After |
|--------|-------|
| It's free. It's fast. But the best part? It works offline. | It's free, fast, and works offline. |
| 이 도구는 무료입니다. 설치도 필요 없습니다. 그런데 가장 좋은 점은? 한국어를 완벽하게 지원합니다. | 이 도구는 무료에 설치 불필요, 게다가 한국어까지 완벽 지원한다. |

### 8. "The truth is?" (진실은?)

Using "truth" as a dramatic device for an opinion or mundane fact.

| Before | After |
|--------|-------|
| Everyone fears AI. But here's the truth: AI isn't your enemy. It's your partner. | AI works best as a productivity multiplier, not a replacement - the people using it well are getting more done, not getting replaced. |
| 많은 사람이 AI를 두려워합니다. 하지만 진실은? AI는 당신의 적이 아니라 파트너입니다. | AI를 두려워할 필요 없다. 잘 활용하면 일을 훨씬 효율적으로 할 수 있는 도구다. |

### 9. Fake Contrarianism (가짜 반골주의)

"Everyone says X. They're wrong." Pretends to challenge consensus but delivers conventional wisdom.

| Before | After |
|--------|-------|
| Everyone says you need to learn to code. They're wrong. You need to learn to ask the right questions. | Coding matters, but in the AI era, knowing how to ask precise questions is becoming the more valuable skill. |
| 모두가 AI 시대엔 코딩을 배워야 한다고 합니다. 틀렸습니다. 진짜 배워야 할 건 질문하는 법입니다. | AI 시대에 코딩도 중요하지만, 좋은 질문을 던지는 능력이 더 핵심적인 경쟁력이 되고 있다. |

### 10. "Most people do X. Successful people do Y." (대부분의 사람들은 X. 성공한 사람들은 Y.)

False dichotomy between ordinary and successful people.

| Before | After |
|--------|-------|
| Most people consume content. Successful people create content. | Creating content teaches you far more than consuming it - the act of writing forces clarity that reading alone never does. |
| 대부분의 사람들은 뉴스를 소비합니다. 성공한 사람들은 뉴스를 만듭니다. | 뉴스를 읽기만 하는 것과 직접 콘텐츠를 만드는 것은 완전히 다른 학습 효과를 준다. |

### 11. "Stop X. Start Y." (X를 멈추고 Y를 시작하라)

Imperative stop/start commands. Bossy and oversimplified.

| Before | After |
|--------|-------|
| Stop chasing perfection. Start shipping. | Waiting for perfection keeps you stuck. Shipping something imperfect and iterating gets you further, faster. |
| 완벽을 추구하는 것을 멈춰라. 실행을 시작하라. | 완벽하게 준비되길 기다리면 아무것도 시작할 수 없다. 일단 해보면서 다듬는 게 낫다. |

---

## Meeting Minutes Profile (회의록 프로파일)

The 11 patterns rarely fire on meeting minutes - 개조식 bullets and tables are the correct register there. But STT transcripts run through a summarizer produce a different kind of slop: "Speaker N" labels, a reporting verb on every sentence, bold on every other phrase, and mis-heard proper nouns. The profile activates when the input looks like a 회의록, 회의 요약, 녹취 정리, or summarizer output.

회의록에는 11가지 패턴이 거의 걸리지 않습니다. 대신 요약기 출력 특유의 슬롭이 있어서, 이를 다루는 7가지 규칙(MM-1 ~ MM-7)을 별도로 적용합니다.

### What NOT to touch

- **Quoted speech is evidence, not slop.** Patterns inside a participant's actual remark stay as-is. The 11 patterns apply to the writer's voice, not the speaker's.
- **Bullets and tables are not Pattern 4.** 개조식 is the correct register for minutes.
- **Numbers, IDs, `[확인]` markers, dates** are never paraphrased away.

### The 7 rules

| # | Rule | What it does |
|---|------|--------------|
| MM-1 | Speaker labels → organization/role | Replace "Speaker 1/3/5" with the organization or role (정책 측 / 플랫폼 측 / 회의 주재자 ...). Uncertain mappings get `[확인]`. Never invent a real name. |
| MM-2 | Reporting-verb tail | Drop 강조했습니다 / 공유되었습니다 / ~하기로 했습니다 filler and convert to 개조식 (~함 / ~필요 / ~합의 / ~미결). |
| MM-3 | Rationale boilerplate | Move "(근거: ...)" decisions into a table with a short 비고 column; drop the rationale if the body already states it. |
| MM-4 | Emphasis inflation | **At most one bold per paragraph** — keep the phrase carrying the point, plain the rest. Do not strip wholesale; the fix is to choose, not delete. Parallel items (① / ②, A vs B) get no bold at all. Promote bold-only pseudo-headers to `###`. |
| MM-5 | STT mis-recognition | Do not silently "correct" mis-heard proper nouns (사번제→사본, 하이밸류→하이브리드 ...). Mark with `[확인]` and collect in a 「용어 · 원문 확인 필요」 table. **The marker and the table are one unit** — inline `[확인]` count must equal table rows. |
| MM-6 | Fixed skeleton | Normalize to a fixed order: 회의 성격 → 정리 기준 → 안건별 섹션 → 결정 사항 → 미결 사항 → 액션 아이템 → 향후 일정 → 용어 확인 → 정리 노트. |
| MM-7 | 정리 노트 gets the hardest scan | The writer's analysis is the only free-prose block, so the 11 patterns actually live there. Lead with the conclusion, match the body's 종결, no bold. |

### MM-2 example

| Before | After |
|--------|-------|
| 참석자들은 '사번 부여'라는 표현이 특정 부서에 국한될 수 있다는 점에 동의하고, 더 포괄적인 '에이전트의 정의'로 용어를 변경하기로 합의했습니다. | '사번 부여'는 특정 부서 일로 읽힐 수 있음 → 「에이전트의 정의」로 용어 변경 합의 |

### Output

In 회의록 mode the per-pattern report is skipped unless you pass `--check`. You get the full re-formatted minutes as a `.md` file, followed by a 3-5 line change summary: what was restructured, what was left untouched (quotes, numbers), and which `[확인]` items need the author's eyes.

---

## Installation

### Claude Code (recommended)

```bash
# From the repo
claude install-skill /path/to/writing-deslop

# Or copy SKILL.md to your project
cp SKILL.md your-project/.claude/skills/writing-deslop/SKILL.md
```

### Manual

Copy `SKILL.md` into your Claude Code project:

```
your-project/
  .claude/
    skills/
      writing-deslop/
        SKILL.md
```

---

## Usage

### In Claude Code

```
# Rewrite mode - detect and fix
> deslop this text: "What's the secret to productivity? Tools? No. Habits? No. It's focus."

# Check mode - report only
> deslop --check: "모두가 AI를 배워야 한다고 합니다. 틀렸습니다."

# Natural language triggers also work
> 이거 AI가 쓴 것 같아. 교정해줘
> 이 글에서 AI체 좀 빼줘

# Meeting minutes mode - applies MM-1 ~ MM-7
> 회의록 교정: [paste summarizer output]
> 요약기 출력 정리해줘
```

### Trigger keywords

The skill auto-activates on these keywords:
- `deslop`, `anti-slop`, `AI 글 교정`, `AI체 교정`, `슬롭 제거`
- `이거 AI가 쓴 것 같아`, `AI 냄새 나`, `로봇 같아`
- `회의록 교정`, `회의록 deslop`, `요약기 출력 정리해줘` (activates the Meeting Minutes Profile)

---

## Design Principles

1. **Preserve the insight** - The original author had a real point. Keep it. Remove only the AI packaging.
2. **Merge fragmented sentences** - Combine one-liners back into flowing paragraphs.
3. **Remove artificial suspense** - State the point directly. Let the content create interest, not the formatting.
4. **Keep the register** - If the original is casual, keep it casual. If formal, stay formal.
5. **Don't over-correct** - Not every short sentence is a slop pattern. Use judgment.

---

## Credits

- Patterns documented in [this Reddit r/ChatGPT post](https://www.reddit.com/r/ChatGPT/comments/1kqe0ph/writing_formats_ruined_by_chatgpt/) about writing formats ruined by AI
- Korean adaptations and bilingual examples by [@marketer.ai.seulki](https://www.instagram.com/marketer.ai.seulki/)

---

## License

MIT
