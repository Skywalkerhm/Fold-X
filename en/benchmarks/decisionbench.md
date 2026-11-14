# DecisionBench: Fold-X evaluation results

[English](decisionbench.md) | [中文版](../../benchmarks/decisionbench.md)

Snapshot reviewed: November 14, 2026. Full DecisionBench 1.0 evaluation: 23,900 questions.

Product names map to the original submissions as follows: **Fold-X Flash = Fold-X 9B 1.3 Deep**; **Fold-X Light = Fold-X 4B 1.0 Deep**; **Fold-X Pro = 27B**. The product names do not change the submitted model versions or scores.

## Full-evaluation scores and reference positions

| Model | Primary accuracy | Score interval (not listed) | Successfully processed | Source |
|---|---:|---:|---:|---|
| Fold-X Flash (9B) | **76.85%** | **Between archived ranks 3–4** | 23,900 / 23,900 | [PR #85](https://github.com/Hanno-Labs/decision-bench-results/pull/85) |
| Fold-X Light (4B) | **74.48%** | **Between archived ranks 5–6** | 23,900 / 23,900 | [PR #82](https://github.com/Hanno-Labs/decision-bench-results/pull/82) |

Both runs covered every question with no recorded execution errors or unsupported items. This describes successful processing, not correctness of every answer. The reference positions show where the submitted scores fall within the comparison set; they are not official leaderboard placements.

### Archived Top 10 · submitted scores shown separately

| Archived rank | Model / submitted version | Accuracy | Record source |
|---:|---|---:|---|
|1|Hanno-Labs/bosun-v3.1-1.7b|84.90%|[Archived main branch](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|2|Hanno-Labs/bosun-v3.1-0.6b|81.18%|[Archived main branch](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|3|mohit67890/imajev-4b|79.69%|[Archived main branch](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|**↳ Reference only**|**Fold-X Flash (9B · 1.3 Deep)**|**76.85%**|**[Submitted, not yet listed](https://github.com/Hanno-Labs/decision-bench-results/pull/85)**|
|4|EldanRing/Winnow-12B|76.65%|[Archived main branch](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|5|ekzhang/openjev-sglang|74.82%|[Archived main branch](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|**↳ Reference only**|**Fold-X Light (4B · 1.0 Deep)**|**74.48%**|**[Submitted, not yet listed](https://github.com/Hanno-Labs/decision-bench-results/pull/82)**|
|6|z-ai/glm-5.3-flash|74.09%|[Archived main branch](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|7|typesafe/jev-1.13|72.03%|[Archived main branch](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|8|deepseek/deepseek-v4.1-flash|71.00%|[Archived main branch](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|9|openai/gpt-5.6-luna|69.90%|[Archived main branch](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|
|10|razorback16/openjev|68.43%|[Archived main branch](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f)|

The numbered rows are the Top 10 among 59 current entries in the November 14, 2026 main-branch archive. Fold-X scores are inserted between adjacent scores for reference only: submitted, not yet listed, and excluded from leaderboard numbering. These are historical positions, not a live leaderboard.

## Fold-X Pro: internal result and conditional position

Internal testing reports **over 82% accuracy on text judgment tasks**. This has not been verified as a full, comparable run on all 23,900 DecisionBench 1.0 questions.

If that result were reproduced on the same dataset version, complete question set, and primary-accuracy scoring protocol, adding Pro separately to the 59 reference entries would place it in the **top 2 / 60, conditionally**. The two highest reference scores are 84.8996% and 81.1841%. “Over 82%” would exceed the second score, but does not establish whether it exceeds the first. It therefore cannot be labeled a confirmed second place or an official ranking.

This conditional estimate is not equivalent evidence to the Flash and Light submissions. A verified full result, per-question records, and model version are needed before reporting a reproducible position.

## Fold-X Flash by task type

| Task type | Accuracy | Questions |
|---|---:|---:|
| Binary judgment | 87.45% | 6,388 |
| Candidate selection | 76.54% | 15,814 |
| Ordinal scoring | 39.87% | 1,698 |

This version performs more strongly on binary judgments and candidate selection; ordinal scoring remains an area for improvement. Overall accuracy is weighted by question count, not a simple average of the three percentages.

## Comparisons with fixed baseline versions

Automated comparison comments in the results repository report the following full-benchmark differences:

| Submitted model | vs. Jev 1.13 (72.03%) | vs. GPT-5.6 Luna (69.90%) |
|---|---:|---:|
| Fold-X Flash (9B) | **+4.82 percentage points** | **+6.95 percentage points** |
| Fold-X Light (4B) | **+2.45 percentage points** | **+4.58 percentage points** |

Sources: [9B automated comparison](https://github.com/Hanno-Labs/decision-bench-results/pull/85#issuecomment-6383351153), [4B automated comparison](https://github.com/Hanno-Labs/decision-bench-results/pull/82#issuecomment-6291636964). These are overall accuracy comparisons on the complete test set; relative performance varies by task.

## How the reference positions are calculated

- DecisionBench 1.0 contains 23,900 questions. Results are ordered by `primary_accuracy`; errors and unsupported items count as incorrect.
- The main-repository snapshot is dated November 14, 2026, at commit `e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f`. Applying the leaderboard frontend’s latest-revision selection rule to 60 result files produces 59 current entries.
- The numbered rows are the Top 10 among 59 current entries in the November 14, 2026 main-branch archive. Fold-X scores are inserted between adjacent scores for reference only: submitted, not yet listed, and excluded from leaderboard numbering. These are historical positions, not a live leaderboard.
- At the snapshot date, the 4B PR had been closed by a bot without merging; the 9B PR remained open and unmerged. Both are author-submitted results. Automated comparisons do not constitute independent reproduction or certification by the benchmark organizers.

See the [frozen results repository](https://github.com/Hanno-Labs/decision-bench-results/tree/e2d6a133cee91b9d8c6fbd076b21f32f3d75c81f) and the [frontend revision-selection rule](https://github.com/Hanno-Labs/decision-bench-leaderboard/blob/1aa3f4d5273dcf3e450be473e96df0a74def4b82/src/lib/data/service.ts).

## What these results support

These results describe the specified model versions on this benchmark. They do not establish an advantage on every task, or support claims about token consumption, cost, or Chinese-language performance. Pro has no verifiable full submission in this review; its position remains a conditional estimate.

[Back to the English GitHub overview](../README.md) · [Open the full showcase](https://skywalkerhm.github.io/Fold-X/en/index.html)
