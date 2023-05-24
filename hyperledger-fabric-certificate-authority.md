# Hyperledger Fabric CA - Certificate Authority

1.  Hyperledger Fabric CA is a Certificate Authority for Hyperledger Fabric which acts as a tool using which you can generate certificates
    -  Hyperledger Fabric uses a library to create certificates but the library can be altered to use custom libraries like OpenSSL
2.  You can generate certificates by specifying the username, password and affiliations which is called Enrollment
    -   Once the certificate is generated, it is known as Enrollment
    -   The Enrollment provides us with multiple functionalities such as:
        -   Certificate renewal and revocation
        -   Registration of identities, or connects to LDAP as the user registry
        -   Issuance of new Enrollment certificates
3.  Hyperledger Fabric CA consists of both components, a client and a server

## Fabric Certificate Authority Architecture

![HLF](img/hlf-ca-architecture.png)
