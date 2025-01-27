# Decentralized Autonomous Organization (DAO) Web Application

This project is a decentralized application (DApp) that allows users to interact with a Decentralized Autonomous Organization (DAO) on the Ethereum blockchain. Users can create proposals, vote on them, and view proposal details, all within a secure and transparent environment. The DApp is built with HTML5, Bootstrap4, JavaScript, and Web3.js and communicates with an Ethereum smart contract deployed to a blockchain network.

## Table of Contents
1. Project Overview  
2. Features  
3. Technology Stack  
4. Installation  
5. Usage  
6. Smart Contract  
7. License

---

## Project Overview

The DAO Web Application allows users to participate in a DAO by proposing changes and voting on proposals in a decentralized manner. The application uses Web3.js to connect to the Ethereum blockchain via MetaMask and interacts with the smart contract to store and retrieve information related to proposals.

## Features

- **Create Proposals:** Users can submit new proposals with a description that gets recorded on the blockchain.  
- **Vote on Proposals:** Users can vote in favor or against a proposal.  
- **View Proposals:** Users can view details of proposals, including the description, vote counts, status, and proposer information.
- **View Recent History:** Users can view the history of all closed proposals including the vote outcome.  

---

## Technology Stack

- **Frontend:** HTML5, CSS3, Boostrap4, JavaScript  
- **Blockchain Interface:** Web3.js  
- **Ethereum Wallet:** MetaMask  
- **Smart Contract:** Solidity  

---

## Installation

### Prerequisites

Ensure you have the following tools installed:
1. **Node.js and npm**: Download and install from [Node.js official website](https://nodejs.org/).  
2. **Truffle**: Install globally with:
   ```bash
   npm install -g truffle
   ```
3. **Ganache**: Download and install from [Ganache official website](https://trufflesuite.com/ganache/).
4. **MetaMask**: Add the MetaMask extension to your browser from [MetaMask website](https://metamask.io/).

### Clone the Repository

```bash
git https://github.com/srthkaggrwl/Decentralized-Autonomous-Organization/tree/hackathon
cd Decentralized-Autonomous-Organization
```

### Install Dependencies

Ensure you have Web3.js installed:
```bash
npm install web3
```

---

## Deployment

### 1. Start Ganache

Open Ganache and create a new workspace or use Quickstart Ethereum.

### 2. Compile and Deploy Smart Contract

Using Truffle, compile and deploy the `SimpleDAO` smart contract to Ganache:
```bash
truffle compile
truffle migrate
```
After deployment, note the contract address from the output.

### 3. Update Contract Address

Replace `contractAddress` in `src/app.js` with the deployed contract address:
```javascript
const contractAddress = "<YOUR_DEPLOYED_CONTRACT_ADDRESS>";
```

---

## Usage

### 1. Connect MetaMask

- Open MetaMask and connect it to the Ganache blockchain.
- Import one of the private keys from Ganache into MetaMask to fund your wallet for testing.

### 2. Run the Application

Open `index.html` in a web browser. MetaMask will prompt you to connect your wallet and approve interactions with the DApp.

### 3. Create, Vote, and View Proposals

#### **Create Proposal**
1. Enter a proposal description in the input field.
2. Click "Create Proposal."
3. MetaMask will prompt for confirmation. Approve the transaction to create the proposal.

#### **Vote on Proposal**
1. Enter the proposal ID and choose to vote "For" or "Against."
2. Click the corresponding button.
3. MetaMask will prompt for confirmation. Approve the transaction to cast your vote.

---

## Smart Contract

The smart contract, `SimpleDAO`, is written in Solidity and handles the core functionalities of the DAO:

- **`createProposal`:** Allows any user to submit a new proposal.  
- **`vote`:** Enables users to vote on an active proposal.  
- **`getProposal`:** Fetches details of a specified proposal.  

### Events

- `ProposalCreated`: Triggered when a new proposal is created.
- `Voted`: Triggered when a vote is cast.

### Smart Contract Functions

- **`createProposal(string description)`:** Creates a new proposal.  
- **`vote(uint proposalId, bool support)`:** Casts a vote (in favor or against).  
- **`getProposal(uint proposalId)`:** Retrieves proposal details.  

---



