# Use OpenSSL With CSR


- [Create self-signed certificate](#create-self-signed-certificate)





## Create self-signed certificate

Execute the following command via console

```bash
// Example 1
openssl req -x509 -sha256 -nodes -days 730 -newkey rsa: 2048 -keyout acmeselfsigned.key -out acmecert.pem

// Example 2
openssl req -x509 -newkey rsa:2048 -nodes -keyout www.acme.es.key -out www.acme.es.crt -days 365
```

Generate self-signed certificate 

If no include -days then generte a certificate valid only one month