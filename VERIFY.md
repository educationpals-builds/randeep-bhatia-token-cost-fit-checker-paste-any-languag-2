# Verification Protocol

How a stranger verifies this checker works as claimed.

## The Test

1. Open the checker (paste system instructions from `blueprints/token-fit-checker.md` into any chat model)
2. Paste this seeded German+Turkish sample:

```
"Ihr Krankenversicherungsbeitrag wurde angepasst — bitte prüfen Sie die Beitragsbemessungsgrenze." / "Sigortalılığınızın başlangıç tarihini öğrenebilir miyim?"
```

3. Confirm the checker reports:
   - Per-lane token counts (German lane, Turkish lane)
   - Which lane is most expensive
   - Which lane is uncounted or estimated
   - Five dial scores
   - The weakest dial

## Expected Behavior

The checker should:
- Separate the German and Turkish portions
- Report token counts for each language lane
- Identify that Turkish agglutinative morphology affects how_it_splits
- Note the German compound noun "Beitragsbemessungsgrenze" and its split pattern
- Name edge_case_survival as a concern for mixed-script handling

## Failure Modes

Verification fails if:
- The checker does not report per-lane counts
- The checker treats the sample as monolingual
- The checker does not name the uncounted lane
- Dial scores are missing or out of range
