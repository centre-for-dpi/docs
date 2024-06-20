# Digital ID

### Context

Government's primary aim is to reach out to specific target user base to easily [**identify**](#user-content-fn-1)[^1] a user and deliver govt services - e.g. medical care, pensions, collect taxes, etc., **Every country can relate to existence of at-least one of the below identity systems**:

1. National Registration Cards (NRC)
2. Regional Govts Identity Cards
3. Registrations done with one or more biometric modalities (finger, iris, face, voice, etc.,) but may or may not have used for deduplication / uniqueness checks
4. Foundational identities - Civil Birth/Death, National Id, etc.,
5. Purpose driven functional identities - Voting, Driving, Farming, Taxation, Professional Practice (Doctor, Lawyer, Teacher, etc.,)
6. Foundational/Functional IDs restricted to certain category of users - e.g., All Citizens, Citizens above x years, Residents, Refugees, etc.,

**In most of the countries foundational or functional IDs are **<mark style="color:blue;">**issued**</mark>** as**:

1. Simple paper optionally with a photo and/or hologram sticker&#x20;
2. Laminate the paper based ID
3. PVC card with one more security features like:
   1. Photo
   2. Hologram sticker
   3. Micro text
   4. Ghost image
   5. ID authority logo
   6. Guilloche patterns
   7. Issue/expiry dates printed
   8. Barcode / QR Code / Magnetic Strip / RFID / Smart Chip
   9. etc.,

While the above IDs are enrolled and issued with multiple levels of physical verification, the IDs issued within a jurisdiction do have a **good level of trust and acceptance** within the country to deliver govt services. However, governments are <mark style="color:blue;">**challenged to accept**</mark> foundational or functional IDs for various reasons:

1. Detecting genuine vs fraudulent ID cards;
2. Trusting scanned QR code content;
3. Procuring large number of  vendor specific card readers (ID cards with RFID, smart chip);
4. Reissuing expired ID cards;
5. Trusting IDs outside of the issuing authority jurisdiction / network (service points, systems);

In these challenging scenarios governments are trying to address globally accepted Sustainable Development Goals (SDGs) by adopting digital transformation programs. Governments and Development Agencies are investing large sums of money to digitise business processes by building portals, mobile apps, and platforms to reach the target user base while NOT able to IDENTIFY & AUTHENTICATE the user with 100% TRUST.\


<mark style="color:purple;">**DIGITISING AN EXISTING ID INTO A DIGITAL ID CAN OPEN UP NON LINEAR OPPORTUNITIES FOR GOVTS TO DRIVE DIGITAL INCLUSION VIA UNIVERSALLY ACCEPTED, TRUSTED DIGITAL IDs.**</mark>

### What is a Digital ID?

Any foundational or functional ID that supports below <mark style="color:blue;">**properties**</mark> is considered a Digital ID:

1. **Human/System Readable -** Digital ID MUST be presented in a format that can be read by a human and systems. Key user identity attributes MUST be made available in QR Code format for systems to easily scan and read.
2. **Verifiable -** QR Code component of ID MUST be digitally signed by the issuing authority and verification of digital signature to prove non-repudiability be made possible. Human verifying a QR code can be made possible using QR Code reader apps/sdk's.
3. **Online/Offline Accessible -** Digital ID MUST be accessible through Online APIs. Digital ID MUST also be made available for offline use through digital wallets or by digitally signed QR codes.
4. **Online/Offline Authentication -** Digital ID MUST be able to authenticate the user both in online and offline modes. In Offline mode authentication service points are able to verify users in low or no network coverage regions with trust.
5. **Consented Use -** Use of Digital ID SHALL enable mechanisms to implement consents from the ID holder during authentication or data access or while other uses of ID.
6. **Privacy Protecting -** Digital ID SHALL enable option to mask ID for usage scenarios where full ID is not required and ensure necessary consented authorisation for data access.
7. **Self / Assisted Use Cases -** Digital ID SHALL enable self & assisted use cases to access, verify and authenticate the user with consents. Use of authorised operators helps to reach digitally illiterate users and helps in inclusion via open APIs with necessary authorisation by the ID holder.&#x20;
8. **Enable Full/Selective KYC Disclosure -** Digital ID SHALL enable option to release full or selective Know Your Customer (KYC) attributes for downstream use of ID.
9. **Unique ID -** Digital ID MAY be deduplicated against biometric or demographic data to ensure ONLY unique IDs are issued. Uniqueness of an ID is NOT a necessary requirement. Many use cases do not require to identify and authenticate an unique user. Identifying and easily/securely authenticating a user is sufficient.&#x20;
10. **Laws/Regulations -** Digital ID MAY be governed by local laws/regulations to ensure equitable access to ecosystem participants across sectors to reduce friction and costs. Laws/regulations ensures acceptance of DIGITAL ID called out though above properties to create a multiplier effect as a foundational Digital Public Infrastructure.

