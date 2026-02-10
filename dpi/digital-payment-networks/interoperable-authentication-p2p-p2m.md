---
description: P2P, P2M
---

# Interoperable Authentication

When we speak about ‘authentication’, we are referring to the ‘knowledge layer’. Authentication means the confirmation of the person as well as transaction. Interoperable, in this context, means standardised. Thus, interoperable authentication means the ability to confirm the transaction in a standardised manner.

### Why:&#x20;

As an economy grows, very often through the nudge provided by the DPI approach, a lot of new fintechs emerge in the market. They offer a variety of services like banks do, such as P2P/P2M payments, loans, bill payments etc. However, they have one stark difference: they are unregulated. This gives them the agility the banks lack to adapt to newer trends and technologies, but the unpredictability and volatility of creating systemic risk. Restricting their growth means stifling entrepreneurship and the economy. Conversely, allowing them to operate freely means more money leaving the formal banking system and going into unregulated hands. The solution to preventing both extremes lies in interoperable authentication.&#x20;

### What:&#x20;

Through interoperable authentication, the central bank can establish a predefined manner for transaction validation to ensure that funds never leave the banking system. The payment transaction is processed only once the authentication is received in a standardised manner in the form of a PIN, one-time password, biometrics, face authentication, etc. The fintechs remain the front end of the user-transaction, but the authentication is collected by the payment switch directly on the backend and settled between the banks themselves.

This solves both use cases: it prevents money from leaving the formal banking system (the goal of the banks) and it prevents users from leaving the fintech application to authenticate themselves (the goal of the fintechs).&#x20;

### How:&#x20;

The authentication page is provided as a standard SDK (software development kit) by the payment switch operator. They publish the page that all fintechs have to use, effectively decoupling this layer from the acquiring application to securely capture sensitive information like PIN, OTP, and biometric data with crypto keys for end financial institutions to decrypt and authorise the payment. This SDK is integrated within all fintechs so that while authentication is done on their application, it is done without the oversight of the fintechs themselves. This SDK is mandated and has to be used by every payment application (including the banks themselves).

This creates 3 distinct layers, and thus roles, for every payment transaction:

1. User layer: This is handled by fintechs who can create diverse, custom user interfaces to grow their market share.
2. Authentication layer: This is handled by the payment switch to securely capture private PIN, OTP, and biometric data and verify each transaction.
3. Settlement layer: This is handled by the banks themselves and settled between each other directly on the backend.

### Benefits:&#x20;

1. Privacy and Security: Enhances trust by allowing individuals to have a standardised experience while authenticating sensitive information and payment transactions across different applications&#x20;
2. Reduces Systemic Risk: By decoupling the verification process from the fintechs, it prevents misuse or leakage of secure PINs, passwords, and biometric data.&#x20;
3. Growth of Formal Economy: It allows the free economy to grow and thrive with the growth of fintechs while ensuring the money remains within the formal, regulated sector.
