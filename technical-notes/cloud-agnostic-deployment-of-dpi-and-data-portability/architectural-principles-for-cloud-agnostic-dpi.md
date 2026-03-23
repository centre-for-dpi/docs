# Architectural Principles for Cloud-Agnostic DPI

The following principles guide cloud-agnostic DPI architecture. For each principle, we identify the open standards and frameworks that enable portable implementation.

<figure><img src="../../.gitbook/assets/Capture d’écran 2026-03-23 à 12.49.38.png" alt=""><figcaption></figcaption></figure>

The diagram above illustrates the four layers of a portable DPI stack.

* Layer 1 (Cloud Platform) represents the interchangeable deployment target — any major cloud provider or an on-premises national data center.
* Layer 2 (Orchestration & Runtime) provides the common abstraction that makes this interchangeability possible, anchored by Kubernetes and OCI container standards.
* Layer 3 (Self-Hosted Infrastructure Components) covers the open-source middleware — databases, identity providers, API gateways, and observability tools — that replace proprietary managed services.
* Layer 4 (DPI Application Services) is where the building blocks sit: Digital Identity, Verifiable Credentials, Data Exchange, Payments, Registries, and Consent Management, all communicating through open standards like W3C VC, OID4VCI, OID4VP, and mDL/mDoc.
* Running vertically across all layers are four cross-cutting pillars: Infrastructure as Code, Security & Zero Trust, Data Portability, and Governance — disciplines that must be applied at every level rather than bolted on at one.
