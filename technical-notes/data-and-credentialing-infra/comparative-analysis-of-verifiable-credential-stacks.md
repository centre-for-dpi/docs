# Comparative Analysis of Verifiable Credential Stacks

### Objective

The primary goal of this comparison is to highlight the unique strengths, technical capabilities, and architectural philosophies of each stack. By analyzing how these platforms handle data, connectivity, and trust, this document aims to guide stakeholders in choosing the solution that best fits their specific use cases—whether those involve government-grade offline identity, enterprise-scale multi-tenancy, or broad European ecosystem compliance.

### Neutrality and Pro Bono Disclaimer

This comparative analysis is conducted on a **pro bono** basis by the Centre for Digital Public Infrastructure. We maintain a **tech-neutral** stance and have not received any financial compensation or "kickbacks" from the analyzed technology providers. Our goal is to support countries in their digital transformation journey, regardless of the specific technology stack they choose to implement.

### Selection of Themes

The technical and operational dimensions explored in this document are not exhaustive. Instead, they represent the **most common themes and challenges** that arise during our country-level consultations. These dimensions were selected to address the specific needs of stakeholders looking for government-grade identity, enterprise scalability, or regulatory compliance.

### Document Structure

The analysis is organized into key technical and operational dimensions:

* **Standards & Data Formats**: An overview of the protocols (e.g., OpenID4VC, W3C) and data structures (e.g., JWT, SD-JWT, mDoc) supported by each provider.
* **Revocation & Security**: An examination of the mechanisms used to invalidate or manage the status of credentials in production environments.
* **Infrastructure & Deployment**: A look at **Multi-Tenancy** capabilities, distinguishing between stacks designed for single-use deployments and those built for scalable SaaS platforms.
* **Operational Connectivity**: A deep dive into **Offline Verification**, assessing how each stack utilizes technologies like BLE, NFC.
* **Trust Anchors**: A comparison of **DID Methods and Blockchain** integrations, ranging from ledger-agnostic web approaches to native Hyperledger Indy or Polygon support.
* **Hosting Options and Licensing:** A look at all implementation models and Licences.
* **Documentation Quality & Sustainability:** Examination of the accessibility of technical guides and the long-term viability.
* **Security, Privacy & Compliance:** how the stacks adhere to security-by-design, cryptographic standards, and regulatory frameworks.

### Assessment Baseline (Version Scope)

| Stack   | Version                            |
| ------- | ---------------------------------- |
| INJI    | Wallet: Mobile (0.21) / Web (0.15) |
| CREDEBL | 2.1                                |
| walt.id | Jan 2026 Release                   |
| QuarkID | Protocol v2.2                      |

### How to Read this Document

Each section includes a Feature Matrix that uses the following visual indicators to allow a quick at-a-glance comparison across stacks:

✅ Full support                                      ⚠️  Partial / In progress                             ❌ Not supported

### 1. Standards Support

**What is it?**&#x20;

These are the technical rules that allow wallets to communicate with each other.

**Importance**

It ensures interoperability. Without common standards, a user with a wallet from one provider couldn't present their credentials to a verifier using another provider

<table><thead><tr><th>Feature</th><th width="86" align="center">INJI</th><th width="122" align="center">CREDEBL</th><th width="102" align="center">walt.id</th><th width="105" align="center">QuarkID</th></tr></thead><tbody><tr><td><strong>W3C VC Data Model 1.1</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><p><strong>W3C VC Data Model 2.0</strong> </p><p><sub><em>CREDEBL via roadmap; QuarkID partial</em></sub></p></td><td align="center">✅</td><td align="center">⚠️</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><p><strong>OpenID4VCI</strong> </p><p><sub><em>Inji Draft 13; walt.id Draft 11 &#x26; 13</em></sub></p></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><p><strong>OpenID4VP</strong> </p><p><sub><em>Inji Draft 23; walt.id Draft 14 &#x26; 20</em></sub></p></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>IETF SD-JWT VC</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><p><strong>ISO 18013-5 (mDL/mDoc)</strong> </p><p><sub><em>Inji &#x26; CREDEBL in progress; walt.id full</em></sub></p></td><td align="center">⚠️</td><td align="center">⚠️</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>ISO 18013-7</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><p><strong>DIDComm v2</strong> </p><p><sub><em>CREDEBL via Aries; QuarkID native</em></sub></p></td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td><td align="center">✅</td></tr><tr><td><strong>SIOPv2</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">⚠️</td><td align="center">✅</td></tr><tr><td><strong>Hyperledger AnonCreds</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td><td align="center">❌</td></tr><tr><td><p><strong>eIDAS 2.0 / EUID ARF</strong> </p><p><sub><em>walt.id only - full alignment</em></sub></p></td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>EBSI / ESSIF</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>DIF Presentation Exchange</strong></td><td align="center">⚠️</td><td align="center">✅</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><strong>Trust over IP (ToIP)</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td><td align="center">❌</td></tr></tbody></table>

