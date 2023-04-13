# Protocol Deployment and Bridge Configuration
Deploying the Uniswap contracts and the relevant bridge infrastructure can occur at any point before the on-chain governance vote.
## Protocol Deployment
Use the deployment script found here TODO: get link to deploy
Verify your deployment is correct by executing the following steps. Post your results in your proposal's [RFC] or [Temperature Check] thread (or  both).
1. Do a thing
2. Do the next thing
3. Something with hardhat, probably
4. Output another thing
## Bridge Configuration
The cross-chain bridge evaluation group published their findings on which bridge solutions were appropriate for Uniswap's use case. Be sure to reference those findings when choosing and deploying your bridge contracts, as the configuration of those contracts is important. While the method varies slightly on a bridge-by-bridge basis, you should generally execute the following steps and post the results in your proposal's [RFC] or [Temperature Check] or both.
1. Do the first thing
2. Do the second thing
3. Be sure the second thing worked then do the third thing
4. Etc

# Write your proposal and post it as an [RFC]
Follow the guidelines here (TODO: link this) in writing your initial proposal. Create an account and post it on the [Uniswap Governance Forum](https://gov.uniswap.org/). Note the **List of Actors** section in the linked template; each one of these stakeholders is vital to a successful proposal. While you do not need to have a complete roster at the time of your first post, you should be reaching out to community members who could potentially fill each role. If you are having trouble, reach out to the [Uniswap Foundation on Twitter](https://twitter.com/uniswapfnd) for guidance.

## Engage with the community
A large and growing number of individuals and firms are active in Uniswap governance. Each will likely have a view on what you are proposing. Reach out to them directly to walk through your rationale, either by DM on the forum itself or via Twitter if they have public profiles. You can find out more about delegates at [Tally](https://tally.xyz/gov/uniswap), and [Boardroom](https://boardroom.io/uniswap/proposals) TODO: add new app. If they are supportive of your proposal, you could ask them to post that support and rationale publicly.
# Post a new [Temperature Check] and start Snapshot poll
After gathering feedback on your [RFC] (and after waiting at least a week), you should start a new thread on the forum with the same title, but replace [RFC] with [Temperature Check]. Incorporate any necessary changes into the body of your proposal. A summary of those changes at the bottom of the new post is also a good idea. At the same time, start a Snapshot poll with three options:
1. Yes - Approve deployment
2. No - Do not approve deployment
3. Abstain

Run the poll for 5 days. Snapshot requires a certain amount of delegated UNI to launch a poll. You should coordinate with your proposal's sponsor to either create the poll for you or delegate you the UNI necessary to do so.

If the `Yes` votes both win and reach a quorum of 10M UNI, you are welcome to move forward.
# On-chain governance proposal
If you have not yet completed the contract deployment and bridge configuration, do so now and add the resulting addresses to your [Temperature Check] post. Community members will publicly verify that the contracts match those in the audited v3 repos, and that you deployed and configured the bridge infrastructure correctly.

To trigger the on-chain vote, you or your sponsor should write a function that calls the `setTextRecord` function on `v3-deployments.uniswap.eth` and passes it the encoded calldatas specifying yourChain and the address of the bridge sender contract. TODO: tighten this up/validate it's right.
