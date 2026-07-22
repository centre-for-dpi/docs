---
description: What establishes Trust in a ‘decentralized trust model’?
---

# Executing a Decentralised Trust Model

With a small number of participants, trust can be handled by knowledge-based configuration; a verifier is simply told which issuers to accept and at a small scale this is perfectly fine. However, this is not realistically scalable.

In an ecosystem at population scale covering  multiple ministries, agencies, financial institutions, educational institutions, wallet providers and independent verifier apps, operational questions start to arise. Which organisations are trusted, who decides that, how are participants onboarded, suspended or revoked, and how does an application discover trusted participants without someone hand-editing a config file every time a new issuer appears.&#x20;

A CA hierarchy is one way to answer these questions in a structured way — but it answers a different question than the one that actually determines whether an ecosystem is centralized or decentralized. Identifiers and key pairs can come from a Certificate Authority, or be self-declared (DIDs); either works, and that choice alone doesn't decide the model.

**Bottom line: a CA is not a prerequisite for verifiable credentials.** For most credential types, a trust registry over DIDs is sufficient on its own; a CA is a conditional add-on, not a default.

**What determines centralization is how issuer authorization is distributed.** In a centralized model, the VC owner — the entity running the credentialing infrastructure — uses identifiers and key pairs (whether CA-issued or self-declared) to onboard issuers and decide what each can publish, but keeps that authorization internal to its own system. **In a decentralized approach that allows for a multi-wallet ecosystem, the VC owner does the same onboarding and authorization — but instead of keeping it internal, publishes issuer details and their permitted credentials in a trust registry.** This lets other wallets, including private-sector ones, discover issuers and what they're authorised to issue.

The latter approach is built further below using the ETSI trusted lists approach.&#x20;

**ETSI Trusted Lists** — a designated authority publishes who is trusted; the verifier reads that published list.

Questions this note helps answer:

Q1. **How does one actually implement ETSI Trusted Lists** — using DeDi as the underlying registry (as an example)? DeDi organises data as Namespace (the scheme operator) → Directory (the list) → Record (one issuer entry).

Q2. **What does a CA add** that this approach doesn't already give, on their own?

Q3. How does one **move from this approach to a PKI/CA model** without redoing what's already built?

## ETSI Trusted Lists

(ETSI TS 119 612 v2.4.1, 2025-08; Trusted List v6)

A Trusted List is a **signed, machine-readable register, published by a designated authority, of approved issuers and the services they offer**. Each entry carries the issuer's identity and status, so a verifier can check whether a given issuer was approved, and when.&#x20;

National lists are maintained by national supervisory bodies; cross-border interoperability is achieved by having a cross-jurisdictional authority — in the EU, the European Commission maintains a List Of Trusted Lists (LOTL) that points to each national list. The verifier pulls and parses a signed list on a cadence: an offline-friendly snapshot rather than a live call.

* The PKI analogy — a conceptual lens, not a hosting choice. For readers coming from PKI: the list-signing key is the equivalent of the pre-trusted root, a listed entry plays the role of the certificate, and "listed and granted at time T" plays the role of a trust-anchor-plus-status check — with no certificate chain to validate. This is a way to understand the list, not a way to host it.
* How the list is hosted — two peer options for the same artefact. The same signed register can be published either as a signed XAdES XML file pulled on a cadence — the ETSI default, and what the EU lists run on today — or as a DeDi registry queried live over REST, where a namespace is the scheme operator, its directory is the list, and each record is a signed issuer entry. Same list shape either way. A verifier can still get the offline-friendly properties availed by DeDi through caching a namespace's records on a schedule instead of querying per-transaction — that's a client-side choice to make, not something DeDi does by default.

ETSI trusted lists may be paired with **a standardised query interface (e.g. TRQP)** sitting in front of it — standardising the question a verifier asks, not the proof itself.

What does not change. Neither option changes the credential itself or how it is verified. Credentials continue to be issued by trusted issuers, held in the holder's wallet, and presented directly to the verifier, who validates them cryptographically at the edge (signature, issuer identity, status, validity, plus any business rules). What changes is only how the verifier decides which issuers to trust in the first place.

### Q1. How does one actually implement ETSI Trusted Lists — using DeDi as the underlying registry?

**Who hosts it. The unit of ownership is the scheme operator — the designated body responsible for a given list.** E.g. for land credentials, if the issuer is a state ministry or department, the oversight authority (say the Department of Land Resources) would be the scheme operator maintaining that list at national level.

