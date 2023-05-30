# Hyperledger Setup Steps

1.  Install Curl
    -   
        sudo apt update && sudo apt upgrade
        sudo apt install curl
        curl --version
2.  Install Docker and Docker Compose
    -   
        sudo apt-get update

        sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common

        curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

        sudo apt-key fingerprint 0EBFCD88

        sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
        
        sudo apt-get update

        sudo apt-get install docker-ce docker-ce-cli containerd.io

        apt-cache madison docker-ce

        HLF prerequisites - Commands

3.  Install Git

        sudo apt-get update

        sudo apt-get install git

        Git –version


4.  Install cURL

        sudo apt install curl

        curl --version


5.  Install Docker

        sudo apt install docker.io

        docker --version

        sudo systemctl start docker

        sudo systemctl enable docker

        sudo groupadd docker

        sudo usermod -aG docker ${USER}

6.  Logout and login to run further command

        docker run hello-world

        ----If you still get docker.sock issues, run the command:

        sudo setfacl --modify user:$USER:rw /var/run/docker.sock


7.  Install Docker Compose

        sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

        sudo chmod +x /usr/local/bin/docker-compose

        docker-compose --version


8.  Install GoLang

        wget -c https://dl.google.com/go/go1.18.1.linux-amd64.tar.gz -O - | sudo tar -xz -C /usr/local


9.  Edit .profile file

        Open "~/.profile" and append the code below to the file

        nano ~/.profile

        export GOPATH=$PATH:/usr/local/go
        export PATH=$PATH:$GOPATH/bin

        source ~/.profile

10. LOGOUT AND LOGIN AGAIN

        go version

        # export GOPATH=$PATH:/usr/local/go
        # export PATH=$PATH:/usr/local/go/bin


        ***NOTE***
        # Before running any code first check that go is reachable. Run the code below

        go version

        # If go is not reachable run the code below to set the go path. Errors can cause the go path to be terminated

        source ~/.profile

        # Then check if go is now reachable

        go version



11. Install nvm, node and npm

        sudo apt-get install build-essential libssl-dev

        curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash

        Paste a resemblance of the following code to continue

        export NVM_DIR="$HOME/.nvm"
        [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
        [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"

        nvm --version

        nvm install v14.15.4

        nvm use v14.15.4

        node --version

        npm --version


12. Working with Docker

        ---Check if docker volumes exist

        docker volume ls

        ---Stop Docker containers

        docker stop $(docker ps -aq)

        ---Remove Docker containers

        docker rm $(docker ps -aq)

        ---Remove Docker volumes

        docker volume prune

        ---Remove Docker Image

        # docker rmi <image_name>

