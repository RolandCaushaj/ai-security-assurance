# Case Definition

What counts as a test case, and how one is validated.

---

## One case = one attack objective

A case is one attack objective with defined preconditions and a pass/fail criterion. Variants are execution detail inside a case, not additional cases.

Example: "Injection via encoded payload" is one case with several execution variants (base64, hex, unicode). It is not three cases.

The count stays at 61. Variants change how a case runs, not what it tests.

---

## Required elements

Every case has:

- **Preconditions** — what must be true before the test runs
- **Pass/fail criterion** — the property the system must hold
- **Detection criterion** — how a violation is detected
- **Reproducible PoC** — runnable command, exit 0 or 1
- **Classification** — mapped to a public control

A case without a validated detection criterion is not accepted.

---

## Validation of the detection criterion

A detection criterion is accepted only if it:

1. Flags a known-violating response
2. Clears a known-refusing response
3. Still flags a refusal followed by compliance

This three-way test guards against two failure modes:

- **False positives** — the criterion flags a system that is behaving correctly
- **False negatives** — the criterion clears a system that is misbehaving

A criterion that fails any of the three is rejected. The case does not ship.

---

## Scope

Cases test the behaviour of shipped systems, as deployed. They do not test:

- Model training
- Bias and fairness
- Data governance and privacy
- Content moderation policy

Those are separate disciplines with separate methodologies.

---

## Related

- [Framework mapping](02-framework-mapping.md)
- [Case library](../cases/01-library.md)
- [mcp-security-audit](https://github.com/RolandCaushaj/mcp-security-audit) — audit methodology
