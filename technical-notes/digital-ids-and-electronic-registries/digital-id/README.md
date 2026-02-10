---
description: >-
  Many countries have built Digital IDs, including Singapore (Singpass),
  Rwanda’s national ID with eKYC, Chile’s national ID and India's Digital ID
  (Aadhaar).
---

# Digital ID

### Context

The government’s primary goal is to reach its target user base efficiently, identify users easily, and deliver public services, such as medical care, pensions, tax collection and more. **Every country can relate to the existence of at least one of the following identity systems**:

1. National Registration Cards (NRC)
2. Regional Government Identity Cards
3. Registrations using one or more biometric modalities (fingerprint, iris, face, voice, etc.), which may or may not have used for deduplication or uniqueness checks
4. Foundational identities such as civil birth and death records, national IDs, etc.
5. Purpose-driven functional identities such as voter IDs, driver’s licenses, farmer registrations, tax IDs, or professional licenses (doctor, lawyer, teacher, etc.)&#x20;
6. Foundational/Functional IDs restricted to certain categories of users (for example, citizens above a certain age, residents, refugees, etc.)

**In most of the countries foundational or functional IDs are&#x20;**<mark style="color:blue;">**issued**</mark>**&#x20;as**:

1. Simple paper documents, optionally with a photo and/or hologram sticker&#x20;
2. Laminated paper-based ID
3. PVC cards with one more security features like:
   1. Photo
   2. Hologram sticker
   3. Micro text
   4. Ghost image
   5. ID authority logo
   6. Guilloche patterns
   7. Issue/expiry dates printed
   8. Barcode, QR code, magnetic strip, RFID, smart chip, etc.

While the above IDs are enrolled and issued with multiple levels of physical verification, the IDs issued within a jurisdiction do have a good level of trust and acceptance within the country to deliver government services. However, governments are <mark style="color:blue;">**challenged to accept**</mark> foundational or functional IDs for various reasons:

1. Distinguishing genuine from fraudulent ID cards
2. Trusting scanned QR code contents
3. Procuring large numbers of  vendor-specific card readers (ID cards with RFID, smart chip)
4. Reissuing expired ID cards
5. Trusting IDs outside of the issuing authority jurisdiction / network (service points, systems)

In these challenging scenarios, governments are trying to address globally accepted Sustainable Development Goals (SDGs) by adopting digital transformation programs. Governments and Development Agencies are investing large sums of money to digitise business processes by building portals, mobile apps, and platforms to reach the target user base while NOT able to IDENTIFY & AUTHENTICATE the user with 100% TRUST.<br>

<mark style="color:purple;">**DIGITISING AN EXISTING ID INTO A DIGITAL ID CAN OPEN UP NON LINEAR OPPORTUNITIES FOR GOVERNMENTS TO DRIVE DIGITAL INCLUSION VIA UNIVERSALLY ACCEPTED AND TRUSTED CREDENTIALS.**</mark>

### What is a Digital ID?

Any foundational or functional ID that supports below <mark style="color:blue;">**properties**</mark> is considered a Digital ID:

1. **Human/System Readable**: Digital ID MUST be presented in a format that can be read by a human and systems. Key user identity attributes MUST be made available in QR Code format for systems to easily scan and read.
2. **Verifiable**: QR code component of the ID MUST be digitally signed by the issuing authority, and verification of the digital signature must be possible to prove non-repudiability. Human verification of a QR code can be made possible using QR Code reader applications and SDKs.
3. **Online/Offline Accessible**: Digital ID MUST be accessible through online APIs and offline through digital wallets or digitally signed QR codes.
4. **Online/Offline Authentication**: Digital ID MUST be able to authenticate the user in both online and offline modes. In offline mode, authentication service points are able to verify users in regions with low or no network coverage while maintaining trust.
5. **Consented Use**: Digital ID SHOULD enable mechanisms for users to provide consent from the ID holder during authentication, data access, or other uses of the ID.
6. **Privacy Protecting**: Digital ID SHOULD allow masking or partial disclosure of data where full ID is not required and ensure necessary consented authorisation for data access.
7. **Self/Assisted Use Cases**: Digital ID SHOULD enable both self-service and use cases to access, verify and authenticate the user with appropriate consents. The use of authorised operators helps reach digitally illiterate users and helps in inclusion via open APIs with necessary authorisation from the ID holder.&#x20;
8. **Enable Full/Selective KYC Disclosure**: Digital ID SHALL enable option to release either full or selective Know Your Customer (KYC) attributes for authorised downstream use of ID.
9. **Unique ID**: Digital ID MAY be deduplicated against biometric or demographic data to ensure ONLY unique IDs are issued. However, uniqueness of an ID is NOT a necessary requirement. Many use cases do not require identifying and authenticating a unique user. Identifying and easily/securely authenticating a user is sufficient.&#x20;
10. **Laws/Regulations**: Digital ID MAY be governed by local laws and regulations to ensure equitable access for ecosystem participants across sectors, thereby reducing friction and costs. Laws/regulations ensure the acceptance of DIGITAL IDs with the properties outlined above, creating a multiplier effect as a foundational Digital Public Infrastructure.

