# 🔯 DPI and Privacy / Security

<mark style="background-color:purple;">**Question**</mark>: Does DPI reduce personal privacy, increase security risks, or hurt public safety by increasing capacity for surveillance?

<mark style="background-color:purple;">**Short Answer:**</mark> Well designed DPI actually improves your control over your own data, is minimalist in data collection (sufficient for access to services and nothing more!), opts for federation rather than centralisation of data, and builds security and privacy preserving features (such as tokenisation, auto data deletion, auditable and tamper proof logs of data access and use, etc.) by design. Successful national ID systems that scale for example, have a minimalist set of data fields so the chances of loss of privacy even in case of a data-breach is low - contrarily, the internet has millions of data points of any individual and much less safeguards (both technical and moral) to protect it.

<mark style="background-color:purple;">**Long Answer:**</mark> Digital Public Infrastructure enables solutions to be built at scale - catering to diverse populations with varying levels of ability and resources, in an equitable manner. This scale and impact can ONLY be achieved by institutionalising data minimalism, privacy and security, and public trust into the systems (as DPI only scales with public and private adoption, which requires trust).

For example, design features of a country’s <mark style="background-color:green;">**national (digital) ID system**</mark> that preserve privacy and trust should include:

* [x] **Minimalism in data capture -** The less data is captured, the less of a honeypot is created.
* [x] **Avoiding tracking** - no collection of location/purpose in ID auth/eKYC
* [x] Creating a **Virtual ID or a token as a fungible alias** for the permanent ID to avoid providing the actual ID number for services
* [x] Authentication done with **consent** of the user (via one time password or biometrics)
* [x] Usage **audits which are permanently auto-deleted** every n months
* [x] **End-to-end encryption** for data at rest and data transport layers
* [x] Allowing residents to **lock their ID and/or biometrics,** disabling authentication
* [x] **Unique tokens that are different for every system**, eliminating the ability to merge databases
* [x] **Multi-factor authentication** for high value transactions
* [x] Advanced **cybersecurity measures** for database security, including periodic ethical hacker tests

Features of <mark style="background-color:green;">**an interoperable data sharing system**</mark> to drive enhanced privacy and security could include:

* [x] **Avoiding centralisation** of data to prevent honeypots - letting data remain where it has been collected, and crafting protocols for real time sharing in a federated manner.
* [x] Introducing **the ability to query databases for a yes or no response as per a criteria or question**, without always requesting the raw data for analysis
* [x] Introducing a **detailed, granular consent** (purpose specific and data specific) artefact (digitally signed for added security) required from the individual to share data
* [x] **Allowing consent to be managed by a data-blind third-party** who acts on behalf of individuals (not the information providers or information users) to ensure an actor with incentives aligned with the individual is showing them a consent request (rather than a data user or provider)
* [x] A **pre-specified time period for access to data** - with consent revocable at any time by the individual
* [x] **Multi-factor, multi-modal authentication** capabilities for signing in to the system

For instance, **Brazil’s PIX has prioritized security** in its payment system through a combination of technologies and regulatory measures: It uses **encryption protocols, two-factor authentication to verify user identities and digitally signed transactions, with possibility to reverse payment within a certain time window.** The financial network itself is not connected to the internet, and **only restricted participants can actually access** the database directly, in addition to regulatory oversight by the Central Bank of Brazil which ensures compliance with financial security standards and promotes user trust in the system.&#x20;

Another example is Aadhaar - India’s ID system which **collects only 4 minimal, constant fields** of an individual - name, date of birth, address, gender. This means that the data is always accurate. Now what if they had collected 10 fields including profession, income, family members, etc? This could change year on year, making the data redundant. Collecting and storing that information would also make systems bulky and inefficient - affecting the speed and accuracy of all systems that use it (such as banks using ID data for eKYC).&#x20;

If data privacy wasn’t guaranteed, and personal information could be shared freely across departments - **for example, if the payments system could send information about your transactions to the tax authorities who subsequently showed up at your doorstep - would anyone sign up for those solutions? Likely not! And DPI would never be able to scale or sustain.**

Evidence of its robust minimalism, privacy, and security is evident in the widespread adoption and long-term sustainability of critical systems like verifiable identities, interoperable payments, healthcare claims settlement networks, education credentials, mobility, and commerce networks globally.

While all technical systems face vulnerabilities, well-designed DPI anticipates and prepares for potential attacks. . If information from a minimalist system is leaked - information that is already more or less public such as your name, date of birth, gender, etc. - you stand to lose much less than when large systems are breached such as your internet history, social media footprints, email accounts etc. which have more damning repercussions. The fear of our internet accounts being breached doesn't stop us from using the internet, similarly, the remote fear of DPI systems being breached should never be a barrier to implementing beneficial measures at scale. We must simply build resilient, secure systems that can stand the test of time.

There are multiple ways to ensure data minimalism, security and privacy such as those outlined above. Similar safeguards can be put in place using a techno-legal approach for all solutions built through the DPI approach. These measures can solidify systems to reduce the probability that a malicious actor can use the systems to increase surveillance, or cause intentional harm.

\


\
