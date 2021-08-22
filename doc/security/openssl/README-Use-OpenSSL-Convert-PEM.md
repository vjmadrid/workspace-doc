# Use OpenSSL With Convert PEM


- [Convert PEM to DER](#convert-PEM-to-DER)
- [Convert PEM to text](#convert-PEM-to-text)
- [Convert certificate + private key (PEM) to PKCS 12](#convert-cert-and-private-key-to-pkcs-12)
- [Convert PEM to PFX](#convert-PEM-to-PFX)
- [Convert PEM to P7B](#convert-PEM-to-P7B)






## Convert PEM to DER

Execute the following command via console

```bash
// Example 1
openssl x509 –outform der –in <filename_pem>.pem –out <filename_der>.der
```



## Convert PEM to text

Execute the following command via console

```bash
// Example 1
openssl x509 -text -in <filename_crt>.crt > <filename_crt>.crt.txt
```



## Convert certificate + private key (PEM) to PKCS 12

Execute the following command via console

```bash
// Example 1
openssl pkcs12 –export –out <filename_pfx>.pfx –inkey <filename_key>.pem –in <filename_pem>.pem

# With chain
openssl pkcs12 –export –out <filename_pfx>.pfx –inkey <filename_key>.pem –in <filename_pem>.pem -chain cacert.pem

// Example 2
openssl pkcs12 -export -in www.acme.es.crt -inkey www.acme.es.key -out www.acme.es.pfx
```



## Convert PEM to PFX

Execute the following command via console

```bash
openssl pkcs12 -export -out <filename>.pfx -inkey <filename_key>.key -in <filename>.crt -certfile <filenameCACert>.crt
```



## Convert PEM to P7B

Execute the following command via console

```bash
openssl crl2pkcs7 -nocrl -certfile <filename>.cer -out <filename>.p7b -certfile <filenameCACert>.cer
```