# SAYMAN JavaScript SDK

Official JavaScript SDK for interacting with the **SAYMAN Blockchain**. Build wallets, send transactions, deploy smart contracts, interact with contracts, and integrate SAYMAN into your applications with a simple API.

> **Status:** Public Testnet

---

## Features

* Wallet creation & management
* Native SAYMAN transaction support
* Smart contract deployment
* Smart contract interaction
* Balance & account queries
* Transaction broadcasting
* Explorer integration
* Lightweight and dependency-free
* Node.js & Browser compatible

---

## Installation

```bash
npm install @sayman/sdk
```

---

## Quick Start

```javascript
const { Client } = require("@sayman/sdk");

const client = new Client({
    rpc: "https://sayman.onrender.com/api"
});
```

or with ES Modules

```javascript
import { Client } from "@sayman/sdk";

const client = new Client({
    rpc: "https://sayman.onrender.com/api"
});
```

---

# Connect to a Node

```javascript
const client = new Client({
    rpc: "https://sayman.onrender.com/api"
});
```

---

# Create a Wallet

```javascript
const wallet = await client.wallet.create();

console.log(wallet.address);
console.log(wallet.privateKey);
console.log(wallet.mnemonic);
```

---

# Import Existing Wallet

```javascript
const wallet = client.wallet.fromPrivateKey(
    "YOUR_PRIVATE_KEY"
);
```

---

# Get Balance

```javascript
const balance = await client.getBalance(
    "YOUR_ADDRESS"
);

console.log(balance);
```

---

# Send Tokens

```javascript
await client.transfer({
    from: wallet,
    to: "RECEIVER_ADDRESS",
    amount: 100
});
```

---

# Estimate Gas

```javascript
const gas = await client.estimateGas({
    to: "RECEIVER_ADDRESS",
    amount: 100
});

console.log(gas);
```

---

# Deploy Smart Contract

```javascript
const contract = await client.contract.deploy({
    bytecode,
    abi,
    args: []
});

console.log(contract.address);
```

---

# Load Existing Contract

```javascript
const contract = client.contract.at(
    CONTRACT_ADDRESS,
    abi
);
```

---

# Read Contract State

```javascript
const result = await contract.call(
    "balanceOf",
    [
        wallet.address
    ]
);

console.log(result);
```

---

# Write Contract State

```javascript
await contract.send(
    "transfer",
    [
        receiver,
        500
    ],
    wallet
);
```

---

# Get Transaction

```javascript
const tx = await client.getTransaction(
    TX_HASH
);

console.log(tx);
```

---

# Get Block

```javascript
const block = await client.getBlock(
    BLOCK_HEIGHT
);

console.log(block);
```

---

# Broadcast Raw Transaction

```javascript
await client.broadcast(
    signedTransaction
);
```

---

# Network Information

```javascript
const info = await client.network();

console.log(info);
```

---

# Explorer

View blocks, transactions, validators and smart contracts using the official explorer.

https://explorer.sayman.network

---

# Documentation

Complete documentation is available at

https://docs.sayman.network

---

# Public Testnet

RPC Endpoint

```
https://sayman.onrender.com/api
```

Explorer

```
https://explorer.sayman.network
```

Faucet

```
https://faucet.sayman.network
```

---

# Example

```javascript
const { Client } = require("@sayman/sdk");

async function main() {
    const client = new Client({
        rpc: "https://sayman.onrender.com/api"
    });

    const balance = await client.getBalance(
        "YOUR_ADDRESS"
    );

    console.log(balance);
}

main();
```

---

# Roadmap

* JavaScript SDK
* TypeScript SDK
* Browser Support
* React Hooks
* React Native Support
* Flutter SDK
* Go SDK
* Rust SDK
* Python SDK
* Java SDK
* C# SDK

---

# Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Open a Pull Request.

---

# Reporting Issues

Found a bug or have a feature request?

Please open an issue on GitHub.

---

# License

MIT License

Copyright © 2026 Vizkus Groups.

---

## Links

* Website: https://sayman.network
* Documentation: https://docs.sayman.network
* Explorer: https://explorer.sayman.network
* Faucet: https://faucet.sayman.network
* GitHub: https://github.com/VizkusGroups/sayman

---

Made with ❤️ by **Vizkus Groups** for the SAYMAN Blockchain ecosystem.
