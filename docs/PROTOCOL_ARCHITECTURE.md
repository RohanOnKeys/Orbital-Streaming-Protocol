# OSPS Protocol Architecture

## Principle

OSPS separates application delivery semantics from the physical link.
Resumable streams, priorities, identities, and integrity remain stable across
VHF, UHF, S-band, X-band, Ka-band, optical, and terrestrial links.

```text
+------------------------------------------------------+
| AI, telemetry, science, control, software            |
+------------------------------------------------------+
| OSPS streams, priority, manifests, resume, integrity |
+------------------------------------------------------+
| BPv7, QUIC, TCP, modem, or link adapter              |
+------------------------------------------------------+
| RF, optical, Ethernet, or vendor network             |
+------------------------------------------------------+
```

## Core objects

- **Session:** authenticated peer and capability context.
- **Stream:** logical ordered workload or object transfer.
- **Chunk:** independently identifiable resumable transfer unit.
- **Manifest:** object metadata, digest, chunks, encoding, and delivery policy.
- **Contact:** scheduled opportunity with capacity, latency, cost, direction,
  and confidence.

## Workload classes

Recommended order:

1. emergency and spacecraft safety;
2. command and control;
3. interactive inference and results;
4. health telemetry;
5. scientific products;
6. software/configuration; and
7. model weights and bulk replication.

Priority must remain subject to mission safety authorization and fairness.

## Reliability

The prototype uses per-chunk ACK and retry. Production OSPS should add
selective ACK ranges, duplicate suppression, expiration, cancellation,
delivery reports, durable sender/relay state, and optional erasure/FEC blocks.

## Scheduling

The scheduler should consider priority, deadline, remaining size, estimated
contact capacity, energy, storage pressure, link confidence, and fairness.
When no contact exists, retained chunks wait without losing progress.

## Congestion and flow control

OSPS should combine contact-plan limits, receiver storage feedback, adapter
telemetry, and transport congestion control. Dedicated scheduled links and
shared Internet paths require different policies.

## BPv7 relationship

A credible path maps OSPS manifests and streams onto BPv7 bundles or extension
blocks. BPv7 supplies forwarding, endpoint identity, lifetimes, and
convergence layers; OSPS supplies workload and streaming semantics.

## Acronym glossary

| Acronym | Meaning |
|---|---|
| ACK | Acknowledgement |
| BPv7 | Bundle Protocol Version 7 |
| FEC | Forward Error Correction |
| OSPS | Orbital Streaming Protocol Secure |
| QoS | Quality of Service |
| RF | Radio Frequency |
| TCP | Transmission Control Protocol |
| UHF | Ultra High Frequency |
| VHF | Very High Frequency |
