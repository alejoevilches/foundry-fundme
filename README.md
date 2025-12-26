# Foundry FundMe Project

## Overview
This project demonstrates the use of the Foundry framework to build and test a decentralized crowdfunding application. The core contract, `FundMe.sol`, allows users to fund a project and withdraw funds securely. It also integrates Chainlink price feeds to ensure accurate conversion rates.

## Project Structure

- **src/**: Contains the main Solidity contracts.
  - `FundMe.sol`: The main contract for managing funds.
  - `PriceConverter.sol`: A library for converting ETH to USD using Chainlink price feeds.
- **script/**: Deployment and interaction scripts.
  - `DeployFundMe.s.sol`: Script to deploy the `FundMe` contract.
  - `HelperConfig.s.sol`: Configuration helper for deployment.
  - `Interactions.s.sol`: Scripts for interacting with the deployed contract.
- **test/**: Contains unit and integration tests.
  - `unit/`: Unit tests for individual contract functions.
  - `integration/`: Integration tests to verify contract behavior in a simulated environment.
  - `mocks/`: Mock contracts for testing purposes.
- **lib/**: External libraries used in the project.
  - `forge-std/`: Standard library for Foundry.
  - `chainlink-brownie-contracts/`: Chainlink contracts for price feeds.
- **broadcast/**: Stores deployment artifacts and logs.
- **cache/**: Caches intermediate files for faster builds.

## Prerequisites

- Foundry: Install Foundry by following the instructions at [Foundry Book](https://book.getfoundry.sh/).
- Node.js: Required for managing dependencies.
- A Chainlink-compatible blockchain network (e.g., Sepolia).

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd foundry-fundme
   ```

2. Install dependencies:
   ```bash
   forge install
   ```

3. Set up environment variables:
   Create a `.env` file and add the required variables (e.g., RPC URL, private key).

4. Compile the contracts:
   ```bash
   forge build
   ```

## Running Tests

- Run all tests:
  ```bash
  forge test
  ```
- Run a specific test file:
  ```bash
  forge test --match-path test/unit/FundMe.t.sol
  ```

## Deployment

1. Deploy the contract to a local network:
   ```bash
   forge script script/DeployFundMe.s.sol:DeployFundMe --fork-url <RPC_URL> --broadcast
   ```

2. Deploy to a testnet (e.g., Sepolia):
   ```bash
   forge script script/DeployFundMe.s.sol:DeployFundMe --rpc-url <RPC_URL> --private-key <PRIVATE_KEY> --broadcast
   ```

## Features

- **Secure Funding**: Users can fund the contract, and only the owner can withdraw funds.
- **Price Conversion**: Uses Chainlink price feeds to convert ETH to USD.
- **Testing**: Comprehensive unit and integration tests ensure contract reliability.

## Contributing

1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add your message here"
   ```
4. Push to the branch:
   ```bash
   git push origin feature/your-feature-name
   ```
5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Foundry](https://getfoundry.sh/): A blazing fast, portable, and modular toolkit for Ethereum application development.
- [Chainlink](https://chain.link/): Decentralized oracle network for reliable price feeds.

---

Happy coding!
