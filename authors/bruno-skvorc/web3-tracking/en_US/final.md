# Do Not Track Web3 - How Private is your Multi-account Mobile Wallet?

I was doing some research into [blockchain](https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/) wallets with support for multiple accounts for [Wallets.Review](https://wallets.review) the other day. I realized that as I switch identities in the app, I'm not actually paying attention to what the app is doing with them. Am I being tracked somehow, my various crypto identities linked and consolidated by an observing party?

There are two threat vectors.

## Wallet is malicious

The first problem case is when the wallet is closed source. Without you being able to inspect its code, it can send logs to the server about every address used on the device. This then consolidates identities into one and your [personal data is promptly sold](https://haveibeensold.app).

There are two ways to get around this.

### Use open source wallets

When a wallet is open source, everyone can inspect how it works. You may not be able to read the code, but someone else definitely is and you can be sure they're paying attention.

Worst case - wait for a critical mass of users before you jump on board with your own money. Use early adopters as human shields. Let them test the waters first and then slowly join in with gradually larger amounts until you reach the desired level of exposure.

![Operation human shield](https://bitfalls.com/wp-content/uploads/2018/10/humanshield.jpg)

### Use audited wallets

If a wallet (understandably) does not wish to publish its source code, for either business or security reasons, they should make sure they're [audited by a reputable company](https://audithor.io). An audit will tell users two things.

First, it will tell them that the developers of the wallet are in it for the long run. Not only did they find the money for an audit (those are historically quite expensive), but they invested the time and effort to both polish their code to an auditable level and to wait for the audit to be done. This indicates that they are not in a rush - a critical trait in the crypto scene.

Second, if the company performing the audit is reputable or the people representing it have enough to lose by making a bad call, you can implicitly trust the results even more. The amount of money to be gained by backing a malicious actor then becomes insignificant when compared to the potential loss of earnings from losing every potential client's trust.

Obviously, finding a wallet which was both audited and is open source is a winning combination.

It should be noted that if a wallet is closed source, you probably have more important things to worry about - for example, whether [your keys are yours](https://wallets.review/attributes.html#keys), or if they too are being sent to a remote server somewhere, accumulating until enough users have enough funds to collectively finance an exit scam.

## Dapp is malicious

This only applies in cases where the app has a dapp browser, but is the attack vector that's more interesting to me personally.

When using a dapp browser, many users don't care or pay attention to what the dapp is doing with their address. The situation was made somewhat better on desktop with MetaMask choosing to no longer expose the authenticated user's Ethereum address to [absolutely every website ever](https://thenextweb.com/hardfork/2019/03/22/metamask-ethereum-privacy-address/), but on mobile it's hard to gauge what's going on even after you've granted an app permission to see your address. Does it apply to this one address only? Does it apply to all of them on this app? How about device-wide?

I've looked at several wallets for [Wallets.Review](https://wallets.review), but as you can imagine it takes a while to properly try out a regular app, let alone a crypto wallet, so there are only 9 in total, 6 of which have both a dapp browser and multi-identity support. Of the 6 apps: Status, Trust Wallet, AlphaWallet, imToken, Coinbase Wallet and Opera, only one is safe from this exploit: [Status](https://wallets.review/apps/status).

So what is the exploit?

Put simply, it's up to the dapp to decide what to do with your Ethereum address both before and after switching: it can log your address into a cookie or localstorage ("cookie" for both in the text below), and then do the same for a new address you switched to. Then, once more than one address is in the same cookie, the dapp can report home and consolidate two identities into one. The wallet itself has only very limited control over this and I argue that it should exercise it.

You might argue that a dapp can do this even if a browser clears cookies, it will simply report back each address and if the User-Agent and IP match, that's grounds for linking identities. True, but only if the wallet doesn't also use a custom UA to throw off sniffers (it should!). Sadly, as most dapp browsers are little more than webkit with web3js injected into them, few wallets take the time to [customize the UA](https://stackoverflow.com/questions/36590207/set-user-agent-with-webview-with-react-native), instead using whatever their library of choice contains.

At this point this must seem pretty generic to you and you might be wondering how to check if you're safe against this exploit. I've got good news! You CAN!

Wallets.Review now has a small web page with web3 injected which will log any Ethereum address you visit with and spit it back out at you on next visit. It'll store the addresses in both localstorage and cookie, so you can use the tool to check if your mobile dapp-enhanced wallet clears both or just one of them. There's a handy button, too, for quick clearing of cache and re-testing.

The tool is [Don't Track Web3](https://wallets.review/dont-track-web3.html).

[![Don't Track Web3](https://bitfalls.com/wp-content/uploads/2018/10/dont-track.png)](https://wallets.review/dont-track-web3.html)

Take it for a spin, see what your wallet says and [let me know](https://twitter.com/bitfalls) so I can add it to the site. If you know any wallet developers, please tell them about this and make sure they add cache and cookie clearing to their dapp browsers along with UA masking.

## Conclusion

Be careful trusting apps in this new world of crypto economy. Don't get fooled by good UX and richness of features - you're probably paying for that somehow, especially if the app is free. Always go with open source or heavily audited apps and never keep on a mobile wallet more money than you would in your pocket. 

While most apps today provide you with immense benefits and help you do personal finance on a variety of offerings from staking to lending, holding large sums of money at the reach of a fingerprint isn't a good idea for obvious reasons. 

And even though you may not consider your holdings to be that great to be of value to anyone, I assure you, you're _always_ valuable to someone. At best, you're an identifying variable in an [unmasking graph](https://audithor.io/digital-forensics/) targeted at someone else. At worst, you're your future self's worst nightmare when the crypto-IRS comes knocking.