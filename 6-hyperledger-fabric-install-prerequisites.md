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
            sudo curl -L "https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

            sudo chmod +x /usr/local/bin/docker-compose

        <LOGOUT AND RELOGIN AT THIS STEP>
3.  Install Go
    -   ### Go to the directory you want to install go and run the curl command to download it 
        <hr>   
   
            curl -O https://d1.google.com/go/go1.10.3.linux-amd64.tar.gz

            sha256sum go1.10.3.linux-amd64.tar.gz

            tar xvf go1.10.3.linux-amd64.tar.gz

            sudo chown -R root:root ./go
            sudo mv go /usr/local

            mkdir $HOME/go_projects

    -   ### Paste the following code below into the ./profile 
        <hr>   
            
            sudo nano ./profile

            export GOROOT=$HOME/go
            export GOPATH=$HOME/go_projects
            export PATH=$PATH:/usr/local/go/bin:$GOROOT/bin

            Press Ctrl+X and type Y when done.

4.  Install nodejs
    <hr>

        sudo apt install nodejs



