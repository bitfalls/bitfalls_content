A DAO is a "Decentralized Autonomous Organization". This sounds daunting, but it's really just a multi-user application on the blockchain which has no leader, but is controlled by its members. The control is typically exercised through voting on proposals, and votes are weighed by a member's skin in the game (collateral, participation, reputation, etc.)

As we were building [Blockada DAO](https://blockada.io/dao), we wanted a way to make sure all our members were humans, not just different Ethereum addresses owned by the same person. This problem is known as Sybil resistance - resistance to one person posing as many. After all, our DAO is used to fund meetups and events by means of voting for grants - this would be much easier to manipulate without some kind of identity constraint.

[MolochDAO](https://molochdao.org), a popular funding DAO for [Ethereum 2.0](https://our.status.im/tag/two-point-oh) projects, gets around this problem by:

a) requiring a non-trivial amount of money staked (collateral) before you can add someone to the DAO and,

b) preventing people from applying to join the DAO and instead requiring existing members to recommend non-members as new joinees.

This is very good when you're looking to have a small(er) DAO, but when your members might not have the capital to fund their applications, or when you're aiming to have a big DAO that covers lots of ground (global events and meetups!), then it becomes unfeasible.

So I decided to make joining Blockada DAO much easier - almost zero barriers - but outsource the Sybil resistance.

## HumanityDAO

A while back, a new DAO made a splash in the crypto community: [HumanityDAO](https://humanitydao.org). It required people to use Twitter to verify their identity and let existing members vote on the "humanity" of these applicants.

Mired in controversy at the start (some people decided to block and kick a lot of applicants), it has since recovered and is currently a working but relatively pointless registry of somewhat real people on the blockchain.

Privacy implications aside (hopefully everyone used clean addresses to register!), HumanityDAO is exactly the kind of registry we can use as a whitelist for joinees.

Rather than re-invent the wheel and create another registry in BlockadaDAO, I opted for a D2D method (Dao 2 Dao) and decided to read the "humans" straight out of HumanityDAO before letting them into Blockada. Put simply: in order to apply to be a member of BlockadaDAO, you need to be _a human_. So how can _you_ do this for your project? It's simple - all it takes is one function modifier (plus a line of code or two) and you're good to go. Here's the final code for an example smart contract. We'll explain it below.

```solidity
pragma solidity ^0.5.2;

contract HumanityDAO {
    function isHuman(address who) public view returns (bool) {}
}

contract onlyHumanCheck {

    uint256 public counter;
    HumanityDAO dao;

    constructor() public {
        dao = HumanityDAO(0x4EE46dc4962C2c2F6bcd4C098a0E2b28f66A5E90);
    }

    function increaseCounter() public onlyHuman {
        counter = counter + 1;
    }

    modifier onlyHuman() {
        require(dao.isHuman(msg.sender), "Only callable by a human!");
        _;
    }

}
```

## How it works

We know from experience that HumanityDAO's contract is at address `0x4EE46dc4962C2c2F6bcd4C098a0E2b28f66A5E90` (experience being any of: inspecting transactions when joining, simply searching Etherscan or Github, asking the founders, etc.), and if we take a look at it in Etherscan, we can see that not only does it have the `isHuman` method that we need, but the source code is right there for us to copy.

![Etherscan overview](https://bitfalls.com/wp-content/uploads/2018/10/01-4.png)

![Etherscan code](https://bitfalls.com/wp-content/uploads/2018/10/02-2.png)

In the example above, our contract is `onlyHumanCheck`. The other contract at the top, `HumanityDAO`, is not the real HumanityDAO - it's an abstract part of it that we need in order to be able to call the `isHuman` function on it. Abstract functions don't have to contain the function body. They do need to match the signature (a.k.a. shape, inputs and outputs) of however they are being used (i.e. pass in `address`, get a `bool`) and need to match the implementation in the original contract otherwise they won't work. So the easiest way to find the method you need is inspecting the contract you want to interact with, as we did in the screenshots above.

Then, we define our HumanityDAO stub contract:

```solidity
contract HumanityDAO {
    function isHuman(address who) public view returns (bool) {}
}
```

The `isHuman` function will now be available to us in our contract as long as we have a `HumanityDAO` contract instance. But how do we get that? With this part:

```solidity
    HumanityDAO dao;

    constructor() public {
        dao = HumanityDAO(0x4EE46dc4962C2c2F6bcd4C098a0E2b28f66A5E90);
    }
```

We define a new variable called `dao` of the `HumanityDAO` type. This just means "we'll store HumanityDAO into this variable".

Then, in the constructor of our contract (i.e. when the function that's auto-called when the contract is created on the blockchain) we set the value of `dao` to `HumanityDAO(0x4EE46dc4962C2c2F6bcd4C098a0E2b28f66A5E90)`

We call this a new _instance_ of `HumanityDAO`. HumanityDAO is just a list of functions, but when we "feed" it with an address like we did above, it has something to use those functions on. So in this case, we set our list of functions (a single `isHuman`) to work on the deployed, live version of HumanityDAO which sits at that specific address. This gives us the power to call `isHuman` on the live registry of people.

_Note: when using a [testnet](https://bitfalls.com/2018/05/31/what-is-an-ethereum-testnet-and-how-is-it-used/), the HumanityDAO address would be different. This is all happening on the mainnet._

We then write our modifier.

```solidity
    modifier onlyHuman() {
        require(dao.isHuman(msg.sender), "Only callable by a human!");
        _;
    }
```

Modifiers are used to modify functions without copy-pasting code around. They make the DRY principle easier easier to follow (Don't Repeat Yourself). The first `require` line is a condition: require that the `msg.sender` (i.e. the issuer of the transaction) returns `true` from the `isHuman` function on the `dao` variable. In other words, make sure the sender of the transaction is human. If this condition is not met, the error message "Only callable by a human!" is returned. The line `_;` tells solidity "copy the rest of the function in this place here". So modifiers add lines of code into existing functions without you having to move code around. Now let's use it.

```solidity
    function increaseCounter() public onlyHuman {
        counter = counter + 1;
    }
```

With this in place, only those who are humans in the HumanityDAO will be able to increase this smart contract's counter variable. Go ahead and try it, the contract is deployed on address `0xaf9887a77dd21d1c6e1574b26f67ea6357596b88`.

## Trying it out

The easiest way to try this out is to use this UI around the contract, made with OneClickDapp: [https://oneclickdapp.com/origin-smart/](https://oneclickdapp.com/origin-smart/)

If you try clicking the Sign & Submit button while logged into a MetaMask address that is NOT a human in the HumanityDAO, you get a warning before even trying to submit:

![Impossible Execution Warning](https://bitfalls.com/wp-content/uploads/2018/10/04-1.png)

But if you try it with a Human address, it's all good.

![All good with the transaction](https://bitfalls.com/wp-content/uploads/2018/10/05-1.png)

## Conclusion

Ethereum is more than programmable money. It's financial Lego Technics - intricate components you can tie together to make some truly epic robots work. Cross-contract communication of this type is becoming more and more common, and I encourage you to reuse someone else's work when building your own. Reuse tokens, read from external contracts, use the blockchain for what it was meant - a global computer - and instead of polluting the landscape with yet another token or token curated registry, you'll have injected new value into existing components. Enjoy!
