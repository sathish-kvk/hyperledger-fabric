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