**Differences:**

**Inji** and **walt.id** focus on modern web-friendly standards such as W3C VC 2.0 and OpenID4VCI. **walt.id stands out as the only stack with native, full alignment for the European ecosystem (eIDAS 2.0 and EUID Architecture and Reference Framework).** CREDEBL maintains a robust focus on the Hyperledger Aries ecosystem and DIF protocols, supporting deployments from enterprise scale to national-scale digital trust ecosystems. **QuarkID** acts as a versatile hybrid, supporting modern OpenID flows while adding advanced peer-to-peer security through **DIDComm v2** and **SIOPv2**.

**Implications:**

Using **walt.id** is essential for projects requiring compliance with the **European Union Digital Identity (EUID)** wallet regulations or eIDAS 2.0. **Inji** is highly effective for integration within modern web-based mobile wallets in emerging markets. **CREDEBL** is the better fit for environments requiring the advanced privacy features of the AnonCreds ecosystem. **QuarkID** offers a unique advantage for those needing both standard web flows and highly secure, encrypted messaging between devices, particularly in the Latin American region.

### 2. Data Formats

**What is it?**

&#x20;The technical structure used to package credential information.

**Importance:**

This determines how "heavy" a credential is and what security algorithms it uses.

<table><thead><tr><th>Feature</th><th width="79" align="center">INJI</th><th width="112" align="center">CREDEBL</th><th width="100" align="center">walt.id</th><th width="102" align="center">QuarkID</th></tr></thead><tbody><tr><td><strong>JSON-LD with Linked Data Proofs</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>JWT (JWS)</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>SD-JWT</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>ISO mDoc (CBOR / 18013-5)</strong></td><td align="center">⚠️</td><td align="center">⚠️</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>AnonCreds / ZKP-CL</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td><td align="center">❌</td></tr><tr><td><strong>ZKP (other - BBS+ / etc.)</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td></tr><tr><td><strong>Ed25519</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>secp256k1 / secp256r1</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><strong>RSA</strong></td><td align="center">✅</td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>Decentralized Web Nodes (DWN)</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td></tr></tbody></table>

**Differences:**

**walt.id** offers the greatest versatility by supporting mobile identity formats like **mDoc (ISO 18013-5)**. **CREDEBL** specializes in **AnonCreds (ZKP)** signatures, while **Inji** prioritizes JSON-LD with Linked Data Proofs. **QuarkID** strengthens this category by offering support for **ZKP (Zero-Knowledge Proofs)** and modern formats like **SD-JWT**.

**Implications:**

Choosing **walt.id** allows an organization to issue digital driver’s licenses compatible with international transport standards. **CREDEBL** provides superior data protection through Zero-Knowledge Proofs, which allow users to prove attributes without revealing unnecessary underlying data.

### 3. Revocation Capabilities

**What is it?**&#x20;

The mechanism used to invalidate a credential before its expiration date.

**Importance**

This is vital for **trust**. A system without efficient revocation is not viable for legal or high-security use cases.

