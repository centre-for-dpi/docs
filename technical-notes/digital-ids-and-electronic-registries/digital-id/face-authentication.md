---
description: >-
  Approach to enabling inclusion in onboarding individuals for use cases such as
  social protection
---

# Face Authentication

## Overview

Authenticating a user is the most primitive action in any service delivery. Assuming the user's registered photo is available in digital form and is easily verifiable, implementing face authentication on mobile phone app(s) creates a non-linear scale in providing services in an inclusive way.

## Assumptions

1. A country or any government department offers a digitally signed artefact (i.e., JSON/XML document as file or in QR code format) containing foundational/functional ID or ID alias, photo, and any other minimal information required for validation to deliver a service.
2. Access to this digitally signed artefact can be obtained through a digital copy shared or securely cached on a mobile device, scanned through QR code using a printed or physically issued card.

## Challenges

The following are a few common challenges in any given country or context that is the primary cause for user exclusion who may otherwise can be easily reached to deliver services:

1. **Access** : Not all users are digitally savvy enough to own and/or operate a mobile phone.
2. **Reach** : Network connectivity or coverage is a universal challenge to access online services.
3. **Digital Literacy** : Many users lack digital financial literacy e.g., handling of PIN/OTPs.
4. **Choice** : Users trust known neighborhood agents, and choice to pick the service touch points/agents is key to build trust/inclusion
5. **Automation** : Manual steps and processes cause delays and introduce middlemen.

## Approach

The following key capabilities should be considered  to address the above challenges:

1. **Mobile First** : A mobile-first approach enables service delivery using mobile devices including phones, tablets, and laptops. Ideally, applications should be built once and deployed across operating system platforms to keep the IT systems lean.
2. **Online/Offline** : Mobile device-based delivery enables local secure storage to strategise processes for offline delivery when online services are not reachable due to network connectivity or coverage limitations. System processes can be configured to grant device-level online/offline policies based on local context.
3. **Smart Synchronization**: Offline service delivery requires master, reference and recent transactional data available for taking minimum required business validations.
4. **Self/Assisted** : Business processes to be aligned for self and assisted use case scenarios.
5. **Local Face Auth** : Face authentication with liveness checks should be implemented on edge devices as a reusable software library/module accessible across various department applications. This can act as a digital rail infrastructure component.
6. **Device Registration** : All mobile devices enabled to provide self or assisted services can be registered to manage granular level of controls to deliver services in secure and trusted environments.
7. **Assisted Operators**: All assisted operators enabled to provide assisted services can be trained and registered to deliver remote services.

## Risk Mitigation

1. Face authentication models should be well tested to ensure seamless user experience and address inclusion challenges. The solution should work in conditions like low device technical specifications, lighting conditions, ease of use, local language support, integration with business application flows etc.
2. Face authentication models should be integrated with face **liveness** detection processes as well.
3. Digital **exception** management should be integrated into the workflows through reason codes. Scenarios where face liveness/match, backend service related errors need to be handled through a well thought through exception management process.
4. Continuous improvements to both technical and business processes should be considered by analysing the **telemetry** data from the devices.

## Summary

Face Authentication using a mobile device opens up an opportunity for governments to serve a large number of [excluded](face-authentication.md#3.-challenges) population with ease.&#x20;

## Attributions
