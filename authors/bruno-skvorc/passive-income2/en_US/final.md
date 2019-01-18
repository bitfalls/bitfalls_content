In the [previous post]() we learned how to create a CDP and generate the stablecoin DAI from our ether. This is useful if you have a lot of ether lying around but would still like to be able to speculate with its value without actually selling it. However, what if you'd like a less risky way of growing your fortune? What if you could park the DAI somewhere and collect interest on it? Better yet, what if that interest was... compound interest?

In this post we'll learn how to use the [Compound Finance](https://compound.finance) platform to loan out our DAI and gather interest on these loans - automatically and safely.

## Compound Finance

Compound Finance is a collection of smart contracts and the user interfaces to use them which let you lend out or borrow cryptocurrency in exchange for collateral. Much like the [previously discussed]() MakerDAO CDP, you put down collateral in one cryptocurrency and get a loan in another. The big difference is that you don't _create_ a currency when taking a loan here - instead, you borrow from an existing supply. The smaller that supply is, the bigger the interest rate.

Let's dive right in and learn how to make our crypto earn us some money.