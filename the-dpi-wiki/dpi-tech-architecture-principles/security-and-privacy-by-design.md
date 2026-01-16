# 🔐 Security & Privacy By Design

### Overview (_What to aim for_)

1. Build an architecture that operates on optimal ignorance: **each system should know as little as possible.**
2. Ensure **high auditability and traceability** via digitally signed data, non repudiable change logs, and authenticated transaction trails - even for agents or employees of the hosting department(s).
3. **Build and leverage participant registries** (individuals, entities, things in future) as independent building blocks to create higher trust and auditability.
4. **Adopt verifiable credentials to increase trust** within the system and also enable information verifiability.
5. **Enable structured, granular, and auditable consent artifacts and frameworks** to enable sharing of personal data across systems.
6. **Multiple factors** of authentication/authorisation&#x20;

### Technical Tools (_How to achieve it_)

* [x] **Tokenisation & Masking:** Tokenisation replaces sensitive data (such as an ID number or address) with non-sensitive equivalents (tokens). Masking hides parts of the data to reduce risk of unauthorized access or unnecessary exposure while maintaining data usability for certain purposes.
* [x] **Granular electronic consent:**  A system where users can give specific, detailed permissions for the conditions of use, sharing, and processing of their personal data, allowing them to control which data is accessed, by whom, and for what purposes, thereby enhancing privacy and compliance with data protection regulations. Preferably, the consent should be logged in machine-readable, digitally signed format to ensure trust.
* [x] **End to end encryption:** A method of data protection where information is encrypted on the sender's end and only decrypted on the recipient's end, ensuring that the data remains secure and unreadable to any intermediaries (including service providers) throughout its entire transmission process.
* [x] **Digital signatures:** Cryptographic mechanisms used to verify the authenticity and integrity of digital messages or documents, ensuring that the content has not been altered/tampered with, and confirming the identity of the sender.
* [x] **Verifiable credentials:** Tamper-proof digital certificates issued by multiple authorities (e.g., for identity, education, income) in machine readable formats that use digitally signed QR codes or soft copies to ensure authenticity without requiring centralized storage, thereby enhancing security and autonomy.

### Societal Outcomes (Why it matters)

* [x] Trusted usage of the DPI by individuals and entities
* [x] Cybersecurity and reduced surface area of cyber attacks
