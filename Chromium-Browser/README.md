
# 🚀 Install Chromium Browser on Linux Server 🌐🐧 

Chromium is an **open-source web browser** developed by Google, serving as the foundation for many modern browsers like **Google Chrome, Microsoft Edge, and Brave**. Unlike Chrome, Chromium is fully open-source and doesn’t include proprietary Google services by default.  

### 🌟 Why Install Chromium on a Linux Server?  
Many Linux servers run without a graphical user interface (GUI), but sometimes, you might need a browser for:  

✅ **Running browser-based node extensions** for blockchain networks.  
✅ **Automating web-based tasks** using a remote VPS.  
✅ **Testing dApps and Web3 interactions** in a headless environment.  
✅ **Accessing a lightweight, secure browser** on a non-GUI system.  

---

## **🔧 Install Docker** 🐳  
Before setting up Chromium, install Docker with the following commands:  

```bash
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# ✅ Check Docker version  
docker --version
```

---

## **🕰️ Timezone Check**  
Ensure your server timezone is correctly set:  

```bash
realpath --relative-to /usr/share/zoneinfo /etc/localtime
```

---

## **🌎 Install Chromium in Docker**  

### **1️⃣ Create a Directory** 📂  
```bash
mkdir chromium
cd chromium
```

### **2️⃣ Create a `docker-compose.yaml` file** 📝  
```bash
nano docker-compose.yaml
```

### **3️⃣ Add the Following Configuration** ⚙️  
Replace the placeholders with your preferred **username, password, and timezone**:  

```yaml
---
services:
  chromium:
    image: lscr.io/linuxserver/chromium:latest
    container_name: chromium
    security_opt:
      - seccomp:unconfined # optional
    environment:
      - CUSTOM_USER=YourUsername  # 👤 Replace with your username  
      - PASSWORD=YourPassword  # 🔑 Replace with your password  
      - PUID=1000
      - PGID=1000
      - TZ=Europe/London  # 🌍 Replace with your server's timezone  
      - CHROME_CLI=https://google.com/ # optional  
    volumes:
      - /root/chromium/config:/config
    ports:
      - 3010:3000  # 🌐 Change port 3010 if needed  
      - 3011:3001  # 🌐 Change port 3011 if needed  
    shm_size: "1gb"
    restart: unless-stopped
```
> ✅ **To save and exit:** Press `Ctrl + X`, then `Y`, then `Enter`

---

## **🚀 Start Chromium**
```bash
cd $HOME && cd chromium
docker compose up -d
```

🎉 **Now, access Chromium from your browser using one of the following:**  
- 🌍 **http://Server_IP:3010/**  
- 🔒 **https://Server_IP:3011/**  

---

## **🛑 Stop and Remove Chromium** (If needed)  
```bash
docker stop chromium
docker rm chromium
docker system prune
```

---

## **💜 Conclusion**  
🎉 This setup allows you to **run browser-based nodes, test extensions, or automate tasks** without a graphical interface. 🚀  

**Ovle Lab – Paint the Tech World Purple! 💜**