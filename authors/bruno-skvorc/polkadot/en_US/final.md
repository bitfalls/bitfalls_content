If you're coming to Polkadot from Ethereum - whether out of curiosity or necessity - you'll probably be wondering how it differs from Ethereum 2.0, and what they have in common. Let's dive in.

_Note - to learn more about Ethereum 2.0, please check out [this series](https://our.status.im/tag/two-point-oh/)._

The following post assumes basic knowledge of Ethereum 2.0.

## Parachains / Parathreads vs. Shards

### Shards

Ethereum 2.0 will probably consist of 1024 **shards** and one beacon chain to coordinate them all via crosslinks. Validators - of which there would be hundreds of thousands - are randomly shuffled into committees of 128 members who then produce blocks on the shard chains. Every time a block on a shard chain is produced, other validators attest to it (confirm it). That block's hash is then stored as a crosslink on the beacon chain, at which point other shards can become aware of it.

Cross shard communication depends on shards reading this information and learning that the shard they're interested in has experienced a change. To load that change, they need to query that shard (i.e. connect to the nodes validating that shard). Communication across shards is thus not atomic and can be slow, depending on how many hops the execution of a stack of transactions requires. Composability of smart contracts [may or may not break](https://ethresear.ch/t/cross-shard-defi-composability/6268/6), further possibly stabilized by [yanking](https://ethresear.ch/t/cross-shard-contract-yanking/1450), but it's all in the air right now.

A discussion on reducing shard count by a factor of 16 exists, which would drop the number to a mere 64 and approach the numbers that Polkadot is aiming for with parachains. This would improve composability (higher chance of contracts being on the same shard) and reduce the required number of validators for optimal security (128 * 64 is 8192, versus 131k before), but this is still under heavy [discussion](https://notes.ethereum.org/@vbuterin/HkiULaluS) and has other tradeoffs (notably - more bandwidth to run a validator, you'd need a stable 5Mbit+ connection).

### Parachains

Polkadot's Relay Chain is similar in concept to the beacon chain in Ethereum 2.0. It provides shared security to all the shards, here called **Parachains** (parallel chains). Parachains are independent blockchains which produce their own blocks and those blocks are then candidates for inclusion on the relay chain, much like crosslinks in Eth2. The main difference in parachains and shards is that parachains will be free to implement local logic any way they see fit. They will be application specific, but will share the security of both the relay chain and all other parachains.

A chain optimized for DeFi use might exist, while another optimized for anonymous transactions might exist alongside it. Both will produce their blocks independently based on their own rules, but every X seconds where X is the target block time of the relay chain (depending on network performance - we're aiming for ~6 seconds) the hash of those blocks along with proofs that validators need to verify a legit state transition will be included into the relay chain.

In Ethereum, each shard's _logic_ is identical to that of the other - more on that below. Parachains are added to Polkadot through an [auction system](https://wiki.polkadot.network/docs/en/learn-auction) - candidates bid on up to four 6-month intervals of parachain slot leases. DOTs of the lease auction's winner are locked up for the lease duration and returned afterwards. There will be few parachain slots to lease, so it should be a competitive market but this also means not every application-specific chain can expect to be able to get in on this scarce resource. Polkadot supports parachains as relay chains, so a nested relay chain architecture where a chain is another relay chain with its own parachains is also a possibility (similar to shards having shards in Ethereum 2). This part of Polkadot is still in the research phase.

In other words:

- Ethereum shards: identical (homogenous) chains with shared security, splitting the network's load by evenly distributing it
- Parachains: different (heterogenous) chains with shared security, splitting the network's load by making sure each chain deals with its own specific context

### Parathreads

A special case are Polkadot's **parathreads**. Logically, these are almost identical (see ICMP section below) to parachains, but economically they differ in that they don't lease a parachain slot long term and thus don't need to put down a lot of DOTs into lockdown to enjoy the shared security of Polkadot. Instead, they bid for block production (in non-refundable DOTs) at desired intervals along with other parathreads in the same parachain slot. _Parathreads are users of a special, shared parachain slot._

When it's time for this slot to produce a block to send to the relay chain, the parathreads enter an auction for that block slot on the parachain slot. The top bids get into the relay chain, up to a block limit - currently 50 for the entire relay chain. On the surface, this seems like it would slow down some parathreads (i.e. some app specific blockchains deployed as parathreads) if there are more than 50 in the system, but this is not so - parathreads are designed to be used as "read often, write as needed" blockchains.

For example, a copyright parathread which logs new copyright registrations every so often does not need to submit this information to the relay chain on every block, but only as new information is added into the thread. It can batch these writes and execute them in a single block once per day, week, or any other arbitrary period.

One thing that should be noted is that if a parathread is using a local currency to reward collators, the collator must be natively aware of a DOT->local conversion rate if they are to be able to submit appropriate bids for block production in DOTs. That's an economic problem for a parathread to solve on its own.

Parathreads also require deposits in DOTs but there's no auction for slots - the capacity is estimated to be enough for everyone interested to join.

## Governance

Ethereum has **no on-chain governance** of Ether holders and will probably never have such a system. The decision-making is ultimately social and political, which [can be dangerous for the health of the network](https://decrypt.co/5219/progpow-kristy-leigh-minehan-ethereum-mining-asic-gpu/) due to effective lobbying.

Polkadot comes with **governance built-in** from the start. Three layers of vote holders exist in Polkadot - technical committee, council, and stakeholder (any DOT holder). The Technical Committee can - with the agreement of 3/4 of the Council - propose fast-tracked referenda which have shorter voting and enactment times, mainly for emergency upgrades. Members of the TC are different developer teams of the Polkadot Runtime and Runtime Environment. The Council and Stakeholders can make proposals for referenda, and referenda can change almost any aspect of the chain - from number of parachain/validator slots available, to payout fees, treasury expenses, and more.

_Side note: in Ethereum, members of the Technical Committee would be teams like Nimbus, Chainsafe, the Ethereum Foundation, Pegasys, Prysmatic, Parity, Sigma Prime, and others that are developing Ethereum 2.0 clients._

Stakeholder-suggested proposals have a positive turnout bias, which means a super-majority is required for the proposal to pass. As turnout increases to 100% this ratio edges closer to simple majority i.e. majority carries (50% + 1 vote to win). Council proposals are opposite - they are leaning towards passing by default and need a negative super-majority to fail. Again, as turnout approaches 100%, majority carries is in effect again and there is no difference between the negative and positive turnout bias. Proposals to spend Treasury money are voted on by the council, not the public. Votes are tentatively plutocratic in a one-coin-one-vote way, but can get a buff by the voter indicating the desire to lock the tokens in the vote for a period of time. Quoting from the [Kusama Rollout and Governance post by Gavin Wood](https://medium.com/polkadot-network/kusama-rollout-and-governance-31eb18041044):

> All voters are required to hold for the 30 day period up until the enactment date in the case that “their side wins” (if not then they are otherwise free to sell and leave the network). Those willing to hold for twice as long gain an additional vote. This is the case for up to five additional votes (i.e. those willing to hold for approximately two and a half years gain six votes). Those unwilling to hold at all may still vote but with a 90% reduction in power compared to those who hold for the four week minimum.

Plans exist for adding more governance bodies, but for details on that I recommend reading the post linked above.

It should be noted that making proposals for spending the Treasury's funds (see next section) requires a deposit of 5% of the target amount which is burned if the proposal does not pass, and that the Treasury must be spent entirely every period of 24 days, otherwise it has to burn some of its remaining funds. Both of these mechanics make for some deflationary pressure (see next section).

## Transaction fees and treasuries

In Ethereum, most of the [gas](https://bitfalls.com/2017/12/05/ethereum-gas-and-transaction-fees-explained/) spent on transactions is going to be [burned](https://eips.ethereum.org/EIPS/eip-1559). This creates deflationary pressure on the native currency, ether. The transactions being issued can contain a "tip" amount which acts as incentive for validators to prioritize certain transactions. This way, those using the network directly benefit all stakeholders as burned ether adds value to all ether.

In Polkadot, transaction fees are split between the validators and the treasury, 20% - 80%. There is no burning. This is so that the protocol can throttle its inflation and deflation more effectively. As slashing is inherently an unpredictable event, burning the stake during mass-outage events would cause sudden deflation to no fault of the validators - it was an infrastructure or protocol level failure. In those cases, it's better to have the funds ready to pay for fixing things than to burn the funds and discourage network participation. The ratio of Treasury / Validator distribution can be changed through governance (see previous section).

In Polkadot, blocks have reserved space for crucial transactions - like those of fishermen reporting misbehaviors. This allows fishermen to do their job even if the blocks are full.

Like Ethereum, Polkadot also has tips on transactions for dealing with spikes in block space demand.

## Consensus

Ethereum implements finalization through a system called [Gasper](https://our.status.im/two-point-oh-justification-and-finalization/), a blend of LMD GHOST (Last Message Driven Greediest Heaviest Observed SubTree) and Casper FFG (friendly finality gadget). Finalization is the concept of being so certain a block is correct and cannot be undone that being wrong about this claim would result in the punishment of a large part of the network (a large number of validators). Polkadot uses GRANDPA (GHOST-based Recursive ANcestor Deriving Prefix Agreement) to do the same thing.

Both Ethereum and Polkadot separate block production from finalization. In Ethereum, block production doesn't have a special name. In Polkadot, it's called [BABE](https://research.web3.foundation/en/latest/polkadot/BABE/Babe/) - Blind Assignment for Blockchain Extension. This separation makes sure that block production can continue without finalization, theoretically supporting blockchain growth even with a severely reduced number of validators. Once enough are back online, the finalization process can finalize the blocks starting from the last finalized one.

In Ethereum, every 64th block is taken into account for finalization, and if 2/3 of validators agree (attest to) that this so called _checkpoint_ is valid, then it is _justified_. If they do this for the very next checkpoint too, or the one after it, then the checkpoint is deemed _finalized_ and can be considered irreversible. It qualifies for use by light clients and similar software which isn't interested in syncing with the entire chain's history.

Polkadot is similar but the 64 slot gap isn't there. Instead, as soon as 2/3 of validators agree on a block produced by BABE according to GRANDPA rules, that block and all those before it in the same chain are immediately finalized. GRANDPA - GHOST-based Recursive ANcestor Deriving Prefix Agreement - looks at chain forks with the closest finalized block and decides which blocks to finalize based on that. A big advantage of GRANDPA is that it can finalize whole chains at once, not just block by block. This comes in handy if the validator count has been dramatically reduced (major outage perhaps). Under BABE, blocks will keep being produced, but won't be finalized because of a lack of validators. Once enough validators are back online, an entire history of blocks is finalized at once.

BABE assigns a "Primary" block producer based on the VRF (normal BABE - see Randomness below) and a "Secondary" based on the following equation: `blake2_256(epoch_randomness ++ slot_number) % authorities_len`. When a block producer wins the VRF, it broadcasts a message to say that it's the primary. If no primary messages are received within some window (>>WHAT WINDOW AND HOW TO IMMUNIZE AGAINST LATENCY?), then the Secondary assignee produces the block.  With this backup in place, Polkadot slots are effectively never without blocks, with a caveat - when choosing forks, the chain with more _primary_ blocks is prioritized, so it might happen that this chain has empty slots from the VRF process.

## Randomness

Randomness is very important in blockchains using proof of stake. You need a way to reliably randomly select a subset of your validators to do some work. If this randomness is even the least bit predictable, then it can be abused and validators can game the system by always making sure it's their turn to be rewarded, or by attacking those they know whose turn it is in order to get them punished for unavailability.

In Ethereum 2.0, randomness will come from a two-part system: the first is RANDAO, the second is VDF. RANDAO is what's called a commit-reveal scheme in which, to put it plainly, many validators secretly pick a number, and then the result is some mathematical operation performed on all those numbers, revealed one by one. Since it is not possible to predict which number all of the validators will chose, and the final output can vary wildly depending on just a single one of them, it's not possible to predict this random number. However, it is possible to influence it because the last revealer always has the option of not revealing his number, after he calculated that the current number is more in his favor than the one with his reveal. The chances of this happening are miniscule and the advantage to be gained by this bit-level influence would have to be immense - the network is plenty secure even without mitigating this risk. 

However, it too will probably be mitigated by using a VDF - verifiable delay function. In layman's terms, a VDF is function which is mathematically proven to take a long time, and cannot be sped up by throwing more computers at it (it is non-parallelizable). This delayed function executes another mathematical operation on top of the RANDAO number in order to make the result come "late" - an hour and a half after the numbers have been revealed. These devices will be open source and distirbuted freely, and there is no incentive for running them. For more info on Ethereum 2 randomness, see [this post](https://our.status.im/two-point-oh-randomness/) and for more info on VDF, please see [the VDF research site](https://vdfresearch.org).

In Polkadot, VRF is used. VRF stands for verifiable random function. It's much simpler than RANDAO and VDF in that the validators who are participating in the network have a secret "randomness roll key" which is regenerated for every slot. They use this randomness key along with some other inputs (the randomness of the previous epochs and the slot number) to generate a random number for themselves and only themselves. Then, they compare this number to a protocol-defined number (a so-called threshold) and if their number is less than that threshold, they are a viable candidate for producing the next block. If they rolled too high, they should skip this slot. The VRF function which they use to roll this number is deterministic, so they cannot reroll to try again - for the same input, the same output will be produced. This function also produces a _proof_ - some data that proves the randomly rolled number is legit, without actually showing the roll or the inputs that went into it (thereby keeping the roll key secret). If someone doubts a validator's candidacy as block proposer on a given slot, they can just check the proof and make sure. If it doesn't match, they can report the validator for wrongdoing and have them punished.

RANDAO + VDF is secure by default, in that the number produced is guaranteed to be random.
VRF is secure after the fact (suspected wrongdoing must be pointed out), but is significantly less resource intensive.

## ICMP vs Crosslinks

Crosslinks are how shards in Ethereum will be communicating. By telling the beacon chain that a state change has occured on the shard, the other shards which depend on fresh data from the changed shard need to query it manually. In other words, they need to know what they don't know so that they can request it. This will be a user-land implementation detail and will depend entirely on how wallets, IDEs, protocols and other users of Ethereum implement this communication.

ICMP or inter-chain message passing is Polkadot's way of establishing communication across parachains and parathreads. Each chain and thread have an ingress and egress queue - a queue for incoming and outgoing messages, respectively. Messages are transactions meant for another chain or thread, which are forwarded to the destination parachain or parathread on every block through common collators - collators that are using both of the communicating chains. Since we assume that people will be running collator nodes for different chains at the same time, there should be a reasonably stable mesh effect going on allowing for messages to successfully gossip across to their destination. As a backup, in case some chains or threads are islands and have no other connections, validators will also make sure that ingress and egress queues of the chains and threads they are processing are empty. If not, then they will assume this role of message relayer.

Both modes of communication - crosslinks and ICMP - are asynchronous and thus non-instant. The appearance of real-time communication will be a matter of userland implementation.

## Node types

In Ethereum, the following economy-user and node roles (client software types) exist:

|Name       |Role                                                  |Incentivized|Optional|
|-----------|------------------------------------------------------|------------|--------|
|Beacon node|Full node of all shards. Passes on data to validators.|No          |No      |
|Validator  |Proposes and attests to blocks based on beacon data.  |Yes         |No      |
|VDF ASIC   |Enhances RANDAO to provide better randomness.         |No          |Yes     |

Beacon nodes can potentially be incentivized by being archive nodes of all shards, which means they keep even the data which was wiped due to state rent expiration. A state-rent wiped contract can be restored by an archive node, for a fee. Archive nodes as-a-service are probable in Ethereum 2.0.

In Polkadot:

|Name       |Role                                                        |Incentivized|Optional |
|-----------|------------------------------------------------------------|------------|---------|
|Collator   |Full node of particular shard. Passes on data to validators.|Possibly    |No       |
|Validator  |Full client of all parachains and parathreads. Proposes and attests to blocks based on collator data.      |Yes         |No       |
|Nominator  |Nominates a validator through which to proxy-stake.         |Yes         |In theory|
|Fishermen  |Monitor the network for misdeeds like equivocation or illegal randomness.|Yes|Yes|

Validators can be fishermen, which makes fishermen optional. Nominators are _theoretically_ unnecessary, i.e. the network would work fine without them if the validators had enough self-stake to keep themselves in the validator pool.

## Inflation

In both Polkadot and Ethereum the inflation is dynamic and defined as "minimum necessary inflation". The exact number will depend on the amount of staked coins.

## Validators and staking economy

### Polkadot

In Polkadot a validator is a full client (>>FULL OR LIGHT?) of all chains and threads, thus very resource intensive on hard drive space and read/write ops, and on bandwidth.

The assignment of a validator is periodically (>>HOW OFTEN?) reshuffled so that a single validator isn't always responsible for a single parachain. A validator earns DOT from block production (inflation) and transaction fees in a 80/20 spread. 80% of the transaction fee goes to the Polkadot Treasury. The validator gets rewarded twice - they set a fixed number of DOT to get per reward period (epoch - roughly 6 hours), and the rest is then dividied among all the nominators who have nominated this validator, and the validator, based on their respective amounts of staked DOT. It's important to note that nominators can still lose their DOT if they backed an incompetent validator - this is not delegated proof of stake where you simply signal your trust in someone, you literally unlock your DOTs for "burning by malfeasance" when nominating.

The maximum annual reward for validators is estimated to be 20%, and that's with 50% of all DOTs in existence staked (currently 10 million DOTs as a target). It is likely to be much lower.

A collator is a full node of a specific parachain. The collator passes data which becomes a block candidate, along with proof of the state transition so that the validator can replay and verify it. The collator depends on the local economy of the parachain - likely a local token. A parachain can also use DOTs as a native token, and a local token purely for governance or similar.

Fishermen earn money for each valid report they make on some wrongdoing - the slashing amount is in part burned, in part sent to treasury, and in part given to the fisherman who reported the issue. The amounts depend on the offence and on how many other validators are in the same predicament (e.g. the offline penalties are much bigger if many validators are offline at the same time).

There is no limit to the amount of stake a validator can commit, and the active validators are picked from the top most-staked validators (including nominations) once per era (24 hours). This ensures that all the top validators have approximately the same amount of staked DOTs, and that a single whale can't effectively take over because the reward per validator is the same - it's not proportional to the staked amount. Therefore, the reward per dot is less when you stake more, but the penalty per offence is greater because penalties are proportionate to staked amount. This system incentivizes nominators to nominate less popular validators, keeping the distribution balanced.

### Ethereum

In Ethereum 2.0 only the validators are incentivized. They are given information by beacon nodes which will probably be run by large providers and used remotely (beacon nodes with data for all shards will need above-average machines) and they build crosslinks (see above) and attest to other crosslinks from that data. To become a validator in Ethereum, one needs 32 ether to stake - no more, no less.

In Ethereum, the less Ether is staked the higher the return rate, to incentivize more people to join. For example, for 1 million ether, the annual return rate is predicted to be 18%. For 100 million ether, the return rate drops to 1.81%. This is not a cause of concern, however, because locked ether is taken out of circulation and given that it's "fuel" for the network, the price of the asset should rise proportionately as demand increases, in particular due to other [lock-ups in DeFi](https://defipulse.com/).

### Slashing

Reasons for slashing are the same in both systems:

- producing two blocks for the same slot
- signing two conflicting chains
- being offline

Additionally, in Polkadot there's the penalty for illegal randomness rolls which can be detected by fishermen. See Randomness section above for details.

In Polkadot any offence not only slashes, but also removes a validator from the validator set in the current era. They have to re-qualify to rejoin.

## Smart Contracts, Execution Environments, Runtimes and SPREE

Finally, let's talk bout the meat of the protocol - the execution layer.

In Ethereum, there will be the concept of Execution Enivronments. These will be special runtimes built by special teams and funded by special interests to run and execute custom code. In other words, if someone wants to build the ability to process bitcoin-like transactions into Ethereum, they need to fund a UTXO-execution-environment and make sure all clients add it to their code as well (likely helping with funding those efforts, or contributing outright). Once done, the execution environment becomes available to everyone - it's considered a network upgrade.

The first and default execution environment will be eWASM, a neutered version of WASM flavored for Ethereum. The second one may very well be an EVM EE which would allow Ethereum 1 to continue living and breathing inside of Ethereum 2, perhaps on a dedicated shard. Developing custom EEs will be expensive and hard, so we don't expect to see many of them.

eWASM will support smart contracts through languages that can compile to WASM like [Nimplay](https://github.com/status-im/nimplay/). EVM EE will support smart contracts just like Ethereum does today.

In Polkadot, the relay chain does not have smart contract support. Given that there are no parachains yet, there is effectively nowhere to go if you want to develop a smart contract of any kind on Polkadot. However, Substrate - the framework on which the relay chain is built, and the framework which others will likely use to deploy parachains, has support for modules - blobs of plug-and-play code used to enhance your chain's runtime with new functionality. One such module is the Smart Contracts module which, when plugged into a parachain, can support smart contract execution. There are two caveats to such a model:

1. When you want to just fire up a smart contract, you have to do it on a specific smart-contract parachain (though nothing prevents you from deploying the same thing on all smart contract parachains). Picking between them might be difficult - they can be custom-tweaked for specific use cases (privacy vs speed, for example).
2. That smart contract chain has to communicate with other chains to be of any use, otherwise you're working in a silo.

Given that Polkadot's entire story arc is the interconnectivity of these parachains, the communciation aspect is rather well developed. We mentioned this briefly in the ICMP section above, but here's a recap: the parachain has an egress (outgoing) and ingress (incoming) queue of messages. These messages are processed in order and happen on chain. But how can you be sure your destination chain executed the code you wanted to trigger by sending it a message? This is where SPREEs come in.

Think of SPREEs - Shared Protected Runtime Execution Enclaves - as part of a "standard library" for parachains. The standard library will contain many different SPREEs, and they all live on the relay chain as WASM blobs of code that parachains can "opt in to". For example, say there is a SPREE which handles token transfers. If two parachains opt into this SPREE, they both get the built-in ability to transfer tokens. Thus, a message that says "transfer tokens" means the same thing to both chains, and they can reliably communicate. SPREEs have their own ICMP endpoints so they can receive messages and their own isolated storage.

In summary:

- Ethereum will continue to support smart contracts as it does today, but they will have to be written in a language which can compile to WASM. Several Solidity-to-WASM compilers are in progress and should be ready by then.
- Polkadot will support smart contracts on smart contract parachains. Not all parachains need smart contracts because smart contracts, especially the general kind available on Ethereum, need gas metering to prevent abuse. If you instead rigidly define the types of transactions that are possible on your application specific parachain, you're much more likely to get the economy of usage right, and to reduce various bugs possible due to bad metering implementations.

---

Hopefully, the above comparison points have shed light on the similarities and differences between the two systems. If anything is unclear, flat out wrong, or I simply missed a point you wanted to hear about, shout at me [on Twitter](https://twitter.com/bitfalls)!
