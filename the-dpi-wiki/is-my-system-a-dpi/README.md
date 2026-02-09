# 📢 Is my system a DPI?

There is a flurry of activity in the DPI ecosystem: governments are building DPI from scratch, open-source projects and Digital Public Goods (DPGs) are developing DPI solutions, funders are supporting DPI implementations, and private vendors are marketing their DPI projects.

However, **not everything labeled as DPI truly functions as such**. How can you quickly identify whether a system or solution is a genuine DPI architecture?

Before diving in, let's recap a few key points:

* Open source does not automatically mean DPI, nor do DPI implementations need to rely solely on open-source solutions.
* DPI implementations must use open APIs, open standards, and open specifications to achieve interoperability and reusability.&#x20;
* All DPI implementations are designed to be reusable by third-party public and private institutions, and not just beneficial to the implementing institution.
* Every DPI implementation must adhere to and internalise five key  [technical design](https://docs.cdpi.dev/the-dpi-wikipedia/dpi-tech-architecture-principles) principles.

<figure><img src="../../.gitbook/assets/DPI Thinking Extended- CDPI (Root Deck) (1).jpg" alt=""><figcaption></figcaption></figure>

_Note:  Whether or not something is a DPI should not be thought of as a yes/no checklist criteria; rather, a digital asset can grow in its maturity as a DPI for the ecosystem depending on the value addition and innovation potential it provides at affordable costs for both public and private use cases._&#x20;

_That said, below are some key technical features that can help move certain key digital systems or assets further in maturity along the journey to becoming robust digital public infrastructure for the ecosystem._&#x20;

1. [<mark style="background-color:purple;">**Digital ID System**</mark>](https://docs.cdpi.dev/technical-notes/digital-ids-and-electronic-registries/digital-id)<mark style="background-color:purple;">**:**</mark>

* For a DigitalID system to function as DPI, it should have an [**ID authentication layer**](https://docs.cdpi.dev/technical-notes/digital-ids-and-electronic-registries/digital-id/id-auth). This means the system should be able to process requests and **return yes/no answers for verification requests**.&#x20;
* For inclusion, implementation can also support **multiple authentication modes** (known as multi-modal authentication) for further inclusivity. For example, **online** (auth API, email one time password), **2G-connected** (mobile one time password) and **offline** (verifiable QR on paper) modes, multiple modes for **biometric authentication** such as fingerprint matching, face matching, iris matching, etc.&#x20;

Additionally, more mature ID systems should enable the following capabilities:

* [**eKYC**](https://docs.cdpi.dev/technical-notes/digital-ids-and-electronic-registries/digital-id/ekyc-identity-profile-sharing) (**API-based profile data sharing** based on a successful authentication for ease of onto external public or private services)&#x20;
* [**Single Sign-On**](https://docs.cdpi.dev/technical-notes/digital-ids-and-electronic-registries/digital-id/single-sign-on-sso) (enabling login to other public or private goods and services with the ID)
* [**e-signing**](https://docs.cdpi.dev/technical-notes/electronic-signature-pki-and-trust-infra/esign) (replacing a wet signature with an ID-enabled electronic signature), which all help trigger a high-trust digital economy)

2. <mark style="background-color:purple;">**Registries Containing Personal Data:**</mark>

Registries are one of the most common digitisation implementations, often understood as simple databases.

A registry implementation can be considered a DPI if it stores **data**&#x20;

* in a **machine-readable,**
* &#x20;**digitally signed format**&#x20;
* that external parties, **both public and private**, **can access**&#x20;

a. The first and simplest way to enable data sharing using registries is to generate [verifiable credentials](https://docs.cdpi.dev/technical-notes/data-and-credentialing-infra/verifiable-credentials) for the holder as a natural exhaust for the stored data.

b. Registries operating as mature DPI can also enable **access system-to-system directly via open APIs.** These open API standards can come from self-defined national standards or derived from well-accepted open specifications like the [G2P Connect/ DCI](https://g2pconnect.cdpi.dev/protocol/interfaces/registries) APIs.

3. <mark style="background-color:purple;">**Digital Payments Infrastructure:**</mark>

_a._ [_Peer-to-Peer/Person-to-Merchant (P2P/P2M) Payments_](https://docs.cdpi.dev/technical-notes/digital-payment-networks)

Often, instant bank-to-bank payment systems are packaged as DPI implementations. However, for a P2P/P2M payments infrastructure to truly operate as DPI, it should be

**Inclusive:** The infrastructure should have scaled to usage by the **majority of the population** without significant cost or technology barriers&#x20;

**Interoperable:** To operate as a mature DPI, a payment rail should support the movement of money across:

* Any account used for payment (bank, wallet, mobile money, credit lines)
* Any app used to pay (bank, wallet, mobile money, fintech)
* Any device or channel (feature phones, PoS machines, smartphones, QR stickers; online/offline, dynamic QR)
* Any recipient of payment (P2P, P2M, P2G, G2P, etc.)

This represents the ideal (though evolving) state of mature payments DPI. Countries do not need to build all of this on day one though - they can add capabilities as they build, but the initial architecture should be **future-proof, programmable, and easily extensible** allowing ease of addition of new features.

_b._ [_G2P Payments_ ](https://g2pconnect.cdpi.dev/)

Government-to-Person (G2P) benefits is a complex ecosystem with many modules, including scheme management, beneficiary management, disbursement systems, settlement systems, and last-mile cash-in/cash-out systems, all spread across various departments.&#x20;

{% hint style="info" %}
The presence of a digitised G2P infrastructure <mark style="color:red;">**does not**</mark> automatically imply a DPI implementation. Some modules, such as beneficiary scheme management, are simply digital solutions.
{% endhint %}

G2P systems can operate as DPI by **utilizing reusable infrastructure, such as** [**registries**](https://g2pconnect.cdpi.dev/protocol/interfaces/registries)**, an** [**ID-Account mapper**](https://g2pconnect.cdpi.dev/protocol/interfaces/beneficiary-management/mapper-architecture)**, and** [**cash-in/cash-out standards**](https://docs.cdpi.dev/technical-notes/digital-payment-networks/cash-in-cash-out-cico)**.**

* Collected **beneficiary data** can be **converted into a registry for reuse** by other departments (see #2 on registries).
* An **ID-Account mapper** (a four-field registry mapping a verifiable ID or phone number to an account number) can be used to **route payments without repetition.**&#x20;

4. <mark style="background-color:purple;">**Data sharing infrastructure - Personal :**</mark>

a. User-centric [Verifiable Credentials](https://docs.cdpi.dev/technical-notes/data-and-credentialing-infra/verifiable-credentials)

Digitally issuing PDF certificates in a dedicated app or platform is not considered a DPI approach on its own. Credentials operate as DPI when they are **digitally signed, machine-readable, and can be shared with and verified by anyone.** Adding a signed QR to a PDF certificate is a quick and simple way to convert a digital certificate to a DPI. For more mature data-sharing DPI, the API standards for sharing credentials and the schema for defining the content should be harmonised at a national level.

b. System-to-System Real-time Data Sharing Networks

A centralised data warehouse or repository of personal data is not typically considered a DPI (unless crafted as a Registry above). The DPI approach involves creating **federated, open data-sharing networks where any data consumer or provider can plug in to receive or share data** as per the network's rules. It is highly recommended to collect user consent as part of this flow. Open API standards (for data sharing) and schema will need to be defined at a sector/ national level.

5. <mark style="background-color:purple;">**Data Sharing Infrastructure -**</mark> [<mark style="background-color:purple;">**Anonymised Data:**</mark>](../../technical-notes/data-and-credentialing-infra/non-personal-anonymised-datasets.md)

Uploading PDFs or Excel files in bulk for public consumption is not usually considered DPI, because of its low reusability potential. Anonymised aggregated data should be made available to third parties in a **machine-consumable format with APIs for access.** Permissions and licensing terms can be set on these data sets.

6. <mark style="background-color:purple;">**Unifying Government Services :**</mark>

Many governments use an Enterprise Services Bus (ESB) solution to unify the various services provided by the government into a single-window application or portal. While this architecture is useful, it is also very complex, difficult to maintain and scale, and requires interdepartmental consensus.

The DPI approach would be if each department would **open its APIs for a service and publish them for third parties to consume and integrate into their workflows**. The Department of ICT, for example, could compile all these open APIs and make them easily accessible for integration.

Alternatively, existing government services buses could collectively open up APIs for all the services they have aggregated.

_Note: This article only discusses technical metrics; Good, participatory governance and inclusive market innovations are equally crucial for a DPI implementation._

<br>
