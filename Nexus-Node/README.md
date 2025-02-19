# Nexus Prover Node - Ovle Lab Guide

The Nexus Prover Node allows users to contribute computing power and earn NEX Points by interacting with the Nexus ecosystem. This guide will walk you through setting up a prover node using different methods, including a web browser, a VPS-based browser(Chromium), and a CLI-based setup (currently in development).

---

##  🌐 Multi-Device Compatibility
The Nexus ecosystem is designed to support multiple devices, allowing you to maximize your contributions. Here’s what you need to know:

- You can connect and manage multiple devices, including desktops, laptops, mobile phones, and servers.
- All your devices can be linked and controlled from a single Nexus account.
- It is even possible to run multiple prover nodes across different browser tabs simultaneously.

---

## 🚀 Getting Started: Create an Account
To start contributing to the Nexus ecosystem, follow these steps:

1. Visit the Nexus dashboard: [https://app.nexus.xyz](https://app.nexus.xyz)
2. Create an account and complete the linking instructions.
3. Once your account is set up, you will start earning NEX Points for your contributions.
4. Track your performance on the leaderboard and manage all your nodes in one place.

---

## 🖥️ Running a Prover via Web Browser
### 1. Web Browser Contribution
This is the simplest way to contribute computing power to Nexus.

1. Log in to your Nexus account at [https://app.nexus.xyz](https://app.nexus.xyz).
2. Click the **Start Node** button to begin contributing.
3. Run multiple instances by opening additional tabs across different devices (desktops, laptops, mobile phones).
4. The more computations your node performs, the more NEX Points you earn.

---

### 2. 🖥️ Running a Prover on a VPS (Chromium Browser Method)
If you want to set up a prover on a VPS, you can install a Chromium-based browser and run the web-based node there.

#### **Installing Chromium on Linux VPS**
You need to install a Chromium browser before running the web-based prover. Follow this guide: 

1. Install Chromium:
[Chromium Installation Guide](https://github.com/Ovlelab/node-hub/Chromium-Browser).


2. Open the browser and navigate to [https://app.nexus.xyz](https://app.nexus.xyz).
3. Log in and start your prover node.
4. You can open multiple tabs to increase computational power.

💡 **Tip:** While running multiple instances in a browser can boost your earnings, it's recommended to balance this with a CLI node for better efficiency.

---

### 3. 🔧 Running a Prover via CLI (Command-Line Interface) *(Beta)*
This method is not yet officially live, but here’s how you can prepare for it.

#### **Step 1: Install Dependencies**
Run the following commands to install necessary packages:
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install screen curl libssl-dev pkg-config build-essential git-all protobuf-compiler -y
```

Install Rust:
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

#### **Step 2: Run the Nexus Prover**
Start a **screen session** to keep the process running in the background:
```bash
screen -S nexus
```

Download and install the CLI prover:
```bash
curl https://cli.nexus.xyz/ | sh
```

#### **Step 3: Link Your Node**
Once the installation is complete, the system will prompt you to link your node.

1. When asked to link your node, choose option `2`.
2. Retrieve your `node-id` from the Nexus dashboard:
   - Go to [https://app.nexus.xyz/nodes](https://app.nexus.xyz/nodes)
   - Click `Add Node`, then `Add CLI Node`, and copy the `node-id`.
3. Paste the `node-id` into the terminal when prompted.

#### **Step 4: Managing Your Node in Screen**
- **Detach from the screen session:** `CTRL + A + D`
- **Reattach the session:** `screen -r nexus`
- **Kill the screen session:** `screen -XS nexus quit`

---

## 🎨 Conclusion
By setting up a Nexus Prover Node, you can actively contribute to the ecosystem while earning NEX Points. Whether you choose a web-based, VPS browser, or CLI method, this guide helps you get started efficiently. Also Nex point will be sent to your wallet hourly .

💡 **Stay Updated**: As the CLI method becomes fully functional, we will update this guide with accurate and verified steps.


**Ovle Lab - Paint the Tech World Purple 💜**
