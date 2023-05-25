# Hyperledger Fabric - Membership Service Provider

1.  Membership Service Provider (MSP) is the pluggable interface which supports variety of credentials architectures.
    -   MSP supports all the Certificate Authorities (CAs) or CA-servers being used behind the MSP
    -   MSP is the interface that requests the server because the clients and SDKs can't or don't approach the CA servers directly. Instead, they go to the MSPs which internally has the specific verifications and validations running. Only after they are fulfilled, the request is sent to the CA for generation of certificate.
2.  The Membership Service Provider, MSP involves key aspects for its functioning:
    -   MSP Has four different vital concepts
        -   Concrete identity format
            -   It provides with a particular identity format. Whether using a default or custom defined identity format, both are possible with hyperledger fabric.
            -   For instance, an identity format could be just a normal user with a first name, last name, phone number and email, or it could include addresses and security questions too. This will give a real identity format
        -   User credential validation
            -   Validation is an essential element in hyperledger fabric and earlier also discussed how the validation framework is running at different levels of hyperledger fabric.
            -   Validation is provided by running checksums behind it. This validates all the user credentials as per the requirement. 
            -   Validation can also include the 2Factor Authorization and email confirmation
                -   For instance, we can provision a chaincode which has a 2 factor authorization and email confirmation over our MSP through which we can run a validation process for the user.
        -   User credential revocation
            -   Revocation system is an essential part of the certificate authority. 
                -   For example, if there are vendors who are getting connected to the private blockchain ith a one year contract, then we can create and revoke the certificate after one year. We don't have to revoke manually. We can add the revocation command through the SDKs. Or we can put the revocation with that certificate itself; specifying that it is a time-based certificate where cancellation will happen automatically once the time period exhausts.
        -   Signature generation and verification
            -   Each peer signs the transaction with their respective certificate before sending it to other peers. The other peers verifies the signatures with the helpf of the MSPs.
3.  A hyperledger fabric blockchain etwork can be governed by one or more MSPs, which provides modularity of membership operations, and interoperability across different membership standards
    -   Hence, there can be a possibility of different organizations running on one single blockchain.
        -   Assume we are creating a solution for a bank, when we have multiple banks connected to one single blockchain and there is one MSP for each bank.
        -   This way each bank can have their format of identity, validation and verification which can be used to interact with the blockchain.
        -   It is a more modular approach to membership operations and inter-operability across different standards which are being used. Therefore, some banks can have a certain standard of user format another bank some additional measures of user format