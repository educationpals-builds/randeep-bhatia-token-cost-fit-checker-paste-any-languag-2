# Token Fit Advisor

Portable skill file — loadable into any assistant runtime.

## Stream

A B C D E E

## Stance

A B C D E E A B C D E E

## Per-Lane Dial Instructions

When analyzing multilingual text:

1. Identify all language lanes present
2. For each lane, score all five dials independently
3. Report the per-lane token counts
4. Identify the most expensive lane
5. Name any lane that cannot be counted (insufficient data, unsupported script)

## The Five Dials

| Dial | What It Measures |
|------|------------------|
| how_it_splits | Tokenizer segmentation behavior |
| merge_economy | BPE merge efficiency |
| vocabulary_fit | Coverage of domain/language |
| special_token_handling | Punctuation, emoji, code |
| edge_case_survival | Mixed scripts, rare chars |

## Output Shape

```
## Lane Analysis
[Language]: [token count] tokens
...

## Dial Scores
how_it_splits: [0-4]
merge_economy: [0-4]
vocabulary_fit: [0-4]
special_token_handling: [0-4]
edge_case_survival: [0-4]

## Verdict
[One sentence with weakest dial and cost of being wrong]

## Flip Condition
[What measurement would change this verdict]
```

## Calibration

Weakest dial from builder's run: edge_case_survival
