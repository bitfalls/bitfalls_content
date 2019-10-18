
A number of ventures are pushing to make interaction with the blockchain as seamless and invisible as possible for users of decentralised applications (Dapps). Experienced crypto users are well-versed in the role of wallets, seed phrases, and transaction fees, but there is mounting evidence that these are significant roadblocks to on-boarding users who are not already familiar with crypto.

  

Just consider the process. Instead of what a user is accustomed to when installing and using a typical app, a Dapp might ask them to install [Metamask]([https://metamask.io/]), figure out what public and private cryptographic keys do, and add some crypto (which in turn requires the user to go through KYC processes with an exchange) to cover Gas fees. Plus, if you want to use the Dapp on another device, you’ll likely need to enter your seed phrase. Asking users to develop new skills and routines when using new technology is common, but not to this extent for a technology that is functionally invisible.

  

<h2>Creating a wallet</h2>

  

[MetaMask]([https://metamask.io/]) are well aware of the pain point their service can be for users, and have been developing a simpler user journey. A browser extension for linking Ethereum wallets to your browser, and offering an on-ramp for the decentralised web, MetaMask is a prerequisite for using the majority of Dapps and has seen widespread usage among early adopters. Installing an extension just to make use of a website or application is, however, not something that most people are used to.

  

MetaMask’s new mobile app is a step forward in addressing some of the usability issues we’ve discussed. A first-time user downloading the app is greeted with a ‘Get Started’ button, which creates an Ethereum wallet with one click. A pop-up welcome message tells the user that in order to use the blockchain, they need a wallet, which they’ve just created. At no point is the user confronted with any long strings of letters and numbers- at least not until they’ve deposited some funds at which point they secure the wallet.

  

The app also includes a web3 ‘browser’, which links the user to decentralised services, including routes to buying Ether. It’s unclear how much auditing goes into the listed services, but this view will look a look like an app store to a layman user- a place where they can view all the different decentralised services they can use.

  

<h2>Pumping Gas</h2>

  

In terms of usability, the MetaMask app makes the process of creating a wallet extremely simple, but there is another big issue: Gas, which is needed for executing transactions with Ethereum. Gas fulfils some vital functions for miners but for the layman user essentially represents a transaction fee paid in Ether. Most users understand the concept of transaction fees, even if the specific Ethereum vocabulary isn’t familiar to them. The bigger problem is where the Gas comes from- if a user isn’t holding any Ether to pay the fees, they won’t be able to use a majority of Dapps.

  

MetaMask is experimenting with a solution to solve this problem. At the time of writing, users can opt in to an experimental feature called InstaPay. InstaPay is a layer 2 solution from Connext Network, using state channels to make faster and cheaper transactions. A user deposits Dai, and is able to send it instantly without Gas fees. While the service is still in beta, and the maximum transaction is 10 Dai, it is a development that hints at the promise of layer 2 solutions for scalability, although it still doesn’t solve the problem of a user who has no Ether at all.

  

A recently-launched solution is already helping Dapp developers to reach these users. [The Gas Station Network (GSN)](https://gsn.openzeppelin.com/) is exactly what it sounds like- providing Gas so that Dapps can onboard users and get them using their service without requiring any Ether or other tokens to do so.

  

GSN works by coordinating meta transactions, which are similar to regular transactions but with one key difference. Instead of specifying an amount, signing with your private key, and sending your transaction on-chain, a meta transaction is sent off-chain. This means that the final step, the one which requires Gas, doesn’t happen. At least not right away.

  

Instead of going on-chain, your transaction gets sent to a server called a relayer. This can be an organisation or entity who is willing or incentivised to pay the Gas for you. This is where the GSN comes in, working as a network of relayers for these transactions. The relayer assumes the Gas cost of your transaction and sends it on-chain, and is rewarded for doing so by the Dapp developer. This means there is an extra cost to be assumed by the developer, but as Ramon Recuero [writes](https://blog.openzeppelin.com/gsn-the-ultimate-ethereum-onboarding-solution/):

  

“Transaction costs and gas fees are now part of your customer acquisition cost (CAC). Deal with it. Your users won’t.”

  

<h2>Community funding models</h2>

  

There has also been a significant ground-up approach to overcoming some of these problems from the Ethereum community. Organisations offering bounties and funding have sprung up over the past 12 months to fund and iterate on new solutions to address usability and onboarding. Whilst most of these initiatives are early stage, some have already distributed funds and areas of focus are starting to emerge.

  

[MetaCartel](https://www.metacartel.org/) started out as a group of Ethereum developers working on meta-transactions, later becoming a decentralised autonomous organisation (DAO) with the aim of funding and supporting projects that improve usability and UX, and specifically helping Dapps develop modes of best practice. With two funding waves already completed, MetaCartel has funded 6 projects so far. While none so far have specifically focused on usability, MetaCartel sees developing replacements for Web 2.0 services such as Eventbrite and LinkedIn, and trialling different business models for profitability, as major early priorities.

  

Other smaller bounty initiatives are also developing. At DevCon, the Bounties Network [announced](https://devcon.org/agenda?talk=recZQ75MUfilq6or2) that they are working with Rimble to offer bounties to developers for creative solutions to Dapp UX problems. They called for designs, prototypes, and working demos that solve problems in on-boarding new users, interacting with smart contracts, and transaction status. The aim is to produce a series of open source resources for developers to refer to when working on Dapps that can work as a best practice guide for usability.

  

We may be a little way away from seamless Web3 experiences for non-crypto holders, but the efforts of the Ethereum community to address this problem are beginning to gain traction. Dapps can onboard users without need them to hold Ether, users can create wallets without any of the jargon, and there is real impetus and funding in the Ethereum community to address this area head on.

[https://metamask.io/]: https://metamask.io/
[https://gsn.openzeppelin.com/]: https://gsn.openzeppelin.com/
[https://blog.openzeppelin.com/gsn-the-ultimate-ethereum-onboarding-solution/]: https://blog.openzeppelin.com/gsn-the-ultimate-ethereum-onboarding-solution/
[https://www.metacartel.org]: https://www.metacartel.org
[https://devcon.org/agenda?talk=recZQ75MUfilq6or2]: https://devcon.org/agenda?talk=recZQ75MUfilq6or2
