# Can OSPS Replace Starlink Protocols or HTTPS?

## Short answer

Not today, and not in the same sense.

OSPS could replace some custom application transfer logic above satellite
links. It could complement or run over constellation networks. It should not
claim to replace HTTPS or Starlink internals without interoperability,
security, and performance evidence.

## Starlink

Starlink is an operational broadband system using user terminals, gateways,
satellites, RF links, and optical inter-satellite links. Official public pages
describe technology at a high level, but this project has not identified a
public interoperable wire specification for the internal network.

Therefore OSPS cannot honestly claim a drop-in replacement, direct
compatibility, or measured superiority. This is an inference from the public
source set—not a statement about every private Starlink component.

## What OSPS could replace

With maturity, OSPS might replace proprietary resumable payload APIs, ad hoc
AI model distribution, pass-by-pass retry databases, custom priority logic,
and application-specific transfer manifests.

It would still rely on routing, radios, optical terminals, gateways, spectrum,
and physical network control.

## What OSPS could run over

- commercial constellation IP service;
- QUIC or TLS on continuous links;
- BPv7 in a DTN;
- CCSDS-compatible spacecraft links;
- private optical transport; and
- licensed mission radios.

## HTTPS

HTTPS remains appropriate for websites, browser applications, cloud APIs,
content delivery, and continuous terrestrial paths.

OSPS is useful where no path exists for long periods, object state must survive
destroyed connections, contact capacity is scheduled, and orbital policy must
prioritize workloads.

```text
Web app -- HTTPS/HTTP3 --> Ground OSPS gateway
                                |
                         OSPS over BPv7
                                |
                         RF / optical link
                                |
                        Satellite OSPS node
```

## Requirements before replacement claims

OSPS needs a stable specification, independent implementations, audited
security, flow/congestion control, BPv7 integration, standardized identity,
expiration semantics, controlled benchmarks, hardware tests, and flight
heritage.

## References

- [Starlink technology](https://www.starlink.com/technology)
- [Starlink specifications](https://www.starlink.com/specifications)
- [RFC 9114 — HTTP/3](https://www.rfc-editor.org/rfc/rfc9114.html)
- [RFC 9000 — QUIC](https://www.rfc-editor.org/rfc/rfc9000.html)

## Acronym glossary

| Acronym | Meaning |
|---|---|
| API | Application Programming Interface |
| BPv7 | Bundle Protocol Version 7 |
| CCSDS | Consultative Committee for Space Data Systems |
| DTN | Delay/Disruption-Tolerant Networking |
| HTTP | Hypertext Transfer Protocol |
| HTTPS | HTTP over TLS |
| IP | Internet Protocol |
| OSPS | Orbital Streaming Protocol Secure |
| QUIC | IETF secure multiplexed transport over UDP |
| RF | Radio Frequency |
| TLS | Transport Layer Security |
