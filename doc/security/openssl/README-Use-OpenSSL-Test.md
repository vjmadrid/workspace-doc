# Use OpenSSL With CSR


- [Test URL with SSL Certificate](#test-url-with-ssl-certificate)
- [Test Version SSL used by URL](#test-use-url-ssl-version)
- [Test same public key : CSR, CRT and key](#test-use-url-ssl-version)





## Test URL with SSL Certificate

Execute the following command via console

```bash
// Example 1
openssl s_client -connect www.acme.es:443 –showcerts

// Example 2
openssl s_client -connect www.acme.es:443 2> / dev / null | openssl x509 -noout –enddate

// Example 3
openssl s_client -connect www.acme.es:443
```



## Test Version SSL used by URL

Execute the following command via console

```bash
openssl s_client -connect www.acme.es:443 -ssl2

openssl s_client -connect www.acme.es:443 –ssl3

openssl s_client -connect www.acme.es:443 –tls1

openssl s_client -connect www.acme.es:443 –tls1_1

openssl s_client -connect www.acme.es:443 –tls1_2
```



## Test same public key : CSR, CRT and key

Execute the following command via console

```bash
openssl req -noout -modulus www.acme.es.csr | openssl sha256
openssl x509 -noout -modulus www.acme.es.crt | openssl sha256
openssl rsa -noout -modulus www.acme.es.key | openssl sha256
```