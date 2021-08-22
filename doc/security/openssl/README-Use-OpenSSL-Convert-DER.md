# Use OpenSSL With Convert DER


- [Convert DER to PEM](#convert-DER-to-PEM)





## Convert DER to PEM

Execute the following command via console

```bash
openssl x509 –inform der –in <filename_der>.der –out <filename_pem>.pem
```

Usually, the certificate authority will give you an SSL certificate in .der format, and if you need to use them in apache or .pem format, the above command will help you.


