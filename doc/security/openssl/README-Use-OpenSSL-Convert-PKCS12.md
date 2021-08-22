# Use OpenSSL With Convert


- [Convert PKCS 12 to PEM](#convert-pkcs-12-to-PEM)




## Convert PKCS 12 to PEM

Execute the following command via console

```bash
// Example 1
openssl pkcs12 –in cert.p12 –out cert.pem

// Example 2
openssl pkcs12 -nodes -in www.acme.es.pfx -out www.acme.es.crt
```

