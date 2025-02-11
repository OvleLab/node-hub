# Gaia AI Node Setup Guide

Earn **GaiaPoints** by running a Gaia AI node with the **Qwen2.5-0.5B-Instruct** model and interacting with AI agents. These points can be used for a future Gaia token airdrop!

---

## 1. Gaia Dashboard & XP Program
### Steps to Get Started:
1. **Connect Your Wallet**: [Gaia Dashboard]([https://gaianet.ai/reward?invite_code=Rw1iGQ](https://gaianet.ai/reward?invite_code=RTG94H)) and complete registration.
2. **Boost Your XP**: Use invite code **RTG94H**.
3. **Earn More Points**: Complete social tasks on [Rewards Summary](https://www.gaianet.ai/reward-summary).

---

## 2. Node Setup & Earning Points
By running a Gaia node, you accumulate **Node Points** and **User Points** by:
- Setting up and maintaining a node.
- Keeping it online and processing AI requests.
- Joining a domain.
- Engaging with the AI agent in your domain.

### System Requirements:
- **CPU**: 4 cores
- **RAM**: 8GB
- **Storage**: 10GB

**Tip**: Running multiple nodes (e.g., on VPS and Windows) increases earnings!

---

## 3. Install Dependencies
### Update Packages:
```bash
sudo apt update && sudo apt upgrade -y
```
### Install Python:
```bash
sudo apt install -y python3-pip build-essential libssl-dev libffi-dev python3-dev
```

---

## 4. Remove Old Node (If Installed Previously)
```bash
gaianet stop
curl -sSfL 'https://github.com/GaiaNet-AI/gaianet-node/releases/latest/download/uninstall.sh' | bash
source /root/.bashrc
```

---

## 5. Install Gaia Node CLI
```bash
curl -sSfL 'https://github.com/GaiaNet-AI/gaianet-node/releases/latest/download/install.sh' | bash
source /root/.bashrc
```

---

## 6. Configure Your Gaia Node
### Initialize and Download AI Model:
```bash
gaianet init --config https://raw.githubusercontent.com/OvleLab/node-hub/refs/heads/main/Gaianet-Node/config.json
```

---

## 7. Start & Manage Your Node
### Start Node:
```bash
gaianet start
```
### Stop Node:
```bash
gaianet stop
```

---

## 8. Register Your Node on Gaia Dashboard
1. Get **Node ID** & **Device ID**:
   ```bash
   gaianet info
   ```
2. Go to [Node Settings](https://www.gaianet.ai/setting/nodes) and click **Connect New Node**.
3. Copy and paste the IDs, then click **Join**.

---

## 9. Join a Domain
To maximize rewards, join a domain and interact with its AI agent.
1. Run:
   ```bash
   gaianet stop
   gaianet config --domain gaia.domains
   gaianet init
   gaianet start
   ```
2. Visit [Node Settings](https://www.gaianet.ai/setting/nodes).
3. Click the three dots next to your node → **Join Domain**.
4. Search for `ovlelab.gaia.domain` and complete the setup.

---

## 10. Chat with Your Node
Interact with your AI agent at [Ovle Lab Gaia Domain](https://ovlelab.gaia.domains).
- Convert **GaiaPoints** into **Credit Balance** daily.
- Each day, you can convert **1000 GaiaPoints**.

---

## 11. Automate with AutoChat Bot
### Create an API Key:
- Go to [Gaia API Keys](https://www.gaianet.ai/setting/gaia-api-keys) and generate a key.

### Download & Run AutoChat Bot:
```bash
curl -L -o gaiabot.py https://raw.githubusercontent.com/OvleLab/node-hub/refs/heads/main/Gaianet-Node/gaiabot.py
```

Run the bot in a background session:
```bash
screen -S gaiabot
python3 gaiabot.py
```

- **Detach screen**: `Ctrl+A+D`
- **Reattach screen**: `screen -r gaiabot`
- **Stop bot**: Inside screen, press `CTRL+C`, then run `screen -XS gaiabot quit`

---

## 12. Earn & Track Your Points
- **User Points**: Earned by chatting with AI agents.
- **Node Points**: Earned by keeping your node online & interacting with domains.

Check your points on the [Gaia Dashboard](https://www.gaianet.ai/reward).

🚀 **Maximize rewards by running your node 24/7 and using AutoChat!**

