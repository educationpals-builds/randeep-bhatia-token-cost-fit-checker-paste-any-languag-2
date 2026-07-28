# METHOD: TFLAC

**T**okenization **F**it and **L**ane **A**nalysis **C**hecker

This is the only file where the framework acronym appears.

## The Framework

TFLAC provides a structured approach to evaluating text for tokenization cost and model fit:

1. **Pin the sample** — Capture verbatim bytes, traffic source, stakes, and deadline
2. **Set the five dials** — Score how_it_splits, merge_economy, vocabulary_fit, special_token_handling, edge_case_survival
3. **Call the verdict** — Name the weakest dial, state the position, identify the flip condition
4. **Make it advise** — Configure the checker as a persistent advisor with stance and refusals
5. **Set the standard** — Define probes, read the board, establish the pass gate

## Why Five Dials

Tokenization cost is not a single number. Different failure modes matter for different deployments:

- On-device with capped embedding tables: vocabulary_fit dominates
- Per-token billing: merge_economy and how_it_splits dominate
- Multilingual production: edge_case_survival dominates

## The Lane Principle

Multilingual text must be analyzed per-language lane. A German sentence and a Turkish sentence in the same message have different tokenization profiles. The checker reports per-lane counts and identifies which lane is uncounted.