Can there be more than one? Yes, and that's the normal case, not an exception. The EU model is the clearest existing proof: under eIDAS Article 22, every member state establishes, maintains and publishes its own national trusted list, supervised by its own national body, and the European Commission publishes a single List Of Trusted Lists (LOTL) that points to each of those national lists together with the certificates needed to authenticate them. The LOTL contains pointers, not participant data — it federates the national lists rather than replacing them.

**How this gets implemented domestically**, using DeDi: Say an authorised parastatal agency stands up the first list, scoped to the Ministry of Transport. Later, Health wants to run its own.

1. Transport becomes the scheme operator for its own DeDi namespace. Its directory holds one record per authorised issuer, each carrying identity, scope, and status. Its scope must not overlap ambiguously with Health's.
2. A national aggregator namespace holds pointer records to Transport's and Health's namespaces, plus the key needed to verify each one — the same construct the LOTL is built on, expressed as DeDi records instead of XML pointers.
3. Verifiers pre-trust only the aggregator namespace's key. From there they resolve Transport's and Health's directories automatically via its pointer records, and look up the specific issuer. Adding a third department later means adding one pointer record to the aggregator — no verifier reconfiguration. This is also what defeats a rogue list: a self-declared LOTL from a bad actor is never in any verifier's pre-trusted set, so it is simply never consulted.

**Real example:** the EU eIDAS trust backbone — 27+ national lists, each maintained by a different national body, federated by the Commission's LOTL. Browse the actual live lists:[ https://eidas.ec.europa.eu/efda/tl-browser/](https://eidas.ec.europa.eu/efda/tl-browser/). ETSI TS 119 612 is explicitly written to be usable by non-EU jurisdictions (it even has a "Third Countries" list browser) — this is a general recipe, not an EU-only one.

### Q2. What does a CA add that this approach doesn't already give, on their own?

Two reasons:

1. **Legal recognition.** Most electronic signature laws (eIDAS being the clearest example) define a tiered hierarchy, and only the top tier — a "qualified" signature — is defined around a certificate from a licensed CA (a Qualified Trust Service Provider). That tier carries a legal presumption of validity that shifts the burden of proof onto whoever disputes it. This only matters for specific credential types — contracts, notarised documents, court-admissible evidence, certain cross-border regulatory filings — where local law ties a legal consequence to the signature category itself, not to whether the issuer was authorised. Most VC use cases (a diploma, a licence, a benefit attestation) don't need this: a trust registry answering "was this issuer authorised" is sufficient on its own. Whether a CA is required is therefore a per-credential-type question, not a blanket property of using VCs at all.
2. **Off-the-shelf interoperability.** X.509 is already understood by every browser, OS, TLS stack, and signing tool in general use — no DID resolver or DeDi client needed. If a credential has to be verifiable by systems the country doesn't control (a foreign bank, legacy government software, generic enterprise tooling), a CA-anchored credential gets to "just works" faster.

&#x20;Absent one of these two triggers, a trust registry is the complete answer.

### Q3. How does one move from this approach to a PKI/CA model without redoing what's already built?

**The root of trust is a distinct, swappable layer from the registry contents and the subordinate structure beneath it.** Introducing a CA later means changing what backs the root, not rebuilding the ecosystem around it — provided that separation was built in from day one (more on that at the end).

This migration is close to a non-event, because a Trusted List isn't a temporary stand-in for a CA hierarchy — it's the actual mechanism a CA hierarchy runs inside of once one exists.&#x20;

Under eIDAS, qualified CAs (Qualified Trust Service Providers) don't replace the national trusted list; they're entries in it, supervised through it. So the migration path is additive, not a swap:

1. Stand up the CA — root key, HSM custody, audit, whatever licensing regime applies.
2. Add the CA as a new entry in the existing DeDi namespace/directory, alongside issuers already listed. The list doesn't require entries to be CA-issued — it's agnostic to what backs a listed key.
3. Existing issuers keep operating exactly as before, still listed directly with their current keys — nothing forces them onto the CA. An issuer that wants the new CA's backing (for legal recognition or interoperability reasons — see Q2) gets a certificate and has its existing list entry updated to point to it: a metadata update on a record that already exists, not a new one.
4. Verifiers don't change at all. They already pull the list, find the entry, check status, verify against the listed key — whether that key traces to a self-signed pair or a CA-issued certificate is invisible to that logic.

### Q4. What happens to credentials already issued — under self-declared keys or a CA-issued certificate — when the root of trust changes, e.g. through a key rotation event? Do they have to be reissued?

