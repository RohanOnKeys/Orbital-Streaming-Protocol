# OSPS Development Roadmap

## Research prototype

Demonstrate simulation, contact prediction, chunking, ACK/retry, priorities,
live processes, radio/optical scaffolds, and public documentation.

## Specification

Define canonical encoding, global stream IDs, manifests, negotiation,
selective ACKs, errors, expiration, cancellation, state machines, and test
vectors.

## Production security

Select audited AEAD/signature profiles, define replay and nonce rules, create
identity/authorization, add rotation/revocation, fuzz parsers, and obtain
independent review.

## DTN and CCSDS integration

Map streams to BPv7, use BPSec, adopt endpoint IDs/lifetimes, test established
DTN implementations, and document CCSDS service mappings.

## Performance engineering

Add native cryptography, efficient buffers, parallel streams, selective ACKs,
adaptive chunks, FEC options, storage batching, and energy-aware scheduling.

## Hardware-in-the-loop

Integrate SDR/modem adapters, licensed RF tests, optical emulation, power-loss
testing, flash-wear analysis, and ground-station systems.

## Flight demonstration

Complete mission assurance, safety separation, flight storage integration,
hosted payload/CubeSat tests, staged operations, and public results.

## Open standard

Establish neutral governance, public changes, implementation registry,
compatibility policy, conformance suite, and security response.

## Acronym glossary

| Acronym | Meaning |
|---|---|
| ACK | Acknowledgement |
| AEAD | Authenticated Encryption with Associated Data |
| BPv7 | Bundle Protocol Version 7 |
| BPSec | Bundle Protocol Security |
| CCSDS | Consultative Committee for Space Data Systems |
| DTN | Delay/Disruption-Tolerant Networking |
| FEC | Forward Error Correction |
| OSPS | Orbital Streaming Protocol Secure |
| RF | Radio Frequency |
| SDR | Software-Defined Radio |
