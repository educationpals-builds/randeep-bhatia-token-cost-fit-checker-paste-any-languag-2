# Run Local Guide

Three rungs for running the probe board locally.

---

## Rung 1: Manual

Paste each probe into the checker and compare against expected behavior.

### Protocol

1. Open the checker (system instructions from `blueprints/token-fit-checker.md`)
2. For each probe in `tests/probes.jsonl`:
   - Copy the `input` field exactly (preserve bytes — do not retype)
   - Paste into the checker
   - Compare output against `expected`
   - Record pass/fail

### Byte Preservation Warning

Some probes contain special characters (emoji, Unicode symbols, mixed scripts). Copy-paste the exact bytes from `probes.jsonl`. Retyping may introduce different Unicode representations.

### Expected Lines

| Probe | Expected |
|-------|----------|
| probe-01 | High fragmentation, 3+ subword pieces |
| probe-02 | Multiple suffix boundaries, poor merge economy |
| probe-03 | Script boundary handling, potential fallback tokens |
| probe-04 | ZWJ sequence handling, possible over-tokenization |
| probe-05 | URL structure preserved or systematically split |
| probe-06 | Symbol handling, potential unknown token fallback |
| probe-07 | (learner defined) |
| probe-08 | (learner defined) |

---

## Rung 2: Script

Automated runner using the API.

```python
#!/usr/bin/env python3
"""Token fit checker probe runner."""

import json
import os

def load_probes(path="tests/probes.jsonl"):
    probes = []
    with open(path) as f:
        for line in f:
            if line.strip():
                probes.append(json.loads(line))
    return probes

def run_probe(probe, api_key):
    # Replace with your API call
    # Returns the checker's response
    pass

def grade_response(response, probe):
    # Check if response meets expected behavior
    # Returns (pass: bool, notes: str)
    pass

def main():
    api_key = os.environ.get("API_KEY")
    if not api_key:
        print("Set API_KEY environment variable")
        return
    
    probes = load_probes()
    results = []
    
    for probe in probes:
        response = run_probe(probe, api_key)
        passed, notes = grade_response(response, probe)
        results.append({
            "id": probe["id"],
            "passed": passed,
            "notes": notes
        })
    
    # Print grid
    print("\n=== PROBE BOARD ===")
    for r in results:
        status = "PASS" if r["passed"] else "FAIL"
        print(f"{r['id']}: {status} - {r['notes']}")
    
    # Gate verdict
    passed_count = sum(1 for r in results if r["passed"])
    total = len(results)
    print(f"\n=== GATE: {passed_count}/{total} ===")

if __name__ == "__main__":
    main()
```

---

## Rung 3: Eval Tool / CI

Load `probes.jsonl` into any eval runner for automated re-runs.

### Integration Steps

1. Point your eval tool at `tests/probes.jsonl`
2. Configure the system prompt from `blueprints/token-fit-checker.md`
3. Set up CI to run on prompt or stance changes
4. Compare results against the certified board

### Diffing Against Certified Board

To compare your local run against the certified board:

1. Run all probes locally
2. Export results as JSONL
3. Diff against the certified board on the listing
4. Investigate any regressions
