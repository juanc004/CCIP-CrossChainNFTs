# CrossChainPriceNFT Comprehensive Guide
======================================

This guide provides a step-by-step walkthrough for deploying and interacting with the CrossChainPriceNFT smart contract, enabling the creation and management of dynamic NFTs across different blockchain networks. Utilizing Chainlink's Cross-Chain Interoperability Protocol (CCIP), this guide also includes a challenge for deploying on Polygon Mumbai.

## Step 1: Initial Setup and Contract Deployment
---------------------------------------------

### MetaMask & Network

*   Ensure MetaMask is set to the Sepolia network.

### Remix IDE

*   Open [Remix IDE](https://remix.ethereum.org/).
*   Navigate to "DEPLOY & RUN TRANSACTIONS" and select "Injected provider - MetaMask" as the environment.
*   Confirm you're on the Sepolia (11155111) network.

### Contract Preparation

*   In "FILE EXPLORER", create a new file named `CrossChainPriceNFT.sol`.
*   Copy the provided Solidity contract code into this file.

### Deployment

*   Deploy the `CrossChainPriceNFT` contract via Remix, using the specified constructor arguments.

## Step 2: Minting and Viewing Your NFT
------------------------------------

### Collection on OpenSea

*   Navigate to [OpenSea testnets](https://testnets.opensea.io/).
*   Search for your `CrossChainPriceNFT` contract address to view your collection.

### Minting NFTs

*   Back in Remix, under the `CrossChainPriceNFT` contract, use the `mint` function with your wallet address.

### CrossDestinationMinter Contract

*   Create a new file named `CrossDestinationMinter.sol` in Remix.
*   Copy the respective Solidity code into this file and deploy on the Sepolia network.

## Step 3: Testing Cross-Chain Functionality
-----------------------------------------

### Tests

*   Run the `testMint` and `testMessage` functions from your deployed `CrossDestinationMinter` contract.

### Switch Networks

*   In MetaMask, switch to the Avalanche FUJI network.
*   Verify the network change in Remix to Custom (43113).

### CrossSourceMinter Contract

*   Create and deploy the `CrossSourceMinter.sol` contract on FUJI, inputting the `CrossDestinationMinter` address as a parameter.

## Step 4: Cross-Chain Minting and Link Token Transfer
---------------------------------------------------

### Send LINK Tokens

*   Add LINK tokens to MetaMask for the FUJI network using the provided address.
*   Transfer 5 LINK to your `CrossSourceMinter` address.

### Minting Across Chains

*   Use the `mintOnSepolia` function to mint an NFT from the FUJI network to Sepolia.
*   Confirm the transaction ID via the [CCIP Explorer](https://ccip.chain.link/).

## Step 5: Mint from Polygon Mumbai
--------------------------------

### Setup Mumbai on MetaMask

*   Add Mumbai Network following instructions on [Chainlist](https://chainlist.org/) or manually with the specified details.

### Add LINK Token on Mumbai

*   Add LINK token to your wallet using the [LINK token contract for Mumbai](https://docs.chain.link/resources/link-token-contracts#mumbai-testnet).

### Get LINK from Faucet

*   Obtain LINK tokens from the [Mumbai faucet](https://workshop-faucet.vercel.app/faucets/mumbai).

### Deploy CrossSourceMinterMumbai Contract

*   Create a new file `CrossSourceMinterMumbai.sol` in Remix and paste the provided code.
*   Deploy, setting the `CrossDestinationMinter` address (from Sepolia) as a parameter.

## Step 6: Minting and Funding
---------------------------

### Send LINK to CrossSourceMinterMumbai

*   Transfer 5 LINK to your `CrossSourceMinterMumbai` address on MetaMask.

### Check Balance and Mint

*   Verify LINK balance in Remix and use the `mintOnSepolia` function to mint an NFT from Mumbai to Sepolia.

## Step 7: Review and Verification
-------------------------------

### Review on CCIP Explorer

*   Verify the cross-chain minting operation on [CCIP Explorer](https://ccip.chain.link/).

### View Your NFT on OpenSea

*   Your new NFT should be visible on [OpenSea Testnets](https://testnets.opensea.io/) upon successful minting.

## Watch the Tutorial

For a detailed walkthrough of this project, watch our [YouTube tutorial](https://www.youtube.com/watch?v=IyiiRlz5Y60).

Resources
---------

*   [Chainlink CCIP Supported Networks](https://docs.chain.link/ccip/supported-networks/testnet)
*   [Chainlink Data Feeds](https://docs.chain.link/data-feeds/price-feeds/addresses)
*   [LINK Token Contracts](https://docs.chain.link/resources/link-token-contracts#fuji-testnet)