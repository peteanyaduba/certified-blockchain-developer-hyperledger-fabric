## Hyperledger Fabric

1. When a user uses a blockchain application through the user interface, the request on the application does not go to the blockchain directly
2. The application creates a future update proposal and submits a request for confirmation over the blockchain
3. With the request, the application seek to modify the data stored in the blockchain, or the current state of the blockchain
4. At present, the blockchain is at a stage where all the data has been sent; and we want to add one more transaction on top of that
5. For this, we will modify the state of the blockchain
    The first step is that the application creates a proposal and sends to endorsing peer