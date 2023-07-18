# Interoperable QR Code (P2P/P2M)

## 1. Overview

Interoperable QR code specifications enables choice to users to make payments. Countries that have a near real time interoperable payment network can leverage interoperable QR codes to:

1. Easily initiate payments using QR codes.
2. Enable payments between P2P, P2B/P2M, Bill Payments etc.,
3. Capability to generate dynamic QR codes with amount. For static QR Codes, amount has to be entered by payer.
4. Merchant can automate reconciliation of orders/payments, generate receipts/notifications by integrating with existing accounting platforms. This is a win-win to both business and customer.

## 2. P2M Ecosystem Players

1. Merchant
2. Merchant acquiring bank
3. Customer
4. Customer bank
5. Interoperable payment network switch

Additionally, experience layer at merchant and customer can optionally be supported by payment service provider app by fintech ecosystem connected to banks.

## 3. Specifications

{% tabs %}
{% tab title="v0.1.0 (Draft)" %}
**Status:** Draft Version; Request for Comments&#x20;

**Version**: 0.1.0 Draft

**Date**: 18-Jul-2023

**Authors**: CDPI&#x20;

**Contact**: info@cdpi.dev

**Description**:&#x20;

Interoperable QR Code specs shall enable to easily scan & pay by capturing all the required information to authorise a payment.&#x20;

