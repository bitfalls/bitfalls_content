In this article, we'll go through the process of getting started with the IOTA [cryptocurrency][cc]. We'll go through the process of installing the [wallet] to your desktop computer (read [here][exchangesbad] to find out why not on a mobile device), accepting IOTA, and sending it.

A detailed description of IOTA and how it differs from other blockchains is coming soon in a separate article.

## Wallet

The safest way to control your IOTA is downloading the official [wallet]. If you don't intend to send your IOTA but just receive it, Cold Storage (see below) is a better option.

Begin by [downloading the official wallet][iotawallet]. The images in this post will be demonstrating the process on OS X, but it's almost identical on any platform.

![Installation](https://bitfalls.com/wp-content/uploads/2018/01/01.png)

Once you run the application, it'll ask you about the type of node you want to run. Select "Light". To learn about the difference between these types, see [this post][nodes].

![Node type](https://bitfalls.com/wp-content/uploads/2018/01/02-1.png)

When picking hosts, select one at random. That's the list of full nodes your light node will be connecting to.

If you don't already have an IOTA wallet generated, generate your _seed_ [here][seed]. Copy it and paste it into the wallet's field. This will enable to Login option which will let you open your wallet.

![Login available](https://bitfalls.com/wp-content/uploads/2018/01/03-1.png)

![Otvoreni wallet](https://bitfalls.com/wp-content/uploads/2018/01/04.png)

## Receiving IOTA

To receive IOTA, pick Receive. This will spawn a string of numbers and letters along with a QR code which you can scan with a phone's camera so you don't have to manually type it into a mobile wallet.

![Receive ekran](https://bitfalls.com/wp-content/uploads/2018/01/05.png)

Send this string to the person or entity who needs to send you IOTA, or use it in the "Withdraw to" field of an exchange if pulling IOTA from there.

The option to Attach to Tangle broadcasts the address to the Tangle network signaling the fact that the address has been used. This can be useful for additional safety because, due to some [vulnerabilities in IOTA][mit], someone can under some circumstances extract the [private key][privkey] from the public address.

After receiving the IOTA, the balance should automatically update.

![New balance](https://bitfalls.com/wp-content/uploads/2018/01/06.png)

If your balance is still at 0, and the wallet you're sending from or the exchange you're withdrawing from is saying "confirmed", try switching the node to another one. Keep doing this until your balance changes. This is due to some [fundamental flaws][iotasucks] in the IOTA network.

## Cold Storage

For cold storage, i.e. storing IOTA in a safe place for long term investment, it's best to use a [paper wallet][paper]. An IOTA paper wallet can easily be generated via the [ColdStorage Tools][iotacs] UI.

![IOTA Paper Wallet]()

After having sent the IOTA to the address generated via the tool.

## Sending IOTA

## Conclusion

[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[paranoia]: https://bitfalls.com/hr/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[wallet]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[hw]: https://bitfalls.com/hr/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[mew]: https://myetherwallet.com
[paper]: https://bitfalls.com/hr/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[ledgershop]: https://bitfalls.com/hr/shop/ledger-nano-s-bitfalls-3/
[exchangesgone]: https://bravenewcoin.com/news/36-bitcoin-exchanges-that-are-no-longer-with-us/
[cst]: https://coldstorage.tools
[iotacs]: https://coldstorage.tools/iota
[privkey]: https://bitfalls.com/hr/glossary/#private-key
[bitcore]: https://bitcoin.org/en/bitcoin-core/
[electrum]: https://electrum.org/#home
[Abra]: https://www.abra.com/
[exchangesbad]: https://bitfalls.com/hr/2018/01/01/why-you-shouldnt-keep-your-cryptocurrency-on-an-exchange
[iotawallet]: https://github.com/iotaledger/wallet/releases
[nodes]: https://bitfalls.com/hr/2017/11/26/whats-bitcoin-node-mining-vs-validation/
[seed]: https://ipfs.io/ipfs/QmdqTgEdyKVQAVnfT5iV4ULzTbkV4hhkDkMqGBuot8egfA
[mit]: https://www.media.mit.edu/posts/iota-response/
[iotasucks]: http://archive.is/0PrTf