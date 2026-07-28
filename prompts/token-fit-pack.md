# Token Fit Prompt Pack

Five standalone prompts, one per dial. Usable in any chat model.

---

## Prompt 1: How It Splits

```
Analyze how this text tokenizes. Focus on:
- Compound word boundaries
- Agglutinative morphology (Turkish, Finnish, etc.)
- Script boundary handling
- Subword fragmentation patterns

Report the split pattern and count pieces for the most complex unit.

Text to analyze:
[PASTE TEXT HERE]
```

---

## Prompt 2: Merge Economy

```
Evaluate the merge efficiency of this text under BPE-style tokenization:
- Do common sequences merge into single tokens?
- Are there repeated fragments that stay separate?
- What's the ratio of merged vs fragmented sequences?

Score 0-4 where 4 = optimal merging.

Text to analyze:
[PASTE TEXT HERE]
```

---

## Prompt 3: Vocabulary Fit

```
Assess how well a standard multilingual tokenizer vocabulary covers this text:
- Are domain terms in-vocabulary or split?
- How many out-of-vocabulary fallbacks occur?
- Which language lane has the worst coverage?

Score 0-4 where 4 = excellent coverage.

Text to analyze:
[PASTE TEXT HERE]
```

---

## Prompt 4: Special Token Handling

```
Examine special character handling in this text:
- Punctuation and diacritics
- Emoji and symbols
- URLs and code fragments
- Whitespace and control characters

Identify any characters that tokenize unexpectedly. Score 0-4.

Text to analyze:
[PASTE TEXT HERE]
```

---

## Prompt 5: Edge Case Survival

```
Test edge case behavior for this text:
- Mixed script sequences
- Rare Unicode characters
- Malformed or truncated input
- Boundary conditions

Identify failure modes. Score 0-4 where 4 = robust survival.

Text to analyze:
[PASTE TEXT HERE]
```
