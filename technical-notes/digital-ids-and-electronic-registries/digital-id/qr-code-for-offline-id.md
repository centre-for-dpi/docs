---
description: Best practices design and implementation guide
---

# QR Code for Offline ID

## Context

QR codes are ubiquitous technologies that bridge the physical and digital worlds. QR codes also help users with minimal or no digital literacy to safely navigate digital transactions such as payments, enrolling into social programs, proving credentials (such as driver’s licenses, university degrees, or employment credentials), sharing resources (photos, documents, contacts), tracking ecommerce orders and shipments, etc

{% hint style="info" %}
One of the primary challenges in QR code use is optimizing the payload size to ensure efficient scanning and decoding. For online use cases, URLs with reference codes that redirect to an online service to complete the transaction work well.
{% endhint %}

This note calls out design and implementation best practices in identity and credential domain for **offline use of QR.** These principles are also applicable to other domains.

## Design Considerations

1. **Messages in QR code must be compacted** to ensure low/medium priced mobile phones can easily scan and decode the text. Representing the entire payload (ID/credential data, digital signature, and corresponding public key for verification) in approximately 2000 characters is key to QR code design.&#x20;
2. QR code must be **capable of digitally verifying the authenticity** of the ID credential.
3. QR code should **allow 1:1 face matching** of the photo ID/credential with live person using one or more face matching algorithms. This enables inclusion by enabling users with limited or no devices, or those with minimal digital literacy, to verify their identity and to access digital services with high trust, low cost, and minimal friction (self/assisted, anytime, anywhere use).&#x20;

{% hint style="info" %}
For high density encoded payload (> \~1.5 KB) format, the other parameters like quality of print (plain vs glossy paper), lighting conditions, and camera quality play a critical role in the successful scanning and decoding of QR content.
{% endhint %}

## Recommendations

Based on the above design considerations, CDPI recommends the following design and implementation guidelines:

1. **QR codes must be versioned**. Version number helps refer to the right QR schema registry for decoding. This allows evolvability of the QR.
2. Custom format must support built-in scalability for multiple libraries to decode the QR. Encoding should **allow optionality of certain attributes**, and **capability to add new attributes** that a country would like to incorporate into the QR code.
3. To digitally verify the authenticity of QR codes:
   1. Design should **support more than one cryptographic option** for digital signing to enable reasonable backward and future proofing of new techniques.
   2. Design should **allow key rotation** and assume there will be valid QR codes with different key pairs issued at different times.
   3. **Make public signing keys available as a registry**. All known public signing keys should be easily referenced using a key ID, which also helps reduce the QR code size.
4. To protect sensitive attributes such as permanent IDs, phone numbers, email ID, etc., consider designing **encryption or one-way hashing using a user-controlled key** as salt. Additionally, consider Secure QR format over regular QRs.
5. Raw compressed face photos in the QR should be compatible with **at least 3 different face matching algorithms, with threshold scores (FRR and FAR)** that are acceptable and align with overall inclusion strategies. Face images can also be represented as templates or embeddings, which helps reduce the photo size to a few hundred bytes (approximately 500).
6. **End-to-end testing** should be conducted in multiple phases to ensure all functional and non-functional objectives of the design and specifications are achieved:
   1. **Phase 1**: Lab testing with synthesised data sets to validate the design, specifications, and code. Testing can be through APIs and not necessarily people involved. Sample size: \~10 QR messages, \~5 devices.
   2. **Phase 2**: Controlled team testing with actual people in the office or nearby location. Sample size: \~100 QR messages, \~10 devices, \~1 location.
   3. **Phase 3**: Integrating the solution with actual business application/workflow and controlled field testing. Sample size: \~1,000 people, \~100 devices and \~10 locations.
   4. **Phase 4**: Rolling out the above integrated business use case solution within a region (or country-wide) to evaluate end-to-end solution offering (including 1:1 face matching). Additionally, test the solution against multiple use cases to get feedback and improve specifications, design, and solution offerings.
   5. **Phase 5**: Formal 1.0 release of specifications and solution for the country or region. Propose specifications with regional and/or global standardisation bodies.

{% hint style="info" %}
In addition to above technical recommendations, QR code should be popularised through branding, certification and campaigns.
{% endhint %}

## References

1. QR code specifications to encode foundational ID attributes [CBOR tag 169](https://docs.mosip.io/1.2.0/overview/standards-and-specifications/169-qr-code-specification)&#x20;
