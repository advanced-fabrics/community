# Security Self-Assessment

## Scope

AdvFab observes and, when explicitly authorized, changes cloud-native network state. The principal assets are routing intent, topology and measurement data, provider credentials, workload identity and release integrity.

## Trust boundaries

- User and CLI to Kubernetes or Observation API.
- Controller to provider over authenticated transport.
- Provider to managed network systems.
- CI identity to GHCR and release metadata.
- Registry or mirror to the consumer cluster.

## STRIDE threats and controls

- Spoofing: short-lived mTLS identities, Kubernetes service accounts and optional SPIFFE identities.
- Tampering: signed desired state, immutable digests, provenance and admission-time verification.
- Repudiation: operation IDs, Kubernetes audit events and provider apply receipts.
- Information disclosure: least-privilege RBAC, redaction and prohibition of secrets in status or support bundles.
- Denial of service: bounded requests, deterministic server-side sampling, rate limits and reconciliation backoff.
- Elevation of privilege: observe-only defaults and independent provider capability, policy, RBAC and identity gates for apply.

This is an initial self-assessment and must be revised whenever a trust boundary or mutation capability changes.
