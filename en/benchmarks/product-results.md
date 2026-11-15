# Accuracy, speed, and efficiency: the evidence

[中文版](../../benchmarks/product-results.md) · [Overview](../README.md)

These results distinguish team-run tests from an anonymized enterprise trial report. Different datasets, configurations, and environments are reported separately. This update reviewed reports and product summaries; it did not rerun the experiments.

## Team-run tests

| Task | Baseline or conditions | Fold-X result | Scope |
|---|---|---|---|
| Consumer-complaint classification · 936 questions | Same-sized model generating answers: 745/936, or 79.59% | 836/936, or 89.32%: 91 additional correct answers | Historical team run; +9.72 percentage points calculated from counts |
| Chinese semantic understanding · 1,200 questions | C-SEM public v1.0, zero-shot; four tasks of 300 questions | Flash deep configuration: 1120/1200, 93.33% macro-average | Word relations 97.00%, sentence relations 86.33%, ambiguous words 91.33%, rhetoric 98.67%; not an official hidden-test ranking |
| Judgment and classification · 1,213 questions | Same-parameter-count model answering in natural language | 75.5% less cumulative model inference time | Local-test summary in team materials; excludes model loading and is not end-to-end cloud API latency |

Classification figures were cross-checked against the earlier report, without independently replaying all per-question records. Chinese results come from the October 20, 2026 team report. Public questions may overlap with base-model training material; no contamination-free or current official first-place claim is made. Historical configurations should not be assumed identical to the current Flash-1.3 service.

## Long-document retrieval and factual verification across languages

A team evaluation summary dated October 20, 2026 adds results for passage retrieval, factual consistency, and Chinese-language business judgments. These are historical report values, presented separately from external evaluations and enterprise feedback. This update checked the report; it did not independently rerun the per-question experiments.

| Capability and task | Configuration | Reported result | Scope |
|---|---|---|---|
| Chinese passage retrieval · LongBench v1 | Fold-X Flash · deep | **100.0%, 200/200** | Every question in this Chinese retrieval test was answered correctly; this does not mean 100% accuracy on all Chinese tasks |
| English passage retrieval · LongBench v1 | Fold-X Flash · deep | **98.5%** | The specified English retrieval task, not an overall LongBench score |
| English factual consistency and hallucination detection · RAGTruth | Fold-X Light · standard | **Hallucination-class F1: 66.71%, 2,700 items** | The report’s full sample scope; F1 is neither accuracy nor a percentage reduction in hallucinations |
| Chinese hallucination-resistance evaluation · HalluQA | Fold-X Flash · deep | **76.9%** | A benchmark score, not the probability of hallucination-free answers in production |
| Legal tasks · LawBench five-task subset | Fold-X Flash · deep | **Five-task macro-average: 58.4%** | Legal knowledge questions, dispute focus, consultation topic, viewpoint matching, and case analysis only |

**Different tasks use different configurations.** Each row identifies the configuration behind its score. The five best results must not be presented as the performance of one configuration. On the full RAGTruth evaluation, the report gives hallucination-class F1 scores of 66.71% for Light standard, approximately 50.4% for Flash standard, and approximately 40.6% for Flash deep. A larger model or deeper mode is not better on every task.

**What the results support:** the retrieval scores provide concrete evidence of locating information in Chinese and English long documents. RAGTruth supports exploring factual checks on generated content, while HalluQA and the selected LawBench tasks add evidence on Chinese-language judgments. They do not establish end-to-end document-review success or professional legal qualifications.

**Comparison and ranking limits:** the original report places Fold-X results alongside historical public model records. Evaluation methods or sample scopes differ in some comparisons. This summary reports task scores without claiming official first place, a current ranking, or superiority across tasks. Matching sample counts do not establish identical evaluation conditions. Public questions may overlap with training material, and these historical configurations should not be assumed identical to the current Flash-1.3 API service.

This complements the C-SEM results: C-SEM focuses on word meanings and sentence relationships, while these tests address long-document retrieval and factual verification. The report’s equally weighted composite is omitted because averaging accuracy and F1 would not produce a general-purpose accuracy measure.

## Cost observations from complete workflows

| Historical workflow | Estimated API cost reduction | Processing-time reduction | Token reduction |
|---|---|---|---|
| Batch processing of similar tasks | 10.5% | 6.3% | 46.5% |
| Mixed document tasks | 8.6% | 8.0% | 24.6% |
| Simulated expert bid review | 12.8% | About 8.5% | 7.2% |

Source: historical workflow summaries in team materials dated November 12, 2026. Each task is compared with direct calls to the same external model; the batch task includes repeated material. Costs are estimated from API usage for the complete task and exclude servers, labor, and other delivery costs. These are workflow-level observations, not benefits attributable to a single call to the current decision model, current API discounts, or guaranteed savings. These workflows were not independently rerun for this update.

## Anonymized enterprise trial: fewer abstentions and errors

An enterprise-supplied report compares Fold-X Flash v1.3 Deep with DeepSeek Chat on the same 453 records and question wording. The table uses the input setting that did not directly supply the field used to derive the target label. The company name, project identifiers, field codes, internal file paths, and raw business records are not published.

| Metric | DeepSeek Chat | Fold-X | Change |
|---|---|---|---|
| Target classification accuracy, counting abstentions as incorrect | 84.11% | 89.62% | +5.51 percentage points |
| Abstention rate | 13.91% | 9.49% | −4.42 percentage points |
| Incorrect judgments | 9 | 4 | 5 fewer |
| Accuracy among answered items, excluding abstentions | 97.69% | 99.02% | +1.33 percentage points |
| Mean request duration | 1027.1 ms | 442.3 ms | About 56.9% lower |

The report also states that Fold-X answered 23 of the 63 items on which the baseline abstained, and all 23 answers were correct. This illustrates improved answer coverage in this sample; it does not establish calibrated confidence.

**Essential context:** 452 of the 453 records belong to the same class, with just one counterexample. Always predicting the majority class would achieve 99.78%, above both models. This trial therefore does not establish general judgment ability or a statistically significant accuracy advantage. Another input setting supplies the field used to derive labels; its 97.57% result is not used as the headline result.

The two later stages of the report’s broader rule chain were not tested, so this does not establish completion of the full business review. The Fold-X run used rescoring of existing results; full wall-clock duration and token usage were not measured. No end-to-end throughput, token-saving, or cost-saving claim follows. Values are reported by the enterprise; the underlying per-record files were not available for independent recalculation in this update.

A more balanced dataset with difficult counterexamples is needed to validate quality, abstentions, human-review costs, and end-to-end timing. This is real enterprise trial feedback, not independent third-party certification.
