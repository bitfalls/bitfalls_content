Rudarenje Bitcoina i ostalih kriptovaluta popularno je već neko vrijeme. Nije lako početi s rudarenjem jer je potrebna velika početna investicija i puno struje. Za razliku od kriptovaluta koje se rudare jer koriste [Proof of Work (PoW)](https://bitfalls.com/hr/glossary/#proof-of-work), kriptovalute bazirane na [Proof of Stake (PoS)](https://bitfalls.com/hr/glossary/#proof-of-stake) sustavu koriste algoritme koje ne zahtijevaju snagu procesora ili grafičke kartice. Valjanost blokova provjeravaju svi koji posjeduju tu valutu, a odabir se vrši nasumično za svaki blok. U prethodnom članku možete pročitati razlike između [konsenzus protokola](https://bitfalls.com/hr/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/).

Generalno pravilo kod PoS je da što više kriptovalute posjeduješ, više značiš. Skoro svaka kriptovaluta ima različit sustav za nagrađivanje pa savjetujemo da istražite više za svaku prije početka. Na primjer, STRAT tokeni - o kojem ćemo pisati u ovom članku - se izdaju brzinom od 1 token po bloku (svakih 60 sekundi), dok se PIVX tokeni izdaju po 5 tokena po bloku, ali se raspoređuju u 3 dijela!

U ovom članku objašnjeno je kako napraviti staking uređaj koristeći jeftini Single-Board Computer (SBC) i kako početi ovjeravati transakcije Stratisa dokazivanjem uloga.

_Želite kupiti Stratis ili neku drugu PoS valutu da započnete? [Javite nam se!](https://bitfalls.com/how-to-buy-cryptocurrency/)_

## Korak 1: Nabava opreme

*Ako već posjedujete Raspberry Pi s internet pristupim i upoznati ste s njim, možete prijeći na sljedeći korak ili 5. korak za instalaciju novčanika.*

Za izgradnju uređaja potreban je sljedeći hardware:

 * Raspberry Pi. U ovom članku korištena je verzija Zero, ali neki novčanici (npr. QTUM) traže više memorije pa je moguće uzeti i Raspberry Pi 3 kako bi osigurali rad sa svim kriptovalutama. Cijena, ovisna o modelu: 35-230kn.
 * Raspberry Pi adapteri. Kako  bi spojili monitor potreban je "Ž/M mini HDMI u HDMI" i "micro-B USB u USB" za spojiti tipkovnicu/miš. Cijena oko 6kn za svaki. *Preporučujemo da uzmete [set adaptera](https://shop.pimoroni.com/products/zero-adaptor-kit).*
 * Ethernet pločica ENC28J60 + GPIO modul + jumper žica ili samo [Micro USB u Ethernet](https://www.aliexpress.com/snapshot/0.html?orderId=87405596761683&productId=32610315110). Cijena: 25kn *Mi smo koristili Ethernet pločicu, ali je preporučljivo uzeti takav USB adapter ako ne možete lemiti te nećete trebati USB hub za dodatne USB ulaze.*
 * MicroSD kartica s barem 8GB memorije i barem UHS-1 klase. *Moguće da jeftinije kartice neće biti kompatibilnije s uređajem pa ako imate sumnje provjerite [vodič za kupnju SD kartica](http://elinux.org/RPi_SD_cards). Cijena: 95-160kn.
 * Čitač/pisač MicroSD ili SD kartica (ako koristite veliki MicroSD adapter), ali većina laptopa ili računala ih već ima pa provjerite svoj.
 * Ako imate USB adapter s jednim ulazom, razmislite da nabavite USB hub kako bi spojili tipkovnicu i miš u isto vrijeme. Ako ste naručili navodno spomenuti USB adapter s više ulaza i Ethernetom, onda nije potreban USB hub.

Opremu je lako za nabaviti i može se naći u većini lokalnih ili internet dućana. Minimalni budžet je oko 160kn. Korištene materijale možete vidjeti u slici ispod.

![Raspberry Pi Zero kit](../images/rpi_kit.jpg)

## Step 2: Raspbian instalacija

Operacijski sustav za Raspberry Pi, Raspbian, možete preuzeti sa [Raspberry službene stranice](https://www.raspberrypi.org/downloads/raspbian/). *Napomena: ako imate stariju verziju Raspberry uređaja, zadnja verzija možda neće raditi te je potrebno skinuti stariju kao što je Jessie. Ako se Raspberry ne boota, to je vjerojatno izvor problema.*

Kako bi instalirati Raspbian na MicroSD karticu (spojenu u računalo) možete pratiti službeni instalacijski vodič, a mi savjetujemo da jednostavno instalirate na karticu preuzeti ZIP dokument koristeći [Etcher](https://etcher.io/).

Nakon toga, stavite MicroSD karticu u Raspberry (PWR ulaz) i spojite ga u struju koristeći klasični Micro-USB punjač za mobitele.

Možete pogledati kako smo mi spojili Raspberry na slici ispod.

![Raspberry Pi staking setup](../images/setup.jpg)

## Step 3: Raspbian konfiguracija

Prvo je potrebno instalirati posljednje nadogradnje operacijskog sustava. Otvorite Terminal (CTRL+ALT+T) i upišite naredbe:

```bash
sudo apt update; sudo apt upgrade -y
```

Kako bi mogli alocirati više memorije, potrebno je povećati veličinu swap prostora. Zbog toga, otvorite konfiguracijsku datoteku sa: `sudo nano /etc/dphys-swapfile`. Izmijenite liniju koja sadržava tekst `CONF_SWAPSIZE` i promijenite vrijednost u 512 ili 1024. Spremite izmjene (CTRL+O, ENTER, CTRL+X).

Zatim resetirajte servis: 

```bash
sudo service dphys-swapfile restart
```

### Step 3.1: Uključite Ethernet (ako je korištena ENC28J60 pločica):

Za pristup internetu koristili smo Ethernet pločicu koja se mora omogućiti na uređaju. Potrebno je napraviti sljedeće korake:

* otvoriti Raspbian konfiguraciju izvršavajući naredbu u Terminalu: `sudo raspi-config`
* otiđite na Interfaces
* otvorite SPI i odaberite yes
* izađite iz konfiguracije
* izvršite u Terminalu: `sudo nano /boot/config.txt`
* upišite `dtoverlay=enc28j60` u datoteku i spremite
* izvršite naredbu `reboot` za ponovno pokretanje

## Step 4: Spajanje s Raspberry uređajem

Zbog lakšeg rukovanja odobriti ćemo udaljeni pristup (s osobnog računala) uređaju preko *ssh*. Izvršite naredbe:

```bash
sudo service ssh start
```

To bi trebalo biti privremeno (do ponovnog pokretanja) pa provjerite [druge metode osposobljavanja ssh pristupa](https://www.raspberrypi.org/documentation/remote-access/ssh/)  ako želite držati to uvijek upaljeno. U tom slučaju, **bitno** je promijeniti početnu lozinku koristeći naredbu `passwd`.

Sada bi trebali pomoći spojiti se sa svog računala preko [PuTTY](http://www.putty.org/) programa ili na UNIX-u u terminalu izvršavajući:

```bash
ssh pi@raspberrypi.local
```

... koristeći lozinku `raspberry`.


## Step 5: Preuzimanje Stratis novčanika

Pratite idućih par koraka kako bi instalirati novčanik s grafičkim sučeljem. Ako ste iskusniji u terminalu i preferirate koristiti Raspberry bez monitora i grafičkog sučelja, pogledajte službeni vodič za prevođenje [stratisd](https://olcko.gitbooks.io/staking-stratis-on-a-raspberry-pi/content/compile-stratisd.html).

### Step 5.1: Instalacija potrebnih sistemskih datoteka

Upišite u terminal: 

```bash
sudo apt-get install -f build-essential autoconf automake git g++ libtool make unzip wget qt5-default qt5-qmake qtbase5-dev qtbase5-dev-tools libqt5webkit5 libqt5webkit5-dev libqt5qml5 libqt5quickwidgets5 qml-module-qt-labs-settings qtdeclarative5-dev-tools qttools5-dev-tools libboost-all-dev libssl-dev libdb++-dev libdb5.3++-dev libdb5.3-dev libminiupnpc-dev libqrencode-dev libprotobuf-dev
```

### Step 5.2: Preuzmite izvorni kod
Izvršite:

```bash
git clone https://github.com/stratisproject/stratisX.git
```

### Step 5.3: Prevođenje novčanika

Izvršite:

```bash
cd stratisX;qmake;make;strip stratis-qt
```

### Step 5.4: Pokretanje novčanika

Dok ste još uvijek u `stratisX` direktoriju, izvršite:

```bash
sudo cp stratis-qt /usr/local/bin
```

Sada možete pokrenuti Stratis novčanik iz bilo kojeg direktorija upisujući samo `stratis-qt` u terminal.

Kako bi stvorili kraticu na početnom ekranu, izvršite: 

`cp stratis-qt ~/Desktop`

## Step 6: Postavljanje novčanika

Ovaj korak bi trebao biti već poznat svima koji su prethodno koristili bilo kakav novčanik. Prvo je potrebno sinkronizirati mrežu prije nego što je moguće početi s radom. Sinkroniziranje će potrajati par sati.

### Step 6.1: Enkripcija novčanika

Novčanik mora biti enkriptiran. To možete napraviti birajući `Settings -> Encrypt wallet` gdje zatim upisujete svoju lozinku.

### Step 6.2: Otključavanje novčanika

Novčanik je potrebno otključati birajući `Settings -> Unlock wallet` i upisujući prethodno postavljenu lozinku.

### Step 6.3 Prebacivanje STRAT tokena

Svoje STRAT tokene trebate prebaciti u svoj novi novčanik. Adresu, kojoj ćete poslati tokene, preuzmite iz `Receive` kartice.

Nakon što ste prebacili tokene u novčanik, potrebno je ostaviti sve upaljeno da radi. Ne zaboravite da je za nagrađivanje najbolje kad novčanik radi 24/7.

![Staking STRAT screenshot](../images/wallet-staking.jpg)

### Preporučljive stvari za napraviti

Ne zaboravite napraviti sigurnosnu kopiju ako ste stvorili novi novčanik ili možete uvesti postojeći novčanik koristeći privatni ključ. U oba slučaja, možete provjeriti službene [upute za novčanik](http://stratisplatform.com/files/Stratis_Wallet-Instructions_v2.0.0.pdf).

Također, nemojte zaboraviti nadograđivati verzije novčanika. Proces nadogradnje je sličan instalaciji, ali morate povući novu verziju. Možete jednostavno pratiti službeni [vodič za nadogradnju](https://olcko.gitbooks.io/staking-stratis-on-a-raspberry-pi/content/updating-stratis.html).

## Dodatan savjet za veću zaradu

Kako bi maksimizirali svoju zaradu potrebno je spojiti sve transakcije u jedan blok. To je moguće napraviti, bez gubljenja težine u mreži, koristeći značajku novčanika *Coin control*.

Da biste to učinili, slijedite sljedeće korake:

1. U novčaniku, otvorite `Settings -> Options -> Display` i označite `Display coin control features`.
2. Kopirajte svoju adresu (iz `Receive` kartice).
3. Kliknite na `Send coins`, zatim `Inputs` i odaberite sve coine.
4. Pošaljite 1 coin (ili bilo koji iznos) na svoju adresu.

Otvorite ponovno karticu `Inputs` kako bi se uvjerili da je sve stvarno spojeno. Nakon što primite svoje nagrade, ponovite ove korake.

## Zaključak

Nagrade za dokazivanje uloga nisu velike (a nisu ni investicije ako već želite posjedovati kriptovalutu) tako da ne očekujete velike zarade. 
The money benefits of staking are not big (though the investment isn't either) so don't expect a big profit. Međutim, još uvijek je bolje od bankovnih štednji, a podržavate i mrežu kriptovalute. Za predviđanje zarade možete koristiti [STRAT calculator](https://stratispool.com/). 

Postoje i druge kriptovalute koje koriste PoS kao što su: QTUM, PIVX, Signatum, Navcoin itd. - mogu se pronaći na [Crypto compare listi](https://www.cryptocompare.com/coins/#/btc) kada odaberete PoS  u koloni "proof type". Neke nove kriptovalute, poput Aerium, u svojoj ranoj fazi daju puno veće nagrade kao poticaj za rane korisnike i developere. Nagrade se mogu dobiti i za ostale kriptovalute koje koriste dPoS konsenzus kao ARK ili LISK, ali nagrada se dobiva od delegata za koje se glasa i zbog toga su stvoreni poolovi glasača.

Sve više kriptovaluta prelazi na PoS kao [Ethereum](https://bitfalls.com/2017/10/02/ethereums-development-roadmap-metropolis/) pa će biti zanimljivo vidjeti što će se sve događati. Ne zaboravite da možda ne bi trebali držati kriptovalutu u koju ne vjetujete samo zbog nagrada jer možete završiti imajući bezvrijedne kriptovalute. Međutim, ako planirate [hodl](https://bitfalls.com/glossary/#hodl) neku kripto valutu, onda zašto ne? 

Javite nam svoja iskustva!