# [RFC] - Deploy Uniswap v3 on *yourChain*

## List of actors
**L1 or L2 team**: target chain for deployment

**Proposer**: entity or individual that creates the proposal on forum, and manages the governance process

**Deployer**: entity that handles the deployment of Uniswap v3 contracts on other chains or L2s

**Bridge Provider**: cross-chain messaging solution selected from the Bridge Assessment Committee recommendations

**Proposal Sponsor**: entity that has enough UNI to sponsor the final on-chain vote. The Uniswap Foundation is typically able to serve as the sponsor for these proposals.

## Rationale
A description of the destination chain. Include any relevant context, which could include:
- A technical overview, including any differences that would require changes to the v3 contract deployment process
- A DeFi ecosystem overview with usage and growth metrics
- Any grants or funds available for incentive programs / hackathons / etc

This section can be as detailed as you see fit, and could include graphics and charts along with text if you think they will be compelling.

## Deployment Details
If the contracts are already deployed, list them here in table form.

| Contract Name                                                                                       | Address                                                                                                               |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| [UniswapV3Factory.sol](https://github.com/Uniswap/v3-core/blob/main/contracts/UniswapV3Factory.sol) | [0x1F98431c8aD98523631AE4a59f267346ea31F984](https://etherscan.io/address/0x1F98431c8aD98523631AE4a59f267346ea31F984) |

Note that you do not need to deploy contracts before an *RFC* or *Temp Check*. You must deploy the contracts before the on-chain governance vote.

## Bridge Details
Detail the bridge protocol you will configure so your deployment of v3 is subject to the control of Uniswap's Ethereum governance contracts. Make sure to reference the Bridge Committee's guide to choosing and configuring a bridge. After you deploy the bridge contracts (which like the protocol contracts can be at any point in this process until the on-chain vote) list the relevant contracts in a table below.

| Contract Name                | Address                                                                                                                      |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| BSC Wormhole Sender Contract | [0x5f1ece07a0f36fec2d6e7796cd9c84959f3a1baa](https://goerli.etherscan.io/address/0x5f1ece07a0f36fec2d6e7796cd9c84959f3a1baa) |
