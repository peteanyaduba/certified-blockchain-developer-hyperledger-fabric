# Deploying the Hyperledger Container

    mkdir hlf && cd hlf

    curl -sSL http://bit.ly/2ysbOFE | bash -s 2.0.0

    export PATH=$PATH:$HOME/fabric-samples/bin

    cd ~/fabric-samples/fabcar/javascript

    sudo apt install npm

    npm update

## Start the Fabric engine -

    docker rm -f $(docker ps -aq)

    cd ~/fabric-samples/fabcar

    ./startFabric.sh

    cd ~/fabric-samples/fabcar/javascript

    node enrollAdmin.js

    node registerUser.js

    node query.js

    node invoke.js