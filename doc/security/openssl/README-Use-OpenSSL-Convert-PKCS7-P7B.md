# Use OpenSSL With Convert


- [Convert P7B to PEM](#convert-P7B-to-PEM)
- [Convert P7B to PFX](#convert-p7B-to-PFX)




## Convert P7B to PEM

Execute the following command via console

```bash
// Example 1
openssl pkcs7 -print_certs -in <filename>.p7b -out <filename>.cer
```



## Convert P7B to PFX

Execute the following command via console

```bash
# Step 1
openssl pkcs7 -print_certs -in <filename>.p7b -out <filename>.cer
 
# Step 2
openssl pkcs12 -export -in <filename>.cer -inkey <filename>.key -out <filename>.pfx -certfile <filenameCACert>.cer
```