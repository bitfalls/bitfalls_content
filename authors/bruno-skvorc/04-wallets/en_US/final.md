A *wallet* is a special _address_ which can receive [cryptocurrency tokens][cc]. Concept-wise, it's similar to an email address. Every [blockchain] has its own type of wallet, and they usually aren't compatible with each other (you can't send bitcoins to an Ethereum address, for example).

Anyone can have as many wallets (addresses) as they wish and there's no way to reveal the identity behind an address unless the user slips up, or publicly declares this. Most blockchains make address information publicly accessible - the amount of tokens contained on it and all its past transactions are visible to everyone. If we compare this to an email address, a wallet is like an email inbox which everyone can read, but only the owner can send messages in.

Tokens on a given address are used with the help of a _private key_ - a combination of letters and numbers mathematically impossible to guess. All tokens are "moved" from address A to address B by signing a transaction with this private key which is then sent to the blockchain for confirmation. It's important to note that in cryptocurrency, tokens aren't moved per-se as you're used to assets being moved. Instead, the owner of a given amount of tokens in considered to be the address which was last declared to be the owner by all participants of a blockchain's ecosystem.

As an analogy, consider person A having nothing in their pockets, but 200 witnesses around them proclaiming loudly that person A has $500. If person A says "I'm giving all my $500 to person B" in front of all these witnesses, then the witnesses will inform every new arrival that person B is now worth $500, not person A. If someone claims otherwise, the other witnesses will notice this and correct the failing witness. This is how the [blockchain] works.

These transactions of value are signed with the private key which only the owner of an address has. There are three main ways to get your wallet (so, a public address + a private key):

- generate your key and address with the help of a _blockchain client_ (the software tool of the blockchain the token of which interests you - i.e. with Bitcoin that could be Electrum, with Ethereum it could be Metamask, MyEtherWallet, or Mist).
- use a hardware solution like the [Ledger Nano S][ledger] - a USB-stick-like device which saves your private key for you and can contain a multitude of addresses for several different cryptocurrencies
- open an account on a cryptocurrency exchange site

Opening an account at an exchange is by far the easiest method, but due to the fact that these exchanges mostly keep the private key of the generated wallet to themselves, you're never really in control of the wallet. If the exchange disappears or gets hacked, so do your funds - like it happened with Mt.Gox and Bitfinex. It's highly recommended you move your tokens off of an exchange and into a privately controlled wallet as soon as possible after obtaining them. 

To find out how to get started with each individual cryptocurrency and how to receive and send tokens, see [here][wallet].

[cc]: https://bitfalls.com/en/2017/08/20/cryptocurrency/
[blockchain]: https://bitfalls.com/en/2017/08/20/blockchain-explained-blockchain-works/
[ledger]: https://bitfalls.com/en/shop/ledger-nano-s-bitfalls/
[wallet]: https://bitfalls.com/en/2017/09/01/send-receive-bitcoin/
