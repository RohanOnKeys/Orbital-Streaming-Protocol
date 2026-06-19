# OSPS Protocol Comparisons

## Summary

| Capability | OSPS proposal | HTTPS/TCP | HTTP/3/QUIC | BPv7 |
|---|---|---|---|---|
| Web semantics | No | Yes | Yes | No |
| Continuous-link maturity | Low | High | High | Adapter-dependent |
| Durable object resume | Native goal | Application-defined | Application-defined | Natural fit |
| Contact plans | Native goal | No | No | Operations/routing layer |
| Multi-hop DTN | Future | No | No | Yes |
| Workload priority | Native goal | Application-defined | Streams/application | Policy-dependent |
| Standard security | Not yet | TLS | TLS 1.3 integrated | BPSec |
| Interoperability | Research only | Global | Global | DTN ecosystem |

## HTTPS and TCP

HTTPS is ideal for web APIs, browsers, caches, and established identity.
Applications can add resumable ranges, ETags, multipart uploads, and object
stores. OSPS differs by making retained orbital progress and contact-aware
scheduling central. It should not replace HTTPS for ordinary web traffic.

TCP supplies reliable ordered bytes while a connection exists, but it does not
define persistent object state after that connection disappears.

## HTTP/3 and QUIC

HTTP/3 over QUIC provides secure multiplexed streams, per-stream flow control,
modern congestion control, low-latency establishment, and path migration.
These are major advantages over the current OSPS prototype.

OSPS adds value at the object layer by preserving work through long periods
with no path. An application can also build that over HTTP/3; OSPS aims to
standardize it for orbital workloads.

## BPv7 and CCSDS

BPv7 is designed for delay-tolerant store-and-forward networking. It defines
bundles, endpoint IDs, lifetimes, processing, extensions, status reports, and
convergence-layer adaptation.

OSPS should become a streaming/workload profile over BPv7 rather than compete
with its mature multi-hop model. Applicable CCSDS telemetry, command, file
delivery, security, and DTN standards should be reused.

## Proprietary constellation systems

Without a public wire specification and reproducible benchmark, OSPS cannot
claim drop-in compatibility or superiority over a proprietary constellation
network. Its potential differentiator is openness: public specifications,
conformance tests, multiple implementations, and medium-independent workload
semantics.

## Fair performance comparison

Use identical payloads, contacts, losses, hardware, security levels,
persistence requirements, and success criteria. Until then, claim prototype
outcomes—not universal speed leadership.

## References

- [RFC 9000 — QUIC](https://www.rfc-editor.org/rfc/rfc9000.html)
- [RFC 9114 — HTTP/3](https://www.rfc-editor.org/rfc/rfc9114.html)
- [RFC 9171 — BPv7](https://www.rfc-editor.org/rfc/rfc9171.html)
- [CCSDS Bundle Protocol](https://public.ccsds.org/Pubs/734x2b1.pdf)

## Acronym glossary

| Acronym | Meaning |
|---|---|
| BPv7 | Bundle Protocol Version 7 |
| BPSec | Bundle Protocol Security |
| CCSDS | Consultative Committee for Space Data Systems |
| DTN | Delay/Disruption-Tolerant Networking |
| ETag | HTTP Entity Tag |
| HTTP | Hypertext Transfer Protocol |
| HTTPS | HTTP over TLS |
| OSPS | Orbital Streaming Protocol Secure |
| QUIC | IETF secure multiplexed transport over UDP |
| TCP | Transmission Control Protocol |
| TLS | Transport Layer Security |
