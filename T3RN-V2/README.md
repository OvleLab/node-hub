# 🚀 Setting Up T3rn V2 Node

The **T3rn Node** is essential for interacting with the t3rn blockchain, allowing users to participate in thier testnet and earn BRN token which will be converted to TRN during mainnet launch. This guide walks you through the setup process step by step.

---

## 🛠️ Step 1: Set Up a VPS

1. Choose a VPS provider like [Contabo](https://www.tkqlhce.com/click-101114590-13484397) with **Ubuntu 22.04**.
2. Connect to your VPS using SSH:
   ```sh
   ssh root@<IP_OF_YOUR_VPS>
   ```
or 

3. To connect using **Termius**:
    - Download and install [Termius](https://www.termius.com/)
    - Open the application and click **New Host**
    - Enter the following details:
    - **Alias**: Any name (e.g., "t3rn VPS")
    - **Hostname**: `<IP_OF_YOUR_VPS>`
    - **Username**: `root`
    - **Password / SSH Key**: Use password or add your SSH private key
    - Click **Save**, then **Connect**

---

## 💰 Step 2: Claim Faucet Tokens

You need at least **0.1 BRN** to run the node. Claim faucet tokens here:
- [Caldera Faucet](https://b2n.hub.caldera.xyz/) *(Use VPN for multiple claims)*
- ETH faucets:
  - [QuickNode](https://faucet.quicknode.com/arbitrum/sepolia)
  - [Chainlink](https://faucets.chain.link/arbitrum-sepolia)
  - [BwareLabs](https://bwarelabs.com/faucets/arbitrum-sepolia)
  - [Alchemy](https://www.alchemy.com/faucets/ethereum-sepolia)
  - [MetaMask](https://docs.metamask.io/developer-tools/faucet/)
  - [Google Cloud](https://cloud.google.com/application/web3/faucet/ethereum/sepolia)
  - [Sepolia Testnet Bridge](https://testnetbridge.com/sepolia) *(Convert mainnet ETH to testnet)*
  - [SuperBridge](https://testnets.superbridge.app/base-sepolia) *(Move ETH across testnets)*

---

## ⚙️ Step 3: Configure Your Node

### 1️⃣ Update Your System
```sh
sudo apt update && sudo apt upgrade -y
```

### 2️⃣ Install Screen
```sh
apt install screen
```


## 🔄 Step 3: Remove Previous Version (If Installed)

If you have previously installed an older version, remove it before proceeding:
```sh
rm -rf executor-linux-v0.*
rm -rf executor
```


### 4️⃣ Download t3rn Binaries
```sh
wget https://github.com/t3rn/executor-release/releases/download/v0.56.0/executor-linux-v0.56.0.tar.gz
```

### 5️⃣ Unzip the File
```sh
tar -xvzf executor-linux-v0.56.0.tar.gz
cd executor
```

### 6️⃣ Create a Screen Session
```sh
screen -S t3rn
```

### 7️⃣  Set Up Environment Variables
**Important:** Replace `<YOUR_WALLET_PRIVATE_KEY>` with your actual private key.
```sh
export ENVIRONMENT=testnet
export LOG_LEVEL=debug
export LOG_PRETTY=false
export EXECUTOR_PROCESS_BIDS_ENABLED=true
export EXECUTOR_PROCESS_ORDERS_ENABLED=true
export EXECUTOR_PROCESS_CLAIMS_ENABLED=true
export EXECUTOR_PROCESS_ORDERS=true
export EXECUTOR_PROCESS_CLAIMS=true
export EXECUTOR_MAX_L3_GAS_PRICE=10000
export ENABLED_NETWORKS='arbitrum-sepolia,base-sepolia,optimism-sepolia,unichain-sepolia,l2rn'
export RPC_ENDPOINTS='{
    "l2rn": ["https://b2n.rpc.caldera.xyz/http"],
    "arbt": ["https://arbitrum-sepolia.drpc.org", "https://sepolia-rollup.arbitrum.io/rpc"],
    "bast": ["https://base-sepolia-rpc.publicnode.com", "https://base-sepolia.drpc.org"],
    "opst": ["https://sepolia.optimism.io", "https://optimism-sepolia.drpc.org"],
    "unit": ["https://unichain-sepolia.drpc.org", "https://sepolia.unichain.org"]
}'
export EXECUTOR_PROCESS_PENDING_ORDERS_FROM_API=false
```

Now, set your private key separately:
```sh
export PRIVATE_KEY_LOCAL=<YOUR_WALLET_PRIVATE_KEY>
```

---

## 🚀 Step 4: Start the Node

1. **Navigate to the bin directory**:
   ```sh
   cd executor/bin
   ```
2. **Run the executor**:
   ```sh
   ./executor
   ```
3. **Detach from the screen** (let it run in the background):
   - Press `CTRL + A + D`

To **check logs**:
```sh
screen -r t3rn
```
To **exit logs**, press `CTRL + A + D`.

---

## 📊 Step 5: Verify Node Status

Check your BRN balance here:
🔗 [t3rn Rewards](https://unlock3d.t3rn.io/rewards)

---

## 🎖️ Step 6: Get the Executor Role

1. **Take a screenshot** of your executor dashboard:
   ```
   https://bridge.t1rn.io/executor/<YOUR WALLET ADDRESS>/
   ```
2. **Send it with your address** to the Discord channel:
   🔗 [t3rn Discord](https://discord.gg/w9RcRz2XAH)

---

## 🎉 Conclusion

You’ve successfully set up your **t3rn V2 Node**! If you encounter issues, refer to official documentation or community support.

🔗 **Join the Community:**
- [t3rn Discord](https://discord.gg/t3rn)
- [Twitter](https://twitter.com/t3rn_io)

---

## 🌟 Ovle Lab Guide

This guide is brought to you by **Ovle Lab**, a community dedicated to blockchain innovation, decentralized networks, and hands-on learning. Stay connected and paint the tech world purple! 💜

🔗 **Join our Community:**
- [Discord](https://discord.gg/ovlelab)
- [Twitter](https://twitter.com/OvleLab)

