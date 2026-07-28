# Lane Fit Data Sheet

The calibration record.

## Seeded Samples

### Sample 1: German

```
Ihr Krankenversicherungsbeitrag wurde angepasst — bitte prüfen Sie die Beitragsbemessungsgrenze.
```

### Sample 2: Turkish

```
Sigortalılığınızın başlangıç tarihini öğrenebilir miyim?
```

## Per-Language Lane Counts

| Lane | Estimated Tokens | Notes |
|------|------------------|-------|
| German | TBD | Compound nouns inflate count |
| Turkish | TBD | Agglutinative suffixes inflate count |

## Advisor's Dial Strips

### Run 1 (German sample)

| Dial | Advisor Score |
|------|---------------|
| how_it_splits | — |
| merge_economy | — |
| vocabulary_fit | — |
| special_token_handling | — |
| edge_case_survival | — |

### Run 2 (Turkish sample)

| Dial | Advisor Score |
|------|---------------|
| how_it_splits | — |
| merge_economy | — |
| vocabulary_fit | — |
| special_token_handling | — |
| edge_case_survival | — |

## Builder's Drift Ruling

A B C D E EA B C D E EA B C D E EA B C D E E

## Stance Line Added

Based on the drift ruling, the following stance line was added to the advisor:

A B C D E E A B C D E E
