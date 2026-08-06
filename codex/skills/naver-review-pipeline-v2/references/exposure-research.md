# Naver Exposure Research Basis

Verified: 2026-07-26

Use this reference to separate current official guidance from third-party
heuristics. Recheck the live sources when the user requests current research or
when this verification is more than 90 days old.

## Evidence Tiers

### Tier 1 — Official And Directly Actionable

Naver's 2026 content guide confirms these principles:

- Write from firsthand experience, including concrete cases, failed attempts,
  problem-solving steps, and detailed reviews.
- Maintain a consistent core topic so the channel can be recognized as a
  knowledgeable source.
- Disclose sponsorship and cite original sources transparently.
- Use titles, subheadings, paragraphs, lists, images, and videos to make
  information easy to find.
- Put critical information in text even when it appears in media.
- Keep time-sensitive information current.
- Define the reader and TPO, explain the actual process, include relevant
  alternatives and decision reasons, report actual results and surprises, and
  use context-relevant media.
- Avoid mechanical AI output, copied or stitched content, excessive promotion,
  irrelevant keywords, unrelated media, and inaccurate information.

Sources:

- [AI 시대에 사용자의 선택을 받는 콘텐츠 작성 가이드](https://blog.naver.com/naver_search/224296857688)
- [AI 시대에 사용자의 선택을 받는 콘텐츠 작성 가이드_실전편](https://blog.naver.com/naver_search/224305800678)
- [콘텐츠 작성시 권장 사항](https://searchadvisor.naver.com/guide/content-basic)

Naver Search Advisor also confirms:

- Keep titles concise, accurate, and representative of the content.
- Do not repeat the same word unnaturally.
- Do not insert unrelated popular keywords.
- Do not use misleading titles or thumbnails merely to increase views.
- Search exposure depends on many factors; adding more words does not guarantee
  a higher rank.

Source:

- [콘텐츠 작성시 권장 사항](https://searchadvisor.naver.com/guide/content-basic)

### Tier 1 — Homefeed Mechanics, With Limits

Naver's engineering publication describes Homefeed as a personalized
recommendation system using content quality and popularity plus user context
such as clicks, subscriptions, search history, topic preference, consumption
history, and feedback. Its ranking work predicts both click probability and
satisfaction; the cited implementation defines satisfaction using longer dwell
time.

This supports optimizing honest title relevance and satisfying body content.
It does **not** support the claim that title clicks and body dwell time alone
determine Homefeed exposure.

Source:

- [홈피드: 네이버의 진입점에서 추천 피드를 외치다!](https://d2.naver.com/helloworld/0207214)

### Tier 2 — Useful Third-Party Observation

NAEO can be used as an observational diagnostic for sampled search and AI
Briefing visibility. Its own site states that it checks exposure and does not
directly raise views. Treat its recommendations as hypotheses to test, not
causal ranking rules.

Sources:

- [NAEO](https://www.naeo.kr/)
- [AI 인용 현황 사용법](https://www.naeo.kr/blog/guide/ai-picks-guide)

## Claim Review

| Advice | Evidence status | V2 action |
|---|---|---|
| Define the reader and situation | Officially supported | Require a TPO brief |
| Explain process, tips, and failed attempts | Officially supported | Require chronological firsthand evidence |
| Compare alternatives and decision reasons | Officially supported | Include only genuine or sourced comparisons |
| Add concrete results and valid measurements | Officially supported | Require method, unit, baseline, and period |
| Use subheadings, lists, tables, and relevant media | Officially supported as readability guidance | Use the structure that best serves the reader |
| Put key media information in text | Officially supported | Require nearby text captions |
| Keep a consistent channel topic | Officially supported | Use a recent active window and state sample size |
| Put a 3-by-2 table at the very top | Not confirmed as a ranking rule | Make a compact summary optional after disclosure |
| Tables sharply increase AI citation probability | Not confirmed causally | Treat as a testable hypothesis |
| GIFs increase search score | Not confirmed | Use GIF/video only as process evidence |
| Use “의외로” or a question to increase rank | Not confirmed; can become clickbait | Use only when accurate and answered |
| End with a comment question to increase exposure | Not confirmed | Include only when it adds a genuine reader prompt |
| Repeat a keyword a fixed number of times | Not an official general rule | Follow campaign minimums only; audit for stuffing |

## Measurement Integrity

Require this record for numeric claims:

```text
metric:
value:
unit:
baseline:
time window:
environment:
method or instrument:
source:
```

Use these writing classes:

- **Measured fact**: an instrument, timestamp, count, receipt, or documented
  specification supports the value.
- **Observed fact**: the user directly saw or experienced it, but did not
  instrumentally measure it.
- **Subjective rating**: a clearly defined personal scale such as 1–5.
- **Sourced fact**: a product page, official document, or cited study supports
  it.
- **Hypothesis**: a proposed optimization or explanation that still needs
  testing.

Never convert an observed impression into a precise percentage. Do not write
`70% 줄었다` unless a defensible method produced that value.

## Channel-Topic Sampling

Use a time-bounded active sample:

1. Prefer the latest 90 active days or latest 20 active posts.
2. Report older history separately after a long hiatus.
3. State sample size, date range, and category counts.
4. Use recency-aware interpretation rather than unweighted all-time counts.
5. Mark conclusions as low confidence when fewer than 10 active posts exist.

This prevents old content from dominating the recommended current channel
identity.

## Post-Publish Research

Treat exposure optimization as an observational improvement program:

1. Record the post, primary query, title, topic pillar, and one major change.
2. Collect the same available metrics at 7 and 28 days.
3. Compare at least three similar posts.
4. Do not infer causality from one before/after result.
5. Record algorithm, seasonality, campaign demand, and topic differences as
   possible confounders.
