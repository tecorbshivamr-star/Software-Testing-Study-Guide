# SOAP API Testing

## What is SOAP?
**SOAP (Simple Object Access Protocol)** is a strict, XML-based protocol specification for exchanging structured information in the implementation of web services.

---

## SOAP vs REST

| Feature | SOAP | REST |
|---|---|---|
| **Format** | Strictly XML | JSON, XML, HTML, plain text |
| **Protocol/Style** | Protocol | Architectural Style |
| **Strictness** | High (WSDL contract required) | Low (Flexible) |
| **State** | Can be stateful | Stateless |
| **Bandwidth** | Heavy (verbose XML payload) | Lightweight |

---

## Understanding WSDL
SOAP relies heavily on a **WSDL (Web Services Description Language)** file. This XML document defines:
- The operations (methods) the web service provides.
- The input/output XML format.
- The URL location of the service.

---

## Typical SOAP Request & Response

### SOAP Request Payload
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:web="http://www.example.com/webservice">
   <soapenv:Header/>
   <soapenv:Body>
      <web:GetStockPrice>
         <web:StockSymbol>AAPL</web:StockSymbol>
      </web:GetStockPrice>
   </soapenv:Body>
</soapenv:Envelope>
```

### SOAP Response Payload
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/">
   <soapenv:Body>
      <web:GetStockPriceResponse xmlns:web="http://www.example.com/webservice">
         <web:Price>175.50</web:Price>
      </web:GetStockPriceResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

---

## 📌 Key Takeaways
- SOAP is highly secure and has built-in transaction support (ACID compliance)—popular in legacy banking systems.
- Testing SOAP involves validating strict XML formats against the WSDL schema.
- Tools like **SoapUI** and **Postman** are standard for validating SOAP endpoints.
