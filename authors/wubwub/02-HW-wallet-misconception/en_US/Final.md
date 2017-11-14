In [this article][hw wallets]  we have explained how hardware wallets like [Ledger][ledger], Trezor, and Keepkey work, but we still see some misconceptions surrounding them.

Let's discuss the two most frequent ones. The text below references Bitcoin as the [cryptocurrency][cc] of choice, but the same applies to all cryptocurrencies.

##  1st Misconception: Cryptocurrency is on the wallet itself

The biggest misconception is that our, for example, Bitcoins are saved on the wallet itself. 

Our Bitcoins aren't saved on the wallet, but on the [blockchain][blockchain]. Our wallet contains the [**private** keys][privkey] which are needed in order for us to sign the transaction and actually send those Bitcoins from one address to another. The real-world equivalent to this would be if we said that we have a car in our pocket, but in reality, we have our car keys in the pocket.

We can think of the blockchain as a public ledger which keeps track of how many Bitcoins every address has.

This misconception is true for both software and hardware wallets.

You can learn more about private/public keys [here][privkey], or [here][blockchain].

## 2nd Misconception: I have a Ledger wallet, but I don't have enough space for all of the apps?

The reason why Ledger can't hold more than five apps at the same time is due to security reasons, mainly because of potential malware wreaking havoc on the device. If the space is limited, the malware has no room to install itself.

_Ok, security is important, but won't I lose the coins if I delete an app?_

No, we can install and uninstall apps as we please without losing any coins on the wallet. [BIP 39] makes this possible as we explained [here][hw wallets]:

Whenever you boot up your Ledger Nano S or Trezor for the first time, you will get a list of words that you have to write down. The master private key is derived mathematically from the word list, which further derives private and public keys depending on the rules of a specific cryptocurrency which is supported by the wallet.

For example, if we uninstall the Litecoin app from the wallet and we install it again after some time, BIP39 will generate the same set of public and private keys and we will have access to our funds that were there before we uninstalled the app. We'll also have access to the funds that came in while the app was deleted.

It is of utmost importance to write down the word list and keep it safe. If your wallet somehow breaks down, you will recover your funds with that word list, either on another hardware wallet or a software wallet on your computer. See [this post][safe] for safekeeping approaches.

## Conclusion

Hardware wallets are one of the safest, if not the safest method of keeping cryptocurrency safe. A lot of time and hard work was put into the technical background and into simplifying the user interface. We hope that the mystery of how they work is at least a little bit clearer.

For more information on the mathematical and technical side but in an easily digestible format, check out [this article][hw wallets].


[hw wallets]:https://bitfalls.com/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[blockchain]:https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[BIP 39]:https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki
[privkey]: https://bitfalls.com/glossary/#private-key
[ledger]: https://bitfalls.com/shop/ledger-nano-s-bitfalls-3/
[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[safe]: https://bitfalls.com/2017/09/08/best-ways-protect-cryptocurrency-wallet/