---
description: Normalised financial address for payments
---

# Financial Address

### Concept

Just as ‘21/02, House X, Street Y, City Z, Postcode - 000’ is your home address (where you stay), the combination of ‘Bank A/c No., Code, Bank Name + Branch’ or “Card number, Provider, Expiry, CVV” serves as your financial address (where your money stays).

A few decades ago, the only way to meet people at home was by giving them your home address and inviting them over. As a result, people had smaller friend circles and fewer people in their lives. Soon, Google Maps simplified an entire address to a single, shareable URL, which allowed people to have a quick, efficient way of sharing their address. Then email addresses, Instagram handles, LinkedIn profiles, and multiple other channels of discovery emerged, encouraging new connections. People’s social lives exploded, and the world as we know it transformed.

The same phenomenon is now happening in the financial world for payments through the concept and implementation of a “financial address”.

A financial address is a system that (i) encourages people to transact digitally, from any store of value, to any store of value, while completely preserving (ii) the privacy of the payer/payee and (iii) the trust of the receiver.

A financial address simplifies any store of value to a unique address in the form of “id-type:id@provider”. For example, “mobile:12345@mobile-pymt” (mobile@mobile-provider) or

“account:12345@national-bank” (account-id@bank-psp-code)

Through this, the payment systems know which account to transfer the money to, while hiding these details from the human and machine eye. It creates a routing mechanism that ensures secure transfer of money, while eliminating the chances of fraud, misuse, or leakages through hacking. The resolution of the final store of value account is left to the final entities doing debit/credit actions of the payment.

### Advantages&#x20;

1. Protects privacy of users encouraging them to transact with various parties freely and safely
2. Enhances cybersecurity by preventing the creation of honeypots (large databases with sensitive financial data that can be hacked or leaked)
3. Allows multiple, and ever evolving, stores of value to be conveniently communicated in a standard format
4. Builds P2P and P2M trust, spurring innovation and adoption.

### Why Financial Address?

The financial world is continually evolving with new products and offerings to customers.

1. Traditionally, bank accounts were identified with customer account number, bank ID, and bank branch. Over time, with the evolution of mobile and net banking, the identifiers have evolved where the branch ID is no longer relevant and has been encapsulated within mobile number/identifier and net banking customer ID respectively.
2. With card-based networks/accounts, product offerings with debit, credit, gift, and pre-paid cards, the attributes to identify a store of value account keep changing. Examples include card type, varying length of card number, card type, expiry year/month, CVV, one time tokens, etc.
3. Digital cash and crypto cash concepts are continuing to evolve.

In these scenarios, defining a store of value account using a fixed key/value or object structure will not be intuitive, and core payment API specifications need to be constantly updated with each new product offering coming into the market.

The idea of normative addressing format to represent any store of value account is referred to as **financial address** (fa). Any payer or payee accounts can now be abstracted to a normative address and resolution of the final store of value account is left to the final entities doing debit/credit actions of the payment.

Similarly, to enable integration with various identity systems and registries, all customer IDs can also be represented in normative addressing formats!

## Principles

1.  Financial address is a case-insensitive, normative representation of a store of value account, represented as id-type:id@provider

    The id-type can be an account num, customer id, user id, virtual id, unique id, one time token, pre-paid voucher no, CDBC ID, etc.

    The resolution of the final store of value details is left to the entity holding these accounts at the point of final debit/credit left of the payment transactions.

    The ID type & provider information in financial address shall enable intermediaries in the payment network to route the payment instructions as per the network rules/polices.

## Examples

{% tabs %}
{% tab title="Financial Address" %}
<pre data-line-numbers><code><strong>token@id-provider e.g token:12345@national-id
</strong>uid@pymt-rail e.g uid:12345@national-id
<strong>vid@id-provider e.g vid:12345@national-id
</strong><strong>mobile@mobile-provider e.g mobile:12345@mobile-pymt
</strong><strong>account-id@bank-psp-code e.g account:12345@national-bank
</strong><strong>account-no@ifsc-code.ifsc.pymt-rail e.g account:12345@abcd0000001.ifsc.pymt-rail
</strong><strong>user-id@psp-code e.g. joeuser@national-bank
</strong>token@psp-code e.g token:123456@a123
code@purpose-code.voucher-provider e.g voucher:12345@food.coupon-network
<strong>cdbc-id@cdbc e.g. 12345@digital-cash"
</strong></code></pre>
{% endtab %}

{% tab title="Identity Address" %}

{% endtab %}
{% endtabs %}

## Attributions

1. The concept of financial address is inspired from NPCI's [UPI Protocol](https://www.npci.org.in/what-we-do/upi/product-overview) use of Virtual Address or UPI ID.
