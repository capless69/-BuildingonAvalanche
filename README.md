# DegenToken

## Overview
The **DegenToken** is an ERC20-compliant token implemented using OpenZeppelin's ERC20 library. It provides essential functionalities for minting, burning, and transferring tokens, with a fixed maximum supply of 100,000 tokens. The contract includes built-in safeguards to enforce the supply limit and access control for minting operations.

## Features
### 1. **Minting Tokens**
- Only the contract owner is allowed to mint new tokens.
- The maximum supply is capped at **100,000 DGN**, preventing over-minting.

### 2. **Burning Tokens**
- Token holders can burn their own tokens, reducing the total supply permanently.

### 3. **Transferring Tokens**
- Fully supports standard ERC20 token transfers between accounts.

---

## Contract Details
- **Token Name**: `Degen`
- **Token Symbol**: `DGN`
- **Maximum Supply**: 100,000 tokens
- **Initial Supply**: Configurable during contract deployment.

---

## Functions
### **constructor(uint256 initialSupply)**
- Initializes the contract by minting an initial supply of tokens to the deployer's address.
- **Parameters**:
  - `initialSupply`: The number of tokens to mint during deployment.

### **mintTokens(address recipient, uint256 amount)**
- Allows the contract owner to mint tokens and send them to a specified address.
- **Modifiers**:
  - `onlyOwner`: Restricts access to the contract owner.
  - `withinMaxSupply`: Ensures the total supply does not exceed the maximum cap.
- **Parameters**:
  - `recipient`: The address that will receive the minted tokens.
  - `amount`: The number of tokens to mint.

### **sendTokens(address recipient, uint256 amount)**
- Transfers tokens from the caller's account to the specified recipient.
- **Parameters**:
  - `recipient`: The address to send the tokens to.
  - `amount`: The number of tokens to transfer.

### **burnTokens(uint256 amount)**
- Allows token holders to burn their own tokens.
- **Parameters**:
  - `amount`: The number of tokens to burn.

---

## Events
### **TokensCreated(address indexed recipient, uint256 amount)**
- Triggered when new tokens are minted.

### **TokensDestroyed(address indexed account, uint256 amount)**
- Triggered when tokens are burned.

---

## Deployment
1. Deploy the smart contract by specifying the `initialSupply` parameter.
2. The deployer's address will be assigned as the contract owner and receive the initial supply of tokens.

---

## Authors
- **Metacrafter Caps**  

---

## License
This project is licensed under the MIT License. See the `LICENSE.md` file for more details.

