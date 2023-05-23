# Hyperledger Fabric Transaction Flow

1.  Channel is properly setup and running
2.  A Certificate Authority (CA) is setup and running
3.  The application user has registered and enrolled with the organization's certificate authority (CA) and received back necessary cryptographic material, which is used to authenticate to the network
4.  The chaincode is installed on the peers and instantiated on the channel
5.  The chaincode contains logic defining a set of transaction instructions and agreed upon price for an asset
6.  An endorsement policy has also been setup for this chaincode, stating that all peers must endorse any transaction


## Transaction Flow Breakdown

1.  Transaction proposal is sent to the endorsing peers
2.  Endorsement response are sent back to the Client by the endorsing peers
3.  Client sends Endorsement Response to the Ordering Services
4.  Ordering Services updates the ledger using the Endorsement Response
5.  Ordering Services receives response from Committing Peers
6.  The response is setting to the other peers informing them the transaction has been committed and that the ledger has been updated
7.  Lastly, connected peers revise their ledger to be in sync with the channel ledger

![HLF](img/hlf-transaction-flow.png)
