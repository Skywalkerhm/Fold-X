# External evaluation: Fold-X Pro across public benchmarks

[中文版](../../benchmarks/external-evaluation.md) · [Overview](../README.md)

**Results from an external evaluator.** This summary uses the supplied external evaluation report dated November 3, 2026 and its archived comparison data. The evaluator and service platform are not named. These results are presented separately from team-run tests and enterprise trial feedback.

## Highlights

- **82.72% overall accuracy across samples from 16 public benchmarks:** both standard and adaptive modes score 1302/1574, placing second in the report’s three-model reference set.
- **Three first or joint-first positions in standard mode:** RTE textual entailment at 95.00% (joint first), QQP question equivalence at 86.00% (first), and TweetEval sentiment at 74.00% (first). This count uses one fixed mode rather than selecting the better mode for each task.
- **85.28% accuracy on a 231-question public decision set in adaptive mode**, versus 83.55% in standard mode. Both place second in the report’s three-model reference set.
- **99.00% on sampled causal reasoning** (COPA, adaptive, 100 questions); 96.00% on sentiment classification (SST-2, both modes, 100 questions) and science questions (ARC, adaptive, 100 questions).

## All 16 benchmark samples

Positions are calculated by comparing each Fold-X mode with the two other models’ values in the report and archived comparison data. They are **positions within this three-model reference set**, not official benchmark leaderboard rankings. Each Fold-X mode is compared separately; equal correct counts receive a joint position.

| Benchmark and task | Questions | Standard accuracy | Standard position | Adaptive accuracy | Adaptive position |
|---|---:|---:|---|---:|---|
| BoolQ · Reading comprehension | 100 | 92.00% | 2 / 3 | 91.00% | 2 / 3 |
| RTE · Textual entailment | 100 | 95.00% | Joint 1 / 3 | 94.00% | 2 / 3 |
| QNLI · Question–sentence relevance | 100 | 92.00% | 2 / 3 | 94.00% | 2 / 3 |
| CoLA · Grammatical acceptability | 100 | 73.00% | 2 / 3 | 72.00% | 2 / 3 |
| MRPC · Sentence paraphrase detection | 100 | 78.00% | 2 / 3 | 78.00% | 2 / 3 |
| QQP · Question equivalence | 100 | 86.00% | 1 / 3 | 85.00% | Joint 1 / 3 |
| SST-2 · Sentiment classification | 100 | 96.00% | 2 / 3 | 96.00% | 2 / 3 |
| TweetEval Sentiment · Social-text sentiment | 100 | 74.00% | 1 / 3 | 74.00% | 1 / 3 |
| AG News · News classification | 100 | 82.00% | Joint 2 / 3 | 82.00% | Joint 2 / 3 |
| ARC · Science questions | 100 | 95.00% | 2 / 3 | 96.00% | 2 / 3 |
| WinoGrande · Coreference and commonsense | 100 | 85.00% | 2 / 3 | 82.00% | 2 / 3 |
| HellaSwag · Context completion | 100 | 82.00% | 2 / 3 | 84.00% | 2 / 3 |
| COPA · Causal reasoning | 100 | 98.00% | 2 / 3 | 99.00% | 2 / 3 |
| Banking77 · Intent classification | 80 | 68.75% | 3 / 3 | 68.75% | 3 / 3 |
| MMLU-Pro · Multidisciplinary knowledge | 100 | 40.00% | 2 / 3 | 42.00% | 2 / 3 |
| C-Eval · Chinese knowledge assessment | 94 | 84.04% | 2 / 3 | 82.98% | 2 / 3 |

The overall score is 82.72% in both modes, but gains and losses differ by task. Adaptive mode has two first or joint-first positions across these samples. The three highlighted standard-mode positions do not imply a lead on every task.

## Public decision set and observed response times

| Evaluation | Mode | Accuracy | End-to-end P50 | End-to-end P95 |
|---|---|---:|---:|---:|
| JevBench public set · 231 questions | standard | 83.55% | 802 ms | 2062 ms |
| JevBench public set · 231 questions | adaptive | 85.28% | 829 ms | 2412 ms |
| General benchmark samples · 1574 questions | standard | 82.72% | 690 ms | 1939 ms |
| General benchmark samples · 1574 questions | adaptive | 82.72% | 778 ms | 2107 ms |

Accuracy and timing are paired by configuration. The report describes serial execution, one question per request, with no retries, from a Singapore client to a service in mainland China. Timings include the network round trip and are not pure model-compute times. Comparable complete cost data was not provided; no lower-cost or faster-service claim is made here.

## Evidence and limits

- The evaluation covers text decisions, not images. Fold-X Pro is the report’s model name; it does not establish parameter count or equivalence to the current Flash-1.3 service.
- General benchmarks were sampled, not evaluated in full. The archived 80-question Banking77 sample covers only two ground-truth intent classes and does not represent all 77 classes.
- The 231 questions are from the JevBench public set, **not the full DecisionBench evaluation or its official leaderboard**. Do not combine this score with the DecisionBench results elsewhere in this showcase.
- New Fold-X values are external report values. Counts and totals were checked arithmetically, but the complete new per-question records were unavailable. This is not an independent rerun or full recalculation. Some percentages are reconstructed from question counts and may differ in the final digit from the report’s three-decimal display.
- Comparison values come from the report and earlier archived runs. The available material does not establish that both comparison models were rerun alongside the updated Fold-X service. Positions describe this report’s comparison set, not live rankings or official certification.
- Public data may overlap with training material. A single run on small samples does not establish statistical significance or production guarantees. Unsupported causal explanations and threshold recommendations in the source report are not repeated here.

Only anonymized scores and a methodology summary are published. Identifying screenshots, source links, service addresses, document identifiers, and execution code are withheld; source material is retained for internal traceability.
