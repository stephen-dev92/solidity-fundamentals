# MyToken — a simple ERC-20 token

A basic ERC-20 token contract with owner-controlled minting and open burning,
built as a first hands-on Solidity project.

## What it does

- Deploys an ERC-20 token (`MTK`) with an initial supply minted to the deployer.
- The contract **owner** can mint new tokens to any address.
- **Any holder** can burn their own tokens, reducing total supply.
- Standard ERC-20 transfers, approvals, and balance checks work out of the box.

## Why I built it

This was my first Solidity project — a way to get hands-on with the ERC-20
standard, ownership/access control, and writing tests for smart contracts
before moving on to more complex contracts (multisig wallets, escrow, staking).

## Tech used

- **Solidity** ^0.8.24
- **Hardhat** — development environment, compiler, local test network
- **OpenZeppelin Contracts** — audited, industry-standard `ERC20` and `Ownable`
  base contracts (rather than writing token logic from scratch)
- **Chai / Mocha** (via `hardhat-toolbox`) — contract testing

## How to run it

```bash
npm install
npm run compile
npm test
```

## Test coverage

The test suite (`test/MyToken.test.js`) checks:
- Initial supply is minted correctly to the deployer
- Owner can mint new tokens
- Non-owners **cannot** mint (access control works)
- Any holder can burn their own tokens
- Standard transfers between accounts work correctly

## Possible next steps

- Add a max-supply cap
- Add a pausable emergency stop
- Deploy to a public testnet (e.g. Sepolia) and verify on Etherscan
