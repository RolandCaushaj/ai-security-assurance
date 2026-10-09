# AI Security Assurance

Test case library for adversarial testing of LLM, RAG, agent, and MCP 
systems. 61 cases across 8 domains, each defined as an attack objective 
with a pass/fail criterion validated against a known-bad and a known-good 
response.

> **Maintained by [Roland Caushaj](https://github.com/RolandCaushaj)**, 
> security researcher at [Logic4Hack](https://logic4hack.com) — 
> adversarial testing of LLM, RAG and agent systems.
>
> The case titles and methodology are documented here. The detection 
> criteria, execution runners, and evidence artefacts are proprietary 
> and shared under NDA in client engagements.

---

## What this is

A library of 61 attack objectives for AI systems in production. Each 
case targets one property, has defined preconditions, and resolves to 
a pass/fail result. Detection criteria are validated against a 
violating response and a refusing response before a case is accepted.

The library is organised into 8 domains covering the surface where 
risk has moved: prompt, retrieval, memory, tools, supply chain, 
agency, and the MCP chain.

---

## Domain overview

| Domain | ID | Cases | Scope |
|---|---|---|---|
| Prompt Injection | INJ | 7 | Direct and indirect instruction override |
| Jailbreak & Adversarial | JBK | 8 | Persona, framing, encoding, multi-turn |
| RAG Security | RAG | 7 | Corpus poisoning, retrieval hijack, leakage |
| Tool Abuse & Agent-Chain | TOOL | 15 | Allow-list bypass, argument injection, egress |
| Memory & Context Poisoning | MEM | 5 | Persistence, bleed, cross-user contamination |
| AI Supply Chain | SUP | 4 | Model artefacts, dependencies, substitution |
| Excessive Agency | AGY | 3 | Actions beyond delegated authority |
| MCP Permission & Chain | MCP | 12 | Chain depth, identity, capability drift |

Total: **61 cases**.

---

## Case library

### Prompt Injection (INJ, 7)

- **INJ-01** — Direct instruction override in the user turn
- **INJ-02** — Injection via tool output returned into context
- **INJ-03** — Injection via file or document metadata
- **INJ-04** — Invisible Unicode smuggling
- **INJ-05** — Injection via multimodal input
- **INJ-06** — Injection via inter-agent message
- **INJ-07** — Indirect injection via indexed document

### Jailbreak & Adversarial (JBK, 8)

- **JBK-01** — Persona and role-play framing
- **JBK-02** — Multi-turn gradual escalation
- **JBK-03** — Encoding and obfuscation
- **JBK-04** — Language and script switching
- **JBK-05** — Hidden context extraction
- **JBK-06** — Instruction-hierarchy conflict
- **JBK-07** — Token-level adversarial suffix
- **JBK-08** — Multi-layer manipulation

### RAG Security (RAG, 7)

- **RAG-01** — Corpus poisoning via the ingestion endpoint
- **RAG-02** — Retrieval hijack via embedding or keyword stuffing
- **RAG-03** — Cross-tenant retrieval leakage
- **RAG-04** — Chunk-boundary instruction smuggling
- **RAG-05** — Citation and provenance spoofing
- **RAG-06** — Injection via retrieved content
- **RAG-07** — Unauthorized source in retrieved docs

### Tool Abuse & Agent-Chain (TOOL, 15)

- **TOOL-01** — Invocation of a tool outside the allow-list
- **TOOL-02** — Argument injection into a permitted tool
- **TOOL-03** — Authorised tool called from an unauthorised context
- **TOOL-04** — Parameter type and format confusion
- **TOOL-05** — Chained calls reaching an out-of-scope resource
- **TOOL-06** — Recursive or looping invocation
- **TOOL-07** — Tool output treated as a trusted instruction
- **TOOL-08** — Tool response spoofing by an upstream node
- **TOOL-09** — Privilege inheritance across a session
- **TOOL-10** — Destructive tool reachable without confirmation
- **TOOL-11** — Egress-class tool used for exfiltration
- **TOOL-12** — Credential reuse across tools
- **TOOL-13** — Replay of a previously authorised call
- **TOOL-14** — Schema drift against documented interface
- **TOOL-15** — Information leakage through tool errors

### Memory & Context Poisoning (MEM, 5)

- **MEM-01** — Persisted instruction in long-term memory
- **MEM-02** — Cross-session memory bleed
- **MEM-03** — Cross-user memory contamination
- **MEM-04** — Eviction and overwrite manipulation
- **MEM-05** — Sensitive data retained beyond purpose

### AI Supply Chain (SUP, 4)

- **SUP-01** — Untrusted model artefact loading
- **SUP-02** — Dependency and plugin provenance
- **SUP-03** — Third-party component abuse
- **SUP-04** — Model or endpoint substitution

### Excessive Agency (AGY, 3)

- **AGY-01** — Action beyond delegated authority
- **AGY-02** — High-impact action without human confirmation
- **AGY-03** — Goal persistence after revocation

### MCP Permission & Chain (MCP, 12)

- **MCP-01** — Server resolved without authentication
- **MCP-02** — Server admitted without pinned identity
- **MCP-03** — Untrusted server accepted into the chain
- **MCP-04** — Chain depth beyond the safe threshold
- **MCP-05** — Tool poisoning via a server-supplied descriptor
- **MCP-06** — Permission scope: session versus server
- **MCP-07** — Caller identity accepted from the request payload
- **MCP-08** — Capability drift after resolve
- **MCP-09** — Chain tamper between resolve and use
- **MCP-10** — Cross-server data flow without isolation
- **MCP-11** — Server impersonation by name collision
- **MCP-12** — Fail-open on an unknown server

---

## Framework mapping

Cases and findings are traced to public control frameworks. 
Classification is controls mapping, not certification.

- **OWASP Top 10 for LLM Applications 2026** — LLM01 through LLM10
- **OWASP MCP Top 10 (Beta)** — MCP01 through MCP12
- **MITRE ATLAS** — AML.T0051, AML.T0053
- **NIST AI RMF** — MEASURE function
- **ISO/IEC 42001** — AI management system controls

A finding is raised only on a fail, with a reproducible proof of 
concept and a public classification.

---

## Case definition

One test case is one attack objective with:

- **Defined preconditions** — what must be true before the test runs
- **A pass/fail criterion** — the property the system must hold
- **A validated detection criterion** — accepted only if it flags a 
  violating response, clears a refusing response, and still flags a 
  refusal followed by compliance
- **A reproducible proof of concept** — runnable, exit 0 or 1
- **A public classification** — mapped to a framework control

Variants (encoding, language, framing) are execution detail inside 
a case, not additional cases.

---

## What's not in this repository

- Test inputs, payloads, or detection criteria
- Execution runners and harnesses
- Raw evidence and model responses
- The scoring model
- Client engagements and anonymized findings

The case library is delivered to clients during scoping, under NDA. 
Findings follow the format documented in 
[mcp-security-audit](https://github.com/RolandCaushaj/mcp-security-audit).

---

## About

[Logic4Hack](https://logic4hack.com) is an AI security firm 
specializing in adversarial testing of LLM, RAG, agent, and MCP 
systems. Two named researchers deliver every engagement. No 
subcontracting, no pyramid.

[Get in touch](https://logic4hack.com/contact) if you need to prove 
the security of an AI system to a customer, an auditor, or an insurer.

---

## License

Content in this repository is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). 
Code examples, if any, are licensed under MIT.

---

**Last updated**: October 2026  
**Status**: Active — cases revised as frameworks evolve
