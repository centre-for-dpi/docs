# eConsent

In any sector, the stream of personal data generated during every transaction enables better decision-making and service delivery. It’s imperative to empower users by enabling consented sharing of granular personal data in a secure, privacy-protected manner. In any user-driven data-sharing framework, the data consumer needs to request the user for their personal data by specifying the quantum of data required, the purpose it’s going to be used for, the duration the data is needed for, the frequency of data pull etc. This step is a precursor to the actual sharing of data by the data provider. Maintaining logs of the agreed-upon data-sharing transaction in a non-repudiable, auditable fashion is a key check.&#x20;

Electronic consent is an artefact/ data structure that records and stores the consent for that data-sharing agreement. Technically, it is a machine-readable electronic document that specifies the parameters and scope of data share that a user consents to in any data sharing transaction.&#x20;

The consent artefact in general consists of the following sections:

1. **Identifier section:** Identifies and lists all the entities involved in a data-sharing transaction; the data provider, the data consumer, the individual, and any other intermediary
2. **Data section:** This section describes the type of data & permissions of the data being accessed including the data fields, date range of data, duration of access, frequency of access, etc. The purpose for which the data is to be accessed should be clearly defined as well.&#x20;
3. **Signatures:** Each consent artefact should include a signature block with signatures of one or more entities as defined in the framework

The electronic consent framework should be programmable, i.e should allow for condition based consent approval with required checks. (eg: Automatic consent approval for access to blood group, allergies, etc, in an emergency)

\
Reference : [MeitY-Consent-Tech-Framework](https://dla.gov.in/sites/default/files/pdf/MeitY-Consent-Tech-Framework%20v1.1.pdf)
