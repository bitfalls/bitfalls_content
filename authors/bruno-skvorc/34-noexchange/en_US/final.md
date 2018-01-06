_For the best experience, we recommend reading the following prerequisite materials:_

- _[What is cryptocurrency?][cc]_
- _[What is a cryptocurrency wallet?][wallet]_
- _[What is a private key?][privkey]_

---

We at Bitfalls have been known to claim that keeping [cryptocurrency][cc] on an exchange where it was bought isn't healthy. But why is that? Which [safer ways][paranoia] are there? Are mobile [wallets][wallet] safer than desktop ones? Are they better or worse than [hardware wallets][hw]? How about [paper] wallets?

## The Risk of Exchanges

It's very easy to get tempted by the ease of use and user-friendliness of keeping cryptocurrency on the exchange where it was bought. Exchanges support several currencies at once, allow for fast reaction times when a currency needs to get traded for something else during market opportunities, and they process enormous amounts of transactions every day so **_they're too big to fail_**.

The latter is the biggest misconception.

When Mt. Gox - the biggest exchange of its day - fell in 2014, it took the bitcoin of its clients along. It happened virtually overnight and no one could react. Mt. Gox fell at its peak and was processing around 70% of all Bitcoin transactions in the world at the time. A single website was processing the vast majority of Bitcoin transactions in the world and still imploded. That wasn't the only incident of the type - since then [many exchanges][exchangesgone] followed the same pattern, and every time they were deemed "too big to fail".

![Spaljen novac](https://bitfalls.com/wp-content/uploads/2018/01/01.jpg)

When your cryptocurrency is on an exchange, you're effectively trusting their word that there's a specific amount of crypto in your account. You don't have your private key - they do - in order to be able to send funds from that address to another one. They cannot share it with you because they would expose themselves to risk (you could send funds without their knowledge).

The only way to get full control over your cryptocurrency is to have the private key of your wallet in your possession and not let anyone else get a glimpse of it.

So, how do you get your own private key?

## Your Own Wallet

There are two main categories of personal wallets which will let you grab control of your own private key: software and hardware.

### Software

Software wallets are programs which you install onto your own mobile device or personal computer. There are several hundred such programs, sometimes dozens per currency.

These wallets can be "light" or "full". We also call them "clients" - a computer term for software which connects to a network or a protocol in order to use it. For example, Outlook is an "email client" because it uses the email protocol to read and send emails.

Full clients download the whole [blockchain][bc] when powering up. This allows them to validate past transactions instantly, instantly notice new incoming transactions and also lets them easily send new transactions into the network directly. Full wallets demand a lot of disk space (hundreds of gigabytes) so they're usually used by power users or merchants. An example of a full client is the [Bitcoin Core][bitcore] software:

![Bitcoin Core softver](https://bitfalls.com/wp-content/uploads/2018/01/02.png)

Light (also called thin) clients communicate with the network and ask full wallets for the information they need. If, for example, a light wallet needs to validate a past transaction, it'll ask a nearby full node about it. Light wallets are small and easy to install and use on mobile devices and/or older machines. Light clients don't have to be installed on devices - they can also be websites like [MyEtherWallet][mew]. One of the high quality Bitcoin light clients is [Electrum][electrum].

#### The Problem with Mobile Wallets

Tread carefully when using light clients (wallets) that get installed on mobile devices.

Mobile wallets often take over private key control for the user for the sake of simplicity and in that effect become almost the same thing as the centralized exchanges we want to avoid. If that wallet's servers become compromised or shut down for any reasons, your cryptocurrency disappears too.

<img src="https://bitfalls.com/wp-content/uploads/2018/01/03.png" width="250" alt="Abra wallet">

_The image below is of [Abra], one such wallet._

Even if you have a mobile wallet which lets you print your private key and fully control it, it's important to remain careful when storing any non-trivial amount of crypto on it. On mobile devices - especially those with very open operating systems like Android - it's easy to run into a fake malware app on the app store and accidentally install software which will spy on your screen and send data to a hacker's server as soon as it sees a key. If the phone is _rooted_ (administration mode activated), it's even easier to lose money - connect it to a compromised public charger at an airport or in public, and you could be going home with an infected phone just waiting for you to install a new wallet or open the screen which shows your private key. It's dangerous to even have it on screen on a secured phone, too - one walk past a compromised webcam, and your key gets immediately harvested.

Mobile devices should not be considered secure under any circumstances.

### Hardware

Hardware wallets are those which store your private key on a physical medium which is wholly offline, i.e. has no contact with the internet (and is therefore unhackable). A hardware wallet is something like a [Ledger][hw] or a [paper wallet][paper]. Read the articles behind those links to learn more.

We recommend using the [Ledger][ledgershop], but even a paper wallet is fine if it's made via a secure tool like those at [ColdStorage Tools][cst]. Print it out (or better yet - engrave it onto a metal or wooden plaque), store it in a lockbox and feel safe.

## Conclusion

The only way to keep your cryptocurrency safe is _cold storage_. In other words, the only safe place in which to store your private key is the one to which only you have access, and which is cut off from the internet.

If buying a hardware wallet like a [Ledger][ledgershop] isn't an option right now, we recommend creating a paper wallet for your desired cryptocurrency by using the quality tools over at [ColdStorage Tools][cst].


[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[paranoia]: https://bitfalls.com/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[wallet]: https://bitfalls.com/2017/08/31/what-cryptocurrency-wallet/
[hw]: https://bitfalls.com/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[mew]: https://myetherwallet.com
[paper]: https://bitfalls.com/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[ledgershop]: https://bitfalls.com/shop/ledger-nano-s-bitfalls-3/
[exchangesgone]: https://bravenewcoin.com/news/36-bitcoin-exchanges-that-are-no-longer-with-us/
[cst]: https://coldstorage.tools
[privkey]: https://bitfalls.com/glossary/#private-key
[bitcore]: https://bitcoin.org/en/bitcoin-core/
[electrum]: https://electrum.org/#home
[Abra]: https://www.abra.com/