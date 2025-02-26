# sBTC Vault Protocol - Bitcoin-Collateralized Stablecoin System

[![Clarity Version](https://img.shields.io/badge/Clarity-2.0-blue)](https://clarity-lang.org)
[![Stacks L2 Compatible](https://img.shields.io/badge/Stacks_L2-Yes-green)](https://www.stacks.co)

A decentralized protocol for minting Bitcoin-backed stablecoins on Stacks Layer 2 with institutional-grade risk management and Bitcoin settlement guarantees.

## Overview

The sBTC Vault Protocol enables non-custodial creation of Bitcoin-collateralized stablecoins through:

- **BTC Collateral Vaults**: Over-collateralized Bitcoin deposits (minimum 150% ratio)
- **Algorithmic Stablecoin**: sUSD minting/burning with sats-native precision
- **Liquidity Pools**: Decentralized market-making with 0.3% fee structure
- **Oracle System**: Price feed management with governance controls
- **Liquidation Protection**: Automated safety mechanisms at 130% collateral ratio

Designed for DeFi institutions, the protocol combines Bitcoin's security with Stacks L2 smart contract capabilities.

## Key Features

### 1. Collateral Management System

- `deposit-collateral`: Lock BTC in non-custodial vaults
- Dynamic collateral ratio calculations
- Block-height timestamped state updates

### 2. Stablecoin Engine

- `mint-stablecoin`: Generate sUSD against BTC collateral
- `burn-stablecoin`: Destroy sUSD to release collateral
- Supply cap enforcement (10M sUSD initial)

### 3. Liquidity Infrastructure

- `add-liquidity`: Provide BTC/sUSD pairs
- `remove-liquidity`: Withdraw pool shares
- Constant product market maker model

### 4. Risk Management

- Real-time collateral health checks
- Liquidation threshold enforcement
- Slippage protection mechanisms

## Technical Specifications

| Parameter              | Value     | Description                      |
| ---------------------- | --------- | -------------------------------- |
| Min Collateral Ratio   | 150%      | Minimum BTC collateralization    |
| Liquidation Threshold  | 130%      | Auto-lock trigger point          |
| Pool Fee               | 0.3%      | LP transaction fee               |
| Precision              | 1e6       | 6 decimal places standardization |
| Max Mint per Operation | 1,000,000 | sUSD anti-flood protection       |

## Architecture

```
User Actions → Contract Interactions → Bitcoin Settlement
           ↳ Oracle Feed
           ↳ Risk Engine
           ↳ Liquidity Pool
```

1. **Core Module**: Manages vault creation and stablecoin minting
2. **AMM Module**: Handles liquidity pool operations
3. **Oracle Module**: Secures price feed updates
4. **Compliance Module**: Enforces regulatory safeguards

## Installation

### Requirements

- Clarinet 1.0.0+
- Stacks Node 2.1.0+
- Bitcoin testnet environment

```bash
git clone https://github.com/yourorg/sbtc-vault-protocol.git
cd sbtc-vault-protocol
clarinet install
```

## Usage Examples

### Deposit Collateral

```clarity
(contract-call? .sbtc-vault deposit-collateral 1000000)
```

### Mint Stablecoins

```clarity
(contract-call? .sbtc-vault mint-stablecoin 500000)
```

### Add Liquidity

```clarity
(contract-call? .sbtc-vault add-liquidity 1000000 500000)
```

## Contributing

1. Fork repository
2. Create feature branch (`feature/[name]`)
3. Submit PR with full test coverage

## References

- [Stacks Documentation](https://docs.stacks.co)
- [Clarity Language Reference](https://clarity-lang.org/docs)
- [sBTC Specification](https://github.com/stacks-network/sbtc)
