# Hyperledger Setup Steps

1.  Install Curl
    -   
        sudo apt update && sudo apt upgrade
        sudo apt install curl
        curl --version
2.  Install Docker and Docker Compose
    -   
        sudo apt-get update

        sudo apt-get install \
            apt-transport-https \
            ca-certificates \
            curl \
            gnupg-agent \
            Software-properties-common

        curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

        sudo apt -key fingerprint OEBFCD88

        sudo add-apt-repository \
            "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
            $(lab_release -cs) \
            stable"
        
        sudo apt-get update

        sudo apt-get install docker-ce docker-ce-cli containerd.io

        apt-cache madison docker-ce

        sudo apt-get install docker-ce=5:20.10.3-3-0-ubuntu-focal docker-ce-cli=5:20.10.3-3-0-ubuntu-focal containerd.io
        
        sudo docker run hello-world

        sudo usermod -aG docker $(USER)
    -   Docker Compose 
        -   
            sudo curl -L
            


