---
description: >-
  DIDs provide a way to establish cryptographically verifiable digital
  identities without relying on a central authority. When used with verifiable
  credentials, they create a trust framework that's both
---

# DIDs & PKI in Verifiable Credentials

### **Credential Issuance**

1. **Identity Establishment**: Both issuer and holder create their DIDs. Each DID is associated with a public-private key pair, where the DID document contains the public key.
2. **Claim Assembly**: The issuer prepares the credential claims (attributes about the holder) and includes their own DID as the issuer and the holder's DID as the subject.
3. **Credential Formation**: The issuer creates a verifiable credential document that includes:
   * The claims about the holder
   * Metadata (issuance date, expiration date, etc.)
   * The issuer's DID
   * The holder's DID

### **Credential Signing**

1. **Hash Generation**: The issuer generates a cryptographic hash of the credential content.
2. **Digital Signature**: The issuer signs this hash using their private key associated with their DID.
3. **Proof Addition**: The signature (proof) is attached to the credential, typically in a format like a JSON-LD proof.
4. **Issuance**: The complete signed credential is provided to the holder, who stores it in their digital wallet.

### **Credential Verification**

1. **Presentation**: When verification is needed, the holder creates a verifiable presentation containing the credential, optionally signs it with their private key, and shares it with a verifier.
2. **DID Resolution**: The verifier resolves the issuer's DID to retrieve the associated DID document containing the issuer's public key.
3. **Signature Verification**: The verifier uses the issuer's public key to verify that the signature on the credential is valid and was created by the claimed issuer.
4. **Validation Checks**: The verifier confirms:
   * The credential hasn't expired
   * The credential hasn't been revoked (often via a registry or status service)
   * The credential schema is valid
   * The issuer is trusted for this type of credential

This process establishes a trust triangle between issuer, holder, and verifier without requiring them to interact directly or rely on a central authority.

## **DIDs vs. Traditional PKI in Verifiable Credentials**

Traditional Public Key Infrastructure (PKI) and DID-based systems both provide ways to verify identities and authenticate data, but they differ significantly in their approach, trust model, and flexibility.

### **Fundamental Differences**

#### **Trust Model**

* **Traditional PKI**: Hierarchical trust with Certificate Authorities (CAs) at the top. Trust flows downward through a chain of certificates.
* **DID**: Decentralized trust without a central authority. Each entity can create and manage their own identifier independently.

#### **Identity Control**

* **Traditional PKI**: Identities are issued by and dependent on third parties (CAs). The CA can revoke certificates unilaterally.
* **DID**: Self-sovereign identity where individuals create and control their own identifiers. No external entity can revoke your DID.

#### **Discovery Mechanism**

* **Traditional PKI**: Certificate directories or authority lookup services.
* **DID**: DID resolvers that can find DID Documents through various methods (blockchains, distributed ledgers, decentralized networks).

### **Specific Differences in Credential Workflows**

#### **Issuance**

* **PKI**:
  * Requires obtaining a certificate from a CA
  * Identity validation often requires human intervention or documentation
  * Typically involves payment to a CA
* **DID**:
  * Anyone can generate their own DID instantly without approval
  * No inherent cost to create a basic DID
  * Multiple methods ("DID methods") for creating identifiers using different technologies

#### **Signing**

* **PKI**:
  * Signs with private key associated with a CA-issued certificate
  * Certificate includes identity information embedded within it
  * Signatures are validated against the CA hierarchy
* **DID**:
  * Signs with private key referenced in the DID Document
  * Identity information is separate from verification methods
  * Signatures are validated using public keys from the DID Document

#### **Verification**

* **PKI**:
  * Verifies through certificate chains up to a trusted root CA
  * Often requires certificate revocation checking through CRLs or OCSP
  * Trust is determined by browser/OS-included root certificates
* **DID**:
  * Resolves DID to retrieve the DID Document with verification methods
  * May check revocation through method-specific mechanisms
  * Trust is contextual and determined by the verifier's trust framework

### **Technical Implementation Differences**

* **Key Management**:
  * PKI typically uses X.509 certificates with predefined fields
  * DIDs use flexible key representation defined in DID Documents
