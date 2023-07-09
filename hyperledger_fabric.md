# What is Hyperledger Fabric?

#### Hyperledger Fabric is an open-source blockchain framework designed for building enterprise-grade solutions. It provides a permissioned network architecture, allowing organizations to create private and secure blockchain networks. With its modular design, Fabric enables the implementation of smart contracts and supports various consensus algorithms, making it suitable for a wide range of business use cases. It offers enhanced privacy features and allows for scalability and flexibility, making it a popular choice for organizations looking to leverage blockchain technology for their specific needs.

## Steps and links used for Installing Hyper Ledger Fabric on Windows

### 1. Open power shell in Admin mode.
### 2. Enable windows SubSystem for Linux
    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

### 3. Enable Virtual Machine feature
    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

### 4. Set WSL-2 as default version
    wsl --set-default-version 2

### 5. Install Ubuntu app from windows store:
#### Open the Microsoft Store and install Ubuntu 20.04 LTS here

### 6. Install windows terminal
#### It enables multiple tabs, quickly between the Linux command line and the windows command prompt.

### 7. Download linux kernel update package:
#### To update the WSL package download setup at the below-mentioned link, it needs admin privilege.
    https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi

### 8. Open Windows Terminal and add a new ubuntu tab, you won’t be able to see the ubuntu terminal. Under add new terminal section.
### 9. Open Installed, “Ubuntu 20.04 LTS” once, So that it will be linked with Windows terminal.
### 10. Updating and installing basic packages for Ubuntu.
    sudo apt update && sudo apt upgrade
    ### 11. Download Docker for windows latest version from
    https://desktop.docker.com/win/stable/amd64/Docker%20Desktop%20Installer.exe
### 12. Enable Docker for Ubuntu

#### 1. Go to Settings
#### 2. Resources
#### 3. WSL integration
#### 4. Enable Ubuntu-20.04
#### 5. Then hit Apply & restart
#### 6. This may take few minutes
#### 7. After Enabling this we will get docker in the ubuntu command line

### 13. Run following command to check if you are able to access it on Ubuntu
    docker –version
    docker-compose –version

### 14. Run following command to install and update basic packages on Ubuntu
    sudo apt update
    sudo apt upgrade

### 15. cURL
#### Check if cURL already exists
    curl –v

### 16. If cURL doesn't exists then install it via following command 
    sudo apt-get install curl

### 17. Check if Go lang exists
    go version

### 18. If Go doesn't then install with following steps: Download the Go lang package for Linux from here.
    sudo wget https://golang.org/dl/go1.16.3.linux-amd64.tar.gz

### 19. The following command will extract the zip file at the downloaded location 
    tar xvf go1.16.3.linux-amd64.tar.gz

### 20. Set GOPATH using following command
    export GOPATH=$HOME/go
    export PATH=$PATH:$GOPATH/bin

### 21. Run the following command to verify that Go lang is installed successfully
    go version

### 22. Run the following command to if git is installed
    git -–version

### 23. Install Hyperledger Fabric and Fabric samples
#### Note: Hyperledger fabric version is 2.3.2

### 24. Create a directory with following command
#### Creates a new Directory:
    mkdir -p $HOME/go/src/github.com/
#### Navigate to that created directory:
    cd $HOME/go/src/github.com/

### 25. Download the latest release of fabric samples and docker images.

#### Run following command under $HOME/go/src/github.com/ directory
    curl -sSL https://bit.ly/2ysbOFE | bash -s

### 26. navigate to fabric folder
    cd $wsl
    cd go/src/github.com/fabric-samples

### 27. Go to test-network
    cd test-network
#### Run following command to remove existing any container or artifacts form previous run.
    ./network.sh down

### 28. Running following will boot up fabric test network
    ./network.sh up

### 29. Run following command to list down all running docker images in docker
    docker ps –a

### 30. Same you can look at docker GUI
