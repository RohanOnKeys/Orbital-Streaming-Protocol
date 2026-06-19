# Implementing OSPS in Satellites

## Deployment model

OSPS should run as supervised flight software or a payload service, never as
an unrestricted process with direct command or radio authority.

```text
Payload applications
        |
OSPS API and scheduler
        |
Persistent queue and object store
        |
BPv7 / radio / optical adapters
        |
Flight computer and communications hardware
```

## Spacecraft components

- **OSPS service:** validates manifests, priorities, chunks, and delivery
  reports.
- **Persistent store:** survives resets with checksums, atomic recovery, and
  wear-aware storage.
- **Contact service:** combines mission plans with navigation and live link
  telemetry.
- **Scheduler:** balances safety, deadline, value, capacity, energy, and
  storage.
- **Adapters:** connect OSPS to TT&C, payload radios, optical terminals, BPv7,
  or IP transports.

## Flight integration

OSPS must obey command authority, safe mode, thermal/power limits, spectrum
licensing, attitude constraints, deterministic resource budgets, watchdogs,
and fault containment. Safety and command traffic require reserved capacity
outside ordinary payload queues.

## Hardware

A practical node needs a mission-appropriate processor, nonvolatile storage,
trusted key storage, clock/counters, bounded buffers, link telemetry, and
watchdog integration. AI missions may additionally use GPUs or accelerators.

## Ground segment

Ground gateways stage uplinks, authenticate spacecraft, receive and verify
objects, bridge to cloud applications, ingest contact plans, maintain audit
logs, and synchronize state across stations.

## Radio integration

Early experiments can carry OSPS through an existing packet modem or SDR. An
audio-jack receiver can collect demodulated narrowband VHF/UHF audio, but it
cannot receive high-rate S-band, X-band, Ka-band, or optical links.

Production integration belongs below OSPS in a modem/link adapter.

## Optical integration

An optical adapter reports acquisition, pointing state, weather, readiness,
capacity, and link margin. OSPS schedules around those conditions but must
never bypass terminal safety systems.

## Incremental path

1. Software simulation.
2. Separate-process network emulation.
3. Hardware-in-the-loop modem test.
4. Licensed ground RF test.
5. Hosted payload or CubeSat demonstration.
6. Multi-node relay experiment.
7. Qualification and operational deployment.

## Acronym glossary

| Acronym | Meaning |
|---|---|
| API | Application Programming Interface |
| BPv7 | Bundle Protocol Version 7 |
| GPU | Graphics Processing Unit |
| IP | Internet Protocol |
| OSPS | Orbital Streaming Protocol Secure |
| RF | Radio Frequency |
| SDR | Software-Defined Radio |
| TT&C | Telemetry, Tracking, and Command |
| UHF | Ultra High Frequency |
| VHF | Very High Frequency |
