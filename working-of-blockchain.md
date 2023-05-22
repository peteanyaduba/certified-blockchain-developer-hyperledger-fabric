## Hyperledger Fabric

1.  When a user uses a blockchain application through the user interface, the request on the application does not go to the blockchain directly
2.  The application creates a future update proposal and submits a request for confirmation over the blockchain
3.  With the request, the application seek to modify the data stored in the blockchain, or the current state of the blockchain
4.  At present, the blockchain is at a stage where all the data has been sent; and we want to add one more transaction on top of that
5.  For this, we will modify the state of the blockchain
6.  The first step is that the application creates a proposal and sends to endorsing peers
7.  Endorsing peers are peers only with special privileges
8.  The job of the peers is to verify and validate the transaction which is coming in
9.  This is done through a simple process
10. Everyone connected to hyperledger fabric blockchain has a peer that holds the state of their blockchain
11. Similarly, endorsing peers have their state of the blockchain. They execute the transaction which is coming in along by simulating it over a copy of the ledger
12. Simulating means that they don't directly change the state of the blockchain.
13. But instead, they hold a copy of the state of the blockchain and then implement the transaction proposal on that copy of the blockchain
14. If the endorsing peer is executed directly over a blockchain, then they are going to change the state of the blockchain as a whole which is available to the complete network