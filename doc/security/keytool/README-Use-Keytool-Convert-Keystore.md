# Use Keytool With Convert CSR


- [Convert Keystore to PKCS12](#convert-keystore-to-PKCS12)





## Convert Keystore to PKCS12

Execute the following command via console

```bash
keytool -importkeystore -srckeystore <filename_jks>.jks -destkeystore <filename_p12>.p12 -srcstoretype jks -deststoretype pkcs12
```



