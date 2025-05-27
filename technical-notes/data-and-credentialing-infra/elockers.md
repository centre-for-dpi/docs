---
description: >-
  A powerful intervention to scale up trusted digital credentials across the
  ecosystem
---

# eLockers

### Why is an e-locker essential?&#x20;

Imagine a person, A, who needs to apply for a government job. She travels to a metropolitan city Y to look for jobs while her documents are still safely back home in town X. In a world without an e-locker the entire process from securing documents to securing a job could involve the following:&#x20;

1. She will have to locate the original documents right from birth certificate to identity proof to college marksheets. To do so, she will either have to travel back herself (spending essential time and money) or ask someone to send them to her (risking loss or damage through courier).&#x20;
2. These documents may have been misplaced over the years due to misfortune or carelessness. The process of reapplying for them could take months. If she tries to apply through an agent to expedite the process, it can open the gates to corruption and misuse of her documentation. &#x20;
3. Once the documents have been secured and submitted, the onus will now be on the agency to verify all information - not just hers but for the thousands of applications who have applied to fill in the few vacancies. It will be a massive undertaking of labour, money and time involving paper storage, manual verification and audits. The chances of fraud through misuse of another’s documents or false modification of their own will also always be high.&#x20;

Multiple organisations face similar challenges for the dispersal of essential services and opportunities to the public. The process of verification - of ensuring that someone is who they say they are is extensive and exhaustive; at least it used to be … before an e-locker.&#x20;

<a href="https://vc.cdpi.dev/" class="button primary">Read more on CDPI's VCs knowledge base</a>

### What is an e-locker?&#x20;

An e-locker is an online, verifiable, digital locker App where various government issued and approved documents are stored. An e-locker provides the following services:&#x20;

1. Anytime Anywhere Access: to all documents in a secure, tamper-evident way (through digital signatures and time stamps). Any agency (government, private or public) can apply to issue or receive documents through an e-locker. They have to be approved by the government to be issuers, and by the individuals to be receivers of their documents.&#x20;
2. Authentication: of all documents, pre-verified, at par with physical original copies. The e-locker can be built on top of a national ID that can uniquely identify every individual to connect them with their data using multifactor authentication based log-in, or allow log in based on a mobile number or other verifiable identifier &#x20;
3. Data Exchange: granular consent (for a specific time period and purpose) based exchange of documents in machine readable formats for low cost software evaluations of data (such as those offered by a lending algorithm or shortlisting people for jobs)&#x20;

An e-locker is based on the following principles:&#x20;

1. **Decentralised control, consent-first approach** - it fetches the data from a variety of organisations based on real time user consent and the unique document or individual ID number instead of storing it in a centralised database.&#x20;
2. **High-trust, low risk** - it can use the highest government level security systems such as multi factor authentication, 2048 bit RSA SSL encryption, ISO 27001 certified data housing, security audits and more, to build a layer of trust between all parties and eliminate fraud. The documents are also protected and guaranteed under the Indian IT Act.&#x20;
3. **Paperless power sharing** - it steers the cumbersome, paper and labour heavy, governance systems to a digital era and allows equitable distribution of power among individuals from all income, educational and societal levels. It is able to do so by providing multiple options for organisations to integrate and for people to come onboard the system depending on their own technical capabilities. The goal of DPI is to decrease the digital divide by connecting with them at their level while raising them up to a common standard.  &#x20;
4. **Many apps, many certificates** - Well designed eLockers should have open APIs for issuers of documents and requestors of documents to power multiple apps to access the credentials based on an open network approach&#x20;

In a world with an e-locker, A would have all her documents stored on her smartphone for easy access and sharing. Within a day, she could apply, be verified, selected, and employed by any agency.&#x20;

Another urgent use-case for an e-locker was storing and verifying an individual's vaccination certificates during the Covid-19 pandemic. The use of e-lockers during this period also demonstrated how easy it would be to store all certifications and documents right from business licence/ registration, to proof of academic history and employment history, to land ownership, individual identity and more.&#x20;

### How does implementing an e-locker benefit a country?&#x20;

By creating a uniform system for retrieval of documents (while keeping storage of data still decentralised) through an e-locker, a government can:&#x20;

1. Stimulate the country’s digital economy across sectors (financial institutions, employers, healthcare providers, social sector workers) by providing verification of individuals’ documents. Large scale adoptions of DPI such as e-lockers also builds public trust in technologies and triggers new innovation in trusted digital services.&#x20;
2. Build inclusive systems and structures by eliminating the time, effort, cost gaps that often dominate the availment of opportunities such disbursement of health, financial and social services and leave the last mile population behind&#x20;
3. Reduce corruption and exploitation by building high-trust systems for the vulnerable sections of society who lack the knowledge and tech-savviness to use private, paid providers (who may not be recognised under the country’s IT Act anyway)&#x20;
4. Make it convenient for multiple local, provincial, state, or national departments to provide digitally signed quality digital documents It allows any department to issue digitally signed machine readable credentials without purchasing their own signing infrastructure while still retaining control over the documents they issue.&#x20;
5. Allow organic and asynchronous digital growth in a society by letting different organisations integrate with an e-locker at their own pace..&#x20;

In India, an MSME portal, Udyam, was able to integrate and issue their existing certifications for small businesses through e-lockers in just three weeks!&#x20;



### How does an e-locker work? Tech overview of the system

1. Type of DPI: Data Sharing & Models
2. There are 3 parties to any interaction: the issuer of documentation, the individual and the requester of documentation.&#x20;
3. Issuers upload groups of verified documents in various repositories, and individuals can upload their own documents self-attested in personal e-lockers. Requesters can ask for information from either place.&#x20;
4. All information can communicate with each other and pass freely in the system because it complies with DLTS specifications, has unique document URIs and authentication using strongly verifiable identity
5. When the requester asks for a particular document, it is passed on to the individual who provides a URI of either a repository or their e-locker. Requester uses DLTS Gateway API to access the document based on the URI. This API call may need one more step of consent verification from the individual.&#x20;
6. The gateway provider will map the URI to an actual URL to draw out the actual documentation and send it back to the requester. Authentication and time-stamping will be automatically conducted both ways (from gateway to repository and back). Anonymised audit logs will be stored by the gateway and the repository provider. This completes the process.
7. The e-locker has 2 published sets of open APIs - one for the requestor and one for the issuer.&#x20;
8. You can also open APIs in any e-locker app so that any application can fetch the credentials in the future (not just the official e-locker application) as long as you have verifiable identity that used to log in.  &#x20;

\


&#x20;Further reading: S[unbird Registry and Credentials ](https://docs.sunbirdrc.dev/learn/readme) and [DIVOC verifiable credentials ](https://divoc.digit.org/platform/verifiable-credential-vc-production-deployment)

\