<table><thead><tr><th>Feature</th><th width="80" align="center">INJI</th><th width="111" align="center">CREDEBL</th><th width="100" align="center">walt.id</th><th width="103" align="center">QuarkID</th></tr></thead><tbody><tr><td><p><strong>Bitstring Status List (v1.0)</strong></p><p><sub><em>Inji experimental</em></sub></p></td><td align="center">⚠️</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><p><strong>StatusList2021 (W3C)</strong> </p><p><sub><em>Inji JSON-LD only</em></sub></p></td><td align="center">⚠️</td><td align="center">✅</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>RevocationList2020</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><p><strong>IETF Token Status List</strong> </p><p><sub><em>CREDEBL for SD-JWT &#x26; ISO mDoc</em></sub></p></td><td align="center">❌</td><td align="center">✅</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><p><strong>AnonCreds tails + accumulators</strong> </p><p><sub><em>CREDEBL production-ready</em></sub></p></td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td><td align="center">❌</td></tr><tr><td><strong>On-chain revocation registry</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td><td align="center">✅</td></tr><tr><td><strong>Suspension (separate purpose)</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><strong>Custom status reasons via policy</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><strong>Self-hosted API endpoint</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr></tbody></table>

**Differences:**&#x20;

**CREDEBL** stands out with the broadest multi-format revocation coverage: a production-ready solution based on "tails files" and accumulators for AnonCreds, plus IETF Token Status List support for SD-JWT and ISO mDoc credentials. This makes CREDEBL the only stack with production-grade revocation across all three major credential formats. **Inji** is currently in an experimental phase with Bitstring Status Lists. **walt.id** and **QuarkID** implement the more modern IETF Token/Bitstring Status Lists.

**Implications:**

For large-scale deployments that require the ability to invalidate thousands of credentials instantly, **CREDEBL** offers the most mature architecture. **walt.id** and **QuarkID** provide the most flexibility for defining custom status reasons (such as suspension) via policy.

### 4. Multi-Tenancy

**What is it?**

The ability for a single software installation to serve multiple independent clients or organizations securely

**Importance**

It reduces operational costs and complexity. It allows an organization to provide Credentials Issuing Service to various sub-departments or external clients

<table><thead><tr><th>Feature</th><th width="76" align="center">INJI</th><th width="111" align="center">CREDEBL</th><th width="97" align="center">walt.id</th><th width="103" align="center">QuarkID</th></tr></thead><tbody><tr><td><p><strong>Full multi-tenant architecture</strong> </p><p><sub><em>walt.id Enterprise Stack only</em></sub></p></td><td align="center">❌</td><td align="center">✅</td><td align="center">⚠️</td><td align="center">✅</td></tr><tr><td><strong>Shared agents (multi-tenant)</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">⚠️</td><td align="center">✅</td></tr><tr><td><strong>Dedicated agents (single-tenant)</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>Tenant-specific configurations</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">⚠️</td><td align="center">✅</td></tr><tr><td><strong>White-labeling / sub-accounts</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">⚠️</td><td align="center">✅</td></tr><tr><td><strong>Designed for SaaS deployments</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">⚠️</td><td align="center">✅</td></tr><tr><td><strong>Agent-agnostic architecture</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">⚠️</td><td align="center">❌</td></tr><tr><td><p><strong>National-scale deployment support</strong> </p><p><sub><em>Inji &#x26; CREDEBL proven at national scale</em></sub></p></td><td align="center">✅</td><td align="center">✅</td><td align="center">❌</td><td align="center">⚠️</td></tr></tbody></table>

**Differences CREDEBL** and **QuarkID** were designed specifically for **SaaS deployments**, allowing for the management of multiple clients through shared or dedicated agents. **Inji** is typically limited to a single issuer per deployment. **walt.id** provides this capability through its Enterprise Stack.

**Implications**

If your goal is to build a platform that offers "Credentialing as a Service" to third parties, **CREDEBL** or **QuarkID** are the most viable technical choices. It is equally important to note that **CREDEBL** also supports large-scale dedicated deployments for national government programs, not only SaaS models. **Inji** would be more expensive to scale in a multi-tenant SaaS scenario as it requires a separate instance for every client/issuer.

