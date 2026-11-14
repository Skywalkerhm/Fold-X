# Frequently asked questions

[中文版](../../docs/faq.md) · [Overview](../README.md)

## What is Fold-X?

A multimodal decision model for judgments, choices, and scoring across text and images, designed for accuracy, speed, and efficiency. Flash-1.3 is currently available through an API.

## What should I try first?

Classification, condition checks, candidate selection, scoring, or image-condition screening. Start with a task that has clear inputs, outputs, and acceptance criteria, and test representative samples.

## Can I run the eight demos directly through the API?

The API supplies decisions. Video search, games, robotics, and traffic applications also need frame extraction, environment connections, action execution, or other integration. A demo is not a promise that the complete application is a standard service.

## What supports the Chinese-language capability?

Testing covers word meaning, sentence relationships, ambiguous words, and rhetorical knowledge. Flash in its deep configuration achieved a 93.33% macro-average across four C-SEM public-set tasks totaling 1,200 questions in a team-run test. This is not accuracy across all Chinese-language tasks.

## Are accuracy, speed, and efficiency guaranteed on every task?

They are product goals, not unconditional guarantees. Quality depends on the task; model timing differs from end-to-end API latency; costs must cover the complete workflow. Each result includes its test conditions and limitations.

## Is a returned score the probability that the answer is correct?

No. Scores help compare options or apply thresholds, but should not be treated as validated correctness probabilities. Evaluate them on your own data and use human review where appropriate.

## How do I get access and how is it billed?

Use the HTTPS text or image APIs. Current access supports point-based and time-based allowances; pricing and quotas are confirmed during onboarding. Contact the founders for a trial, or use GitHub Issues for general product questions.

## Are code, weights, or customer records published here?

This repository presents product capabilities, evaluation summaries, and demonstrations. It does not publish core implementation, model weights, keys, or raw customer data. Discuss business data and handling requirements privately.
