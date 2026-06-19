# OSPS Security Model

## Goals

Production OSPS needs mutual authentication, confidentiality, integrity,
replay resistance, workload authorization, key rotation/revocation, audit
records, and safe malformed-input handling.

## Threats

Attackers may eavesdrop, inject, modify, replay, impersonate nodes, exhaust
storage, abuse priority, exploit parsers, steal keys, compromise relays,
falsify contact plans, or deny the physical channel.

## Identity and trust

Nodes need mission-managed identities bound to credentials and authorization.
Options include mission PKI, provisioned public keys, hardware roots of trust,
short-lived certificates, and BPSec contexts.

## Cryptography

The simulation's educational cipher is not deployable. Production profiles
need audited AEAD, explicit nonce rules, strong key derivation, downgrade
protection, algorithm agility, and flight-suitable cryptographic libraries.

## Object and link security

Adjacent-link security protects one hop. Signed/authenticated manifests and
payload digests protect objects across storage and relays. A relay may forward
encrypted content without permission to read it.

## Availability

Implement authenticated admission, quotas, bounded sizes, safety reserves,
priority authorization, timeouts, duplicate suppression, and backpressure.

## Key lifecycle

Document manufacturing enrollment, launch provisioning, activation, rotation,
emergency revocation, ground credential loss, recovery, mission transfer, and
end-of-life zeroization.

## Verification

Publish a threat model, test vectors, fuzz results, replay/downgrade tests,
power-loss tests, penetration tests, and independent cryptographic review.

## Acronym glossary

| Acronym | Meaning |
|---|---|
| AEAD | Authenticated Encryption with Associated Data |
| BPSec | Bundle Protocol Security |
| HMAC | Hash-Based Message Authentication Code |
| OSPS | Orbital Streaming Protocol Secure |
| PKI | Public Key Infrastructure |
| RF | Radio Frequency |