### Why is Digital ID important?

Many government programs do not require a unique ID to deliver services; only a few do.&#x20;

The use of Digital IDs enables policymakers to reduce friction and cost; and allow integration between systems.

By using Digital IDs, policymakers can integrate with other jurisdiction functional IDs. Identifying duplicates through trusted demographic data techniques represents a continuous improvement process aimed at eliminating ghost beneficiaries.

Digital IDs made available from existing functional ID systems can eventually be linked to deduplicated foundational IDs when a country adopts such a deduplicated issuance platform.

While a biometric deduplicated ID system is considered a foolproof ID issuance platform, governments need not wait for such an ideal scenario to identify a user with TRUST both in physical and digital worlds.&#x20;

### How to convert an existing ID to a Digital ID

Governments can consider the following indicative suggestions as an inspiration to convert physical IDs to Digital IDs:

1. The government should enable issuance and use of PKI certificates in accordance with globally accepted practices within the country.
2. ID authority that owns and maintains a physical registry can consider digitising the data as is into a database.
3. Any additional cleanup to improve the quality and standardization of data formats should be taken up during this phase.
   1. A recent high-quality photo and/or verified mobile number should be part of the ID database/registry.
   2. These two key ID attributes will enable robust verification and authentication capabilities.

The ID authority should procure PKI certificates to issue Online Digital IDs through Auth/eKYC APIs and Offline Digital IDs through mobile wallet and eLocker applications.

The ID authority should enable government and private ecosystem players to access Digital ID through APIs, self/assisted use, acceptance of digitally signed docs, cybersecurity and information security laws, user privacy laws, and related policies.

### Merging multiple different ID cards into one card is not necessary

Merging many different identity cards is not necessary, and in fact, various countries retain a combination of functional IDs (such as a driver's license, farmers certificate etc.) and foundational IDs.&#x20;

A foundational ID can scale nationally to become a national ID only when it remains minimalist (captures the very basic 5-7 data points on an individual, such as name, gender, date of birth, address, and some authentication capabilities) and delivers value through reusability (by e-Auth and e-KYC).&#x20;

* e-Authentication is a feature that provides a yes/no response upon verification request. &#x20;
* e-KYC is a feature that submits foundational profile fields in addition to authentication.&#x20;
* Single Sign-On (SSO) capability allows an individual to log on to any government or private portal on the basis of their government issued ID (similar to using a Google account to log on to a website).&#x20;

For _**functional IDs**_, building an authentication feature would be most useful, as it enables other government departments to verify an individual’s identity before providing services. For example, a social benefits department can authenticate whether an applicant is a registered farmer before processing benefit transfers.&#x20;

For _**national IDs**_ (such as minor ID, passport, non-resident ID), e-Auth or SSO may be built.&#x20;

For the _**national foundational ID**_, any of the three features may be built for individuals to utilise.&#x20;

These capabilities can be built on any current identity in the country (depending on the nature of the ID) within a matter of weeks and leveraged by individuals and institutions to access trusted information based on the individual's consent, to provide more efficient access to services such as opening a bank account or accessing benefits through a government portal.&#x20;



**IMPORTANT NOTES:**&#x20;

1. EACH COUNTRY MUST DEVELOP ITS OWN STRATEGY TO MAKE FOUNDATIONAL AND FUNCTIONAL IDS AVAILABLE AS DIGITAL IDS.&#x20;
2. THIS DIGITAL ID CONCEPT FOR A PERSON CAN BE EXTENDED TO ORGANISATIONS, ENTITIES, AND THINGS.
3. HAVING A DIGITAL ID IS A MUST-HAVE DIGITAL PUBLIC INFRASTRUCTURE (DPI) FOR ANY DIGITAL TRANSFORMATION JOURNEY!

## Attributions
