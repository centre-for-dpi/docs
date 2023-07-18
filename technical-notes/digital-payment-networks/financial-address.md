---
description: Normalised financial address for payments
---

# Financial Address

## Concept

1. The financial world is continually evolving with new products and offerings to customers.&#x20;
   1. Traditionally bank accounts were identified with customer account number, bank id, bank branch. Overtime, with evolution of  mobile and net banking the identifiers have evolved where the branch id is no longer relevant and this got encapsulated with in mobile number/identifier and net banking customer id respectively.
   2. With card based networks/accounts, product offering with debit, credit, gift, pre-paid cards the attributes to identify a sore of value account keeps changing. e.g., card type, varying length of card number, card type, expiry year/month, cvv, one time tokens, etc.,
   3. &#x20;Digital cash and Crypto cash concepts are continuing to evolve.
2. In these scneairos, defining a store of value account using a fixed key/value or object structure will not be intituitive and core payment api specifications need to be constantly updated with each new product offering coming into market.
3. The idea of normative addressing format to represent any store of value account is referred to as **financial address** (fa). Any payer or payee accounts now can be abstracted to a normative address and resolution of final store of value account is left to the final entities doing debit/credit actions of the payment.
4. On similar lines, to enable integration with various identity systems/registries of all customer ids can also be represented in normative addressing formats!

## Principles

1. Financial address is case insensitive normative represenation of a store of value account represented as id-type:id@provider
2. id-type can be a account num, customer id, user id, virutal id, unique id, one time token, pre-paid voucher no, cdbc  id, etc.,
3. The resolution of final store of value details is left to the entity holding these accounts at final debit/credit lef of the payment transactions.
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
