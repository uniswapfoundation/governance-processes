### Instructions
1) Copy this file and replace placeholder text with the relevant details of a given deployment
2) Open a pull request adding the new .md file, being sure to follow the naming convention `v3-deployment-details-chainName`

# Introduction
The following document provides details about the deployment and maintenance of the Uniswap V3 smart contracts on `InsertYourChain`

# Uniswap Contract Deployments
The latest version of `@uniswap/v3-core`, `@uniswap/v3-periphery`, `@uniswap/swap-router-contracts`, and `@uniswap/v3-staker` are deployed at the addresses listed below.

| Contract                                                                                                                                                     | Address                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------- |
| [UniswapV3Factory](https://github.com/Uniswap/uniswap-v3-core/blob/v1.0.0/contracts/UniswapV3Factory.sol)                                                    | addressWithBlockExplorerLink |
| [Multicall2](https://etherscan.io/address/0x5BA1e12693Dc8F9c48aAD8770482f4739bEeD696#code)                                                                   | addressWithBlockExplorerLink |
| [ProxyAdmin](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v3.4.1-solc-0.7-2/contracts/proxy/ProxyAdmin.sol)                                   | addressWithBlockExplorerLink |
| [TickLens](https://github.com/Uniswap/uniswap-v3-periphery/blob/v1.0.0/contracts/lens/TickLens.sol)                                                          | addressWithBlockExplorerLink |
| [Quoter](https://github.com/Uniswap/uniswap-v3-periphery/blob/v1.0.0/contracts/lens/Quoter.sol)                                                              | addressWithBlockExplorerLink |
| [SwapRouter](https://github.com/Uniswap/uniswap-v3-periphery/blob/v1.0.0/contracts/SwapRouter.sol)                                                           | addressWithBlockExplorerLink |
| [NFTDescriptor](https://github.com/Uniswap/uniswap-v3-periphery/blob/v1.0.0/contracts/libraries/NFTDescriptor.sol)                                           | addressWithBlockExplorerLink |
| [NonfungibleTokenPositionDescriptor](https://github.com/Uniswap/uniswap-v3-periphery/blob/v1.0.0/contracts/NonfungibleTokenPositionDescriptor.sol)           | addressWithBlockExplorerLink |
| [TransparentUpgradeableProxy](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v3.4.1-solc-0.7-2/contracts/proxy/TransparentUpgradeableProxy.sol) | addressWithBlockExplorerLink |
| [NonfungiblePositionManager](https://github.com/Uniswap/uniswap-v3-periphery/blob/v1.0.0/contracts/NonfungiblePositionManager.sol)                           | addressWithBlockExplorerLink |
| [V3Migrator](https://github.com/Uniswap/uniswap-v3-periphery/blob/v1.0.0/contracts/V3Migrator.sol)                                                           | addressWithBlockExplorerLink |
| [QuoterV2](https://github.com/Uniswap/v3-periphery/blob/main/contracts/lens/QuoterV2.sol)                                                                    | addressWithBlockExplorerLink |
| [SwapRouter02](https://github.com/Uniswap/swap-router-contracts/blob/main/contracts/SwapRouter02.sol)                                                        | addressWithBlockExplorerLink |
| [Permit2](https://github.com/Uniswap/permit2)                                                                                                                | addressWithBlockExplorerLink |
| [UniversalRouter](https://github.com/Uniswap/universal-router/blob/main/contracts/UniversalRouter.sol)                                                       | addressWithBlockExplorerLink |

## Deployment Method

Describe the process by which the contracts were deployed, including any software packages that were used. For example:

These addresses are final and were deployed from these npm package versions:

- [`@uniswap/v3-core@1.0.0`](https://github.com/Uniswap/uniswap-v3-core/tree/v1.0.0)
- [`@uniswap/v3-periphery@1.0.0`](https://github.com/Uniswap/uniswap-v3-periphery/tree/v1.0.0)
- [`@uniswap/swap-router-contracts@1.1.0`](https://github.com/Uniswap/swap-router-contracts/tree/v1.1.0)
- [`@uniswap/v3-staker@1.0.2`](https://github.com/Uniswap/v3-staker/tree/v1.0.2)

# Uniswap Pool Deployments

Every Uniswap pool is a unique instance of the `UniswapV3Pool` contract and is deployed at its own unique address. The contract source code of the pool will be auto-verified on etherscan. For example, here is the [ETH/USDC 0.3% pool](https://etherscan.io/address/0x8ad599c3a0ff1de082011efddc58f1908eb6e6d8) on Ethereum mainnet.

You can look up the address of an existing pool on [Uniswap Info](https://info.uniswap.org/#/) or by calling the [`getPool`](../reference/core/interfaces/IUniswapV3Factory.md#getpool) function on the `UniswapV3Factory` contract.

```solidity
getPool("0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48", "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2", 3000)
```

# Wrapped Native Token Addresses

The Uniswap Protocol supports trading of ERC20 tokens. In order to swap a native asset like ETH (or MATIC on Polygon), the Uniswap protocol wraps these assets in an ERC20 wrapped native token contract. The protocol uses the following WETH9 addresses on Ethereum and Ethereum Testnets

| Network  | ChainId | Wrapped Native Token | Address                                      |
| -------- | ------- | -------------------- | -------------------------------------------- |
| Ethereum | `1`     | WETH                 | `0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2` |
| Ropsten  | `3`     | WETH                 | `0xc778417E063141139Fce010982780140Aa0cD5Ab` |
| Rinkeby  | `4`     | WETH                 | `0xc778417E063141139Fce010982780140Aa0cD5Ab` |
| Goerli   | `5`     | WETH                 | `0xB4FBF271143F4FBf7B91A5ded31805e42b2208d6` |
| Kovan    | `42`    | WETH                 | `0xd0A1E359811322d97991E03f863a0C30C2cF029C` |

# Deployment History
Record the relevant deployment milestones here. This should include any forum posts, Snapshot polls, and on-chain votes leading up to the deployment, as well as any the posts, polls and post-deployment governance votes that have e.g. enabled a new fee tier or otherwise changed the deployment. Items in the `Discussion` column should link to the relevant context.

| Description                               | Link                                   |
| ----------------------------------------- | -------------------------------------- |
| Temperature check to deploy               | gov.uniswap.org/something              |
| Snapshot poll to deploy                   | snapshot.org/uniswap/something         |
| On-chain vote to deploy                   | vote.uniswapfoundation.org/proposal/32 |
| Temperature check to enable 1bps fee tier | gov.uniswap.org/something              |
| Snapshot poll to enable 1bps fee tier     | snapshot.org/uniswap/something         |
| On-chain vote to enable 1bps fee tier     | vote.uniswapfoundation.org/proposal/33 |

# Cross-chain Governance Configuration
Describe the cross-chain message passing infrastructure utilized by this deployment at both a high and low level. Provide detailed instructions describing how the Uniswap timelock contract passes messages to the destination UniswapV3Factory contract. Be specific about functions that proposals should call and the parameters they should pass.
