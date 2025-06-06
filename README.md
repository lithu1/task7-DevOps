

# Task 7: Monitor System Resources Using Netdata


##  Objective
Install and run **Netdata** using Docker to monitor real-time system and application performance on an EC2 instance.



## 🛠 Tools Used
- **AWS EC2* (Ubuntu instance)
- **Docker*
- **Netdata*
- **GitHub*


## 🔧 Setup Steps

## 1. Launched EC2 Instance
- OS: Ubuntu 22.04 LTS
- Type: t2.micro (Free Tier)
- Ports opened: **22 (SSH)**, **19999 (Netdata)**

## 2. Installed Docker
```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo usermod -aG docker $USER

## 3. Ran Netdata Container
docker run -d --name=netdata -p 19999:19999 --cap-add=SYS_PTRACE --security-opt apparmor=unconfined netdata/netdata

## 4. Accessed Dashboard
http://54.83.113.171:19999

![image](https://github.com/user-attachments/assets/c60135a3-eb61-4832-a194-ff4d10f740c1)

