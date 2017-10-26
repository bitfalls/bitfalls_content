Mining Bitcoin and other cryptocurrencies has been out there for some time. Getting into it requires big initial investments and a lot of electricity. But unlike mining currencies which use Proof of Work (PoW) system, Proof of Stake (PoS) based cryptocurrencies have algorithms that don't require CPU/GPU power but coin owners who are randomly selected get to validate blocks. You can read more about those consensus protocols in the [previous article](https://bitfalls.com/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/).

General rule with PoS is that the more coins you have, the higher you’re appreciated. Almost each coin has different system for staking rewards so you should research more about each. For example, STRAT tokens are issued at a rate of 1 token per block (every 60 seconds) and PIVX at 5 tokens per block but are distributed into three pieces!

This tutorial shows how to build a staking device using cheap Single-Board Computer (SBC) and how to start staking Stratis token (STRAT) on it.

## Step 1: Getting the equipment and materials
*If you are already own Raspberry Pi with Internet access and you are familiar with it, continue to next step or Step 5 for wallet installation.*

To build a staking device, you'll need the following hardware:
 * Raspberry Pi. In this tutorial Zero version is used but some wallets like QTUM require more memory so you can buy RPi 3 to make sure that you can cover staking all coins). Price depending on model: 5-35$.
 * Raspberry Pi adaptors. To connect to monitor "Mini HDMI to HDMI" and "micro-B USB to USB A female" to connect keyboard/mouse. Price: 1$ each. *It's recommended to buy [adaptor kit](https://shop.pimoroni.com/products/zero-adaptor-kit).*
 * Ethernet board ENC28J60 + GPIO module + jumper wires or [Micro USB to Ethernet](https://www.aliexpress.com/snapshot/0.html?orderId=87405596761683&productId=32610315110). Price: 3.5$ *We used the Ethernet board but it's recommended to buy such USB adapter if you can't solder.*
 * MicroSD card with at least 8GB space and which is at least UHS-1 class. *It's possible that cheapest ones won't be compatible with RPi but if you have any doubts check this [guide for picking SD cards](http://elinux.org/RPi_SD_cards). Price: 15-25$.
 * A card reader/writer for MicroSD or SD (if using full size MicroSD adapter) but most laptops or PCs already have it.
 
The equipment is easy to get and can be found in most local or online shops. Minimum budget is around 25$. In the picture below you can see the materials we used.

![Raspberry Pi Zero kit](../images/rpi_kit.png)

## Step 2: Installing Raspbian operating system

You can get the Raspberry operating system from [Raspbian offical website](https://www.raspberrypi.org/downloads/raspbian/). *Note: if you have an older version of Raspberry, later version might not work and you may have to download bit older release such as Jessie.*

To install Rasbian on MicroSD card on your PC you can follow the official installation guide for it, but we recommend simply flashing the MicroSD card with downloaded ZIP archive using [Etcher](https://etcher.io/).

After that, just put the MicroSD card into Raspberry and give the Raspberry some power using classical Micro-USB mobile phone chargers (see PWR input on board).

## Step 3: Configure Raspbian

Latest operating system updates should be installed first. On Raspberry open Terminal (CTRL+ALT+T) and run commands: 

`sudo apt update; sudo apt upgrade -y`

To be able to allocate more memory swap size must be increased by editing the swap configuration file. To change the swap space open file by running: `sudo nano /etc/dphys-swapfile`. Modify the line containing `CONF_SWAPSIZE` and set it to 512 or 1024 and save the file (CTRL-O, ENTER, CTRL-X).

Then restart service: 

`sudo service dphys-swapfile restart`

### Step 3.1: Enable Ethernet (if ENC28J60 board is used):

We've used Ethernet board for Internet access so we need to enable it. Follow next steps:
* open Raspbian configuration by running: `sudo raspi-config`
* navigate to Interfaces
* open SPI and select yes to enable it
* exit configuration
* run `sudo nano /boot/config.txt`
* write `dtoverlay=enc28j60` in file and save it
* run `reboot` for restart

## Step 4: Connect to your Raspberry

To be able to remote access the device we need to enable ssh service. On Raspberry and run command:

`sudo service ssh start`

But this should only be temporary (until reboot) so you check [other methods](https://www.raspberrypi.org/documentation/remote-access/ssh/) if you want to keep it opened. It is **important** to change your default login credentials using command `passwd`.

Now you should be able to connect from your PC by running:

`ssh pi@raspberrypi.local`

using password `raspberry`.


## Step 5: Download Stratis wallet

Follow next few steps to install core wallet with GUI. If you are more experienced and prefer accessing your Raspberry without using monitor and GUI, check official guide to compile [stratisd](https://olcko.gitbooks.io/staking-stratis-on-a-raspberry-pi/content/compile-stratisd.html).

### Step 5.1: Install required system files
Run: 


`sudo apt-get install -f build-essential autoconf automake git g++ libtool make unzip wget qt5-default qt5-qmake qtbase5-dev qtbase5-dev-tools libqt5webkit5 libqt5webkit5-dev libqt5qml5 libqt5quickwidgets5 qml-module-qt-labs-settings qtdeclarative5-dev-tools qttools5-dev-tools libboost-all-dev libssl-dev libdb++-dev libdb5.3++-dev libdb5.3-dev libminiupnpc-dev libqrencode-dev libprotobuf-dev`

### Step 5.2: Download source files
Run:

`git clone https://github.com/stratisproject/stratisX.git`

### Step 5.3: Compile wallet
Run:

`cd stratisX;qmake;make;strip stratis-qt`

### Step 5.4: Running Stratis wallet

While you are still in `stratisX` directory run:

`sudo cp stratis-qt /usr/local/bin`

Now you are able to start Stratis wallet from any directory if you just type `stratis-qt`.

To place it on Desktop run: 

`cp stratis-qt ~/Desktop`

## Step 6: Setup wallet

This step should already be familiar if you've used any wallets previously. You fist need to synchronize blockchain before you can start staking.

After transfering coins to wallet, you just need to leave it running. Don't forget that a staking wallet is at it's best when running 24/7.

Remember to make backup if this is your new wallet or you can import the existing wallet. In both cases, check the official [guide for wallet import/restore](https://olcko.gitbooks.io/staking-stratis-on-a-raspberry-pi/content/setup-wallet.html#add-an-existing-wallet-from-a-backup).

Also, don't forget to keep your wallet version updates. Process of updating is similar to installing but previously you need to pull new version. When needed, you can follow official [guide for updating](https://olcko.gitbooks.io/staking-stratis-on-a-raspberry-pi/content/updating-stratis.html).

## Conclusion

 Money benefits of staking are not big (but again investment isn't too) so don't expect a big profit. However, it's still better than bank savings and you still support coin network. To predict your Stratis rewards you can use [STRAT calculator](https://stratispool.com/). 

There are other coins which use you can stake like QTUM, PIVX, Signatum, Navcoin and others which can be easily found on [Crypto compare list](https://www.cryptocompare.com/coins/#/btc) when selecting PoS as proof type. Other coins which have dPOS consensus like ARK or LISK can also be staked but you gain reward from delegates for which you vote and that's why the pools of voters are created.

Let us know if you try staking any of them!



