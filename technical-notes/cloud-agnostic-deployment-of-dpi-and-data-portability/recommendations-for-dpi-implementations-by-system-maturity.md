# Recommendations for DPI Implementations by System Maturity

Rather than a one-size-fits-all approach, cloud-agnostic recommendations should be calibrated to a system's maturity and criticality.

**Tier 1 — Foundation (All DPI Deployments)**

Every DPI implementation, regardless of scale, should adopt these practices from the outset:

* **Containerize applications** using OCI-standard container images and orchestrate through Kubernetes.
* **Codify infrastructure** with provider-agnostic tools such as Terraform or Pulumi, stored in version control.
* **Default to open standards** — prefer open-source databases (PostgreSQL, MySQL), S3-compatible object storage, and standard authentication protocols (OpenID Connect, OAuth 2.0) over proprietary alternatives.
* **Document all provider-specific dependencies** and the justification for each.

_Outcomes optimized: reduced time-to-build, baseline security, avoidance of early lock-in._

**Tier 2 — Growth (Systems Handling Significant User Populations)**

As systems grow to serve large user bases, additional measures become cost-effective:

* **Design for data portability** — implement comprehensive data export in standardized formats (JSON, CSV, W3C Verifiable Credentials) from the outset.
* **Invest in abstraction layers judiciously** — create thin abstractions for components most likely to require portability (storage, identity, messaging), but avoid over-engineering.
* **Test portability regularly** — periodically deploy to alternative infrastructure to validate assumptions and detect drift.

_Outcomes optimized: data portability, service quality, migration flexibility._

**Tier 3 — Systemically Critical (Infrastructure Essential to the Economy)**

When a DPI system becomes systemically important — national identity, core payments, civil registry — the full cloud-agnostic posture is warranted:

* **Multi-provider deployment** — active-active or primary-secondary configurations across at least two independent providers.
* **Contractual exit strategies** — service level agreements must include data export requirements, exit assistance provisions, and minimum notice periods.
* **Formal architectural review** — regular review of all provider-specific dependencies with explicit portability trade-off decisions.
* **Minimum downtime targets** — design for near-zero downtime during provider transitions.

_Outcomes optimized: resilience, zero downtime, full sovereignty, vendor negotiation leverage._
