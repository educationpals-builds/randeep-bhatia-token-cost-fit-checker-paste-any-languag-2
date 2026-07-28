# The Story

I built a token cost and fit checker for multilingual support queues.

The problem: our on-device assistant has a capped embedding table, and inference is billed per token. We needed to know which languages in our support queue would blow the budget before Thursday's architecture review.

The traffic mix was real: 38% German, 22% Turkish, 19% English, and the rest Thai, Arabic, and Mandarin. I pinned two actual tickets from the queue — one German, one Turkish — and ran them through the five dials.

The probe that fooled it: A B C D E EA B C D E EA B C D E E

The weakest dial across the board was edge_case_survival. Mixed scripts and rare characters exposed gaps in how the checker handled boundary conditions.

The fix came from the drift ruling on the seeded runs. I added a stance line to make the advisor more explicit about per-lane reporting.

The gate it now holds: A B C D E EA B C D E EA B C D E EA B C D E E

Re-certification runs when the traffic mix shifts or when we add a new language lane to the queue.

The domain lesson: tokenization cost is not one number. German compounds and Turkish agglutination fail differently. The checker has to report per-lane, or the verdict is useless for architecture decisions.
