# Use Keytool With Verify




- [Verify the content of a (proprietary) keystore](#verify-content-propietary-keystore)
- [Verify the content of a keystore (external)](#verify-content-external-keystore)
- [Verify the content of a specific value](#verify-content-specific-value)
- [Verify the content of a certificate](#verify-content-certificate)


The own keystore is the one that is usually generated in the user's own home directory as ".keystore".

Use parameter : -storepass <keyStorePass>





## Verify the content of a (proprietary) keystore

Execute the following command via console

```bash
// Example 1
keytool -list
```



## Verify the content of a keystore (external)

Execute the following command via console

```bash
// Example 1
keytool -list -v -keystore <path_name_keystore>.jks
```



## Verify the content of a specific value

Execute the following command via console

```bash
// Example 1
keytool -list -v -alias <alias_name>

// Example 2 
keytool -list -keystore <path_name_keystore>.jks -alias <alias_name>
```



## Verify the content of a certificate

Execute the following command via console

```bash
// Example 1
keytool -printcert -file <filename_cert.pem>

// Example 2 
keytool -printcert -v -file cacert.pem
```