# Deploy the V3 Protocol Contracts

The first step in setting up Uniswap V3 on a new EVM chain is to deploy the smart contracts that make up the protocol. For convenience, the Uniswap Labs team has created a set of deployment scripts and management CLI that will coordinate and deploy the necessary contracts to a new EVM chain. 

All you need to do is create the account to deploy with, fund it for gas fees (40-50M gas required), then run one command in the CLI. The script will sequentially deploy each contract, creating checkpoints as it goes that can be reverted back to in case any issues arise.

To start a deployment follow the detailed CLI instructions here → https://github.com/Uniswap/deploy-v3

# Deploying the Subgraphs
[The Graph](https://thegraph.com/en/) is one of the most popular blockchain data indexing tools. If the chain you deployed to supports it, it is highly recommended that you set up a [Sub Graph](https://thegraph.com/docs/en/developer/define-subgraph-hosted/) to index Uniswap activity on the new chain. 

Having a Subgraph for your deployment not only allows integrators to access fast, reliable data, but will also make integrating with existing parts of the Uniswap Ecosystem, like [info.uniswap.org](info.uniswap.org) a seamless experience. 

Setting up a "Sub Graph" to index the Uniswap Protocol on a newly deployed chain allows users to easily query data about Uniswap activity on the new deployment and even build integrations with fast reliable data access. 

The best way to set up your Subgraph is to start with an existing one from another chain and edit it to correspond to yours. You'll then submit that to The Graph and it will start indexing. 

When you're ready to start setting up your Subgraph, follow these detailed instructions → [Setting up a Subgraph](https://github.com/Uniswap/v3-new-chain-deployments/blob/main/subgraph_instructions.md).

# Create Your Token List
[Token Lists](https://tokenlists.org/) are another key primitive in the Uniswap and larger DeFi eco-system. Token Lists are a simple schema for identifying supported tokens on a dApp. 

```
{
  "name": "Example Token List",
  "timestamp": "2022-03-01T22:44:18.339Z",
  "version": {
    "major": 4,
    "minor": 2,
    "patch": 0
  },
  "tokens": [
    {
      "logoURI": "https://logo.io",
      "chainId": 42161,
      "address": "0x7cb16cb78ea464aD35c8a50ABF95dff3c9e09d5d",
      "name": "0xBitcoin Token",
      "symbol": "0xBTC",
      "decimals": 8,
      "extensions": {}
    },
    ...
    ]
}
```

As a next step in the deployment of a new chain, you will author a token list to represent the tokens supported on your chain and host it (preferably on IPFS or another decentralized system). With an up to date Token List, you can easily manage the tokens supported in the Uniswap App as well as in dApps across the ecosystem. 

Follow the instructions in the [Token Lists Package](https://github.com/Uniswap/token-lists#authoring-token-lists) to author, validate and host your token list. You'll need a valid Token List to proceed with future steps. 

# Validate Your Deployment
- Compile the list of [deployed addresses](https://github.com/Uniswap/deploy-v3/blob/b7aac0f1c5353b36802dc0cf95c426d2ef0c3252/src/deploy.ts#L23-L36) from the deploy-v3 script.
- Ensure that all of the contracts are verified on your blockchain explorer (i.e. Etherscan).
- Pull down the deployed bytecode for each contract(i.e. from [Etherscan](https://etherscan.io/address/0x1f98431c8ad98523631ae4a59f267346ea31f984#code) or a tool like [Cast](https://github.com/foundry-rs/foundry/tree/master/cast).
- Compare the bytecode to the [mainnet deployment](https://docs.uniswap.org/protocol/reference/deployments). The only differences should be the contract immutables, including addresses of other deployment contracts.
- Test the deployment! Some important cases to consider:
  - Swapping native asset -> ERC20 and ERC20 -> native asset through the SwapRouter
  - Adding and removing liquidity with native asset through the NonfungiblePositionManager

