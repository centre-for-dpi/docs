---
description: Approach to enabling inclusion in social protection space
---

# Face Authentication

## 1. Overview

Authenticating a user is most primitive action in any service delivery. Assuming user's registered photo is available in digital form and is easily verifiable, then opening up face authentication on mobile phone app(s) shall give non linear scale to provide services in an inclusive way.

## 2. Assumptions

1. Country or any department offers a digitally signed artefact i.e JSON/XML document as file or in QR code format with foundational/functional ID or ID alias, Photo and any other minimal information requried for validation to deliver a service.
2. Access to this digitally signed artefact can be through a digitial copy shared or securely cached on a mobile device, scanned through QR code using a printed or physically issued card.

## 3. Challenges

Following are few common challenges in any given country / context that is the primary cause for user exclusion who may other wise can be easily reached to deliver services:

1. **Access** : Not all users are digitally savy to own and/or operate a mobile phone.
2. **Reach** : Network connectivity or coverage is a universal challenge to avial online services.
3. **Digital Literacy** : Many users lack digital financial literacy e.g., handling of PIN/OTPs.
4. **Choice** : Users trust known neighbourhood agents and choice to pick the service touch points/agents is key to build trust / inclusion.
5. **Automation** : Manual steps/processes cause delays, middlemen

## 5. Approach

Following are few key capabilities to consider to address above challenges:

1. **Mobile First** : Mobile first approach is to have service delivery enabled using mobile devices like phones, tablets, laptops. Ideally build once and deployed across operating system platforms is encouraged to keep the IT systems lean.
2. **Online/Offline** : Mobile device based delivery enables local secure storage to strategise processes for offline delivery when online services are not reachable due to network connectivity/coverage. System processes can be dictated to grant device level online/offline policies based on local context.
3. **Smart Synchronization**: Offline service delivery requires required master, reference and recent transactional data available for taking minimum required business validations.
4. **Self/Assisted** : Business processes to be aligned for self and assisted use case scenarios.
5. **Local Face Auth** : Face authentication with liveness checks on the edge device as reusable software library/module across various department apps. This can act digital rail infrastructure component.
6. **Device Registration** : All mobile devices enabled to provide self or asssisted services can be registered to manage granual level of controls to deliver services in secure and trusted environments.
7. **Assisted Operators**: All assisted operators enabled to provide assisted services can be trained and registered to deliver remote services.

## 6. Risk Mitigation

1. Face authentication models should be well tested to ensure seamless user experience to address **inclusion**. The solution should work in conditions like low device technical specifications, lighting conditions, ease use, local language support, integration with business application flows etc.,
2. Face authentication models should be integrated with face **liveness** detection process as well.
3. Digital **exception** management should integrated into the workflows thought reason codes. Scenarios where face liveness / match, backend service related errors to be handled through a well thought through exception management process.
4. Continuous improvements to both technical and business processs should be considered by analysing the **telemetry** data from the devices.

## 7. Summary

Face Autentication using a mobile device opens up an oppurtunity for governments to serve large number of [excluded](face-authentication.md#3.-challenges) population with ease.&#x20;
