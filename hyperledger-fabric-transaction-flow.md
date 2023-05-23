# Hyperledger Fabric Transaction Flow

1.  Channel is properly setup and running
2.  A Certificate Authority (CA) is setup and running
3.  The application user has registered and enrolled with the organization's certificate authority (CA) and received back necessary cryptographic material, which is used to authenticate to the network
4.  The chaincode is installed on the peers and instantiated on the channel
5.  The chaincode contains logic defining a set of transaction instructions and agreed upon price for an asset
6.  An endorsement policy has also been setup for this chaincode, stating that all peers must endorse any transaction


## Transaction Flow Breakdown

1.  Transaction proposal is sent to the endorsing peers by the Client
2.  Endorsement response are sent back to the Client by the endorsing peers
3.  Client sends Endorsement Response to the Ordering Services
4.  Ordering Services updates the ledger using the Endorsement Response
5.  Ordering Services receives response from Committing Peers
6.  The response is setting to the other peers informing them the transaction has been committed and that the ledger has been updated
7.  Lastly, connected peers revise their ledger to be in sync with the channel ledger

<hr/>

![HLF](img/hlf-transaction-flow.png) 

### Transaction Flow - Orderer Services
<hr>

![HLF](img/hlf-transaction-flow-orderer.png)
<!-- <img src="img/hlf-transaction-flow-orderer.png"  width="600"> -->

## Transacton Proposal

1.  A client in an organization uses some SDK or an application to initiate the transaction
2.  The Transacton proposal is prepared and is sent to endorsing peers
3.  The proposal is a request to invoke a chaincode function so that data can be read and/or written to the peer ledger

![HLF](img/hlf-transaction-proposal.png)

## Endorsement Response

1.  After the transaction has been sent to the endorsement peers, the endorsing peers check for the validity of the format of the transaction proposal, for the duplicity of the transacton proposal, the signature check using Membership Service Provider and authorization of the requesting client.
2.  In case the transaction has a wrong client signature, or one that is not present with the Membership Service Provider, then, the client is not authorized to create a transaction over the hyperledger system. Thus it's necessary that the Client has a certificate issued by the MSP. And it is mandatory that the client use this issued certifiate to sign the transaction.
3.  After that, the endorsing peers take the transaction proposal inputs as arguments and forward them to chainode function. By input arguments it means the endorsing peers execute a chaincode set over the copy of the ledger.
4.  Once the Chaincode gets executed against the current state database to produce response value, read set and write set. For example, if using MySQL and have created an ID, then we know there is a user table with an identity 100. After that, a new entry is formed in the user table with the identity as 101.
5.  Similarly, in this database, we are not directly updating the ledger. Instead we are checking if after 100, 101 is coming or not. It updates a copy of the ledger after the 101st entry has come in, and it puts this entry as a read and write set within the transaction proposal.
6.  Then the Endorsing peers signs this transaction using their certificate. Once it is approved, the proposal response is sent to the client again.

![HLF](img/hlf-endoresment-response.png)