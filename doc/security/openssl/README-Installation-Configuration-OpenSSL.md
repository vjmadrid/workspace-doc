# Installation / Configuration OpenSSL

OpenSSL (pip installs packages) is the the tool for create, manage and convert SSL certificates

Concepts :

* **SSL:** Capa de conexión segura
* **CSR:** solicitud de firma de certificado
* **TLS:** seguridad de la capa de transporte
:**PEM:** Correo con privacidad mejorada
* **DER:** Reglas de codificación distinguidas
* **SHA:** Algoritmo hash seguro
* **PKCS:** estándares de criptografía de clave pública



Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install Pip](#install-pip)
- [Verify Pip Version](#verify-pip-version)
- [Upgrade Pip](#upgrade-pip)
- [Install Package](#install-package)





## <a name="check-prerequisites">Check Prerequisites</a>

It is available together with the Python installation

 * Since Python 2 version 2.7.9
 * Since Python 3 version 3.4





## <a name="install-pip">Install OpenSSL</a>

**Use Brew for Mac**

```bash
brew install openssl
```






## Self-signed certificate

* XXX





## <a name="create-rsa-private-key">Create RSA private key</a>

Execute the following command via console

```bash
// Example 1
openssl genrsa -out acmeprivate.key 2048

// Example 2
openssl genrsa -out www.acme.es.csr 2048
```


## Show and verify certificates

* Verify CSR


## <a name="verify-csr">Verify CSR</a>

Execute the following command via console

```bash
// Example 1
openssl req -noout -text -verify -in acme.csr

// Example 2
openssl req -noout -text -verify -in www.acme.es.csr
```

Ensure that you send CSRs to the issuing authority with the required details




## <a name="verify-rsa-private-key">Verify RSA private key</a>

Execute the following command via console

```bash
// Example 1
openssl rsa -in acmeprivate.key –check

// Example 2
openssl rsa -noout -text -check -in www.acme.es.key
```


## <a name="verify-certificate">Verify Certificate</a>

Execute the following command via console

```bash
// Example 1
openssl x509 -in certfile.pem -text –noout

// Example 2
openssl x509 -noout -text -in www.acme.es.crt
```

## <a name="verify-certificate-pkcs-12">Verify Certificate with PKCS 12 Format</a>

Execute the following command via console

```bash
// Example 1
openssl pkcs12 –info –nodes –in cert.p12

// Example 2
openssl pkcs12 -info -in www.acme.es.pfx
```



## <a name="verify-authority-signatory-certificate">Verify authority of the signatory of the certificate</a>

Execute the following command via console

```bash
openssl x509 -in certfile.pem -noout -issuer -issuer_has
```

## <a name="verify-hash-certificate">Verify hash certificate</a>

Execute the following command via console

```bash
openssl x509 -noout -hash -in example.pem
```

## <a name="convert-DER-to-PEM">Convert DER to PEM</a>

Execute the following command via console

```bash
openssl x509 –inform der –in sslcert.der –out sslcert.pem
```

Usually, the certificate authority will give you an SSL certificate in .der format, and if you need to use them in apache or .pem format, the above command will help you.


## <a name="convert-PEM-to-DER">Convert PEM to DER</a>

Execute the following command via console

```bash
openssl x509 –outform der –in sslcert.pem –out sslcert.der
```

## <a name="verify-date-PEM">Verify Date PEM</a>

Execute the following command via console

```bash
openssl x509 -noout -in certificate.pem -dates
```


## <a name="convert-cert-and-private-key-to-pkcs-12">Convert certificate + private key to PKCS 12</a>

Execute the following command via console

```bash
openssl pkcs12 –export –out sslcert.pfx –inkey key.pem –in sslcert.pem

# With chain
openssl pkcs12 –export –out sslcert.pfx –inkey key.pem –in sslcert.pem -chain cacert.pem
```


## <a name="convert-pkcs-12-to-PEM">Convert PKCS 12 to PEM</a>

Execute the following command via console

```bash
openssl pkcs12 –in cert.p12 –out cert.pem
```


## <a name="test-url-with-ssl-certificate">Convert PKCS 12 to PEM</a>

Execute the following command via console

```bash
openssl s_client -connect yoururl.com:443 –showcerts

openssl s_client -connect secureurl.com:443 2> / dev / null | openssl x509 -noout –enddate

openssl s_client -connect www.acme.es:443
```


## <a name="verify-use-url-ssl-version">Verify Version SSL used by URL</a>

Execute the following command via console

```bash
openssl s_client -connect secureurl.com:443 -ssl2

openssl s_client -connect secureurl.com:443 –ssl3

openssl s_client -connect secureurl.com:443 –tls1

openssl s_client -connect secureurl.com:443 –tls1_1

openssl s_client -connect secureurl.com:443 –tls1_2
```
