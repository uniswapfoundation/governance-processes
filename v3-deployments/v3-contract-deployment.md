# Deploy the V3 Protocol Contracts

The first step in setting up Uniswap V3 on a new EVM chain is to deploy the smart contracts that make up the protocol. For convenience, the Uniswap Labs team has created a set of deployment scripts and management CLI that will coordinate and deploy the necessary contracts to a new EVM chain. 

All you need to do is create the account to deploy with, fund it for gas fees (40-50M gas required), then run one command in the CLI. The script will sequentially deploy each contract, creating checkpoints as it goes that can be reverted back to in case any issues arise.

To start a deployment follow the detailed CLI instructions here → https://github.com/Uniswap/deploy-v3

# Validate Your Deployment
- Compile the list of [deployed addresses](https://github.com/Uniswap/deploy-v3/blob/b7aac0f1c5353b36802dc0cf95c426d2ef0c3252/src/deploy.ts#L23-L36) from the deploy-v3 script.
- Ensure that all of the contracts are verified on your blockchain explorer (i.e. Etherscan).
- Pull down the deployed bytecode for each contract(i.e. from [Etherscan](https://etherscan.io/address/0x1f98431c8ad98523631ae4a59f267346ea31f984#code) or a tool like [Cast](https://github.com/foundry-rs/foundry/tree/master/cast).
- Compare the bytecode to the [mainnet deployment](https://docs.uniswap.org/protocol/reference/deployments). The only differences should be the contract immutables, including addresses of other deployment contracts.
- Test the deployment! Some important cases to consider:
  - Swapping native asset -> ERC20 and ERC20 -> native asset through the SwapRouter
  - Adding and removing liquidity with native asset through the NonfungiblePositionManager

