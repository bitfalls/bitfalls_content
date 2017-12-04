Parity, the [Ethereum][eth] client and wallet, announced today that it has discovered a [critical security issue](https://paritytech.io/blog/security-alert.html) in its implementation of multi-sig addresses.

**No funds have been lost - they just cannot be moved from a Parity multi-sig wallet - all such wallets are temporarily locked**

Multi-sig addresses are wallets which require several private keys to sign a transaction, not just one. The last multi-sig security issue happened in [July 2017](https://paritytech.io/blog/security-alert-high-2.html) and today's issue is directly caused by the fix for the last one. The previous leak allowed a nefarious actor to take control of a multi-sig wallet by calling a special function which would transfer ownership. That bug has been fixed, but the code for the fix has another bug and is abstract enough to apply to all wallets using that fix.

Thus, a bug triggered on this fix happened today and caused it to replicate on all multi-sig Parity wallets, rendering them unusable and locked in place. We must say again: **all funds are safe**, they are merely locked. Remember, your currency is always [on the blockchain][miscon], never on the wallet or device itself!

We're awaiting further developments.

[miscon]: https://bitfalls.com/hr/2017/10/21/2-common-misconceptions-hardware-wallets/
[eth]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/