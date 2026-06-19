# OSPS — Orbital Streaming Protocol Secure

OSPS is a proposed disruption-tolerant protocol for secure, prioritized data
streaming between orbital compute nodes, satellites, ground stations, and
applications on Earth.

OSPS treats storage, resumption, priority, and contact awareness as normal
protocol behavior. It is currently a research proposal and simulation-backed
design—not an approved standard, flight-qualified implementation, Bundle
Protocol replacement, or description of Starlink's proprietary internals.

## Documentation

| Page | Purpose |
|---|---|
| [Vision and future](docs/VISION_AND_FUTURE.md) | Problem, goals, use cases, and direction |
| [Protocol architecture](docs/PROTOCOL_ARCHITECTURE.md) | Layers, framing, sessions, QoS, ACKs, and resumption |
| [Satellite implementation](docs/SATELLITE_IMPLEMENTATION.md) | Integration into spacecraft and ground systems |
| [Benefits and use cases](docs/BENEFITS_AND_USE_CASES.md) | Value for AI, telemetry, science, and relays |
| [Security model](docs/SECURITY_MODEL.md) | Threats, cryptography, identity, and keys |
| [Protocol comparisons](docs/PROTOCOL_COMPARISONS.md) | HTTPS, QUIC, BPv7, TCP, and satellite links |
| [Starlink and HTTPS](docs/STARLINK_AND_HTTPS.md) | What OSPS could replace or complement |
| [Roadmap](docs/ROADMAP.md) | Path from prototype to flight-ready standard |
| [Research report](docs/RESEARCH_REPORT.md) | Evidence, results, and limitations |
| [Deployment reference](docs/DEPLOYMENT_REFERENCE.md) | Example RF, optical, relay, and ground designs |
| [Standardization](docs/STANDARDIZATION.md) | Governance, conformance, and standards path |

## Design position

OSPS should combine:

- contact-aware transfer planning;
- durable store-and-forward state;
- resumable chunk streams;
- workload-aware priority;
- RF and optical link independence;
- end-to-end object integrity; and
- eventual interoperability with DTN standards.

The credible future is an application and streaming profile over proven
transport, security, and DTN foundations—not an isolated reinvention of every
network layer.

## References

- [RFC 9000 — QUIC](https://www.rfc-editor.org/rfc/rfc9000.html)
- [RFC 9114 — HTTP/3](https://www.rfc-editor.org/rfc/rfc9114.html)
- [RFC 9171 — Bundle Protocol Version 7](https://www.rfc-editor.org/rfc/rfc9171.html)
- [CCSDS Bundle Protocol](https://public.ccsds.org/Pubs/734x2b1.pdf)
- [Starlink technology](https://www.starlink.com/technology)

## Acronym glossary

| Acronym | Meaning |
|---|---|
| ACK | Acknowledgement |
| AI | Artificial Intelligence |
| BPv7 | Bundle Protocol Version 7 |
| CCSDS | Consultative Committee for Space Data Systems |
| DTN | Delay/Disruption-Tolerant Networking |
| HTTP | Hypertext Transfer Protocol |
| OSPS | Orbital Streaming Protocol Secure |
| QoS | Quality of Service |
| QUIC | IETF secure multiplexed transport over UDP |
| RF | Radio Frequency |
| TLS | Transport Layer Security |