* **Cryptographic Flexibility**:
  * PKI generally relies on specific algorithms (often RSA, ECDSA)
  * DIDs support varied cryptographic methods and can be updated over time
* **Protocols**:
  * PKI uses protocols like PKIX, OCSP, and CRL
  * DIDs use HTTP-based resolution, ledger queries, or other method-specific resolution
* **Proof Format**:
  * PKI typically uses PKCS formats
  * DIDs often use JSON-LD Proofs or other web-native formats

DIDs and PKI can also be complementary - some DID methods use PKI principles internally, and some credential systems combine elements of both approaches.

In a DID system, anyone can technically create a DID and issue credentials, but several mechanisms prevent effective impersonation:

### **Preventing Issuer Impersonation**

#### **1. DID Control and Ownership**

* Each DID has unique cryptographic keys that only the controller possesses
* You cannot create a credential that verifies against another issuer's DID unless you have their private keys
* Creating your own DID doesn't allow you to impersonate an existing issuer

#### **2. Trust Registries and Frameworks**

* Verifiers typically maintain or reference "trust lists" of authorized issuer DIDs
* These registries map known organizations to their authorized DIDs
* A credential from an unknown or untrusted DID would be rejected

#### **3. Verifiable Issuer Credentials**

* Legitimate issuers often have their own verifiable credentials from higher authorities
* Example: A university might have a credential from an accreditation body
* These create chains of trust similar to certificate chains in PKI

#### **4. Domain Linkage**

* Many DID methods support cryptographically linking DIDs to web domains
* Services like DID Configuration and Well-Known DID Configuration allow domain owners to prove they control specific DIDs
* Verifiers check that credentials come from DIDs linked to expected domains

#### **5. Reputation Systems**

* Some ecosystems implement reputation scoring for issuers
* Historical verification of legitimate credentials builds trust over time

### **Real-World Example**

If someone tries to impersonate a university:

1. They create their own DID (not the university's actual DID)
2. They issue credentials listing themselves as the university
3. When a verifier checks the credential:
   * They resolve the issuer's DID and find it's not on their trusted list for that university
   * The DID isn't linked to the university's domain
   * The issuer has no verifiable credentials from educational accreditation bodies

The impersonation fails not because they can't create DIDs or credentials, but because verifiers implement trust frameworks that reject credentials from untrusted sources.

This highlights why the verifier's role in establishing what DIDs they trust is crucial - it's similar to how browsers decide which certificate authorities to trust in PKI, but more flexible and contextual.

### **Offline DID verification**

### For DID Web (Decentralized Identifiers on the Web), offline verification works through a combination of cryptographic techniques and local verification of previously downloaded data. Here's how it typically functions:

1. **Pre-fetching of DID Documents**: Before going offline, the verifier needs to download the DID document from the web location specified in the DID (typically at `https://{domain}/.well-known/did.json`).
2. **Cryptographic Material Storage**: The DID document contains public keys and verification methods that are stored locally by the verifier.
3. **Verification Process**:
   * When presented with a credential, the offline verifier extracts the issuer's DID
   * It checks its local cache for the corresponding DID document
   * It uses the public keys from that document to verify the digital signature on the credential
   * No internet connection is needed during this verification step
4. **Trust Model**: The verifier must trust that the cached DID document was valid when downloaded and that it hasn't been revoked or updated since.
5. **Limitations**:
   * Cannot check for revocation status in real-time
   * Cannot verify freshly issued credentials from issuers whose DID documents weren't pre-cached
   * Cannot detect if the issuer has rotated keys since the DID document was cached

This approach works well for scenarios with predictable issuers and where occasional connectivity is available to update the cache of DID documents. For higher security requirements, periodic online synchronization is recommended to refresh the cached documents.

[Inji sample deployment architecture using PKI](https://cdpi-tech-arc-resources.s3.ap-south-1.amazonaws.com/Inji+PKI.svg)

[Inji sample deployment architecture using DID](https://cdpi-tech-arc-resources.s3.ap-south-1.amazonaws.com/Inji+DID.svg)
