

## Installing docker and docker compose 

1. sudo apt update && sudo apt upgrade -y
2. sudo apt install -y ca-certificates curl gnupg
3. curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

4. sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io
5. sudo usermod -aG docker $USER
6. sudo curl -L "https://github.com/docker/compose/releases/download/$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d'"' -f4)/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

7. sudo chmod +x /usr/local/bin/docker-compose
8. docker-compose --version


## Inslalling docker image 

### 1. Download the image
docker pull python:3.12.8

### 2. Start the container interactively
docker run -it --entrypoint bash python:3.12.8

### 3. Check pip version
pip --version


For me --> 

### Exit the container
exit  # or Ctrl + P, Ctrl + Q to detach

### See running containers
docker ps

### See all containers (including stopped ones)
docker ps -a

### Restart and re-enter a container
docker start -ai <container_id>

### Stop a running container
docker stop <container_id>

#### Remove a container
docker rm <container_id>

### Remove the Python image (optional)
docker rmi python:3.12.8


