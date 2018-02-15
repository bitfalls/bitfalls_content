Jeste li ikad ćuli za [NEO]? Ne, ne, ne Neo iz Matrixa. Nego [kriptovalutu][crypto] NEO?
Niste jedini. NEO je obično predstavljen kao "Kineski [Ethereum]", no je li to previše pojednostavljeno objašnjenje? Ili je NEO čista "Kineska kopija" Ethereuma?

O ovome članku ćemo objasniti kako NEO funkcionira i njegove razlike u odnosu na Ethereum.

NEO se prvi put pojavio u 2014. godini pod imenom AntShares, a za njegov začetak je odgovoran Da Hongfei.
NEO nije dobio previše pažnje sve do lipnja 2017. godine kad je AntShares preimenovan u NEO.

## NEO vs Ethereum

Primarni cilj Ethereuma je omogučiti gradnju decentraliziranih aplikacija na [blockchainu][blockchain] koje su praktički nezaustavljive.

### Pametna ekonomija 

Primarni cilj NEO-a da stvori nešto što Da Hongfei zove "pametna ekonomija".
Pod to spada digitalizacija identiteta, digitalizacija (tokenizacija) fizičke imovine uparene s "pametnim ugovorima".

Imovina kao osobni automobil, stan ili zemljište postali bi tokeni na NEO platformi koji su pridruženi vašem digitalnom identitetu, ili drugačije rečeno, vi ste vlasnik te imovine.

Ti tokeni se naravno mogu slati na NEO mreži. što bi značilo da u slučaju prodaje npr. osobnog automobila, lako možete taj automobil prodati i u roku par minuta prebaciti vlasništvo na novu osobu, a vi biti plačeni bez ikakve potrebe za kompliciranom i sporom papirologijom, jer je sve  ovjereno na blockchainu.

Dok su ovakve stvari moguće na Ethereumu, najbitnija razlika u ovome je da je NEO građen da podliježe regulaciji države, za razliku od Ethereuma koji je više anarhistički orijentiran.
Za razliku od Ethereuma, NEO se ne može [forkati][fork], što je vrlo bitno za ovakav projekt. (Objasniti ćemo zašto je otporan na forkanje niže u tekstu)

### Digitalni identitet

Digitalnim identitetom se smatraju identificirajuće informacije individualnih osoba, organizacija i ostalih entiteta koje su digitalne. Sustavi koji koriste digitalne identitete baziraju se na PKI (Public Key Infrastructure) X.509 standardu, koje NEO također implementira.
Na ovo možemo gledati kao osobna iskaznica na blockchainu.

### Pametni ugovori

Ethereum za pametne ugovore koristi svoj jezik, Solidity. Programeri koji žele razvijati na Ethereum platformi, moraju naučiti novi programski jezik.

NEO podržava pregršt poznatih programskih jezika koje večina programera zna.
Neki od njih su: C#, Java, Python.

### Ekonomski Model

Ovdje se NEO dosta razlikuje od Ethereum platforme.

Ethereum ima jedan nativan token na mreži s kojim plaćate gas, a to je Ether. Ether je potreban za sve transakcije na mreži, bilo to jednostavno slanje Ethera s jedne adresu na drugu, ili slanje tokena, ili okidanje nekakve funkcije u pametnom ugovoru. 

NEO ima dva nativna tokena:
* NEO
* NeoGas (GAS)

U [izvornom bloku][genesis block] stvoreno je 100 milijuna NEO tokena.
Dok se GAS stvara kroz vrijeme od 22 godine kojeg dobivaju sve adrese na kojoj ima barem 1 NEO. Konačni broj GAS tokena je također 100 milijuna.

Na NEO token možemo gledati kao na dionice neke tvrtke. NEO token predstavlja udio pojedinca na NEO mreži i daje pravo glasa u mreži (npr. glasanje za "knjigovođe", promjena nekakvih parametara u mreži itd.). NEO token je ne djeljiv, znaći da možete slati samo cijeli NEO. Ne možete slati 0.5 NEO, 1.34 NEO, nego 1 NEO, 2 NEO, 43 NEO.

Dok naravno kod Ethereuma se može slati 0.0024 ETH itd., dijeljiv je na 18 decimalnih mjesta.

GAS služi kao gorivo za mrežu, sve operacije na mreži trebaju GAS za izvršavanje. GAS je djeljiv na 8 decimalnih mjesta.

### Konenzusni mehanizam

Ethereum trenutno koristi [Proof of Work][POW], a u planu je prelazak na [Proof of Stake][POS] u bližoj budučnosti.

NEO koristi dBFT (Delegated Byzantine Fault Tolerant)


 



[NEO]: https://neo.org
[crypto]: https://bitfalls.com/hr/glossary/#cryptocurrency
[Ethereum]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
[blockchain]: https://bitfalls.com/hr/glossary/#blockchain
[fork]: https://bitfalls.com/hr/glossary/#fork
[genesis block]: https://bitfalls.com/hr/glossary/#genesis-block
[ICO]: https://bitfalls.com/hr/glossary/#ico
[POW]: https://bitfalls.com/hr/glossary/#proof-of-work
[POS]: https://bitfalls.com/hr/glossary/#proof-of-stake