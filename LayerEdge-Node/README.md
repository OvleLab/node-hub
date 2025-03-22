# 🚀 Layer Edge Light Node Setup Guide

The **Layer Edge Light Node** is a lightweight and efficient client that enables users to interact with the Layer Edge network without running a full node. Leveraging ZK proofs and Bitcoin’s Proof-of-Work security, it ensures secure and cost-effective verification. This guide will walk you through setting up the Light Node, allowing seamless integration with the Layer Edge ecosystem.

---

## 🛠️ Step 1: Clone the Light Node Repository

```sh
git clone https://github.com/Layer-Edge/light-node.git
cd light-node
```

---

## 📦 Step 2: Install Required Dependencies

Ensure the following dependencies are installed:

### ✅ Install Go (Version 1.18+)

```sh
wget https://go.dev/dl/go1.23.linux-amd64.tar.gz
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf go1.23.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
```

Verify installation:

```sh
go version
```

### ✅ Install Rust (Version 1.81+)

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

Verify installation:

```sh
rustc --version
```

### ✅ Install Risc0 Toolchain

```sh
curl -L https://risczero.com/install | bash 
```

```sh
source "/root/.bashrc"
```

```sh
rzup install
```

---

## ⚙️ Step 3: Configure Environment Variables

To set up the required environment variables, create a `.env` file in the project root directory:

```sh
nano .env
```

Add the following lines to the `.env` file:

```sh
GRPC_URL=grpc.testnet.layeredge.io:9090
CONTRACT_ADDR=cosmos1ufs3tlq4umljk0qfe8k5ya0x6hpavn897u2cnf9k0en9jr7qarqqt56709
ZK_PROVER_URL=http://your-server-ip:3001  # Replace 'your-server-ip' with the actual server IP hosting the ZK prover service.
# Alternatively:
ZK_PROVER_URL=https://layeredge.mintair.xyz/
API_REQUEST_TIMEOUT=100
POINTS_API=https://light-node.layeredge.io
PRIVATE_KEY='cli-node-private-key'
```

Save and exit (`CTRL + X`, then `Y`, then `Enter`).

> 🔐 **Note:** Replace `'cli-node-private-key'` with your actual private key. Keep it secure and do not expose it in public repositories or logs.
>
> Replace `'your-server-ip'` with the actual server IP.

---

## 🏗️ Step 4: Start the Merkle Service

Run the following command to create a screen session for the Merkle service:

```sh
screen -S merkle
```

This allows the Merkle service to continue running in the background.

Start the Merkle service:

```sh
cd risc0-merkle-service
cargo build && cargo run
```

Wait until the Merkle service is fully initialized before proceeding.

To detach from the screen session, press `Ctrl + A`, then `D`. To reattach:

```sh
screen -r merkle
```

---

## 🚀 Step 5: Build and Run the Layer Edge Light Node

Run the following command to create a screen session for the Light Node:

```sh
screen -S light_node
```

In a separate terminal window, navigate to the root directory and execute:

```sh
go build
./light-node
```

🔑 **Copy the generated public key, as it will be required in the next step.**

To detach from the screen session, press `Ctrl + A`, then `D`. To reattach:

```sh
screen -r light_node
```

## 🌐 Step 6: Connect to Layer Edge Dashboard

1. Navigate to [Layer Edge Dashboard](https://dashboard.layeredge.io).
2. **Connect your wallet.**
3. Click on the **plus (+) sign** in the CLI section.
4. **Add your CLI node’s public key** (copied in Step 5).

⚠️ **Important Notes:**

- One CLI wallet can only be linked to one dashboard wallet.
- Linking is mandatory, even if the CLI and dashboard wallets are identical.
- It may take **10-30 minutes** for the connection to be fully recognized.

---

✅ **Congratulations!** You've successfully set up your Layer Edge Light Node. If you encounter any issues, refer to the official [documentation](https://docs.layeredge.io/) or reach out to our Discord.

---

### 🌟 About Ovle Lab

Ovle Lab is a community-driven initiative focused on blockchain infrastructure, validator programs, and cutting-edge technology. We empower enthusiasts and developers through hands-on learning and real-world blockchain projects. Join us as we **paint the tech world purple 💜!**

🔗 **Join our Community:**
- [Discord](https://discord.gg/ovlelab)
- [Twitter](https://twitter.com/OvleLab)

