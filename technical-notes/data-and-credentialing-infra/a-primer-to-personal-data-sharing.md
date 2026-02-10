# A primer to personal data sharing

Any interaction in a digital economy creates vast amounts of data that, if shared with the right stakeholders, can empower the owner to access a wide range of services. Globally, a lot of emphasis is placed on “data protection” which is ensuring that the individual’s data is protected from unauthorised access. It’s useful to think of data as a modern day currency that can be used to unlock services. This framing brings about a shift from the model of data protection to **data protection and empowerment**, where the user is in control of their data (both privately and publicly held) and can share it freely. Opening up access to personal data, reference data sets (data used to define and classify other data), anonymised and aggregated data sets, training data and models also falls under the bucket of data empowerment.

Personal data sharing can take the form of verifiable credentials sharing or sharing of granular data with the requestor.

Broadly, we can identify three types of consented data sharing:

1. Verifiable credentials using e-wallets
2. System-to-system data sharing
3. Consent-led data sharing using a network

***

1. **Verifiable credentials:** A verifiable credential is a robust instrument of trust which is <mark style="color:purple;">**digitally signed, machine-readable**</mark>, and intended to serve as proof to presenters. Any certificate/credential can be converted into and presented as a verifiable credential (for e.g., vaccination certificates, professional licenses, education records etc.). Sharing verifiable credentials with any of the requesters through a digital wallet or any other means is a form of data sharing. It is also recommended that the data principal’s consent be captured in this process. Common examples in healthcare include sharing vaccination certificates, sharing of doctors’ professional certifications, etc.&#x20;
2. **System-to-system data sharing:** In many cases, there’s a need to share pre-collected or existing data internally (within departments that come under a single umbrella like the government) or <mark style="color:purple;">**within a group of trusted entities.**</mark> In this case, a system-to-system data-sharing process can be put in place without involving the data principal. Data sharing open APIs and an authorization mechanism to verify the requestor’s permission will power this. This architecture should only be used in a high-trust environment. Common examples are the sharing of patients' data between two governments. programs etc. (It is strongly recommended to procure the data principal’s consent before the data sharing and to notify the data principal after the transfer.)
3. **Consent-led data sharing in a network:** In this model, a network facilitates the exchange of data from the data providers to data users via the data principal (user). There's no centralised store of data and data flows real-time based on a request that carries the user's consent as well. The user is wholly in control in this framework. Three powerful technical building blocks can drive user-centric consented, real-time data sharing, namely data sharing APIs, sector-specific data schema, and consent standard.

### Cross-border data sharing&#x20;

Cross-border flows are most straightforward when utilizing user-led methods such as credentials, which don’t require issuing parties to have bilateral or multilateral agreements in place with every possible international credential verifier. Instead, any potential verifying entity of the credential who wishes to access the data can locally verify the digital signature to access the personal data presented by the user. The verifying entity should ensure to have access to (and cache with TTL - time to live settings) trust registries namely: global issuer list, corresponding verification keys and revocation list, and credential data schema to accept credentials with higher trust and convenience for the presenter.

System-to-system data sharing in cross-border use cases requires a slightly higher level of coordination between government departments, including the establishment of international consent managers, supporting legal or regulatory frameworks, security clearances (for opening up of API ports), as well as interoperability of technical systems in order to be successful.

Federated anonymised data sets can be utilised for cross-border research and developmental initiatives as well through proper contextualisation of the data. Please refer [here](non-personal-anonymised-datasets.md) for additional design choices to enable and access federated anonymised data sets.

