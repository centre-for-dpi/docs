---
description: >-
  First principles and architecture questions to evaluate as countries build and
  scale their verifiable credentials infrastructure
---

# Financial Sustainability of Verifiable Credentials

## First principles

Before pricing, it helps to agree on why charging is helpful, and where the line sits between free and paid access to data. The following principles are the shared logic behind data-sharing models followed by some countries:

* **Why a fee may be helpful**: Issuers, and in some cases wallet-infrastructure-providers, bear significant financial and infrastructure costs to provide digitally signed documents. That cost needs to be recoverable to help the model be sustainable.
* **What should stay free:** Data given directly to citizens in digitally-signed formats, downloaded into their own wallet, should be free. It is the citizen’s own data being returned to them, similar to how paper-based documents are issued to citizens without additional costs.
* **What can be charged:** Data shared with third parties over a live API call, such as a bank verifying income for a loan or an employer verifying a marksheet, can reasonably be charged. This is helpful for two distinct reasons: (a) maintaining infrastructure for a live API call costs more than issuing a one-time signed document, and (b) third parties can afford to pay for verification, since even with a fee, it typically costs less in aggregate than what they used to spend verifying physical documents one by one.
* **How to set the amount:** Charges are usually benchmarked to current e-KYC and e-Authentication rates, where present. As long as the charge for the 3rd party verifier such as a bank to avail the digitally signed document is lesser than what they pay for physical verification of documents, they would be financially incentivised to participate in the network.

## Open Architecture Questions:&#x20;

Which services should include financial compensation?

* Which specific documents or verifications should the country launch with, and which of those already have a private-sector buyer ready to pay (banks, insurers, employers)?
* Should all services follow the same rules, or should some (basic identity verification) be treated differently from others (income verification for lending)?

Private vs. Public Third Parties

* Should every third party be charged, or only private-sector entities, with public agencies continuing to share data with each other for free?
* If public agencies are charged at all, should their rate differ from what private entities pay?

Charge Amounts

* Is there an existing ID-authentication or KYC rate in the country's market that a new fee should be benchmarked against?

Money Flow

* Should the third party pay the issuing agency directly, or should payment flow through the wallet/NDI layer first, with the wallet retaining a portion?
* Is there an existing payments infrastructure that can be used to support metering and billing payments?&#x20;

As always, feel free to reach out to the team at CDPI to help co-create answers to these questions and what the financial model could look like in practice for your country.&#x20;
