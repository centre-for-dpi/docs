---
description: Best practices design and implementation guide
---

# QR Code for Offline ID

## Context

QR codes are omnipresent and act as a bridge to connect the physical world with digital. QR codes also help users with minimal or no digital literacy to safely navigate performing digital transactions such as payments, enrolling into social programs, proving credentials (such as driving /university/ employment credentials), sharing resources (like photos/documents/contacts), tracking e-commerce orders and shipments, etc.,

{% hint style="info" %}
One of the primary challenges in QR code use is the size of the payload to encode for easy scan and decode. For online use cases, URLs with reference codes that redirects to an online service to complete the transaction works well.
{% endhint %}

This note calls out design, implementation best practices in identity / credential domain for **offline use of QR**. These principles hold true for other domains as well.

## Design Considerations

1. **Messages in QR code must be compacted** to ensure low / medium priced mobile phones can easily scan and decode the text. Representing the entire payload (id/credential data, digital signature and corresponding public key to verify) in \~2K characters is key to QR code design.&#x20;
2. QR code must be **capable of digitally verifying the authenticity** of the ID credential.
3. QR code should **allow 1:1 face matching** of the photo ID / credential with live person using one or more face matching algorithms. This enables inclusion of  users with no devices or minimal digital literacy to prove identity and to access digital services with high trust, low cost and low friction (self/assisted, any time, any where use).&#x20;

{% hint style="info" %}
For high density encoded payload (> \~1.5 KB) format, the other parameters like quality of print (plain vs glossy paper), lighting conditions and camera quality play a critical role in successful scan and decode of QR content.&#x20;
{% endhint %}

## Recommendations

Based on the above design considerations, CDPI recommends the following design and implementation guidelines:

1. **QR codes must be versioned**. Version number helps refer to the right QR schema registry for decoding. This allows evolvability of the QR.
2. Custom format must support scalability built-in for multiple libraries to decode the QR. Encoding should **allow optionality of certain attribute**s, and **capability to add new attributes** that a country would like to incorporate into the QR code.&#x20;
3. To digitally verify the authenticity of QR:
   1. Design should **support more than one cryptographic option** for digital signing to enable reasonable backward and future proofing new techniques.
   2. Design should **allow key rotation** and assume there will be valid QR codes with different key pairs issued at different time.
   3. **Make public signing keys available as a registry**. All known public signing keys should be easily referenced using a key ID. This helps in reducing the QR code size too.
4. To protect sensitive attributes such as permanent IDs, phone number, email ID, etc., consider designing **encryption or one way hashing through user controlled key** as salt. Additionally, consider Secure QR format over regular QRs.
5. Raw compressed face photo in the QR should work with **at least 3 different face matching algorithm's threshold scores (**[**FRR and FAR**](#user-content-fn-1)[^1]**) 1** that is acceptable and meet in overall inclusion strategies. Face image can also be represented as template/embedding and help in reducing the photo size to few hundred bytes (\~500).
6. **End to end testing** should be carried out in multiple phases to ensure all functional and non-functional objectives of the design / specifications are achieved:&#x20;
   1. **Phase-1**: Lab testing with synthesised data sets to validate the design, specs and code. Testing can be through APIs and not necessarily people involved. Sample size \~10 qr messages, \~5 devices.
   2. **Phase-2:** Controlled team testing with actual people in the office or nearby location. Sample size \~100 qr messages, \~10 devices, \~1 location.
   3. **Phase-3**: Integrating the solution with actual business application/workflow and controlled field testing. Sample size \~1000 people, \~100 devices and \~10 locations.
   4. **Phase-4**: Rolling out the above integrated business use case solution within a region (or country wide) to evaluate end to end solution offering (including 1:1 face matching). Additionally, test the solution against multiple use cases to get feedback and improve specs/design/solution offering.
   5. **Phase-5**: Formal 1.0 release of specs/solution for the country/region. Propose specifications with regional and/or global standardisation bodies.

{% hint style="info" %}
In addition to above technical recommendations, QR code should be popularised through branding, certification and campaigns.
{% endhint %}

## References

1. QR code specifications to encode foundational ID attributes [CBOR tag 169](https://docs.mosip.io/1.2.0/overview/standards-and-specifications/169-qr-code-specification)&#x20;

[^1]: False Reject Rate, False Accept Rate
