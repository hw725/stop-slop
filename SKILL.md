---
name: stop-slop
description: "Remove AI tells from ENGLISH prose - throat-clearing openers, binary contrasts, em dashes, false agency, adverb padding, metronomic rhythm. Trigger on \"영어 자연스럽게\", \"평이한 영어로\", de-slop, humanize, \"sounds like ChatGPT\", or \"AI티 빼줘\"/\"사람이 쓴 것처럼\" when the target text is English. SCOPE LIMITS - non-academic English only. Route Korean text to humanize-korean and 논문·초록 영어 윤문 to academic-english-editing: the no-adverb and no-passive rules strip academic hedging and force first person."
license: MIT
metadata:
  author: Hardik Pandya (https://hvpandya.com)
  version: 1.2.0
  category: writing
  upstream: https://github.com/hardikpandya/stop-slop @ 8da1f030185bdfe8471220585162991eaeb970e9
  cherry_picks: petergyang/no-ai-slop @ 000650b156983f5159695b441477f4e63b25dc85 (MIT) — AUD-20260920-104017-4a029a17
  local_divergence: |
    frontmatter description replaced (upstream trigger "drafting, editing, or reviewing text"
    fired on Korean drafts and academic manuscripts). Body is upstream verbatim.
    2026-08-23 (v1.1.0): humanize-korean 도입으로 한국어 요청을 그쪽으로 넘긴다. 이전에는
    "AI티 빼줘"·"사람이 쓴 것처럼"을 이 스킬이 흡수한 뒤 English only라 거절해 담당이 없었다.
    2026-09-20 (v1.2.0): references/structures.md·phrases.md 끝에 no-ai-slop 체리픽 절을
    붙였다(콜론 반전·faux-insight·-ing 피상 분석·중요성 부풀리기·해석적 메타담화·
    가짜 강동사·동의어 순환·가짜 심오 결말·요약 재진술·형식 슬롭·금지 단어·weasel 출처).
    upstream 원문 절은 그대로이고 추가분은 HTML 주석 아래에 격리돼 있다.
---

# Stop Slop

Eliminate predictable AI writing patterns from prose.

## 적용 범위 (로컬 추가)

**영어 산문 전용이다.** 아래 규칙은 영어의 결을 다루므로 한국어 글에 적용하지 않는다.

**학술 원고에는 쓰지 않는다.** 2026-08-21 A/B 실측에서 두 가지가 확인됐다.

- 「수동태 금지 + 모든 문장에 인간 주어」가 결합해 논문 방법 서술을 1인칭으로 강제한다 (`Machine parsing was abandoned` → `I dropped machine parsing`).
- `references/phrases.md`의 부사 전면 삭제가 학술 hedging(`only`, `routinely`, `approximately`)까지 지워 정확도를 깎는다.

논문·초록·투고 원고의 영어 윤문은 `academic-english-editing`으로 보낸다.

## Core Rules

1. **Cut filler phrases.** Remove throat-clearing openers, emphasis crutches, and all adverbs. See [references/phrases.md](references/phrases.md).

2. **Break formulaic structures.** Avoid binary contrasts, negative listings, dramatic fragmentation, rhetorical setups, false agency. See [references/structures.md](references/structures.md).

3. **Use active voice.** Every sentence needs a human subject doing something. No passive constructions. No inanimate objects performing human actions ("the complaint becomes a fix").

4. **Be specific.** No vague declaratives ("The reasons are structural"). Name the specific thing. No lazy extremes ("every," "always," "never") doing vague work.

5. **Put the reader in the room.** No narrator-from-a-distance voice. "You" beats "People." Specifics beat abstractions.

6. **Vary rhythm.** Mix sentence lengths. Two items beat three. End paragraphs differently. No em dashes.

7. **Trust readers.** State facts directly. Skip softening, justification, hand-holding.

8. **Cut quotables.** If it sounds like a pull-quote, rewrite it.

9. **Name the source.** "Experts agree" and "studies show" are cut or replaced with who said it. See the no-ai-slop cherry-pick sections at the end of [references/phrases.md](references/phrases.md) and [references/structures.md](references/structures.md) (colon reveals, faux-insight setups, `-ing` superficial analysis, importance puffery, metadiscourse, synonym cycling, fake-profound kickers, recap endings, formatting slop).

## Quick Checks

Before delivering prose:

- Any adverbs? Kill them.
- Any passive voice? Find the actor, make them the subject.
- Inanimate thing doing a human verb ("the decision emerges")? Name the person.
- Sentence starts with a Wh- word? Restructure it.
- Any "here's what/this/that" throat-clearing? Cut to the point.
- Any "not X, it's Y" contrasts? State Y directly.
- Three consecutive sentences match length? Break one.
- Paragraph ends with punchy one-liner? Vary it.
- Em-dash anywhere? Remove it.
- Vague declarative ("The implications are significant")? Name the specific implication.
- Narrator-from-a-distance ("Nobody designed this")? Put the reader in the scene.
- Meta-joiners ("The rest of this essay...")? Delete. Let the essay move.
- Colon reveal ("The best part: it learns")? Make it a plain sentence.
- "Experts agree" / "studies show" without a name? Name the source or cut it.
- Trailing "-ing" analysis ("…, highlighting their commitment")? Replace with the concrete consequence.
- Final aphorism or mic-drop line? Delete it and end on the last concrete sentence.

## Scoring

Rate 1-10 on each dimension:

| Dimension | Question |
|-----------|----------|
| Directness | Statements or announcements? |
| Rhythm | Varied or metronomic? |
| Trust | Respects reader intelligence? |
| Authenticity | Sounds human? |
| Density | Anything cuttable? |

Below 35/50: revise.

## Examples

See [references/examples.md](references/examples.md) for before/after transformations.

## License

MIT
