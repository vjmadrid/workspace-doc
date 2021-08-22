# Use OpenSSL With Private Key


- [Create RSA private key](#create-rsa-private-key)
- [Create ECC private key](#create-ecc-private-key)





## Create RSA private key

Execute the following command via console

```bash
// Example 1
openssl genrsa -out acmeprivate.key 2048

// Example 2
openssl genrsa -out www.acme.es.csr 2048
```



## Create ECC private key

Execute the following command via console

```bash
// Example 1
openssl ecparam -out acme.key -name prime256v1 -genkey
```