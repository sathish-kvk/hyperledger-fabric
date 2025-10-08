# E-Contract Blockchain Application

A Hyperledger Fabric-based blockchain application for managing electronic contracts with a complete UI and API layer.

## 🏗️ Architecture

This application consists of:
- **Blockchain Network**: Hyperledger Fabric with Certificate Authority, Orderers, and Peers
- **Smart Contracts (Chaincode)**: Business logic deployed on the blockchain
- **API Layer**: Node.js REST API for blockchain interaction
- **UI Layer**: Web-based user interface

## 📋 Prerequisites

- **Docker & Docker Compose**: Latest version
- **Node.js**: Version 18 or higher
- **npm**: Latest version
- **Linux/Unix environment** (tested on Ubuntu)

## 🚀 Quick Start

### 1. Bring up Certificate Authority (CA)
```bash
cd e-contract-main/blockchain/artifacts/channel/create-certificate-with-ca
sudo docker-compose up -d

This will start the CA containers required for certificate generation.
2. Generate Certificates
bash./create-certificate-with-ca.sh
This creates cryptographic materials in e-contract-main/blockchain/artifacts/channel/crypto-config
3. Create Channel Artifacts
bashcd e-contract-main/blockchain/artifacts/channel
./create-artifacts.sh
This generates the genesis block in e-contract-main/blockchain/channel-artifacts
4. Start Orderers and Peers
bashcd e-contract-main/blockchain/artifacts
sudo docker-compose up -d
This will start 7 containers (orderers and peer nodes).
5. Create and Join Channel
bashcd e-contract-main/blockchain/scripts
./createChannel.sh
Expected Output:
Using organization 1
Status: 201
{
  "name": "mychannel",
  "url": "/participation/v1/channels/mychannel",
  "consensusRelation": "consenter",
  "status": "active",
  "height": 1
}
...
Successfully submitted proposal to join channel
6. Deploy Chaincode
bashcd e-contract-main/blockchain/scripts
./deployChaincode.sh