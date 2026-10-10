# Verification and evaluation approach

CanonRoot treats a model's answer as **untrusted until reviewed**, even if it is fluent and includes plausible references.

## Layers of checking

| Stage | Question |
| --- | --- |
| **Evidence eligibility** | Is the supporting material permitted for the intended use? |
| **Reference integrity** | Do cited references correspond to evidence provided to the model? |
| **Deterministic screening** | Does the claim contain language or references suggesting weak support or overstatement? |
| **Semantic evaluation** | Does the cited evidence actually justify the assertion, and does the claim represent earlier positions fairly? |
| **Bounded correction** | Can unsafe wording be revised and successfully reviewed against the same evidence? |
| **Display decision** | If the required checks fail, should the claim be withheld? |

These checks have different jobs. Lexical similarity is not evidence of entailment; equally, a claim with unfamiliar wording is not automatically false. The semantic stage requires careful interpretation and is itself fallible.

## Adversarial testing

The project includes development workflows that exercise **Answer → Challenge → Response** using live model calls and check that only reviewed output moves to the next stage. It also includes evaluation cases designed to probe contradictions, misrepresentation of another position, and fabricated attributions.

The existence or success of an individual test run does not imply production readiness, universal reliability, or comprehensive theological correctness. A release would require broader evaluation across passages, viewpoints, source editions, models, client devices, and operational conditions.

## Illustrative failure scenarios

1. **Invented citation:** A claim references an evidence item the retrieval stage did not provide. The reference-integrity check rejects it.
2. **Overstated wording:** A claim says a passage *proves* a contested inference more strongly than the evidence supports. Review may request a narrower statement.
3. **Mischaracterized opponent:** A response attributes a claim to the challenge that the challenge never made. The attribution check should catch the mismatch.
4. **Unresolved correction:** A revised claim still fails review. It must not be promoted to verified reader-facing content.
5. **Ineligible source:** Material permitted for display is not automatically suitable for model input. Source policy blocks unauthorized transfer.

These scenarios explain intended safeguards; they are not real incident reports or measured performance outcomes.

## What would establish confidence over time?

- Explicit test cases spanning multiple theological perspectives and passages.
- Independent reviewers and reproducible evaluation fixtures.
- Measurement of false acceptance, false rejection, and source-attribution fidelity.
- Review of source editions and licensing conditions.
- End-to-end testing of authenticated client, server, and operational boundaries.

Until those steps are complete, CanonRoot should be understood as a **developing system with safeguards**, not an infallible interpreter or finished public service.
