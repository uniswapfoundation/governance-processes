
Deploying and configuring the Uniswap v3 smart contracts on a non-Ethereum chain and rallying community support for their canonical status are two distinct processes that you can complete in parallel. They culminate in an on-chain vote that, if successful, adds the new deployment to a register of other non-Ethereum deployments governed by the DAO.

While you can certainly complete both processes independently, the DAO has formed a cross-chain accountability committee that can help along the way. You can contact the committee here TODO: figure out the best way to solicit inbound.

# Protocol Deployment and Bridge Configuration
Deploying the Uniswap contracts and the relevant bridge infrastructure can occur at any point before the on-chain governance vote. The Uniswap accountability committee can provide technical assistant to new deployments. Please reach out to @0xkydo via twitter.

## Protocol deployment
Deploy, verify, and test the Uniswap V3 contracts to your network using the scripts and instructions found [here](https://github.com/Uniswap/v3-new-chain-deployments). 

If you have deployed and verified your contracts prior to your first forum post, add a table to that post with the Contract Name in one column and the address (preferrably linked to the canonical blockchain explorer) in a second. If you deploy the contracts in the middle of the process, update your forum post or posts with the same table. 

| Contract Name    | Address |
| ---------------- | ------- |
| UniswapV3Factory | 0x....  |


## Bridge configuration
The Uniswap Foundation has convened a Bridge Assessment Committee to evaluate a subset of the cross-chain messaging protocols available. As of May 1, 2023, the committee has not yet issued bridge recommendations or configuration instructions. This guidance is expected soon and this section will be updated as and when it is available. 

# Write your proposal and post it as an RFC
Follow the guidelines [here](https://github.com/uniswapfoundation/governance-processes/blob/main/v3-deployments/v3-deployment-proposal-template.md) in writing your initial proposal. Create an account and post it on the [Uniswap Governance Forum](https://gov.uniswap.org/). Note the **List of Actors** section in the linked template; each one of these stakeholders is vital to a successful proposal. While you do not need to have a complete roster at the time of your first post, you should be reaching out to community members who could potentially fill each role. If you are having trouble, your contact at the Accountability Committee should be able to provide guidance.

## Engage with the community
A large and growing number of individuals and firms are active in Uniswap governance. Each will likely have a view on what you are proposing. Reach out to them directly to walk through your rationale, either by DM on the forum itself or via Twitter if they have public profiles. You can find out more about delegates at [Tally](https://tally.xyz/gov/uniswap), and [Boardroom](https://boardroom.io/uniswap/proposals) TODO: add new app. If they are supportive of your proposal, you could ask them to post that support and rationale publicly.

# Post a new Temperature Check and start Snapshot poll
After gathering feedback on your RFC (and after waiting at least a week), you should start a new thread on the forum with the same title, but replace RFC with Temperature Check. Incorporate any necessary changes into the body of your proposal. A summary of those changes at the bottom of the new post is also a good idea. At the same time, start a Snapshot poll with three options:
1. Yes - Approve deployment
2. No - Do not approve deployment
3. Abstain

Run the poll for 5 days. Snapshot requires an address to which 10k UNI is delegated to launch a poll. If you do not have the required UNI delegated to you, you should coordinate with your proposal's sponsor to either create the poll for you or delegate you the UNI necessary to do so.

If the `Yes` votes both win and reach a quorum of 10M UNI, you are welcome to move forward.

# On-chain governance proposal
If you have not yet completed the contract deployment and bridge configuration, do so now and add the resulting addresses to your Temperature Check post. Community members, including members of the Accountability Committee, will publicly verify that the contracts match those in the audited v3 repos, and that you deployed and configured the bridge infrastructure correctly.

To trigger the on-chain vote, you or your sponsor should write a function that calls the `setTextRecord` function on `v3deployments.uniswap.eth` and passes it the encoded calldatas specifying [your chain's ID](https://chainlist.org/) as the key and "`bridgeSenderContractAddress, localUniswapV3FactoryAddress`" as the value. Functions 2-8 in the `Executable Code` tab of [this proposal](https://www.tally.xyz/gov/uniswap/proposal/38) are examples of this function call.

# Follow up
Add a list of your deployment's contracts to this repo. Open a pull request creating a new folder in the `v3-deployments` directory containing a markdown file formatted per [this template](https://github.com/uniswapfoundation/governance-processes/blob/main/v3-deployments/v3-deployment-details.md). Be sure to update the `Deployment History` section following any other notable governance votes that touch your deployment. 

