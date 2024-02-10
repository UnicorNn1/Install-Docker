## Update the package repository
```bash
sudo apt update
```
## Install the prerequisite packages
```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
## Add the Docker GPG key
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
## Add the Docker repository to APT sources
```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```
## Update the package repository again
```bash
sudo apt update
```
## Install Docker
```bash
sudo apt install docker-ce
```
## Start and enable the Docker service
```bash
sudo systemctl start docker
sudo systemctl enable docker
```
## This code adds the Docker repository to your system, installs Docker from the repository, and then starts and enables the Docker service so that it starts automatically when your system boots.

To verify that Docker is installed and running, you can use the following command:
```bash
sudo systemctl status docker
```
## You should see output similar to the following, indicating that the Docker service is active and running:
```bash
● docker.service - Docker Application Container Engine
   Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
   Active: active (running) since Tue 2022-11-08 12:34:47 UTC; 1s ago
     Docs: https://docs.docker.com
 Main PID: 1118 (dockerd)
    Tasks: 5
   Memory: 43.7M
   CGroup: /system.slice/docker.service
           └─1118 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
```
## You can also use the docker command to verify that it is installed and working correctly. For example, you can run the following command to download and run the hello-world Docker image:
```bash
docker run hello-world
```
## This should download the hello-world image and run a container using that image, which will display a message and then exit. If this command completes successfully, it indicates that Docker is installed and working correctly on your system.
# You can also install Docker with a different command
## or Install Docker
```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```
```bash
sudo apt-get update
sudo apt-get install \
ca-certificates \
curl \
gnupg
```
```bash
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```
```bash
echo \
"deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
"$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update && apt upgrade -y
```
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```





