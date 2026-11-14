# API access and availability

[中文版](../../docs/api.md) · [Overview](../README.md)

Fold-X is a multimodal decision model. **Fold-X Flash-1.3 currently provides text-decision and image-condition APIs over HTTPS.** Contact the team about Light and Pro access; a model appearing in a benchmark does not automatically mean it is available on the current service.

## Available capabilities

| Service | Input | Output | Per request |
|---|---|---|---|
| Text decisions | Text or structured context, questions, and options | Selected options, scoring levels, or condition scores | 1–256 independent questions |
| Image conditions | One image and natural-language conditions | Match decisions, scores, and threshold results | One condition, or 1–64 conditions |
| Balance lookup | An authorized key | Remaining points or days | No charge for lookups |

Video search, games, robotics, and traffic demos combine Fold-X with an application. Frame extraction, action execution, environment connections, and presentation require integration. The API does not take over an entire application simply because a demo shows it.

## Start a trial

1. [Contact the team](contact.md) with your task, expected volume, and quality, latency, or cost targets.
2. Receive a service address, the appropriate key, and usage allowance.
3. Validate inputs and outputs on a small representative sample before scaling up.

Authenticate with `Authorization: Bearer YOUR_API_KEY`. Keep your key on your server or in a secure environment variable, never in a public repository or webpage. No real key is included here; connection details are provided during onboarding.

## Endpoints and results

| Endpoint | Purpose |
|---|---|
| POST /v1/systemone | Text decisions |
| POST /v1/systemone/stream | Text decisions with SSE progress |
| POST /v1/image/classify | Image-condition judgments |
| POST /v1/image/classify/stream | Image judgments with SSE progress |
| POST /v1/key/balance | Usage balance |

Text requests contain `state` and `questions`. `choice` returns an option ID, `score` returns a scoring-level index, and `noul` returns a condition score. `review_mode` supports `standard` and `adaptive`; compare them on your own task data before choosing.

Image requests contain `image_base64` and either `description` or `questions`. `matches` is the model decision; `threshold_match` indicates whether the score meets the chosen threshold. They can differ. Scores should not be interpreted as accuracy validated for your business task.

## Input and operating limits

- Text request JSON is limited to 4 MiB. The documented per-question limit is 262,144 tokens across context, question, options, and associated input. Actual capacity and latency depend on content and load.
- Images may be JPEG, PNG, or WebP, up to 1 MiB, with each dimension between 32 and 8,192 pixels and at most 25 million pixels in total. Request JSON is limited to 12 MiB.
- For a busy-service 503 response, respect `Retry-After` and reduce concurrency. A 429 response indicates insufficient allowance; do not retry it blindly. Check credentials for 401 and correct inputs for 422.
- Selected answers, candidate scores, and demo readings do not replace evaluation of accuracy and latency on your own data.

## Billing and timing

The current manuals describe point-based and time-based access. Point-based text charges are question count multiplied by max(1, round-half-up(UTF-8 state bytes / 1024)). Questions and options are excluded; structured state uses compact JSON. Each question costs at least one point. Image charges count successful condition judgments. Invalid or failed requests and capacity rejections do not consume points. Confirm actual pricing and allowance during onboarding; historical test pricing is not a current offer.

Measure API performance from the client sending a request to receiving the complete result. The image fields `inference_seconds` and `elapsed_seconds` measure work within the service; the latter excludes upload and image decoding and is not complete end-to-end API latency.

This summary is based on service manuals retrieved on November 14, 2026. No paid inference was performed for this update. Full manuals are supplied with access. Public documentation covers usage, not internal implementation.
