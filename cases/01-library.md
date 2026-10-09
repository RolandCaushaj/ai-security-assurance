# Case Library

61 test cases across 8 domains. Each case is one attack objective with defined preconditions and a pass/fail criterion.

Case titles are public. Payloads, detection criteria, and execution runners are proprietary and shared under NDA in client engagements.

---

## Prompt Injection (INJ, 7)

| ID | Objective |
|---|---|
| INJ-01 | Direct instruction override in the user turn |
| INJ-02 | Injection via tool output returned into context |
| INJ-03 | Injection via file or document metadata |
| INJ-04 | Invisible Unicode smuggling |
| INJ-05 | Injection via multimodal input |
| INJ-06 | Injection via inter-agent message |
| INJ-07 | Indirect injection via indexed document |

---

## Jailbreak & Adversarial (JBK, 8)

| ID | Objective |
|---|---|
| JBK-01 | Persona and role-play framing |
| JBK-02 | Multi-turn gradual escalation |
| JBK-03 | Encoding and obfuscation |
| JBK-04 | Language and script switching |
| JBK-05 | Hidden context extraction |
| JBK-06 | Instruction-hierarchy conflict |
| JBK-07 | Token-level adversarial suffix |
| JBK-08 | Multi-layer manipulation |

---

## RAG Security (RAG, 7)

| ID | Objective |
|---|---|
| RAG-01 | Corpus poisoning via the ingestion endpoint |
| RAG-02 | Retrieval hijack via embedding or keyword stuffing |
| RAG-03 | Cross-tenant retrieval leakage |
| RAG-04 | Chunk-boundary instruction smuggling |
| RAG-05 | Citation and provenance spoofing |
| RAG-06 | Injection via retrieved content |
| RAG-07 | Unauthorized source in retrieved docs |

---

## Tool Abuse & Agent-Chain (TOOL, 15)

| ID | Objective |
|---|---|
| TOOL-01 | Invocation of a tool outside the allow-list |
| TOOL-02 | Argument injection into a permitted tool |
| TOOL-03 | Authorised tool called from an unauthorised context |
| TOOL-04 | Parameter type and format confusion |
| TOOL-05 | Chained calls reaching an out-of-scope resource |
| TOOL-06 | Recursive or looping invocation |
| TOOL-07 | Tool output treated as a trusted instruction |
| TOOL-08 | Tool response spoofing by an upstream node |
| TOOL-09 | Privilege inheritance across a session |
| TOOL-10 | Destructive tool reachable without confirmation |
| TOOL-11 | Egress-class tool used for exfiltration |
| TOOL-12 | Credential reuse across tools |
| TOOL-13 | Replay of a previously authorised call |
| TOOL-14 | Schema drift against documented interface |
| TOOL-15 | Information leakage through tool errors |

---

## Memory & Context Poisoning (MEM, 5)

| ID | Objective |
|---|---|
| MEM-01 | Persisted instruction in long-term memory |
| MEM-02 | Cross-session memory bleed |
| MEM-03 | Cross-user memory contamination |
| MEM-04 | Eviction and overwrite manipulation |
| MEM-05 | Sensitive data retained beyond purpose |

---

## AI Supply Chain (SUP, 4)

| ID | Objective |
|---|---|
| SUP-01 | Untrusted model artefact loading |
| SUP-02 | Dependency and plugin provenance |
| SUP-03 | Third-party component abuse |
| SUP-04 | Model or endpoint substitution |

---

## Excessive Agency (AGY, 3)

| ID | Objective |
|---|---|
| AGY-01 | Action beyond delegated authority |
| AGY-02 | High-impact action without human confirmation |
| AGY-03 | Goal persistence after revocation |

---

## MCP Permission & Chain (MCP, 12)

| ID | Objective |
|---|---|
| MCP-01 | Server resolved without authentication |
| MCP-02 | Server admitted without pinned identity |
| MCP-03 | Untrusted server accepted into the chain |
| MCP-04 | Chain depth beyond the safe threshold |
| MCP-05 | Tool poisoning via a server-supplied descriptor |
| MCP-06 | Permission scope: session versus server |
| MCP-07 | Caller identity accepted from the request payload |
| MCP-08 | Capability drift after resolve |
| MCP-09 | Chain tamper between resolve and use |
| MCP-10 | Cross-server data flow without isolation |
| MCP-11 | Server impersonation by name collision |
| MCP-12 | Fail-open on an unknown server |

---

**Total: 61 cases across 8 domains.**
