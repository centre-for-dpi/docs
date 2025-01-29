---
description: Normalised financial address for payments
---

# Financial Address

## Concept

Just the way ‘21/02, House X, Street Y, City Z, Postcode - 000’ is your home address (where you stay), the combination of ‘Bank A/c No., Code, Bank Name + Branch’ or “Card number, Provider, Expiry, CVV” etc. is your financial address (where your money stays).&#x20;

A few decades ago, the only way to meet people at home was by giving them your home address and inviting them over. So people had smaller friend circles and fewer people in their lives.  Soon, Google Maps simplified an entire address to a single, shareable URL which allowed people to have a quick, efficient way of getting their address out. Then email addresses, instagram handles, linkedin profiles and multiple other channels of discovery came along encouraging new connections. People’s social lives exploded, and the world as we know it transformed.&#x20;

The same is now happening in the financial world for payments through the concept and implementation of a “financial address”. &#x20;

A financial address is a system that (i) encourages people to transact digitally, from any store of value, to any store of value, while completely preserving (ii) the privacy of the payer/payee and (iii) the trust of the receiver.&#x20;

A financial address simplifies any store of value to a unique address in the form of “id-type:id@provider”. For example,  “mobile:12345@mobile-pymt”  (mobile@mobile-provider)  or&#x20;

“account:12345@national-bank” (account-id@bank-psp-code)&#x20;

Through this, the payment systems know which account to transfer the money to, while hiding these details from the human and machine eye. It creates a routing mechanism that ensures secure transfer of money, while eliminating the chances of fraud, misuse, or leakages through hacking. The resolution of the final store of value account is left to the final entities doing debit/credit actions of the payment.

## Advantages&#x20;

1. Protects privacy of users encouraging them to transact with various parties freely and safely&#x20;
2. Enhances cybersecurity by preventing the creation of honeypots (large databases with sensitive financial data that can be hacked or leaked)&#x20;
3. Allows multiple, and ever evolving, stores of value to be conveniently communicated in a standard format&#x20;
4. Builds P2P and P2M trust - spurring innovation and adoption.&#x20;

## Why Financial Address?

The financial world is continually evolving with new products and offerings to customers.&#x20;

1. Traditionally bank accounts were identified with customer account number, bank id, bank branch. Overtime, with evolution of  mobile and net banking the identifiers have evolved where the branch id is no longer relevant and this got encapsulated with in mobile number/identifier and net banking customer id respectively.
2. With card based networks/accounts, product offering with debit, credit, gift, pre-paid cards the attributes to identify a store of value account keeps changing. e.g., card type, varying length of card number, card type, expiry year/month, cvv, one time tokens, etc.,
3. &#x20;Digital cash and Crypto cash concepts are continuing to evolve.

In these scenarios, defining a store of value account using a fixed key/value or object structure will not be intuitive and core payment api specifications need to be constantly updated with each new product offering coming into market.

The idea of normative addressing format to represent any store of value account is referred to as **financial address** (fa). Any payer or payee accounts now can be abstracted to a normative address and resolution of final store of value account is left to the final entities doing debit/credit actions of the payment.

On similar lines, to enable integration with various identity systems/registries of all customer ids can also be represented in normative addressing formats!

## Principles

1. Financial address is case insensitive normative representation of a store of value account represented as id-type:id@provider
2. id-type can be a account num, customer id, user id, virtual id, unique id, one time token, pre-paid voucher no, cdbc  id, etc.,
3. The resolution of final store of value details is left to the entity holding these accounts at final debit/credit left of the payment transactions.
4. id-type & provider information in financial address shall enable intermediaries in the payment network to route the payment instructions as per the network rules/polices.

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
