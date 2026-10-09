# Framework Mapping

Every case and every finding is traced to a public control. Classification is controls mapping, not certification.

---

## Why mapping matters

A finding without classification is not usable by procurement. A CISO cannot take an unclassified finding to a risk committee. A finding mapped to a public control can be discussed in the language the organisation already uses.

Classification also enables comparison: two findings from two engagements, both mapped to OWASP MCP04, are comparable. Two findings without classification are not.

---

## Frameworks in scope

### OWASP Top 10 for LLM Applications 2026

LLM01 through LLM10. Covers prompt injection, insecure output handling, training data poisoning, model denial of service, supply chain, sensitive information disclosure, insecure plugin design, excessive agency, overreliance, and model theft.

### OWASP MCP Top 10 (Beta)

MCP01 through MCP12. Covers server authentication, pinned identity, chain admission, chain depth, tool poisoning, permission scope, caller identity, capability drift, chain tampering, cross-server data flow, name collision, and fail-open behaviour.

### MITRE ATLAS

Adversarial Threat Landscape for AI Systems. Cases map primarily to AML.T0051 (LLM prompt injection) and AML.T0053 (exfiltration via AI application).

### NIST AI RMF

AI Risk Management Framework. Cases map to the GOVERN, MEASURE, and MANAGE functions depending on whether the case identifies a governance gap, a measurable property, or a mitigable risk.

### ISO/IEC 42001

AI management system standard. Cases map to operational controls related to access, change management, and evidence retention.

---

## What mapping is not

Mapping is not certification. Certification of a system against a framework is issued by an accredited body, not by a security test.

Mapping a finding to a control states that the finding relates to that control. It does not state that the system satisfies the control.

---

## How to read a classification

A finding classified as "OWASP MCP04 · MITRE AML.T0051 · NIST AI RMF · ISO/IEC 42001" means:

- The weakness relates to OWASP MCP04 (chain depth)
- The same weakness maps to MITRE ATLAS AML.T0051 (LLM prompt injection)
- The NIST AI RMF function touched is MEASURE
- The ISO/IEC 42001 control area touched is operational

The classification is guidance for procurement, not a compliance statement.

---

## Related

- [Case definition](01-case-definition.md)
- [Case library](../cases/01-library.md)
- [mcp-security-audit](https://github.com/RolandCaushaj/mcp-security-audit) — how findings are produced
