# Probe Board

All 8 probes with pasteable inputs, targeted dials, expected behaviors, and results.

## Pre-Generated Probes (1–6)

### Probe 1: German Compound Noun

**Input:**
```
Beitragsbemessungsgrenze
```

**Targets:** how_it_splits, vocabulary_fit

**Expected:** High fragmentation, 3+ subword pieces

**Result:** —

---

### Probe 2: Turkish Agglutination

**Input:**
```
Sigortalılığınızın
```

**Targets:** how_it_splits, merge_economy

**Expected:** Multiple suffix boundaries, poor merge economy

**Result:** —

---

### Probe 3: Mixed Script

**Input:**
```
Hello مرحبا 你好
```

**Targets:** edge_case_survival, special_token_handling

**Expected:** Script boundary handling, potential fallback tokens

**Result:** —

---

### Probe 4: Emoji Sequence

**Input:**
```
👨‍👩‍👧‍👦 family emoji
```

**Targets:** special_token_handling

**Expected:** ZWJ sequence handling, possible over-tokenization

**Result:** —

---

### Probe 5: URL with Parameters

**Input:**
```
https://example.com/path?param=value&other=123
```

**Targets:** special_token_handling, how_it_splits

**Expected:** URL structure preserved or systematically split

**Result:** —

---

### Probe 6: Rare Unicode

**Input:**
```
℃ ™ © ® ¼ ½ ¾
```

**Targets:** edge_case_survival, vocabulary_fit

**Expected:** Symbol handling, potential unknown token fallback

**Result:** —

---

## Learner Probes (7–8)

### Probe 7

**Input:**
```
A B C D E EA B C D E EA B C D E E
```

**Targets:** —

**Expected:** —

**Result:** —

---

### Probe 8

**Input:**
```
A B C D E EA B C D E EA B C D E E
```

**Targets:** —

**Expected:** —

**Result:** —

---

## Results Grid

| Probe | how_it_splits | merge_economy | vocabulary_fit | special_token_handling | edge_case_survival |
|-------|---------------|---------------|----------------|------------------------|--------------------|
| 1 | — | — | — | — | — |
| 2 | — | — | — | — | — |
| 3 | — | — | — | — | — |
| 4 | — | — | — | — | — |
| 5 | — | — | — | — | — |
| 6 | — | — | — | — | — |
| 7 | — | — | — | — | — |
| 8 | — | — | — | — | — |

## Board Reading

A B C D E EA B C D E EA B C D E EA B C D E EA B C D E E