### 5. Offline Verification

**What is it?** The ability to present and validate an identity even when the issuer, user, or verifier does not have an active internet connection.

**Importance**

Critical for border control, rural areas, or emergency situations where connectivity is unreliable.

<table><thead><tr><th>Feature</th><th width="80" align="center">INJI</th><th width="116" align="center">CREDEBL</th><th width="98" align="center">walt.id</th><th width="106" align="center">QuarkID</th></tr></thead><tbody><tr><td><p><strong>BLE (Bluetooth Low Energy)</strong> </p><p><sub><em>Inji via Tuvali protocol</em></sub></p></td><td align="center">✅</td><td align="center">❌</td><td align="center">⚠️</td><td align="center">✅</td></tr><tr><td><strong>NFC</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>Wi-Fi Aware (mDL)</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>QR Code offline verification</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><p><strong>PixelPass QR compression</strong> </p><p><sub><em>Inji exclusive</em></sub></p></td><td align="center">✅</td><td align="center">❌</td><td align="center">❌</td><td align="center">❌</td></tr><tr><td><p><strong>Offline face authentication</strong> </p><p><sub><em>Inji exclusive</em></sub></p></td><td align="center">✅</td><td align="center">❌</td><td align="center">❌</td><td align="center">❌</td></tr><tr><td><strong>AnonCreds offline predicates</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td><td align="center">❌</td></tr><tr><td><strong>Status list caching</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><strong>Works without internet</strong></td><td align="center">✅</td><td align="center">❌</td><td align="center">⚠️</td><td align="center">✅</td></tr></tbody></table>

**Differences:**

**Inji** leads this section with native support for **Bluetooth Low Energy (BLE)** and offline face authentication. **QuarkID** matches this with peer-to-peer sharing via BLE and offline-scannable QR codes. **CREDEBL** relies primarily on online agent connectivity for verification.

**Implications:**

The primary advantage of **Inji** and **QuarkID** is their ability to function in government identity programs in low-connectivity areas where face-to-face verification is a **non-negotiable** requirement.

### 6. DID Methods & Blockchain

**What is it?**&#x20;

This defines where the root of trust for the identity lives (e.g., a web domain, a specific blockchain like Ethereum, etc).

**Importance:**

It determines the level of decentralization, cost, and censorship resistance of the system.

<table><thead><tr><th>Feature</th><th width="75" align="center">INJI</th><th width="112" align="center">CREDEBL</th><th width="96" align="center">walt.id</th><th width="102" align="center">QuarkID</th></tr></thead><tbody><tr><td><strong>did:web</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>did:key</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>did:jwk</strong></td><td align="center">✅</td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>did:peer</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td><td align="center">✅</td></tr><tr><td><strong>did:indy (Hyperledger Indy)</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td><td align="center">❌</td></tr><tr><td><strong>did:ebsi (EBSI/ESSIF)</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>did:cheqd</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>Polygon blockchain</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">⚠️</td><td align="center">✅</td></tr><tr><td><p><strong>zkSync Era / Rootstock / ETH</strong> </p><p><sub><em>QuarkID multichain EVM</em></sub></p></td><td align="center">❌</td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td></tr><tr><td><p><strong>X.509 Certificate Trust Anchoring</strong> </p><p><sub><em>CREDEBL: Trust Chain &#x26; Trust Registry</em></sub></p></td><td align="center">❌</td><td align="center">✅</td><td align="center">⚠️</td><td align="center">❌</td></tr><tr><td><strong>Ecosystem Governance framework</strong> <sub><em>CREDEBL: incl. IATA Travel PoC</em></sub></td><td align="center">❌</td><td align="center">✅</td><td align="center">⚠️</td><td align="center">⚠️</td></tr><tr><td><strong>Ledger-agnostic / custom VDR</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>No blockchain dependency</strong></td><td align="center">✅</td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td></tr></tbody></table>

**Differences:**&#x20;

