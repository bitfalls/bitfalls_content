In this short guide we'll go through the steps required for getting started with the popular [cryptocurrency][cc] Litecoin (LTC): how to obtain it, store it, and send it.

## Background

Litecoin is an early clone (or [fork][forks]) of Bitcoin. Charlie Lee, the author of Litecoin, was a Google engineer and until recently a programmer for [Coinbase][cb]. He created Litecoin in 2011 when he decided to look "under the hood" of Bitcoin and learn what the [blockchain][bc] is all about. He realized that it was quite easy to make something better than Bitcoin offers even today, and thus decided to reduce the time required to [mine][mining] a [block] from 10 minutes to 2.5 minutes, and increased the theoretical maximum supply of LTC to 84 million (from Bitcoin's [theoretical maximum][finite] of 21 million).

The mining algorithm was also changed to one which requires more RAM. Until recently, this made it harder to mine on [ASIC][l3] machines - computers designed to perform just this one function very well, thus giving an unfair advantage to all who can obtain them.

When Coinbase added Litecoin as an entry currency to its offers, LTC's popularity exploded, turning it into a viable long term threat to both Bitcoin and Bitcoin Cash.

## How to get Litecoin?

1. [Bitfalls][buycc]: Contact us if you'd like to buy some. No verification is needed, and transaction size has no upper limit (within reason). We accept direct bank transfer in EUR or USD, or direct payments to our HRK account, or even PayPal (starting at a maximum of $100 per day). After the purchase, we send the receipt, and the LTC will arrive straight to the address you provided when accepting the trade. We never hold your money, unless there's some technical difficulties or when you buy our [portfolio management][folio] service.

1. [Coinbase][cb] - one of the first and oldest of cryptocurrency exchanges, currently supports purchasing BTC, Eth and LTC directly with your credit or debit card. Requires a quite rigorous KYC and verification process. Has relatively high fees but the best user experience - easiest to use. After buying LTC on Coinbase, store it somewhere safe (see below).

1. [Bitstamp][bitstamp] is similar to Coinbase, but supports more deposit methods and more currencies. Their fees can also be rather expensive. Bitstamp is easy to use and it's easy and cheap to withdraw from the platform to one's own address. They also have a strict verification process.

1. Any other exchange. Most exchanges don't support entering the market with LTC and will instead need you to enter by buying Eth or BTC. This entry crypto is then sent to an exchange like Bittrex, Bitstamp, Binance, etc. where you can further trade it for LTC.

After getting some LTC, it's important to safely store it. Remember: a cryptocurrency you keep in your exchange is never safe. It's only secure if the private key of your [wallet] is in your possession and your possession alone.

## Storing Litecoin

There are several ways to safely store Litecoin.

### Paper Wallet

As described in [this post][paper], a paper wallet is actually a really good option. Generate an address on one of the secure sites like https://liteaddress.org, print your "wallet" and hide it. The public part of the address (marked by the green SHARE word) can be used in public. That part is used when you want to check balance or send money TO the wallet.

![A Litecoin wallet](https://bitfalls.com/wp-content/uploads/2017/12/01.png)

Send your LTC from an exchange TO this green / left code. If you bought some [from us][buycc], this part will be handled for you - just send us the left code with your order (the part starting with LczA...).

After having sent it to this address, your LTC is as safe as the red part of the paper wallet is - keep that code secret, and your LTC is safe. After printing, wipe the file from your computer if you saved it somewhere.

### Hardware wallet

The safest option is definitely a [hardware wallet][hw]. We definitely recommend reading the article to learn about the advantages it offers.

Here's how to set the [Ledger Nano S][ledger] up to receive Litecoin.

- If you haven't done so already, activate your Nano S by connecting it to the computer via the USB port. If this is the first time it was plugged in, it'll spit out 24 words which you **must** write onto the paper that comes with the Ledger and store them safely. This is your Recovery Phrase, and is used to restore funds if you lose your Ledger or it gets stolen.

- After having set it up with a PIN, the Litecoin app needs to be installed onto the device. Download the official [App Manager][manager] which will let you update the device and install new wallets. Connect the Ledger to the computer, enter the PIN, run the Ledger Manager app you installed, and install the Litecoin app from the list. If offered, update the device's firmware, too.

  ![Ledger Manager](https://bitfalls.com/wp-content/uploads/2017/12/Screenshot-2017-12-13-16.34.22.png)
  
- After having installed the Litecoin app onto the device, install the [Litecoin wallet client][ltcapp] onto your computer.

- Navigate to the Litecoin wallet on the device itself, and open it. Then open the wallet app on the computer. If it asks you about Legacy / Segwit, pick Segwit.

  ![Segwit](https://bitfalls.com/wp-content/uploads/2017/12/03-1.png)
  
  - The application that's open on the computer should open the screen presenting the information about your account, including the "Receive" tab which lets you see the address to which you send LTC if you want to deposit it onto the Ledger. Use this address to withdraw from an exchange you bought LTC on (again, if you bought from us, we'll do this for you).

  ![Wallet otvoren](https://bitfalls.com/wp-content/uploads/2017/12/04.png)
  
  It's important to be aware of common misconceptions about hardware wallets - the money isn't actually ON the wallets. More info [here][miscon].
  
**Note**: At the moment of this writing, Coinbase still hasn't implemented Segwit so a Litecoin address starting with an M might bother them (you'll know because their interface will warn you). To avoid this, instead of generating an L address (Legacy), turn your M address into a `3` address with [this tool](https://litecoin-project.github.io/p2sh-convert/) - simply enter the M address from your Ledger into this field and click convert.
  
  ![M to 3](https://bitfalls.com/wp-content/uploads/2017/12/05.png)
  
  Then send the money to the `3EPJ...` address fearlessly - both lead to the same destination: your Ledger.
  
### Other storage ideas
  
It's possible to keep your LTC on an exchange, but it's highly discouraged. There isn't a single exchange that's too big to disappear overnight. Over 35 have disappeared so far, and one such overnight evasion act was also Mt. Gox - an exchange which processed over 80% of all BTC transactions at its peak.
  
Another good hardware wallet is [Trezor] - you might want to look into that if Ledger isn't available in your area or if you prefer a different look, feel, or functionality.

## Sending Litecoin

### Ledger

In regards to sending, Ledger is the simpler option. Instead of Receive, select Send. After entering the address and the amount, confirm the transaction - once in the interface, and once on the device itself when asked.

![Slanje LTCa preko Ledgera](https://bitfalls.com/wp-content/uploads/2017/12/06.png)

The window will also let you select the transaction speed (faster is more expensive) and see the estimation of expenses.

### Paper Wallet

Sending from a paper wallet is a little harder. As we explained in the [introduction to sending and receiving Bitcoin][startbtc], there are two methods to unlock a paper wallet: import and sweep.

Import means the private key is loaded into the app and the app then uses this private key to sign transactions. Sweep means the app not only loads the key but also sends the whole amount to a new address as generated by the app, thereby making the old key useless. The latter is safer but more expensive (requires a transaction to be made) and slower.

There are several wallets which support private key imports, the most popular of which are:

- [Jaxx.io](http://jaxx.io)
- [Electrum-LTC](https://electrum-ltc.org/)

Install either of them onto your operating system / device, scan the QR code of your private key (or manually type it in), and your funds will be ready for sending. If you performed an import instead of a sweep, store the paper somewhere safe afterwards or better yet - destroy it. Here's the full procedure of sending from a paper wallet using Electrum-LTC:

1. If this is your first time running it, choose auto-connect on the first screen
2. The second screen will ask you for the name of the file in which to store your [wallet]. Leave it at the default setting, or change the location if you wish. Remember to back up this file later - losing the file means losing the wallet.
3. Pick "Standard Wallet" on the next screen.
4. Pick "Use Public or Private Keys" on the next screen to get to the option to load your private key. Enter it by scanning the QR code with your webcam, pasting, or manually typing it in.

![Import key](https://bitfalls.com/wp-content/uploads/2017/12/07.png)

After importing the private key, the application will ask you for a password with which to additionally secure your wallet. This is optional but recommended.

Finally, you'll be able to see the imported address' balance.

![LTC history](https://bitfalls.com/wp-content/uploads/2017/12/08.png)

To send the LTC, open the "Send" tab, enter the destination address and amount, pick an optional description and set the transaction speed, and click Send again. Your LTC is on the way.

## Conclusion

Litecoin is a relatively cheap cryptocurrency with a bright future - not because of the technology, but because of the "digital silver" that it's known as, complementing Bitcoin as the "digital gold". Because of this brand recognition and cheaper and faster transactions, LTC could seriously threaten Bitcoin and Bitcoin Cash in the long term - maybe not in monetary value, but definitely as a means of transacting.

[cc]: https://bitfalls.com/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[forks]: https://bitfalls.com/2017/11/07/segwit2x-fork-can-expect-whos-behind/
[block]: https://bitfalls.com/glossary/#block
[finite]: https://bitfalls.com/2017/09/17/bitcoin-finite-just-myth/
[mining]: https://bitfalls.com/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[l3]: https://shop.bitmain.com/antminer_l3_litecoin_asic_scrypt_miner.htm
[cb]: https://www.coinbase.com/join/542b0423734ab06764000001
[buycc]: https://bitfalls.com/how-to-buy-cryptocurrency/
[eth]: https://bitfalls.com/2017/09/19/what-ethereum-compare-to-bitcoin/
[folio]: https://bitfalls.com/portfolio-management/
[bitstamp]: https://bitstamp.net
[wallet]: https://bitfalls.com/2017/08/31/what-cryptocurrency-wallet/
[paper]: https://bitfalls.com/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[trezor]: https://trezor.io/
[hw]: https://bitfalls.com/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[ledger]: https://bitfalls.com/shop/ledger-nano-s-bitfalls-3/
[manager]: https://www.ledgerwallet.com/apps/manager
[miscon]: https://bitfalls.com/2017/10/21/2-common-misconceptions-hardware-wallets/
[ltcapp]: https://chrome.google.com/webstore/detail/ledger-wallet-bitcoin/kkdpmhnladdopljabkgpacgpliggeeaf
[startbtc]: https://bitfalls.com/2017/09/01/send-receive-bitcoin/