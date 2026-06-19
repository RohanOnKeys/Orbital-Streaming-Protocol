# OSPS Standardization Strategy

## Why standardize

An orbital protocol matters only if independent systems interoperate safely.
A public repository is not itself a standard.

## Required specifications

OSPS needs normative documents for architecture, encoding, state machines,
manifests, acknowledgements, errors, priority/contact hints, security, BPv7
mapping, adapters, and conformance tests.

## Governance

Create a public change process, compatibility policy, security disclosure
channel, independent maintainers, implementation-neutral decision process,
intellectual-property policy, and published design records.

## Conformance

At least two independent implementations should pass byte vectors,
malformed-input tests, state traces, interruption/resumption, duplicate/replay,
extension negotiation, security vectors, and BPv7 integration.

## Possible standards paths

- open experimental application protocol;
- OSPS profile over BPv7;
- BPv7 extension blocks;
- IETF Internet-Draft;
- CCSDS engagement; or
- open industry specification and certification.

Expert and agency review should guide the venue.

## Compatibility principles

Reuse existing standards, negotiate versions, preserve unknown non-critical
extensions, reject unknown critical extensions, protect against downgrade, and
publish migration paths.

## Claims

Every public statement should distinguish implemented, simulated, measured,
proposed, future, and unsupported behavior. “Secure” is a requirement, not
proof that a prototype is secure.

## Acronym glossary

| Acronym | Meaning |
|---|---|
| BPv7 | Bundle Protocol Version 7 |
| BPSec | Bundle Protocol Security |
| CCSDS | Consultative Committee for Space Data Systems |
| IETF | Internet Engineering Task Force |
| OSPS | Orbital Streaming Protocol Secure |
| TLS | Transport Layer Security |
