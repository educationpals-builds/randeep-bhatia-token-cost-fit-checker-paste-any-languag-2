# Charter: Token Cost + Fit Checker

The builder's full calibration run.

## Pinned Sample

"Ihr Krankenversicherungsbeitrag wurde angepasst — bitte prüfen Sie die Beitragsbemessungsgrenze." / "Sigortalılığınızın başlangıç tarihini öğrenebilir miyim?" (two verbatim tickets from the queue)

## Traffic Mix

14-day support queue export: 38% German, 22% Turkish, 19% English, remainder Thai / Arabic / Mandarin

## Stakes

Picks the vocabulary for the on-device assistant — the embedding table is capped and inference is billed per token

## Deadline

Thursday's architecture review

## Split Note

http://127.0.0.1:8765/np-follow-topic-preview.html http://127.0.0.1:8765/np-follow-topic-preview.html http://127.0.0.1:8765/np-follow-topic-preview.html http://127.0.0.1:8765/np-follow-topic-preview.html http://127.0.0.1:8765/np-follow-topic-preview.html http://127.0.0.1:8765/np-follow-topic-preview.html

## Five Dial Scores

| Dial | Score (0–4) |
|------|-------------|
| how_it_splits | 2 |
| merge_economy | 1 |
| vocabulary_fit | 3 |
| special_token_handling | 2 |
| edge_case_survival | 2 |

### Cost Note

A B C D E F

### Weakest Dial

edge_case_survival

## Verdict

A B C D E E A B C D E E

## Flip Condition

A B C D E E A B C D E E

## Demanded Test

A B C D E E
