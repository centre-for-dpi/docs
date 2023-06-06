---
description: Interoperable Payments
---

# QR Code

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

## 3. Specification

#### Interoperable QR Links specifications [yaml file](src/qr\_spec\_ex.json)

#### JSON Sample:

```yaml
{
  "payee_fa": "joeuser@gtbank",
  "payee_name": "Kapoor Printing & Stationeries",
  "amount": "117.50",
  "init_mode": "QR",
  "currency": "KSH",
  "mid": "M-12345",
  "posId": "POS-123",
  "expiry": "20230605T101225+5:30",
  "orderId": "2023/123456",
  "additional_data": {
    "bill_number": "",
    "reference_no": "",
    "key1": "value1"
  },
  "sign": ""
}
```

## 4. Technical Considerations

1. QR code content can also be represented in URI or Fixed tag representation formats for use in low network environment is encouraged. e.g.,
   1. _**xxx**_://pay?payee\_fa=joeuser@gtbank\&payee\_name=Kapoor Printing & Stationeries\&amount=117.50\&currency=KSH\&mid=M-12345
   2. \<tbd>
2. Signed QR code content is mandatory to ensure security and detect any malicious requests / phishing attacks.
3. &#x20;Scanning of QR codes and verification of digitally singed QR code content is the responsibility of the payment apps on customer mobiles.
4. Payment Network provider shall manage the registry of all authorised **acquiring** banks allowed to onboard merchants and offer digitally singed QR codes.&#x20;
5. Additional features like push requests, deep linking through intent calls can be extended using this specification as baseline.

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

1. QR Code printing specifications **here**

