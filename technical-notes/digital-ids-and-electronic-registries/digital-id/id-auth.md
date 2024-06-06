# ID-Auth

In the previous section, we discussed the concept of a digital ID. It’s imperative to reiterate that the **core attributes** of a digital ID are that it is both machine and human-readable, verifiable, and digitally signed to ensure it is tamper-proof.

Verifying the identity of a user (also called authentication) before any transaction is a fundamental function in any economy, and is the key feature that can upgrade any existing ID system to help it operate as digital public infrastructure. Everyday activities like opening a bank account, availing a government service, purchasing a new mobile sim card, etc. necessitate a layer of trust and traceability. Traditionally, verification has been done by producing physical copies of any issued govt. document and acceptance of the document was left to the individual/ entity providing service. This is a low-trust, time-consuming, and expensive process.

The most powerful application/ addition of any identifier is to use it for electronic authentication across a digital economy by any public or private player. This can be done by building a digital auth layer on top of the ID system, enabling people to prove their identities online or offline.&#x20;

**ID authentication** is the process by which an ID number or a tokenized version of the ID along with one type of authentication factor is used to verify a citizen's identity.  The ID system can be queried and it will provide a **Yes/ No response to the question - “Are you who you claim to be?”**

There are a few key modes of authentication:

1. Demographic; which verifies a person’s name, address, date of birth, or other information fields
2. Biometric; which verifies a person’s fingerprints or iris&#x20;
3. [Face auth](face-authentication.md); which verifies a person’s face picture
4. One-time password; where a single-use password is sent to a registered mobile number or email address

ID Authentication provides an API-based authentication mechanism for entities to validate individuals. In each of the above cases, the ID number and one piece of information are submitted to the ID authority’s database for its verification and the ID authority verifies the correctness of the details submitted, or the lack thereof.&#x20;

Additionally, offline local ID authentication can happen if the ID authority offers a digitally signed artefact i.e. JSON/XML document (as a file or in QR code format) with foundational/functional ID or ID alias, photo, and any other minimal information required for validation to deliver a service.

Depending on the strength of verification required, two-factor authentication can also be considered. In all these cases, the citizen is assumed to have consented to the verification process.

Authentication should be thought through <mark style="background-color:purple;">**three key dimensions :**</mark>

* <mark style="color:green;">**Proof:**</mark> What's the authentication intended to prove? Is it proof of document, proof of identity, proof of presence or proof of existence.

<figure><img src="../../../.gitbook/assets/Copy of Pyramid Infographics by Slidesgo.jpg" alt=""><figcaption></figcaption></figure>

* <mark style="color:green;">**Self and assisted**</mark> channels
* <mark style="color:green;">**Offline and online**</mark> modes

<div data-full-width="false">

<figure><img src="../../../.gitbook/assets/Screenshot 2023-10-24 at 17.30.54 (1).png" alt=""><figcaption></figcaption></figure>

</div>

Building this authentication layer on ID and opening it to licensed private/ public service providers is a huge step towards innovation as well as inclusion. Online, low-cost, and almost instant authentication will power the rise of an entirely new class of applications and increase trust in the digital economy.&#x20;

### Probable challenges & workarounds:

1. Hard Infrastructure, connectivity & coverage: Procurement of any specialized hardware for authentication can become prohibitively expensive at a national scale. This and accessibility constraints can impede the delivery of services in rural, remote areas.&#x20;

* A choice that any government can make in this regard is to allow private players to become e-auth service providers after adequate training & certification. Opting to publish all the hardware standards brings market forces into play, resulting in competitive prices for everyone.
* Offering offline mobile-first authentication can eliminate the need for smaller scale verifiers to procure expensive hardware such as smartcard readers or biometric scanners.&#x20;

2. Inclusion & scale: Not all segments of the population can utilise biometrics due to factors such as age or disability. Additionally, not everyone possesses the digital proficiency to own or use a mobile phone. Overlooking these realities risks excluding these vulnerable groups from accessing vital services.

* Enabling multimodal (via OTP, QR codes, biometrics and face) & offline authentication will solve for inclusion at scale - increasing the coverage of services.

3. **Data security & privacy:** Concerns about the security of data and possible misuse of the shared information.

* It’s on the government to balance innovation while ensuring that no one has uncontrolled access to private data.  The concerned government departments can choose to identify authorised service providers after licensing and testing. These should be mandated to maintain logs of data accessed, which can then be scrutinised by the regulators.

The digital ID serves as a key to a broad spectrum of services, encompassing financial inclusion, social protection, and efficient benefits delivery. Seamless, inexpensive user verification can power multiple use cases within the govt. and beyond. For example,&#x20;

* Authentication for benefits delivery like -&#x20;

&#x20;        \- G2P payments

&#x20;       \-   Health insurance coverage&#x20;

&#x20;        \- Enrollment in scholarship programs&#x20;

&#x20;        \- Subsidies distribution

* Voter registration
* Biometric attendance for govt. Officials or schemes
* Authentication for data fetches (such as credentials)
* Face authentication for liveness&#x20;

**References:**

1. [https://docs.mosip.io/1.2.0/modules/id-authentication-services](https://docs.mosip.io/1.2.0/modules/id-authentication-services)
2. [https://govstack.gitbook.io/bb-identity/3-terminology](https://govstack.gitbook.io/bb-identity/3-terminology)
