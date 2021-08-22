# Use OpenSSL With Verify

- [Verify CSR](#verify-csr)
- [Verify RSA private key](#verify-rsa-private-key)
- [Verify Certificate](#verify-certificate)
- [Verify Certificate with PKCS 12 Format](#verify-certificate-pkcs-12)
- [Verify authority of the signatory of the certificate](#verify-authority-signatory-certificate)
- [Verify hash certificate](#verify-hash-certificate)
- [Verify Date PEM](#verify-date-PEM)
- [Verify content certificate](#verify-content-certificate)





## Verify CSR

Execute the following command via console

```bash
// Example 1
openssl req -noout -text -verify -in acme.csr

// Example 2
openssl req -noout -text -verify -in www.acme.es.csr
```

Ensure that you send CSRs to the issuing authority with the required details



## Verify RSA private key

Execute the following command via console

```bash
// Example 1
openssl rsa -in acmeprivate.key –check

// Example 2
openssl rsa -noout -text -check -in www.acme.es.key
```



## Verify Certificate

Execute the following command via console

```bash
// Example 1
openssl x509 -in certfile.pem -text –noout

// Example 2
openssl x509 -noout -text -in www.acme.es.crt

// Example 3
openssl verify -purpose sslserver -CAfile certificatebundle.pem -verbose www.acme.es.crt
```



## Verify Certificate with PKCS 12 Format

Execute the following command via console

```bash
// Example 1
openssl pkcs12 –info –nodes –in cert.p12

// Example 2
openssl pkcs12 -info -in www.acme.es.pfx
```



## Verify authority of the signatory of the certificate

Execute the following command via console

```bash
openssl x509 -in certfile.pem -noout -issuer -issuer_has
```



## Verify hash certificate

Execute the following command via console

```bash
openssl x509 -noout -hash -in <filename_cert>.pem
```



## Verify Date PEM

Execute the following command via console

```bash
openssl x509 -noout -in <filename_cert>.pem -dates
```



## Verify content certificate

Execute the following command via console

```bash
// Example 1
keytool -printcert -file <filename_cert>.pem

// Example 2
keytool -printcert -v -file <filename_ca_cert.pem>.pem

// Example 3
$ openssl pkcs12 -info -in <filename_cert>.pfx
```