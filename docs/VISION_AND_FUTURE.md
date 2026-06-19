# OSPS Vision and Future

## The problem

Terrestrial networking usually assumes a usable path exists when a transfer
starts. Orbital systems violate that assumption: satellites leave ground
visibility, bandwidth changes during passes, links are asymmetric, and data
may wait onboard for hours.

OSPS proposes a streaming model where interruption is expected rather than
fatal.

## Vision

OSPS could connect orbital AI nodes, Earth-observation satellites,
inter-satellite relays, RF and optical ground stations, cloud systems, and
applications. Workloads would carry priority, deadline, integrity, and
delivery requirements.

## Goals

- Preserve acknowledged progress across total link loss.
- Prioritize control, inference, results, telemetry, and bulk data.
- Support RF, optical, and terrestrial adapters.
- Protect endpoint identity, confidentiality, and object integrity.
- Use predicted contacts without assuming predictions are perfect.
- Scale toward relay constellations and established DTN standards.

## Non-goals

OSPS should not replace every network layer, define radio modulation, use
hobby cryptography in flight, depend on one constellation vendor, or claim
knowledge of proprietary systems without public evidence.

## Future architecture

```text
Application -> Ground OSPS gateway -> RF contact -> Orbital compute node
                         \-> DTN backbone -> Optical relay -> Satellite
```

The strongest future design uses OSPS for orbital workload semantics, BPv7 for
multi-hop delay-tolerant forwarding, and QUIC/TLS for suitable continuous
segments.

## Why orbital AI changes traffic

Orbital AI creates model uplinks, compact inference requests, urgent results,
intermediate products, and large sensor datasets. Their urgency differs.
OSPS exposes those differences to scheduling instead of treating all bytes as
equally valuable.

## Success criteria

OSPS becomes credible after independent implementations interoperate, security
is reviewed, failure recovery is measured, BPv7/CCSDS integration exists,
hardware tests pass, and an eventual flight demonstration succeeds.

## Acronym glossary

| Acronym | Meaning |
|---|---|
| AI | Artificial Intelligence |
| BPv7 | Bundle Protocol Version 7 |
| CCSDS | Consultative Committee for Space Data Systems |
| DTN | Delay/Disruption-Tolerant Networking |
| OSPS | Orbital Streaming Protocol Secure |
| QUIC | IETF secure multiplexed transport over UDP |
| RF | Radio Frequency |
| TLS | Transport Layer Security |
