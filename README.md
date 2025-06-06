# 🚀 Task 7: Monitor System Resources Using Netdata

## 📌 Objective
Install and run **Netdata** using Docker to monitor real-time system and application performance on an EC2 instance.

---

## 🛠 Tools Used
- **AWS EC2** (Ubuntu 22.04 LTS)
- **Docker**
- **Netdata**
- **GitHub**

---

## 🔧 Setup Steps

### 1. Launch EC2 Instance
- **OS**: Ubuntu 22.04 LTS  
- **Instance Type**: `t2.micro` (Free Tier)  
- **Security Group Ports Opened**:  
  - `22` (SSH)  
  - `19999` (Netdata Web Dashboard)

---

### 2. Install Docker
Update and install Docker on your EC2 instance:

```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo usermod -aG docker $USER
```

> **Note:** You may need to log out and back in again to apply Docker group changes.

---

### 3. Run Netdata Container

Run the Netdata container using Docker:

```bash
docker run -d --name=netdata \
  -p 19999:19999 \
  --cap-add=SYS_PTRACE \
  --security-opt apparmor=unconfined \
  netdata/netdata
```

This will start Netdata and expose the dashboard on port `19999`.

---

### 4. Access Netdata Dashboard

Open your browser and go to:

 **[http://54.83.113.171:19999]**




---

![image](https://github.com/user-attachments/assets/942f9ec6-0935-4041-898d-e095e4819f88)
