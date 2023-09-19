---
description: Reference Links
---

# Curated Specifications

## 1. Overview

Centre for Digital Public Infrastructure (CDPI) curates open standards and specifications across various categories of DPIs for easy reference. This is an initiative to curate specifications that follow [DPI principles](../technical-notes/dpi-tech-architecture-principles/) to enable countries to create required Digital Public Infrastructure rails.

**Note:**

1. This is a draft and all stakeholders in DPI space can share their comments.
2. Reference implementations listed here are as per the claim of implementing org. CDPI has not verified the claims.
3. Countries are advised to independently verify at the time of the adoption.

## 2. Identifier & Registries

### 2.1 Auth & eKYC

1. OAuth - [specs](https://www.rfc-editor.org/rfc/rfc6749)
2. Open ID - [specs](https://openid.net/developers/)
3. SAML - [specs](http://docs.oasis-open.org/security/saml/Post2.0/sstc-saml-tech-overview-2.0.html)

## 3. Signatures & Consent

### 3.1 eSign

1. PKCS #10 - [standard](https://datatracker.ietf.org/doc/html/rfc2986)

### 3.2 Digital Data Sharing Consents

1. Electronic Consent artefact - [spec](https://dla.gov.in/sites/default/files/pdf/MeitY-Consent-Tech-Framework%20v1.1.pdf)

## 4. Payments

### 4.1 G2P, P2P & P2M Payments

1. G2P Connect Solution - [docs](https://g2pconnect.cdpi.dev/g2p-connect/readme) | [specs](https://g2p-connect.github.io/specs/)
2. P2P / P2M - Unified Payments Interface Protocol (forthcoming)
3. UK Open Banking Payments - [specs](https://standards.openbanking.org.uk/api-specifications/)

#### 4.1.1 Reference Implementations

1. Batch payments -  [Mojaloop](https://docs.mojaloop.io/getting-started/), [Mifos](https://mifos.org/resources/documentation/)
2. Beneficiary / Scheme Mgmt partners - [OpenG2P](https://docs.openg2p.org/guides/developer-guides), [OpenSPP](https://docs.openspp.org/index.html), [DIGIT](https://core.digit.org/)
3. Cash In Cash Out (CICO) - AePS [specs](https://www.npci.org.in/PDF/AePS/MicroATM\_Standards\_v1.5.1\_Clean.pdf?TSPD\_101\_R0=08f002952bab20008b7d8da5fd1e2eab2b05707bcf97d4d8a37e2e70559f1e5cf52cf371b2dd168808262911fb14300061acdcd788119a546d34e72dd804f44c2e3b50502dbe0deab71add6e66931a3c1c3f7d06c44de06e493ae71639d420a0) published by NPCI/IBA/UIDAI

## 5. Data & Open AI/ML Models

### 5.1 Verifiable Credentials Issuance

1. W3C compliant issuance [standard](https://www.w3.org/TR/vc-data-model/) | implementation [guide](https://www.w3.org/TR/vc-imp-guide/) | draft issuance api [specs](https://w3c-ccg.github.io/vc-api/)
2. ISO/MDL
3. G2P Connect issuance [docs](https://g2pconnect.cdpi.dev/protocol/interfaces/credentialing) | specs

#### **5.1.1 Reference Specs/Implementations:**

1. Sunbird VC issuance [docs](https://docs.sunbirdrc.dev/learn/readme) | [specs](https://github.com/Sunbird-RC/sunbird-rc-core/tree/main/api-documentation)
2. Inji by MOSIP [docs](https://docs.mosip.io/inji/) | specs

### 5.2 Verifiable Credentials - Presentation

1. W3C compliant presentation standard | Implementation [guide](https://www.w3.org/TR/vc-imp-guide/)

#### 5.2.1 Reference Specs/Implementations:

1. Credential Schemas: Sunbird VC [specs](https://github.com/VC-Specs/vc-specs) | [schemas](https://docs.google.com/spreadsheets/d/1y4z1X7Dfercj7C3wkKbPAR\_ExHbL\_KgXbwtFzeFK078/edit#gid=1454655977) (draft)

### 5.3 Consented Data Sharing

1. Account Aggregator (Financial data sharing) [specs](https://github.com/Sahamati/account-aggregator-standards)

## 6. Discovery & Fulfilment

### 6.1 eCommerce Network

1. Beckn Protocol - [docs](https://becknprotocol.io/) | [specs](https://github.com/beckn/protocol-specifications)

### 6.2 Education

1. Sunbird - [docs](https://sunbird.org/product/building-blocks) | specs
2. BeckN DSEP - docs | [specs](https://github.com/beckn/DSEP-Specification)

### 6.3 Healthcare

1. BeckN Decentralised Health Protocol - DHP [docs](https://developers.becknprotocol.io/docs/introduction/introduction/) | [specs](https://github.com/dhp-project/DHP-Specs)
2. Health Claims Exchange - HCX [docs](https://docs.hcxprotocol.io) | [specs](https://github.com/hcx-project/hcx-specs)
3. Data Exchange: DEPA [docs](https://depa.world) | [specs](https://github.com/iSPIRT/DEPA/blob/main/depa\_2.0.yaml)
4. Vaccination certificate (Verifiable credential): DIVOC [docs](https://divoc.digit.org/) | [specs](https://github.com/egovernments/DIVOC)
