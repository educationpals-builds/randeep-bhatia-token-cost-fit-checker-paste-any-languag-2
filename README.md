# Token Cost + Fit Checker

A conversational checker that evaluates any pasted text for tokenization cost and model fit across multiple languages.

## How This Checker Was Built

This checker was calibrated against real multilingual support tickets. The builder's own sample and verdict serve as the worked example.

### The Worked Example

**Sample:**
> "Ihr Krankenversicherungsbeitrag wurde angepasst — bitte prüfen Sie die Beitragsbemessungsgrenze." / "Sigortalılığınızın başlangıç tarihini öğrenebilir miyim?" (two verbatim tickets from the queue)

**Traffic source:** 14-day support queue export: 38% German, 22% Turkish, 19% English, remainder Thai / Arabic / Mandarin

**Stakes:** Picks the vocabulary for the on-device assistant — the embedding table is capped and inference is billed per token

**Deadline:** Thursday's architecture review

**Verdict:** A B C D E E A B C D E E

**Weakest dial:** edge_case_survival

## One-Paste Rebuild

To rebuild this checker:

1. Copy the system instructions from `blueprints/token-fit-checker.md`
2. Paste into any chat model that supports system prompts
3. The checker is ready — paste any text to get a cost-and-fit read

## Repository Structure

- `charter.md` — The full calibration run
- `blueprints/token-fit-checker.md` — System instructions for the checker
- `prompts/token-fit-pack.md` — Standalone prompts, one per dial
- `skills/token-fit-advisor.skill.md` — Portable skill file
- `data/lane-fit-sheet.md` — Calibration data sheet
- `tests/` — Probe board, pass gate, and runner
- `METHOD.md` — The framework
- `VERIFY.md` — Verification protocol
- `STORY.md` — The builder's story

<!-- educationpals-build-verified -->