**Specification:** [link](https://centre-for-dpi.github.io/docs/qr\_code.html) | [source](../../technical-specs/payments/src/qr\_code.yaml)

**Discussions**:  [link](https://github.com/orgs/centre-for-dpi/discussions)

**Attributions**:&#x20;
{% endtab %}

{% tab title="v0.1.0 Sample" %}
{% code title="qr_code_sample.json" overflow="wrap" lineNumbers="true" fullWidth="true" %}
```json
{
  "version": "1.0.0",
  "payee_fa": "joeuser@national-bank",
  "payee_name": "Printing & Stationeries Co",
  "amount": "138.50",
  "amount_split": {
    "sale": "117.37",
    "igst": "21.13"
  },
  "init_mode": "POS",
  "currency": "ZAR",
  "mid": "M-12345",
  "pos_id": "POS-123",
  "expiry": "20230605T101225+5:30",
  "order_id": "2023/123456",
  "ref_url": "https://printing.co/orderId=2023/123456",
  "additional_data": {
    "bill_number": "123",
    "reference_no": "PO123",
    "key1": "value1"
  },
  "sign": ""
}
```
{% endcode %}
{% endtab %}

{% tab title="v0.1.0 (yaml)" %}
{% code lineNumbers="true" fullWidth="true" %}
```yaml
openapi: 3.0.0
info:
  title: QR Code
  description: 'Interoperable QR code specification. '
  version: 0.1.0
  contact:
    name: CDPI
    email: info@cdpi.dev
  license:
    name: CC BY-SA 4.0
    url: 'https://github.com/centre-for-dpi/docs/blob/main/LICENSE'
  servers:
    - url: 'https://sndbx.dpg.org/{namespace}/ver'
    - description: Sandbox Server
paths :
  /qr/pay:
    post:
      summary: /qr/pay
      description: End point to post the payment instructions read from QR scan
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Qr'
      responses:
        default:
          description: "success"
  /qr/pay/{url_encoded_req}:
    get:
      summary: /qr/pay/{url_encoded_qr_req}
      description: | 
        1. End point to post the payment instructions read from QR scan
        2. The same Qr code spec can be used in Scan & Pay, Click & Pay and Deep Linking modes
      parameters:
        - $ref: '#/components/parameters/url_encoded_qr_req'
      responses:
        default:
          description: "success"
components:
  parameters:
    url_encoded_qr_req:
      in: path
      name: url_encoded_qr_req
      description: URL encoded Qr request json object
      required: true
      schema:
        type: string
        example: "%7B%0A%20%20%22version%22%3A%20%221.0.0%22%2C%0A%20%20%22payee_fa%22%3A%20%22joeuser%40national-bank%22%2C%0A%20%20%22payee_name%22%3A%20%22Printing%20%26%20Stationeries%20Co%22%2C%0A%20%20%22amount%22%3A%20%22138.50%22%2C%0A%20%20%22amount_split%22%3A%20%7B%0A%20%20%20%20%22sale%22%3A%20%22117.37%22%2C%0A%20%20%20%20%22igst%22%3A%20%2221.13%22%0A%20%20%7D%2C%0A%20%20%22init_mode%22%3A%20%22POS%22%2C%0A%20%20%22currency%22%3A%20%22ZAR%22%2C%0A%20%20%22mid%22%3A%20%22M-12345%22%2C%0A%20%20%22pos_id%22%3A%20%22POS-123%22%2C%0A%20%20%22expiry%22%3A%20%2220230605T101225%2B5%3A30%22%2C%0A%20%20%22order_id%22%3A%20%222023%2F123456%22%2C%0A%20%20%22ref_url%22%3A%20%22https%3A%2F%2Fprinting.co%2ForderId%3D2023%2F123456%22%2C%0A%20%20%22additional_data%22%3A%20%7B%0A%20%20%20%20%22bill_number%22%3A%20%22123%22%2C%0A%20%20%20%20%22reference_no%22%3A%20%22PO123%22%2C%0A%20%20%20%20%22key1%22%3A%20%22value1%22%0A%20%20%7D%2C%0A%20%20%22sign%22%3A%20%22%22%0A%7D"
  schemas:
    Amount:
      type: number
      description: Describes amount in decimal value format
      pattern: '^\d{1,13}\.\d{1,2}$'
      example: "117.50"
    KeyValue:
      type: object
      description: Key Value object to track additional details
      properties:
        key:
          type: string
        value:
          type: string
    Qr:
      type: object
      description: Describes interoperable QR code specs for P2M payments
      properties:
        ver:
          type: string
          example: "1.0.0"
        txnId:
          description: System generated unique transaction id for each payment request and applicable in dynamic qr's
          type: string
          example: "2023/123456"
        txnTs:
          description: Transaction time stamp. Applicable in dynamic qr's
          type: string
          format: date-time
          example: "20230605T101125+5:30"
        payeeFa:
          type: string
          description: "<br>
            1. Financial address is case insensitive normative represenation of a store of value account represented as id-type:id@provider <br>
            2. Every payer/payee financial address must resolve to an actual store of value account number for processing the payment instruction <br>
            3. It is recommended the mapping between id and store of value account details to be held only at final store of value entity and intermediaries can hold 
            3. Few examples: <br>
                - token@id-provider e.g token:12345@national-id <br>
                - uid@pymt-rail e.g uid:12345@national-id <br>
                - vid@id-provider e.g vid:12345@national-id <br>
                - mobile@mobile-provider e.g mobile:12345@mobile-pymt <br>
                - account-id@bank-psp-code e.g account:12345@national-bank <br>
                - account-no@ifsc-code.ifsc.pymt-rail e.g account:12345@abcd0000001.ifsc.pymt-rail <br>
                - user-id@psp-code e.g. joeuser@national-bank <br>
                - token@psp-code e.g token:123456@a123 <br>
                - code@purpose-code.voucher-provider e.g voucher:12345@food.coupon-network <br>
                - cdbc-id@cdbc e.g. 12345@digital-cash"
          format: "^[a-zA-Z0-9.-]+@[a-zA-Z0-9.-]+$"
          example: "joeuser@national-bank"
        payeeName:
          description: Resolved payee name from the network for additional reference
          type: string
          example: "Printing & Stationeries Co"
        totalAmt:
          $ref: '#/components/schemas/Amount'
        splitAmts:
          description: |
            1. Breakup of amount into various categories
            2. Sum of the splits to add up to the amount 
            3. Countries/Implemenations can customise as per local context
          type: array
          items:
            type: object
            properties:
              desc: 
                type: string
                description: description of various category of split amount types
                enum: ["tip", "svcCharge", "vat", "gst", salesTax", "round", "disc", "other"]
              amt:
                $ref: "#/components/schemas/Amount"
        mode:
          type: string
          description: |
            1. Mode of payment initiation, indicative list
            3. Countries/Implemenations can customise as per local context
          enum: ["terminal", "pos", "online", "atm", "other"]
        cur:
          description: |
            1. Currency code allocated as per ISO 4217 format
            2. Codes for the representation of currencies and funds
          type: string
          pattern: '^[A-Z]{3,3}$'
          example: "ZAR"
        mid: 
          description: Merchant Id
          type: string
          example: "M-12345"
        tid: 
          description: Terminal Id
          type: string
          example: "POS-123"
        expiry:
          description: Expiry date-time
          type: string
          format: date-time
          example: "20230605T101225+5:30"
        refNum:
          description: Reference no can refer to order id, bill no to carry business context
          type: string
          example: 2023/123456
        refUrl:
          description: referne url
          type: string
          example: "https://printing.co/orderId=2023/123456"
        note:
          description: Note made by user or system to easily refer to the payment/txn
          type: string 
          maxLength: 20
          example: "catrdige 10 nos"
        additional_data:
          description: Additional data that may be useful especially when generating dynamic qr codes.
          type: array
          items:
            $ref: "#/components/schemas/KeyValue"
        sign:
          description: Digital signature
          type: string
      required:
      - payer_fa
      - payee_fa
      - amount
      - init_mode
      - sign
```
{% endcode %}
{% endtab %}
{% endtabs %}

## 4. Deep Linking

QR code content can also be represented in URI representation to enable single QR spec in Deep Linking. Deep Linking enables sharing the scanned QR codes across mobile applications with in a device to easily transfer control from business app to payment apps.

It is recommended to represent the JSON QR code spec in URL encodded format. URL encoding shall ensure to accomodate JSON nested attributes in string represenation to carry in an URI.

```
xxx://pay?%7B%0A%20%20%22version%22%3A%20%221.0.0%22%2C%0A%20%20%22payee_fa%22%3A%20%22joeuser%40national-bank%22%2C%0A%20%20%22payee_name%22%3A%20%22Printing%20%26%20Stationeries%20Co%22%2C%0A%20%20%22amount%22%3A%20%22138.50%22%2C%0A%20%20%22amount_split%22%3A%20%7B%0A%20%20%20%20%22sale%22%3A%20%22117.37%22%2C%0A%20%20%20%20%22igst%22%3A%20%2221.13%22%0A%20%20%7D%2C%0A%20%20%22init_mode%22%3A%20%22POS%22%2C%0A%20%20%22currency%22%3A%20%22ZAR%22%2C%0A%20%20%22mid%22%3A%20%22M-12345%22%2C%0A%20%20%22pos_id%22%3A%20%22POS-123%22%2C%0A%20%20%22expiry%22%3A%20%2220230605T101225%2B5%3A30%22%2C%0A%20%20%22order_id%22%3A%20%222023%2F123456%22%2C%0A%20%20%22ref_url%22%3A%20%22https%3A%2F%2Fprinting.co%2ForderId%3D2023%2F123456%22%2C%0A%20%20%22additional_data%22%3A%20%7B%0A%20%20%20%20%22bill_number%22%3A%20%22123%22%2C%0A%20%20%20%20%22reference_no%22%3A%20%22PO123%22%2C%0A%20%20%20%20%22key1%22%3A%20%22value1%22%0A%20%20%7D%2C%0A%20%20%22sign%22%3A%20%22%22%0A%7D
```

## 5. Stress Testing

Above specifications have been stress tested for below use cases with json samples for easy reference:

<table><thead><tr><th width="73">No</th><th width="199">Scenario</th><th>Remarks</th></tr></thead><tbody><tr><td>1</td><td>Initiation Modes</td><td>Scan &#x26; Pay, Click &#x26; Pay, Deep Linking</td></tr><tr><td>2</td><td>Initiation Locations</td><td>Terminals, POS, Online, ATM</td></tr><tr><td>3</td><td>Static / Dynamic QRs</td><td></td></tr><tr><td>4</td><td>P2M &#x26; P2P use cases</td><td></td></tr><tr><td>5</td><td>Subscripitons / Recurring Payments</td><td>Fixed amount e.g., Rentals, Equity/MF SIPs, EMIs, Subscriptions, etc.,</td></tr><tr><td>6</td><td>Bill Payments</td><td>Varying amount e.g., Utilities</td></tr><tr><td>7</td><td>IPO Payments</td><td></td></tr><tr><td>8</td><td>Refunds</td><td></td></tr><tr><td>9</td><td>Buy Now Pay Later</td><td></td></tr><tr><td>10</td><td>Step Up/Down Payments</td><td></td></tr></tbody></table>

## 6. Technical Considerations

1. Signed QR code content is mandatory to ensure security and detect any malicious requests / phishing attacks.
2. &#x20;Scanning of QR codes and verification of digitally singed QR code content is the responsibility of the payment apps on customer mobiles.
3. Payment Network provider shall manage the registry of all authorised **acquiring** banks allowed to onboard merchants and offer digitally singed QR codes.&#x20;

## 5. Typical flow

Below is a typical flow to make initiate merchant based QR code based payments:

1. Merchant signs up with acquiring banks to avial QR code based payment service
2. Using merchant's banking interface, merchant requests a static QR code
3. Additionally merchant may integrate with POS terminal to gerneate dynamic QR codes using APIs for each transaction with amount and other customised attributes like description, tax info etc.,
4. Customer using her payment app scans the interoperable qr code
5. Payment app checks singed QR code scanned is non-tampered and is from trusted source. Uses network registry to identify the acquiring banks
6. Customer payment app provides a choice to customer to select linked account to pay for the transaction
7. Customer payment app securly collects banking account pin to authorise the payment from the customer
8. Customer payment app initiate the payment on interoperable payments network to pay to the merchant's account
9. Notification of payment status is notified to merchant and customer by the respective banking apps.

## 6. Additional References

1. QR Code printing specifications <**tbd>**