**CREDEBL** has the deepest integration with traditional identity blockchains like **Hyperledger Indy** and Polygon, but also with x.509 Certificate-base trust anchoring. **Inji** and **walt.id** adopt a "blockchain-minimal" approach, prioritizing web-based methods like **did:web**. **QuarkID** leverages public EVM-compatible chains like **Polygon** to provide transparency without the complexity of private ledgers.

**Implications:**

**CREDEBL** is the preferred choice for organizations that need flexible trust governance: whether based on private distributed ledgers (Hyperledger Indy, Polygon), existing PKI infrastructure (X.509 certificates), or a structured ecosystem governance framework with a Trust Registry. **QuarkID** is ideal for those wanting public immutable transparency. **Inji** and **walt.id** offer easier integration with current web infrastructure, avoiding a hard dependency on a specific blockchain network.

### 7. Hosting Options & Licensing

**What is it?** The legal framework (license) and physical deployment models (Cloud/On-premise) available for the stack

**Importance:**

Determines the total cost of ownership, legal freedom to modify/redistribute, and the level of sovereignty over data residency.

<table><thead><tr><th>Feature</th><th width="106" align="center">INJI</th><th width="118" align="center">CREDEBL</th><th width="108" align="center">walt.id</th><th width="110" align="center">QuarkID</th></tr></thead><tbody><tr><td><strong>Cloud deployment</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>On-premise deployment</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><p><strong>Sovereign cloud support</strong> </p><p><sub><em>walt.id places specific emphasis</em></sub></p></td><td align="center">⚠️</td><td align="center">⚠️</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><strong>MIT License</strong></td><td align="center">✅</td><td align="center">❌</td><td align="center">❌</td><td align="center">❌</td></tr><tr><td><strong>Apache 2.0 License</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>Enterprise edition available</strong></td><td align="center">❌</td><td align="center">⚠️</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><p><strong>Foundation-backed</strong> </p><p><sub><em>MOSIP &#x26; Linux Foundation respectively</em></sub></p></td><td align="center">✅</td><td align="center">✅</td><td align="center">❌</td><td align="center">❌</td></tr></tbody></table>

**Differences**

Most stacks utilize the **Apache 2.0** license, while **INJI** uses the even more permissive MIT license. All support flexible hosting, but walt.id places a specific emphasis on "sovereign cloud" environments.

**Implications**

High flexibility for governments to maintain data sovereignty through on-premise hosting across all stacks. The choice of **MIT** vs. **Apache 2.0** primarily affects how organizations can redistribute modified versions of the core software.

### 8. Documentation Quality & Sustainability&#x20;

**What is it?**

The accessibility of technical guides and the long-term viability/funding of the project.

**Importance:**

High-quality documentation reduces implementation time; project sustainability ensures long-term maintenance and updates.

<table><thead><tr><th>Feature</th><th width="110" align="center">INJI</th><th width="113" align="center">CREDEBL</th><th width="106" align="center">walt.id</th><th width="112" align="center">QuarkID</th></tr></thead><tbody><tr><td><strong>Extensive developer documentation</strong></td><td align="center">✅</td><td align="center">⚠️</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><strong>API reference docs</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><strong>Quickstart / sandbox guides</strong></td><td align="center">✅</td><td align="center">⚠️</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>Active developer community</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><p><strong>Foundation / institutional backing</strong> </p><p><sub><em>MOSIP &#x26; Linux Foundation</em></sub></p></td><td align="center">✅</td><td align="center">✅</td><td align="center">❌</td><td align="center">⚠️</td></tr><tr><td><strong>Regular release cadence</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><strong>Open roadmap published</strong></td><td align="center">⚠️</td><td align="center">⚠️</td><td align="center">✅</td><td align="center">❌</td></tr></tbody></table>

**Differences**&#x20;

**walt.id** currently offers the most structured documentation for developers. **INJI** and **CREDEBL** benefit from the long-term stability of major international foundations (MOSIP and Linux Foundation).

**Implications**

Projects with stronger institutional or foundation backing (Inji, CREDEBL) offer higher long-term peace of mind for national-scale infrastructure.

### 9. Security, Privacy, & Compliance

**What is it?**&#x20;

