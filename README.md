# Install-Docker-in-Raspberry-Pi-4

# Installing Docker on Raspberry Pi 4 Board

# To install Docker on Raspberry Pi 4, we need these environment:

  1) A Raspberry Pi 4 single-board computer.
  2) Internet connectivity on the Raspberry Pi 4.
  3) A micro SD card with the Raspberry Pi OS image on it.

Before install Docker on our Raspberry Pi OS, we must update all the packages on our Raspberry Pi OS. 
First we need to update APT package repository cache with the following command

>	$ sudo apt-get update

Now we need to upgrade. Press Y and press Enter button. To update all the packages on our Raspberry Pi OS, enter following command

>	$ sudo apt upgrade

After end this process, we must reboot the system using this command

>	$ sudo reboot

Next main step is installing Docker on Raspberry Pi OS. 

We must download the Docker installation script on our Raspberry Pi 4 using following command line

>	$ curl -fsSL https://get.docker.com -o get-docker.sh

The Docker installation script get-docker.sh will be download in your current working directory. Type ls command to check.

Next we need to run the Docker installation script get-docker.sh as root with the following command

>	$ sudo bash get-docker.sh

Docker script will download and install all the packages form the internet.

After Docker is installed, add our login user to the docker group using following command

>	$ sudo usermod -aG docker $(whoami)

Reboot the Raspberry Pi OS for changes to take effect using following command line

>	$ sudo reboot

After reboot Raspberry Pi OS, then run the following command to verify whether docker is installed or not

>	$ docker version

After successfully installed I have got following output:

pi@pivpn:~ $ docker version 
Client: Docker Engine - Community
 Version:           20.10.2
 API version:       1.41
 Go version:        go1.13.15
 Git commit:        2291f61
 Built:             Mon Dec 28 16:18:13 2020
 OS/Arch:           linux/arm
 Context:           default
 Experimental:      true

Server: Docker Engine - Community
 Engine:
  Version:          20.10.2
  API version:      1.41 (minimum version 1.12)
  Go version:       go1.13.15
  Git commit:       8891c58
  Built:            Mon Dec 28 16:15:48 2020
  OS/Arch:          linux/arm
  Experimental:     false
 containerd:
  Version:          1.4.3
  GitCommit:        269548fa27e0089a8b8278fc4fc781d7f65a939b
 runc:
  Version:          1.0.0-rc92
  GitCommit:        ff819c7e9184c13b7c2607fe6c30ae19403a7aff
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0

Second main step is installing Docker Compose on Raspberry Pi OS

If we need multiple containers, such as a web server container, honeypot and a database server container then we need to use Docker compose.
If we use RAW Docker, we need to start, stop, and configure these containers separately.

Before install Docker Compose, we must install Python???s pip package. We can install it on Raspberry Pi OS with the following command

>	$ sudo apt install python3-pip ???y

Once complete the install Python???s pip package we can install Docker Compose using following command

>	$ sudo pip3 install docker-compose

After install Docker Compose, then run the following command to check whether we can access it or not

>	$ docker-compose version

After successfully installed I have got following output:

pi@pivpn:~ $ docker-compose version
docker-compose version 1.28.2, build unknown
docker-py version: 4.4.1
CPython version: 3.7.3
OpenSSL version: OpenSSL 1.1.1d  10 Sep 2019

After successfully installed Docker I have got following output from Docker Image:

pi@pivpn:~ $ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
4ee5c797bcd7: Pull complete 
Digest: sha256:31b9c7d48790f0d8c50ab433d9c3b7e17666d6993084c002c2ff1ca09b96391d
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (arm32v7)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
