# A primer to personal data sharing

Any interactions in a digital economy create huge swathes of data that if shared with the right stakeholder, can empower the owner to access a wide range of services. Globally, a lot of emphasis is placed on “data protection” which is ensuring that the individual’s data is protected from unauthorised access. It’s useful to think of data as a modern day currency that can be used to unlock services. This framing brings about a shift from the model of data protection to **data protection & empowerment** where the user is in control of their data (both privately & publicity held) and can freely share it. Opening up access to personal data, reference data sets (data used to define and classify other data), anonymised and aggregated data sets, training data and models also falls under the bucket of data empowerment.&#x20;

Personal data sharing can take the form of verifiable credentials sharing or sharing of granular data with the requestor.&#x20;

Broadly, we can identify three types of consented data sharing:

1. Verifiable credentials using wallets/eLockers
2. System-to-system data sharing&#x20;
3. Consent manager-led data sharing using network



1. **Verifiable credentials:** A verifiable credential is a robust instrument of trust which is <mark style="color:purple;">**digitally signed, machine-readable**</mark> and intended to serve as proof to presenters. Any certificate/ credential can be turned into and presented as a verifiable credential (for eg; Vaccination certificate, professional license, education records etc.) Sharing the verifiable credentials to any of the requesters through a digital wallet or any other means is a form of data sharing. It is also recommended that data principal’s consent be captured in this process. Common examples in healthcare are; sharing vaccination certificates, sharing of doctors’ professional certifications, etc.&#x20;
2. **System-to-system data sharing:** In many cases, there’s a need to share per-collected/ existing data internally (within departments that come under a single umbrella like the government) or <mark style="color:purple;">**within a group of trusted entities.**</mark> In this case, a system-to-system data-sharing process can be put in place without involving the data principal. Data sharing open APIs and an authorization mechanism to verify the requestor’s permission will power this. This architecture should only be used in a high-trust environment. However, it is strongly recommended to procure the data principal’s consent before the data sharing and to notify the data principal after the transfer. Common examples are the sharing of patients' data between two govt. programs etc.&#x20;
3. **Consent manager-driven data sharing:** This model of data sharing involves the establishment of <mark style="color:purple;">**neutral, independent third parties called consent managers**</mark>. These consent managers act on the data principals’ behalf and control the flow of data with the help of a consent artefact (a digital framework/ data structure). The consent managers are data blind and hence their incentives are aligned with the users. The consent artefact should have provisions to specify the quantum, expiry, frequency, and purpose of the data pull. Examples will be sharing PHR with a doctor or wellness app etc.&#x20;
