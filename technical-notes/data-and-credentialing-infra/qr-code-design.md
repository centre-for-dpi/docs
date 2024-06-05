---
description: Best practices implementation guide
---

# QR Code Design

## Context

QR codes are omnipresent and act as a bridge to connect the physical world with digital. QR codes also help users with minimal or no digital literacy to safely navigate doing digital transactions in payments, enrolling into social programs, verifying driving, university, employment credentials, , sharing resources like photos/documents/contacts, facilitating e-comments orders, tracking shipments, etc.,

One of the primary challenges in  QR code use is the size of the payload to encode for easy scan and decode. For online use cases, URLs with reference codes to redirect to an online service to complete the transaction should help.

This note is to call out design principles, implementation best practices in use of QR codes in identity / credential domain in offline use cases. These principles hold true for offline use cases in other domains as well.

## Offline QR Code - Design Considerations

1. Messages in QR code should be compacted to ensure low and medium priced mobile phones can easily scan and decode the text. Representing the actual message, digitally signed and with the corresponding public key required to verify all in \~2K characters is key to QR code design. Scanning applications should easily scan and read the QR code content.

Please note, when the payload is encoded in high density (> \~1.5 KB) format, the other parameters like quality of print (plain vs glossy paper), lighting conditions and camera quality do play a role in successful scan and decode of QR content.&#x20;

2. QR code must hold digitally signed content with capability to verify the reputability of content with high trust.&#x20;
3. For the current use cases in Foundation/Functional ID (and credentials) face photograph for offline face authentication, representing the face photo that can be used by face matching algorithms along with corresponding public key (to verify signed payload) becomes a necessary condition for optimal use QR code adoption. This enables  inclusion of  users with no devices or minimal digital literacy to prove identity and to access digital services with high trust, low cost and low friction.

## Recommendations

Based on the above design considerations, CDPI recommends the following for the QR code implementation:

1. Custom format must  support scalability built-in for multiple libraries to decode the QR. The econding should ensure there is optionality of certain attributes, capability to add new attributes that a country would like to incorporate into the QR code.&#x20;
2. Face photo embedded in the QR should  be well tested for at least 3 different face matching algorithms for a successful match threshold scores (FRR and FAR) that is acceptable and helps in inclusion strategies.
3. Support more than one cryptographic option for digital signing to enable reasonable backward and future proofing new techniques.
4. End to End testing should be carried out using various mobile devices (phones/tablets) for ensuring successful scanning of QR codes, decoding, verification of Digital Signatures and 1:1 face matching.
5. End to End testing should be carried out in multiple phases to ensure all functional and non-functional objectives of the specifications are achieved:
   1. Phase-1: Lab testing with synthesised data sets to validate the design, specs and code. Testing can be through APIs and not necessarily people involved. Sample size \~10 qr messages, \~5 devices.
   2. Phase-2: Team testing with actual people in the office or nearby location in a controlled manner. Sample size \~100 qr messages, \~10 devices.
   3. Phase-3: Integrating the solution with actual business application/workflow and testing in the field in a controlled manner. Sample size \~1000 people, \~100 devices and \~10 locations.
   4. Phase-4: Rolling out the above solution through a business use case within a region or country wide to improve the end to end offering. Additionally, testing the solution against multiple use cases to get feedback and improve the specs.
   5. Phase-5: Formal 1.0 release of specs/solution and proposing specifications with  regional and/or global standardisation bodies.
6. Consider reviewing the attributes that go into the QR from a security perspective. For e.g.,
   1. If any permanent, non-revocable tokens that enables authentication (ie. mobile number that enabled OTP auth, permanent national id numbers, etc.,) then it is good to review these attributes' presence in QR code. Bad actors in the ecosystem may misuse and increase the threat vectors on the core digital public infrastructure.
7. Face image can be represented as template/embedding for the face matching apps to match against. template/embedding to easily represent face images in order of a few hundred bytes (\~500).
8. Consider the use of secure QR code formats as an alternative option for encoding any sensitive information.

## References

1. QR code specifications to encode foundational ID attributes [CBOR tag 169](https://docs.mosip.io/1.2.0/overview/standards-and-specifications/169-qr-code-specification)&#x20;