Adherence to security-by-design, cryptographic standards, and regulatory frameworks.

**Importance**

Essential for protecting citizen data and meeting legal requirements (such as GDPR or national data laws).

<table><thead><tr><th width="335.20001220703125">Feature</th><th width="87" align="center">INJI</th><th width="108.5999755859375" align="center">CREDEBL</th><th width="98.7999267578125" align="center">walt.id</th><th width="104" align="center">QuarkID</th></tr></thead><tbody><tr><td><strong>Security-by-design principles</strong></td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td><td align="center">✅</td></tr><tr><td><strong>Key management infrastructure</strong></td><td align="center">⚠️</td><td align="center">⚠️</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><strong>Auditability / audit trails</strong></td><td align="center">⚠️</td><td align="center">⚠️</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><strong>GDPR-aligned design</strong></td><td align="center">⚠️</td><td align="center">✅</td><td align="center">✅</td><td align="center">⚠️</td></tr><tr><td><strong>eIDAS 2.0 compliance-ready</strong></td><td align="center">❌</td><td align="center">❌</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><strong>ZKP / selective disclosure</strong></td><td align="center">❌</td><td align="center">✅</td><td align="center">⚠️</td><td align="center">✅</td></tr><tr><td><strong>Hardware security module (HSM)</strong></td><td align="center">❌</td><td align="center">⚠️</td><td align="center">✅</td><td align="center">❌</td></tr><tr><td><p><strong>Biometric authentication</strong> </p><p><sub><em>Inji offline face auth</em></sub></p></td><td align="center">✅</td><td align="center">❌</td><td align="center">❌</td><td align="center">❌</td></tr><tr><td><p><strong>Govt-grade hardening (out-of-box)</strong> </p><p><sub><em>All stacks require implementer hardening</em></sub></p></td><td align="center">⚠️</td><td align="center">⚠️</td><td align="center">⚠️</td><td align="center">⚠️</td></tr></tbody></table>

**Differences**&#x20;

**walt.id** provides the most comprehensive focus on compliance-ready features like auditability. The other stacks prioritize core cryptographic security, leaving specific regulatory "hardening" to the implementer.

**Implications**&#x20;

**walt.id** is particularly well-suited for highly regulated environments (like the EU) where auditability and key management are primary requirements. For other stacks, governments should allocate resources specifically for security hardening during the deployment phase.



### **🔑 Overall Key Distinctions:**&#x20;

**INJI excels at offline capabilities** with BLE and face authentication, making it ideal for low-connectivity environments and government identity programs. Strong focus on mobile-first experience. Takes a blockchain-minimal approach with web-based DIDs.  **So consider Inji if you need a mobile-first solution for government programs in low-connectivity environments.**

**CREDEBL** provides the most comprehensive multi-tenancy and enterprise features, supporting both traditional SSI (AnonCreds) and modern standards. Best for organizations building SaaS platforms or managing multiple clients. **Strongest blockchain support** with native Hyperledger Indy and Polygon integration, ideal for ledger-based implementations. **So consider CREDEBL if you are building population-scale digital trust ecosystems — including Decentralized National ID, Digital Travel Credentials, Academic Credentials, eKYC, or Health Data Exchange — with a focus on self-sovereign identity, privacy-preserving architectures, and local data protection requirements.**

**walt.id** offers the most complete standards compliance across both stacks (Community & Enterprise), with strong eIDAS 2.0 alignment. Enterprise Stack provides production-ready multi-tenancy with extensive management tools. **Broadest DID method support** with focus on European ecosystem (EBSI) and extensibility. **So consider walt.id if you need maximum standards compliance, alignment with European regulations (eIDAS), and high extensibility.**&#x20;

**QuarkID** stands out as a versatile hybrid that balances modern web standards (OpenID4VC) with advanced peer-to-peer security through DIDComm v2. It offers native multi-tenancy for SaaS models and leverages public EVM-compatible chains like Polygon to provide transparency without the complexity of private ledgers. **So consider QuarkId if you want a balanced, multi-tenant platform that combines public blockchain transparency with high-security encrypted messaging**
