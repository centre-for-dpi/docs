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

## 2. Ecosystem Players

### 2.1. Acquiring Banks

### 2.2. Issuing Banks

### 2.3. Merchants

## 3. Specification

#### Interoperable QR Links specifications [yaml file](src/qr\_spec\_ex.json)

#### JSON Sample:

```yaml
{
  "payee_fa": "joeuser@gtbank",
  "payee_name": "Kapoor Printing & Stationeries",
  "amount": "117.50",
  "init_mode": "QR",
  "currency_code": "INR",
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

1. Recommend binary representation standards for use in low network environment is encouraged.
2. Signed QR code content is mandatory to ensure security and detect any malicious requests / phishing attacks.
3. &#x20;Scanning of QR codes and verification of digitally singed QR code content is the responsibility of the payment apps on customer mobiles.
4. Payment Network provider shall manage the registry of all authorised **acquiring** banks allowed to onboard merchants and offer digitally singed QR codes.&#x20;
5. Additional features like push requests, deep linking through intent calls can be extended using this specification as baseline.

## 5. Signature checksum verification

....



