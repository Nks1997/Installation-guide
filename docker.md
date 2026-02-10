# Docker Installation Guide

## 1️⃣ Docker Installation on Ubuntu

1. Update system packages
   sudo apt-get update

2. Install required packages
   sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common

3. Add Docker GPG key
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

4. Add Docker repository
   echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

5. Install Docker
   sudo apt-get update
   sudo apt-get install -y docker-ce docker-ce-cli containerd.io

6. Verify Docker installation
   docker --version
   sudo systemctl status docker

7. Optional: Run Docker as non-root user
   sudo usermod -aG docker $USER
   newgrp docker

---

## 2️⃣ Docker Installation on Windows (Using PowerShell)

1. Download Docker Desktop Installer
   Invoke-WebRequest -UseBasicParsing -OutFile docker-installer.exe "https://desktop.docker.com/win/stable/Docker%20Desktop%20Installer.exe"

2. Install Docker Desktop
   Start-Process -Wait -FilePath .\docker-installer.exe

3. Start Docker Desktop
   Start-Process "C:\Program Files\Docker\Docker\Docker Desktop.exe"

4. Verify Docker installation
   docker --version
   docker info

5. Optional: Enable WSL 2 backend
   Open Docker Desktop > Settings > General > Use the WSL 2 based engine > Apply & Restart

---

## 3️⃣ Post-installation checks

- Check Docker version: docker --version
- Run hello-world container: docker run hello-world
- List running containers: docker ps
- List all containers: docker ps -a
- Remove a container: docker rm <container_id>
- Remove an image: docker rmi <image_name>

---

This guide covers basic Docker installation and verification for Ubuntu and Windows.
