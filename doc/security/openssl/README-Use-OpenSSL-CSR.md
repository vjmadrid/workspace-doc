# Use OpenSSL With CSR


- [Create new CSR](#create-new-csr)
- [Create new CSR with private key](#create-new-csr-with-private-key)
- [Create new CSR with other certificate](#create-new-csr-with-other-certificate)





## Create new CSR

Execute the following command via console

```bash
// Example 1
openssl req -nodes -keyout -newkey rsa: 2048 acme.key -out acme.csr

// Example 2
openssl req -sha256 -nodes -newkey rsa:2048 -keyout www.acme.es.key -out www.acme.es.csr
```

Generate CSR file and key RSA file

Shoul send the CSR file to certificate issuing authority and they will give you a signed certificate mainly in der or pem



## Create new CSR with private key

Execute the following command via console

```bash
// Example 1
openssl req –new –key existing.key –out certificate.csr

// Example 2
openssl req -new -sha256 -key www.acme.es.key -out www.acme.es.csr
```



## Create new CSR with other certificate

Execute the following command via console

```bash
// Example 1
openssl x509 -x509toreq -in www.orig-acme.es.crt -out www.acme.es.csr -signkey www.acme.es.key
```



