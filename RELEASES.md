# Release Process

Releases use semantic versioning. A release candidate requires green API compatibility, conformance, upgrade, security and supply-chain checks. Final 1.0 approval requires two non-author maintainer reviews and a seven-day stable reference-runtime observation window.

Release artifacts are immutable and identified by digest. GitHub OIDC produces keyless Cosign signatures, SLSA provenance and SBOM attestations. GHCR is authoritative; mirrors may only copy verified digests and attestations.

GA deprecations remain supported for at least two minor releases and six months, whichever is longer. Breaking changes require a new major version and an accepted AFEP.
