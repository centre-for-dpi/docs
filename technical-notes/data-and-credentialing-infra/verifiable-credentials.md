# Verifiable Credentials

### Background

Governments interact with the individuals in their country for various purposes - to offer jobs, subsidies, benefits, contracts and more. Private entities such as banks, businesses and educational institutions also interact with individuals to deem eligibility and validity for a number of programs.&#x20;

The foundation for any of these processes is to establish the attributes of the individual by verifying documents to determine their eligibility for services or benefits.&#x20;

In the current scenario, both sectors (public and private) spend considerable amounts of effort into verifying the authenticity of the individual’s data, with no guarantee of success. Mistakes can be costly - with large sums of money and opportunities not reaching the intended people. They can also be dangerous - with unverified individual’s gaining access to sensitive systems and processes.

Digitally verifiable credentials, a simple, marginal improvement to existing systems, built using a Digital Public Infrastructure approach can solve this problem at scale.&#x20;

### What are verifiable credentials?&#x20;

Any issuing authority (whether they are issuing national identity, school certifications, income certificates, recommendation letters, driving licences, tax identity, etc) can make their certificates tamper proof while retaining full autonomy over it.&#x20;

Paper Certificates can contain a digitally signed online / offline QR code that connects the paper based document to an official server and fetches the original certificate for verification. The soft copies of the certificates can be digitally signed to add an extra layer of security guaranteeing authenticity.&#x20;

In this method, no centralisation is required. It allows various departments to retain control over their certificates, and prevents single storage databases that inadvertently become the target of cyber attacks as well as leakages.&#x20;

### How does it work?&#x20;

The application programming interfaces (APIs) of different issuing authorities are opened up to create a real time data fetch between systems. Data is fetched (but not stored) based on API calls made from one system to another asking to validate a particular piece of data based on the individual’s consent. Any data issuing authority and any data-consuming authority can link to the same network by connecting their APIs and clearing their own verification as per the guidelines issued by the country. &#x20;

Data should only be verified based on an individual’s consent. As with all DPIs, the person should be at the centre of the infrastructure. &#x20;

An individual can specify the data he wants verified, the party he wants to share it with, and the period of time he wants to share it for. The consent is granular, purpose specific (eg for a loan or benefit), simple to understand, and revocable.&#x20;

There can be three broad modes of data sharing:&#x20;

1. Consent and data are shared at the same time through the same platform: In this model, the interface itself (wallets or e-lockers) obtain user consent through their platform and share the data immediately. For example, digilocker in India&#x20;

a) Wallets: In digital wallets, users can provide their consent to fetch their digitally signed documents from various entities. These documents are stored on the user’s dashboard and can be shown to anyone. They empower the individual by giving them control over all their verified credentials.&#x20;

b) e-Lockers: In this, the documents are not stored on any dashboard. When the user provides consent, these documents can be fetched from the provider and displayed to the user or the data-consumer he provides his consent to. These eLockers are managed by one or more entities in the country and allow federation of verifiable credentials.&#x20;

2. Consent and data are shared separately and managed through different entities: In this model, the consent is managed through a third-party intermediary known as a consent manager. These entities obtain user consent as per the consent artefact specified and communicate that to data-providers who then separately share that data to the data-consumers. For example, the Account Aggregator ecosystem in India.&#x20;
3. Consent is managed through the data provider: In this model, data is shared between two entities such as two government departments without the individual being directly involved (though ultimately for the individual’s benefit). Consent is provided by the data-provider itself at the time of sharing the data.                      &#x20;

There are many examples of this DPI:&#x20;

Singpass in Singapore is now working to [issue credentials](https://www.developer.tech.gov.sg/our-digital-journey/digital-government-exchange/files/DGX%20DIWG%202022%20Report%20v1.5.pdf) fetched by the Singpass ID. The EU has recently published [digital wallet specifications](https://ec.europa.eu/digital-building-blocks/sites/display/EUDIGITALIDENTITYWALLET/Technical+Specifications); Argentina has verifiable credentials as does India, the Open Wallet Foundation strongly drives the portable identity and credentials agenda. Some US states also accept ISO standard mDL (mobile drivers license) credentials (eg California).

### Benefits:&#x20;

Opening up APIs also allows for multiple market players to build direct and indirect products over it. For example, various user-facing applications can be developed, focusing on different target groups, languages, purposes etc. that allow people to seamlessly provide consent (according to a consent artefact specified) to have their data fetched and shared with third parties.&#x20;

Verifiable credentials empower individuals and institutions alike; they enable people to own their data and allow institutions to focus on delivering last-mile services on the basis of that data.&#x20;

It is only when we can easily know about each individual that we can effectively build for each individual. &#x20;

### Summary of the DPI approach to verifiable credentials:&#x20;

<table data-full-width="true"><thead><tr><th>Technical Layer</th><th>Governance Layer</th><th width="155">Market Layer</th></tr></thead><tbody><tr><td><p>a) Using open spec/standard APIs allow  interoperability between data-issuing authority and any data-consuming authority</p><p><br>b) Embed online / offline machine readable and digitally signed QR codes on all physical documents </p><p><br>c) Digitally sign all documents issued online - this can be done by a department on behalf of multiple agencies, by departments or private entities themselves.</p><p><br>d) Allow verifiable credentials to be available through eLockers or Wallets. </p></td><td><p>a) Specify a consent artefact that articulates to the individual what data they are consenting to share, for what purpose, with whom, for how long, and methods to revoke consent </p><p><br>b) SROs of market players can be set up to monitor user-facing applications dealing with consent. All applications must be data-blind (they cannot access any data, the data-fetch happens behind the scenes, they are simply for user experience) </p></td><td>a) Allow for multiple applications to be built that cater to different sections of society based on region, language, purpose, etc. </td></tr></tbody></table>

#### <mark style="color:blue;">**Additional Resources on Verifiable Credentials:**</mark>

1. [W3C standards](https://www.w3.org/TR/vc-data-model-2.0/) on VCs
2. [Sunbird RC's wiki](https://docs.sunbirdrc.dev/help/comprehensive-overview-electronic-registries-and-verifiable-credentials/verifiable-credentials) on VCs
3. [DIVOC](https://divoc.digit.org/platform/divocs-verifiable-certificate-features-2.0/creating-a-divoc-certificate/overview-of-divocs-digital-certificates) (a credentialling infra that has issued 20 m+ documents):&#x20;
4. Verifiable credentials [101 deck ](https://drive.google.com/file/d/1iTaME2obM6TFboGxJX6U4y0We2gD-Epg/view)
