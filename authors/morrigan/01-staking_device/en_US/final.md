Mining Bitcoin and other cryptocurrencies has been out there for some time now. It's not easy to get into it since big initial investments and a lot of electricity is required. But unlike mining currencies which use the [Proof of Work (PoW)](https://bitfalls.com/glossary/#proof-of-work) system, [Proof of Stake (PoS)](https://bitfalls.com/glossary/#proof-of-stake) based cryptocurrencies have algorithms that don't require CPU/GPU power. Blocks are validated by coin holders who are randomly selected for each block. In a previous article you can read more about the differences between those [consensus protocols](https://bitfalls.com/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/).

The general rule with PoS is that the more coins you have, the higher you’re appreciated. Almost every coin has a different system for staking rewards, so you should research more about each before starting. For example, STRAT tokens - which we'll cover in this post - are issued at a rate of 1 token per block (every 60 seconds), while PIVX are issued at 5 tokens per block but they are distributed into three pieces!

This tutorial shows how to build a staking device using a cheap Single-Board Computer (SBC) and how to start staking Stratis tokens (STRAT) on it.

_Want to buy Stratis or another PoS coin to get started staking? [Let us know!](https://bitfalls.com/how-to-buy-cryptocurrency/)_

## Step 1: Getting the equipment

*If you already own a Raspberry Pi with internet access and you are familiar with it, continue to the next step or Step 5 for wallet installation.*

To build a staking device, you'll need the following hardware:

 * Raspberry Pi. In this tutorial, the Zero version is used but some wallets (i.e. QTUM) require more memory so you can buy the Raspberry Pi 3 to make sure that you can cover staking all coins. Price depending on model: $5-35.
 * Raspberry Pi adaptors. To connect to a monitor we need an "F/M Mini HDMI to HDMI" and "micro-B USB to USB" to connect a keyboard/mouse. Price: $1 each. *It's recommended that you buy an [adaptor kit](https://shop.pimoroni.com/products/zero-adaptor-kit).*
 * Ethernet board ENC28J60 + GPIO module + jumper wires or only [Micro USB to Ethernet](https://www.aliexpress.com/snapshot/0.html?orderId=87405596761683&productId=32610315110). Price: $3.5 *We used the Ethernet board but it's recommended you buy such a USB adapter if you can't solder and you won't need the USB hub because there are also USB inputs.*
 * MicroSD card with at least 8GB space and which is at least UHS-1 class. *It's possible that cheapest ones won't be compatible with RPi but if you have any doubts check this [guide for picking SD cards](http://elinux.org/RPi_SD_cards).* Price: 15-25$.
 * A card reader/writer for MicroSD or SD (if using full size MicroSD adapter) but most laptops or PCs already have it.
 * If you have a USB adaptor with one input, consider getting a USB hub so you can connect a keyboard and mouse at the same time.  
 
The equipment is easy to get and can be found in most local or online shops. The minimum budget is around 25$. In the picture below you can see the materials we used.

![Raspberry Pi Zero kit](../images/rpi_kit.jpg)

## Step 2: Installing Raspbian

You can get the Raspberry operating system, Raspbian, from [Raspbian's offical website](https://www.raspberrypi.org/downloads/raspbian/). *Note: if you have an older version of a Raspberry, the latest version might not work and you may have to download a bit of an older release such as Jessie. If your Raspberry doesn't boot, that could be the issue.*

To install Raspbian on a MicroSD card (inserted in your PC) you can follow the official installation guide for it, but we recommend simply flashing the MicroSD card with a downloaded ZIP archive using [Etcher](https://etcher.io/).

After that, just put the MicroSD card into Raspberry and give the Raspberry some power using a classical Micro-USB mobile phone charger (see PWR input on board).

You can see our setup in the image below.

![Raspberry Pi staking setup](../images/setup.jpg)

## Step 3: Configure Raspbian

The latest operating system updates should be installed first. On Raspberry, open the Terminal (CTRL+ALT+T) and run: 

```bash
sudo apt update; sudo apt upgrade -y
```

To be able to allocate more memory, swap size must be increased by editing the swap configuration file. To change the swap space, open the file by entering: `sudo nano /etc/dphys-swapfile`. Modify the line containing `CONF_SWAPSIZE` and set it to 512 or 1024 and save the file (CTRL+O, ENTER, CTRL+X).

Then restart the service: 

```bash
sudo service dphys-swapfile restart
```

### Step 3.1: Enable Ethernet (if ENC28J60 board is used):

We've used the Ethernet board for Internet access so we need to enable it. Follow the next steps:

* open Raspbian configuration by running: `sudo raspi-config`
* navigate to Interfaces
* open SPI and select yes to enable it
* exit configuration
* run `sudo nano /boot/config.txt`
* write `dtoverlay=enc28j60` in file and save it
* run `reboot` for restart

## Step 4: Connect to your Raspberry

To be able to remotely access the device we need to enable the ssh service. On Raspberry run:

```bash
sudo service ssh start
```

This should only be temporary (until reboot) so check [other methods](https://www.raspberrypi.org/documentation/remote-access/ssh/) if you want to keep it opened. It is **important** to change your default login credentials using the command `passwd`.

Now you should be able to connect from your PC by running:

```bash
ssh pi@raspberrypi.local
```

... using the password `raspberry`.


## Step 5: Download Stratis wallet

Follow the next few steps to install the core wallet with a GUI. If you are more experienced and prefer accessing your Raspberry without using a monitor and GUI, check the official guide to compile [stratisd](https://olcko.gitbooks.io/staking-stratis-on-a-raspberry-pi/content/compile-stratisd.html).

### Step 5.1: Install required system files

Run: 

```bash
sudo apt-get install -f build-essential autoconf automake git g++ libtool make unzip wget qt5-default qt5-qmake qtbase5-dev qtbase5-dev-tools libqt5webkit5 libqt5webkit5-dev libqt5qml5 libqt5quickwidgets5 qml-module-qt-labs-settings qtdeclarative5-dev-tools qttools5-dev-tools libboost-all-dev libssl-dev libdb++-dev libdb5.3++-dev libdb5.3-dev libminiupnpc-dev libqrencode-dev libprotobuf-dev
```

### Step 5.2: Download source files
Run:

```bash
git clone https://github.com/stratisproject/stratisX.git
```

### Step 5.3: Compile wallet

Run:

```bash
cd stratisX;qmake;make;strip stratis-qt
```

### Step 5.4: Running Stratis wallet

While you are still in `stratisX` directory run:

```bash
sudo cp stratis-qt /usr/local/bin
```

Now you are able to start Stratis wallet from any directory if you just type `stratis-qt`.

To place it on your Desktop run: 

`cp stratis-qt ~/Desktop`

## Step 6: Set up wallet

This step should already be familiar to you if you've used any wallets previously. You first need to synchronize the blockchain before you can start staking. That will take a few hours.

### Step 6.1: Encrypt the wallet

The wallet should be protected by encrypting it and it is mandatory here. You can do that by selecting `Settings -> Encrypt wallet` and entering a strong passphrase.

### Step 6.2: Unlock wallet

To start staking you should unlock the wallet by selecting `Settings -> Unlock wallet` and entering the passphrase you previously set.

### Step 6.3 Transferring STRAT

Of course, you need to transfer the STRAT tokens you own to your new wallet. You should already be familiar with transfers so just take the address from the `Receive` tab.

After transferring your coins to the wallet, you just need to leave it running. Don't forget that a staking wallet is at its best when running 24/7.

![Staking STRAT screenshot](../images/wallet-staking.jpg)

### Recommended things to do

Remember to make a backup if this is your new wallet or you can import the existing wallet. In both cases, you can check the official [wallet instructions](http://stratisplatform.com/files/Stratis_Wallet-Instructions_v2.0.0.pdf).

Also, don't forget to keep your wallet version updated. The process of updating is similar to installing but you need to pull the new version. You can follow the official [guide to updating](https://olcko.gitbooks.io/staking-stratis-on-a-raspberry-pi/content/updating-stratis.html).

## Conclusion

The money benefits of staking are not big (though the investment isn't either) so don't expect a big profit. However, it's still better than bank savings and you still support the coin network. To predict rewards from staking Stratis tokens you can use the [STRAT calculator](https://stratispool.com/). 

There are other coins which you can stake like QTUM, PIVX, Signatum, Navcoin and so on - they can be found on the [Crypto compare list](https://www.cryptocompare.com/coins/#/btc) when selecting PoS as proof type. Other coins which have delegated PoS consensus like ARK or LISK can also be staked, but you gain a reward from delegates for which you vote and that's why the pools of voters have been created.

More coins are converting to PoS like [Ethereum](https://bitfalls.com/2017/10/02/ethereums-development-roadmap-metropolis/) so it will be interesting to see what will happen. Don't forget that you shouldn't really start staking a coin in which you don't believe because you could end up holding worthless coins. But if you plan to [hodl](https://bitfalls.com/glossary/#hodl) something then why not? 

Let us know if you try staking any of them!



