# eKYC/ Identity profile sharing

Every identity system has a few data fields like biometrics, photographs, demographic details, email addresses, or mobile numbers, which in combination identifies each individual uniquely. For many applications, it is essential to authenticate the user and obtain their profile details from a trusted source.

KYC involves establishing and verifying a person’s or an organisation’s identity to assess and monitor customer risk. KYC requirements in most countries mandate that citizens provide proof of their identity and address. Physically producing and verifying these documents is expensive at scale because of the high transactional costs involved, large turnaround times, and low trust in the system. As a result, countries reach a point where operational costs around identity verification are a barrier to getting services to the poor and disadvantaged.

This creates the need for a process that’s not only digital, and instant but also fool-proof and non-repudiable.

In an ID-based eKYC system, identity is verified electronically. after which the service provider can access the profile details from the ID authority database. It’s a value addition on top of ID-auth and allows an individual to share these profile fields to any system.

**How does eKYC work?**

The user’s identity is verified using ID number and biometric data/ OTP from ID database via a service provider (refer to e-Auth)

Upon authorisation, the user authorizes the ID authority to release the minimum required demographic information and photograph (KYC packet) to the requesting entity via a standard API.

ID-based e-KYC can be built as an independent service that can be seeded with data for authentication by any ID system. The ID-based e-KYC is an extension of authentication; however, a key distinction is that any requesting entity can receive and store identity profile data.



## Probable challenges & workarounds:

Infrastructure, Connectivity & Coverage: Procurement of any specialized hardware for authentication can become prohibitively expensive at a national scale. Combined with accessibility constraints, this can significantly impede the delivery of services in rural and remote areas.

A choice that any government can make in this regard is to allow private players to become e-auth service providers after adequate training and certification. Opting to publish all the hardware standards brings market forces into play, resulting in competitive prices for everyone.

Offline mobile-first authentication will eliminate the need to procure expensive hardware.

Data security & privacy: Concerns about the security of data and possible misuse of the shared information.

It’s up to the government to balance innovation while ensuring that no unauthorized parties have access to private data. The relevant government departments can choose to identify authorized service providers after licensing and testing. These providers should be mandated to maintain logs of data access, which can then be scrutinized by the regulators.

Users should also have the ability to revoke access to their KYC data from any service provider or entity at any time.

**Use cases:**

* Financial inclusion via bank account opening
* KYC for mobile SIM card purchases
* Securities account opening
* Enrollment in government schemes

**References:**

1. [https://docs.mosip.io/1.2.0/modules/id-authentication-services](https://docs.mosip.io/1.2.0/modules/id-authentication-services)
2. [https://govstack.gitbook.io/bb-identity/3-terminology](https://govstack.gitbook.io/bb-identity/3-terminology)
3. Rebooting India - Nandan Nilekani & Viral Shah
