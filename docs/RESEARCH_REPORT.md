# OSPS Research Report

## Scope

This report summarizes evidence from the North Star simulation work. It is not
a flight test, real RF/optical measurement, or Starlink comparison.

## Demonstrated experiment

Three standalone processes transferred a file through a contact-controlled TCP
channel driven by static TLE-based Skyfield predictions. The channel refused
connections outside passes and closed sockets at pass boundaries.

| Metric | Result |
|---|---|
| Payload | 2 MiB |
| Chunk size | 32 KiB |
| Chunks | 64 |
| Link behavior | Multiple complete interruptions |
| Resume | Persisted receiver chunk state |
| Integrity | Matching SHA-256 |
| Application framing efficiency | Approximately 99.756% |

Accelerated orbital time made the test runnable quickly. Wall-clock throughput
is not a real radio or optical link-rate measurement.

## What this proves

- independent endpoints reconnect;
- acknowledged progress survives destroyed connections;
- receiver state can persist;
- final output can be verified end to end; and
- predicted contacts can control a real socket path.

## What this does not prove

- flight readiness;
- real modem or laser operation;
- superiority over HTTP/3, QUIC, BPv7, or Starlink;
- production security;
- multi-hop routing;
- accurate RF capacity; or
- constellation scalability.

## Efficiency

At 32 KiB chunks, the prototype adds about 80 application bytes for the DATA
frame and ACK, producing approximately 99.756% payload efficiency before
TCP/IP, retransmission, modem, and FEC overhead.

Mission efficiency must also measure energy, storage writes, acquisition time,
idle contact capacity, missed deadlines, and retransmitted bytes.

## Required comparison

Run identical contacts and losses against OSPS, resumable HTTPS, HTTP/3/QUIC,
BPv7, raw TCP, and a non-resumable baseline. Report goodput, total bytes, CPU,
memory, disk writes, energy estimate, completion time, and success rate.

## Conclusion

OSPS has prototype evidence for disruption recovery. Its future value depends
on security, standards integration, hardware tests, and transparent
comparative measurement.

## Acronym glossary

| Acronym | Meaning |
|---|---|
| BPv7 | Bundle Protocol Version 7 |
| FEC | Forward Error Correction |
| HTTP | Hypertext Transfer Protocol |
| HTTPS | HTTP over TLS |
| OSPS | Orbital Streaming Protocol Secure |
| QUIC | IETF secure multiplexed transport over UDP |
| RF | Radio Frequency |
| SHA-256 | Secure Hash Algorithm, 256-bit |
| TCP | Transmission Control Protocol |
| TLE | Two-Line Element set |
