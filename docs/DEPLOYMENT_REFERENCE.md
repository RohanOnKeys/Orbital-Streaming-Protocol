# OSPS Deployment Reference

## Minimal demonstration

```text
Laptop sender -> impaired channel -> laptop receiver
```

This validates framing, resumption, storage, and logs.

## Single-satellite mission

```text
Mission cloud -> Ground OSPS gateway -> Licensed RF link
                                      -> Satellite OSPS service
                                      -> Onboard storage and AI
```

Use HTTPS/QUIC between cloud and ground where suitable, established spacecraft
link stacks below OSPS, and durable manifests at both endpoints.

## Relay constellation

```text
Ground A <-RF-> Satellite A <-Optical-> Satellite B <-RF-> Ground B
```

This requires routing, retention responsibility, endpoint identity, duplicate
suppression, and policy. BPv7 should be the default candidate for forwarding.

## Radio paths

Narrowband experimental receive-only path:

```text
Antenna -> VHF/UHF receiver -> audio output -> PC input -> decoder
```

Higher-rate path:

```text
Antenna -> LNA/filter -> SDR or modem -> link adapter -> OSPS
```

An audio jack cannot receive S-band, X-band, Ka-band, or optical signals.

## Optical path

```text
Optical terminal -> detector/modem -> optical adapter -> OSPS
```

Inputs include pointing, acquisition, weather, link margin, capacity, and
safety status. OSPS must not override optical safety controls.

## Storage sizing

```text
generation rate x maximum outage x safety factor + operational reserve
```

Reserve storage for safety and command classes so bulk data cannot consume all
capacity.

## Observability

Record object IDs, endpoints, priority, contact, acknowledged bytes, retries,
storage, integrity, delivery time, and security events—never secret keys.

## Acronym glossary

| Acronym | Meaning |
|---|---|
| AI | Artificial Intelligence |
| BPv7 | Bundle Protocol Version 7 |
| LNA | Low-Noise Amplifier |
| OSPS | Orbital Streaming Protocol Secure |
| QUIC | IETF secure multiplexed transport over UDP |
| RF | Radio Frequency |
| SDR | Software-Defined Radio |
| UHF | Ultra High Frequency |
| VHF | Very High Frequency |
