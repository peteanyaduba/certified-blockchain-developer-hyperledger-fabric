# Chaincode Introduction

1.  Chaincode is used to handle the business logic of the Hyperledger Blockchain network
2.  These are like smart contracts written in Ethereum and have some functionality of interacting with Blockchain network
3.  Only chaincode can read or manipulate data of Blockchain network like membership details, role and certificates of the peers
4.  It must be installed on every single peer of a channel or an organization
5.  There can be multiple chaincode and they can have different endorsement policies incorporated with each chaincode.

## What does Chaincode look like
1.  Chaincode is an isolated program that maintains its own private state on the ledger
2.  Each chaincode implements:
    -   an Init method and 
    -   an Invoke method
3.  Init is used for setting up the chaincode
4.  Invoke is used to call the functions from the chaincode.
5.  Both methods described above accepts a ChaincodeStubInterface parameter which
    -   carries a client for interacting with the ledger
    -   and for querying other chaincodes
    -   ChaincodeStubInterface is the standard interface implemented by hlf
6.  ChaincodeStubInterface also has a list of arguments passed to the chaincode, which allows the chaincode to implement different behaviours as per the different function calls.


## Chaincode lifecycle
1.  The entities must agree on a chaincode before it can be used.
    -   Chaincodes get instantiated when two entities agree on a particular aspect.
    -   For instance, 
        -   when a client says "I am going to make a transaction"
        -   the endorsing peer "I am going to endorse this transaction"
        -   the ordering service "I want to deliver this transaction"
    -   The chaincode is then initiated on all these three above to perform specific operations.
2.  Quite similar to Ethereum, Chaincode is synonymous with Smart Contract.
    -   If two parties agree on something, we can initiate a chaincode which is like an agreement between them.
    -   Entities that agree to the chaincode must be able to review the chaincode and sign it to prevent tampering.
    -   For instance, if 
        -   The operations channel initiating another chaincode in the pharmacy channel other than the operations channel, the pharmacy channel should be able to see, review and sign the chaincode running behind them.
        -   Therefore, everytime my chaincode is called upon, it's going to be through some peers or clients
        -   These peers or clients will sign the chaincode to prevent any tampering from any external sources
3.  Chaincode is passed around using the package format called "ChaincodeDeploymentSpecification", "ChaincodeDeploymentSpec", which includes the source code, the policies for instantiating the chaincode, and the list of entities that have agreed and signed on the chaincode.
4.  Properly endorsed chaincode can be installed and instantiated on Peers in the network.
    -   For instance, once the Medicine channel receives a request, they will dispatch a medicine according to the operation procedure that is being performed. Then the chaincode can be installed and instantiated by both the Operation Parties as well as the Pharmacy parties.
5.  Peer uses Docker to run a container with the chaincode inside
    -   To instantiate the chaincode, the peers use docker containers to install it
    -   With the help of Docker, a single application created can be deployed to any network since Docker is environment free.
6.  Peer is responsible for managing the chaincode container's lifecycle and networking
    -   The peers who receive the chaincode and install it are the ones managing it.
    -   Peers maintain the lifecylce and networking of the complete chaincode
7. There is a special kind of chaincode called System chaincode which runs as part of the Peer process, not in a separate container. It's used to implement low-level ledger features like the endorser system, query system and validation system.
    -   They give the permission and specification on who is the endorsement peer, committing peer, ordering services, etc are setup inside the system chaincode.
    -   Whenever the anchor peer creates everything, it also creates the system chaincode which is deployed on different computing machines and they perform a specific function depending on the system chaincode.
    -   Minor level ledger system features like the endorsing system, query system and validation system, are deployed using the system chaincode.
    -   On top of these, there are normal chaincodes which are like smart contracts where they will perform certain functions in the blockchain