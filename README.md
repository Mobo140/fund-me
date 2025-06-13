# Foundry Fund Me

![Foundry](https://img.shields.io/badge/Foundry-2023.12-blue)
![Solidity](https://img.shields.io/badge/Solidity-^0.8.18-363636)
![License](https://img.shields.io/badge/License-MIT-green)

A smart contract for collecting funds using Chainlink Price Feeds to convert ETH to USD.

## Table of Contents

- [About The Project](#about-the-project)
- [Technologies](#technologies)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Testing](#testing)
- [Deployment](#deployment)
- [Features](#features)
- [Security](#security)
- [License](#license)

## About The Project

Foundry Fund Me is a smart contract that allows users to send ETH to the contract, with a minimum donation amount of 5 USD (converted from ETH using Chainlink Price Feeds). The contract includes the following main features:

- Sending ETH to the contract with a minimum USD amount
- Withdrawing funds (owner only)
- Getting donation information
- Automatic ETH to USD conversion via Chainlink Price Feeds

## Technologies

- [Foundry](https://book.getfoundry.sh/) - Smart contract development framework
- [Solidity](https://docs.soliditylang.org/) - Smart contract programming language
- [Chainlink](https://chain.link/) - Decentralized oracle for price data

## Getting Started

### Prerequisites

- [Foundry](https://book.getfoundry.sh/getting-started/installation)
- [Git](https://git-scm.com/downloads)

### Installation

1. Clone the repository
```bash
git clone https://github.com/your-username/foundry-fund-me.git
cd foundry-fund-me
```

2. Install dependencies
```bash
forge install
```

## Usage

### Build
```bash
forge build
```

### Test
```bash
forge test
```

### Format
```bash
forge fmt
```

### Gas Snapshot
```bash
forge snapshot
```

### Local Development
```bash
anvil
```

### Deploy
```bash
forge script script/DeployFundMe.s.sol:DeployFundMe --rpc-url <your_rpc_url> --private-key <your_private_key>
```

## Features

### Main Functions

1. `fund()` - Allows users to send ETH to the contract
   - Minimum amount: 5 USD (converted from ETH)
   - Uses Chainlink Price Feeds for conversion

2. `withdraw()` - Allows the owner to withdraw all funds
   - Only the owner can call this function
   - Resets all donation records

3. `cheaperWithdraw()` - Gas-optimized version of withdraw()
   - More efficient gas usage
   - Same functionality as withdraw()

4. Getters:
   - `getAddressToAmountFunded()` - Get donation amount by address
   - `getFunder()` - Get donor address by index
   - `getOwner()` - Get contract owner address

## Security

- Use of Chainlink Price Feeds for reliable price data
- Minimum donation amount checks
- onlyOwner modifier for protected functions
- Safe ETH transfer methods (call instead of transfer/send)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