**No. Existing credentials keep verifying, and reissuance stays a per-issuer, lifecycle-driven event rather than something a root change forces**. This holds for both a CA migration and a routine key rotation, though rotation adds one detail worth spelling out.

To start, it is necessary to clarify a distinction that often becomes obscured by how the question is framed. Within the framework of this discussion, the list-signing key functions as the pre-trusted anchor. There are three separate scenarios frequently categorized as a "root change," though they actually operate at distinct architectural levels:

1. **Adding a CA.** Additive. Listed keys are untouched, verifiers don't change, and nothing is reissued.
2. **An issuer rotating its own signing key.** This is a leaf event, not a root one. It changes one entry, not the pre-trusted anchor. The issuer's list entry is updated to carry the new key, and newly issued credentials are signed under it.
3. **The list-signing key rotating.** This is the actual root-of-trust change: the anchor every verifier pre-trusts is being replaced.

None of the three invalidates anything already in a holder's wallet. The detail rotation adds is this: a rotated key is superseded, not deleted. A verifier checks a credential against the key that was listed at the time the credential was signed, so the old key has to remain resolvable in a retired state for as long as credentials signed under it are still in the field. In practice that means an expired-but-valid X.509 certificate, or a retained verification method in a DID document. Asked this way, "was this key the listed key at signing time," a credential issued yesterday under the old key continues to validate tomorrow, with no reissuance. (Verifying long after signing additionally needs a trusted timestamp, which is what the long-term-validation machinery around ETSI lists already provides.)

The list-signing-key case is handled the same way one level up. The new list-signing certificate is distributed to verifiers ahead of the old one's expiry, giving an overlap window, exactly as the EU LOTL distributes national list-signing certificates. Verifiers pick up the new anchor before the old one lapses. The credentials themselves never enter into it; only the verifier's trust anchor turns over.

Bottom line: a key rotation at any level turns over keys, not credentials. The two have independent lifecycles, and that independence is the whole point of listing keys rather than baking them into the credential. Reissuance happens only when a specific issuer chooses it, or when a credential reaches the end of its normal validity.

### Q5. Does going “decentralised” require the adoption of DeDi?

**No. The same list can be published as signed XML or as a DeDi registry**, and its listed keys can come from DIDs or from a CA — independently of each other. DeDi, DIDs, and the trusted list are three separable choices, not a single bundled path, so "going decentralized" lets a jurisdiction pick what suits it on each axis.

### References

* ETSI TS 119 612 v2.4.1 (2025-08), Trusted List v6: [https://www.etsi.org/deliver/etsi\_ts/119600\_119699/119612/02.04.01\_60/ts\_119612v020401p.pdf](https://www.etsi.org/deliver/etsi_ts/119600_119699/119612/02.04.01_60/ts_119612v020401p.pdf)&#x20;
* EU trusted lists policy and Article 22 basis: [https://digital-strategy.ec.europa.eu/en/policies/eu-trusted-lists](https://digital-strategy.ec.europa.eu/en/policies/eu-trusted-lists)&#x20;
* What the LOTL is (pointers + signing certs): [https://ec.europa.eu/digital-building-blocks/wikis/display/ESIGKB/What+is+the+List+of+Member+States+Trusted+Lists+also+named+List+of+Trusted+Lists+LOTL](https://ec.europa.eu/digital-building-blocks/wikis/display/ESIGKB/What+is+the+List+of+Member+States+Trusted+Lists+also+named+List+of+Trusted+Lists+LOTL)&#x20;
* Official LOTL service / distribution point: [https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/eSignature+List+of+Trusted+Lists](https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/eSignature+List+of+Trusted+Lists)&#x20;
* For Developers: The eIDAS Dashboard APIs: [https://eidas.ec.europa.eu/efda/swagger-ui/index.html](https://eidas.ec.europa.eu/efda/swagger-ui/index.html)
* EU Trusted List Browser (view real lists): [https://eidas.ec.europa.eu/efda/tl-browser/](https://eidas.ec.europa.eu/efda/tl-browser/)&#x20;
* ToIP TRQP v2.0 (Trust Over IP / LF Decentralized Trust); REST/HTTPS over OpenAPI 3.1.0.
* PKI baseline: IETF RFC 5280, RFC 6960;&#x20;
* eIDAS Reg. (EU) 910/2014 Art. 22; CID (EU) 2015/1505 as amended by (EU) 2025/2164.