### Why is Digital ID important?

Many govt programs do not require a unique ID to deliver services. Very few services may actually require a unique id. Use of Digital IDs shall allow policy makers to reduce friction/cost and to allow integration between systems.

Digital ID use shall enable policy makers to integrate with other jurisdiction functional id’s while finding duplicates through trusted demographic data techniques is a continuous improvement process to remove ghost beneficiaries.

Digital IDs made available from existing functional ID systems can eventually link to deduplicated foundational IDs i.e when a country adopts such a deduplicated issuance platform.

While a biometric deduplicated ID system is considered a fool proof ID issuance platform, Governments need not wait for such an ideal scenario to identify a user with **TRUST** both in physical and digital worlds.&#x20;

### How to convert an existing ID to a Digital ID

Governments can consider below indicative suggestions as an inspiration to to convert physical IDs to Digital IDs:

1. Govt should enable issuance and use of PKI certificates as per globally accepted practices within the country.
2. ID authority that owns and maintains a physical registry can consider digitising the data as is into a database.
3. Any additional clean up to improve the quality of the data formats should be taken up during this phase.
   1. Latest good quality photo and/or verified mobile number should be part of the ID database/registry
   2. These two key ID attributes shall open up verification and authentication capabilities.
4. ID authority should procure PKI certificates to issue Online Digital IDs through Auth/eKYC APIs and Offline Digital IDs through mobile wallet / eLocker apps.
5. ID authority should enable govt and private ecosystem players to access Digital ID through api’s, self/assisted use, acceptance of digitally signed docs, cyber & information security laws, user privacy laws and related policies.

### Merging multiple different ID cards into one card is not necessary

Merging many different identity cards is not necessary, and in fact, various countries retain a combination of functional IDs (such as a driver's license, farmers certificate etc.) and foundational IDs.&#x20;

A foundational ID is able to scale to become a national ID only when it is **minimalist** (captures the very basic 5-7 data points on an individual such as name, gender, date of birth, address, and some authentication capabilities) **and delivers value through reusability** (by e-auth and e-kyc).&#x20;

e-Authentication is a feature that can submit a yes/no response when asked, and e-KYC is a feature that can submit foundational profile fields in addition to authentication. The single-sign-on capability allows an individual to log-on to any government or private portal on the basis of their government issued iD (similar to using a Google account to log on to a website).&#x20;

For _**functional IDs**_, building an auth feature would be most useful since other departments can verify the identity of the concerned individual before issuing a service to them (such as a social benefits department authenticates if a person is a farmer before transferring money to them).&#x20;

For _**national IDs**_ (such as minor ID, passport, Non-resident ID), e-auth or SSO may be built.&#x20;

And for the _**national foundational ID,**_ either of the three features may be built for individuals to utilise.&#x20;

These capabilities can be built on any current identity in the country (depending on the nature of the ID) within a matter of weeks and leveraged by individuals and institutions to access trusted information based on the individual's consent to provide more efficient access to services such as opening a bank account or availing benefits through a government portal.  \


**IMPORTANT NOTES:**&#x20;

1. EACH COUNTRY MUST HAVE THEIR OWN STRATEGY TO MAKE FOUNDATIONAL & FUNCTIONAL IDS AVAILABLE AS DIGITAL IDs.&#x20;
2. THIS DIGITAL ID CONCEPT FOR A PERSON CAN BE EXTENDED TO ORGANISATIONS, ENTITIES AND THINGS.
3. HAVING A DIGITAL ID IS MUST HAVE DIGITAL PUBLIC INFRASTRUCTURE (DPI) FOR ANY DIGITAL TRANSFORMATION JOURNEY!

## Attributions

[^1]: 
