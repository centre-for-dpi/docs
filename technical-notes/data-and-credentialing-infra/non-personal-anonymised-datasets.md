---
description: Guidelines for for Decision Making & Research
---

# Non-personal Anonymised Datasets

**Background**

Publicly available anonymized datasets are collections of data that have undergone a process of data anonymization, which preserves the analytical and research value of data while maintaining the anonymity of any data subjects. The purpose of this process is to protect individuals' privacy by removing personally identifiable information (PII), such as names, addresses, and social security numbers, while still making available data containing important insights for policy, administrative, research, or trends assessments across various sectors. Non-personal data includes the above as well as data that had no personal information to begin with (such as public GIS location, regional/national socio-economic indicators, weather, or aggregated tax collections).

These datasets can be made freely available to the public to encourage innovation, promote transparency, or assist in scientific research. For example, public anonymized datasets can be useful in training machine learning (ML) models, analysing aggregated health data to understand disease patterns, devising informed care plans, and designing clinical trials for drug development. They facilitate algorithm training without privacy breaches, inform healthcare strategies, optimise trial protocols, and expedite drug discovery while upholding privacy and ethical standards.

To ensure success at scale, it is important to note that a centralised approach to aggregated datasets may be difficult to scale since every entity will be required to upload their datasets onto a single platform and they may be hesitant to part with their data. Even if they do share their data, ensuring it is regularly updated and synced to the main system would be an uphill task. A simpler approach is to **create an open network policy for anonymized data sharing**. Entities can engage the help of any technology provider and join the network to share their data under their own brand. This would give them **recognition and control over their own datasets** and make it easier to keep them updated over the long term. The choice of whether the data would be freely available at a cost could be a policy decision and the network would support both models.

#### Design Principles for crafting open data sets&#x20;

1. <mark style="background-color:purple;">**Federation by design:**</mark> Rather than striving for a single centralised data repository covering all relevant data for the sector, it may be more pragmatic to continue to foster an ecosystem where multiple such datasets and data providers exist (even across multiple portals/platforms), each contributing to a broader pool of knowledge available to multiple innovators. It is crucial to note that harmonising the data schemas across all units isn't necessarily required, as long as each data publishing entity publishes the data schema used by their dataset.&#x20;
2. <mark style="background-color:purple;">**Privacy by design**</mark> to protect individual identity at all times: Small datasets require special attention when sharing aggregated results to ensure de-anonymization is not possible.
3. <mark style="background-color:purple;">**Open Access:**</mark> It is key to ensure that each dataset is made openly available for others to leverage and reuse effectively through transparent policies.&#x20;
4. <mark style="background-color:purple;">**Open Standards:**</mark> Promoting open standards for data sharing is key to enabling ease of reuse by software algorithms that access and analyse data. Open data schemas and APIs facilitate seamless access to data from multiple sources.

#### Decentralised non-personal data network

Accessing data is also a set of services that can be **facilitated by APIs according to a standardized protocol** for “discovery and fulfilment” of any good or service. A decentralized “non-personal data access network” designed to facilitate access based on unified standards via a protocol such as [Beckn](https://becknprotocol.io/) can enable the following data access services through standard APIs:

1. Discovery of various types of datasets across various agencies and entities (public and private).
2. Licensing and Contracting: Dataset license conditions vary, and both parties should contract before download or access.
3. Download and Access: Access methods range from dataset downloads to data-as-a-service models employing confidential computing. Advanced computing methods may establish data sandboxes instead of straightforward availability to enable deep learning networks for model training.
4. Pricing: While some data may be freely accessible, not all datasets are public or free. Public data is typically expected to be freely accessible, but certain analytics can also be made available at a price point. Pricing enables transparency for all players to make informed decisions and supports a sustainable ecosystem.
5. Update/Feedback cycles: Implementing automatic dataset update notifications ensures timely feedback cycles (for example, yearly), enhancing data relevance over time.

All of these processes occur across diverse agencies publishing data product/service catalogues within a decentralized network. This is crucial for ensuring that both public and private datasets are accessible within a unified decentralized framework.&#x20;

The aforementioned architecture pertains to non-personal data (NPD) across public and private systems, whether through download/access or confidential computing models. All operations are decentralized, allowing dataset services to be managed and updated by agencies worldwide.

#### Reference Examples

1. [Language training datasets](https://bhashini.gov.in/ulca/model/benchmark-datasets) for Indian local language models for training and benchmarking.

Note:&#x20;

_Personal data sharing is not within the scope of this document. Personal and Non-personal data sharing require two different approaches across architecture, policy and governance frameworks._\
_Consent to opt in to share data for anonymization is assumed to be part of the data sharing governance and policies of the source systems/platforms/entities and is outside the scope of this document._\
\
\
<br>
