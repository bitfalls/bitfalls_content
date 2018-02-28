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
Za razliku od Ethereuma, NEO se ne može [forkati][fork], što je vrlo bitno za ovakav projekt. 

NEO ima *finalnost*, 66% knjigovođa se mora odobriti transakciju da se ona stavi u blockchain. Na ovo možemo gledati kao na referendum.

U državi postoji određeni problem, a ljudi moraju glasovati za riješenje tog problema.

Za primjer ćemo uzeti predsjedničke izbore;

U Ethereumu to funkcionira tako da ako večina ljudi glasa za osobu X i ta osoba bude odabrana za predsjenika države, manjina koja je glasala za osobu Y se može odvojiti od te države (lanca) i postaviti osobu Y na mjesto predsjednika u svojoj državi, što nas dovodi do nekakvog zaključka da bi to bila država u državi, što ne funkcionira baš najbolje osim ako ste Vatikan.

NEO funkcionira na sličan naćin kao demokratski izbori, kad se 66% knjigovođa složi da osoba X treba biti predsjednik, osoba Y gubi izbore i tu je kraj priće.


### Digitalni identitet

Digitalnim identitetom se smatraju identificirajuće informacije individualnih osoba, organizacija i ostalih entiteta koje su digitalne. Sustavi koji koriste digitalne identitete baziraju se na PKI (Public Key Infrastructure) X.509 standardu, koje NEO također implementira.
Na ovo možemo gledati kao osobna iskaznica na blockchainu.

### Pametni ugovori

Ethereum za pametne ugovore koristi svoj jezik, Solidity. Programeri koji žele razvijati na Ethereum platformi, moraju naučiti novi programski jezik.

NEO podržava pregršt poznatih programskih jezika koje večina programera zna.
Neki od njih su: C#, Java, Python.

Velika razlika u plasiranju ugovora na blockchian je u tome što kod Ethereum platforme moramo samo platiti transakcijsku naknadu, koja ovisi kompleksnosti ugovora.

Dok kod NEO platforme, za plasiranje pametnog ugovora je potrebno platiti 500 GAS tokena.

### Ekonomski Model

Ovdje se NEO dosta razlikuje od Ethereum platforme.

Ethereum ima jedan nativan token na mreži s kojim plaćate gas, a to je Ether. Ether je potreban za sve transakcije na mreži, bilo to jednostavno slanje Ethera s jedne adresu na drugu, ili slanje tokena, ili okidanje nekakve funkcije u pametnom ugovoru. 

NEO ima dva nativna tokena:
* NEO
* NeoGas (GAS)

U [izvornom bloku][genesis block] stvoreno je 100 milijuna NEO tokena.
Dok se GAS stvara kroz vrijeme od 22 godine kojeg dobivaju sve adrese na kojoj ima barem 1 NEO. Konačni broj GAS tokena je također 100 milijuna.

Na NEO token možemo gledati kao na dionice neke tvrtke. NEO token predstavlja udio pojedinca na NEO mreži i daje pravo glasa u mreži (npr. glasanje za "knjigovođe", promjena nekakvih parametara u mreži itd.). NEO token je ne djeljiv, znaći da možete slati samo cijeli NEO. Ne možete npr. slati 0.5 NEO, 1.34 NEO, nego 1 NEO, 2 NEO, 43 NEO.

Dok naravno kod Ethereuma se može slati 0.0024 ETH itd.,  jer je dijeljiv je  18 decimalnih mjesta.

GAS služi kao gorivo za mrežu, sve operacije na mreži trebaju GAS za izvršavanje.
*GAS je djeljiv na 8 decimalnih mjesta.*

### Konenzusni mehanizam

Ethereum trenutno koristi [Proof of Work][POW] (PoW) rudarenje kao i Bitcoin, a u planu je prelazak na [Proof of Stake][POS] (PoS) u bližoj budučnosti.
Proof of Work trenutno troši enormne količine električne energije, te je dugoročna održivost ovakvog sustava upitna. 

NEO koristi [dBFT (Delegated Byzantine Fault Tolerance)][dBFT] koji je zapravo modificirani Proof of Stake mehanizam, i najsličniji je Delegated Proof of Stake (dPoS) mehanizmu.

Jednostavno objašnjeno, dBFT funkcionira kao sabor.

Ljudi glasaju za delegate ("knjigovođe"), koji postižu konsenzus o valjanim transakcijama i proizvode blokove. Knjigovođe (pojedinci ili institucije) su povezani s pravim identifikacijskim podacima. Što znači da podliježu zakonskoj odgovornosti za svoje postupke. 

Za razliku od politike, ovdje knjigovođe ne dobiju mandat od X vremena, nego se glasovanje odvija u realnom vremenu, što znači da ako pojedini knjigovođa izgubi povjerenje svojih glasača, glasači povlače svoje glasove i taj knjigovođa gubi pravo na sudjelovanje u proizvodnji blokova i validiranju transakcija.

Naravno, ovaj konsezusni algoritam je centraliziraniji od PoW ili PoS mehanizma gdje postoje na tisuče čvorova po cijelome svijetu, ali je dBFT zato puno efikasniji u smislu donošenja odluka, kao npr. implementacija [SegWit] tehnologije na Bitcoin, koja se odužila na nekoliko godina zbog nedostatka konsenzusa.

*NEO tim kreće s decentralizacijom čvorova u Q1 2018. godine.*

#### Transakcije

Zbog dBFT mehanizma  transakcije su **finalne** s jednom potvrdom.
NEO ima teoretskih 10 000 TPS (transakcija po sekundi), dok Ethereum ima teoretskih 30 tps.

Naravno, u praksi je to drugačije, što nas dovodi do 1000 TPS kod NEO-a, i 15 TPS kod Ethereuma.

*Vrijeme generiranja bloka je isto na obje platforme i iznosi 15-20 sekundi.**

### InteropService - interoperetibilni servisi

Koristi se za učitavanje blockchaina, digitalne imovine, identiteta NeoFS i svih ostalih servisa u NEO ekosustavu.
NeoVM (NEO Virtualni Stroj) je moguće prenijeti na drugi blockchain sustav, ili čak sustav koji ne koristi [blockchain] tehnologiju, omogučavajući implementaciju i korištenje pametnih ugovora na drugim platformama.

### NeoX

NeoX protokol omogučava "cross-chain" interoperabilnost, što znači da NEO blockchain može komunicirati i razmjenjivati informacije s drugim blockchain projektima kao što su Ethereum, Bitcoin, Litecoin i ostali.

NeoX je podjeljen na dva dijela:

* Protokol za razmjenu imovine
* Protokol za distribuirane transakcije

#### Protokol za razmjenu imovine

Omogučava razmjenu imovine na različitim blockchain platformama pri tome osiguravajuči da svaki dio transakcije koji se odvija na različitom blockchainu u potpunosti uspije ili ne uspije. 

U protivnom se može dogoditi da osoba dobije npr. NEO koji šaljete, no vi ne dobijete token koji reprezentira vlasništvo nad nekom imovinom, jer je transakcija na Ethereum blockchainu ostala bez gasa.
 
 Da bi se ovo moglo pravilno odraditi, blockchain mora imati podršku za pametne ugovore.
  
  #### Protokol za distribuirane transakcije
 
Omogučava distribuciju transakcija na više blockchain platformi koje podržavaju pametne ugovore. Također, osigurava da se pojedini dio transakcije izvrši na svakoj blockchain platformi na kojoj se treba izvršiti, ili ni na jednoj.

*Ethereum također ima podršku za cross-chain komunikaciju *

### NeoFS - distribuirani podatkovni sustav

NeoFS koristi DHT (distribuirana [hash] tablica) tehnologiju.
Za razliku od današnjeg interneta gdje se podatci ineksira njihovim putem gdje se nalaze na serveru, ovdje se indeksira putem hashanja sadržaja datoteke.

Podatci su spremljeni i distribuirani na više čvorova na mreži. Zbog prirode distribuiranog sustava, moramo voditi računa o omjeru potrebne redundancije i pouzdanosti, odnosno hitnosti pristupa nekoj datoteci.

Tako da će se manje potrebnim datotekama moći pristupiti besplatno ili uz vrlo malu naknadu, dok će se datoteke od presudne važnosti čuvati na "backbone" čvorovima koji će imati monetarni motiv da drže čvorove upaljenim, nešto slično kao rudari u PoW sustavu.

NeoFS služi kao jedan od Interoperabilnih servisa, koji će omogučiti pametnim ugovorima da spremaju velike datoteke na blockchain i ujedno postave dozvole za pristup određenim datotekama . 


*Ethereum također ima podršku za distribuirani podatkovni sustav uz  Swarm.*

### OnChain

OnChain je kompanija koju su osnovali Da Hongfei i Erik Zhang. Kompanija ima vrlo bitnu ulogu oko toga kako se NEO uklapa u ideju pametne ekonomije.

OnChain radi na sustavu DNA (Decentralized Network Architecture) kojem je jezgra NEO. OnChain planira blisko surađivati s Kineskom vladom i kompanijama na integraciji DNA u poslovanje i vladu. Što bi uveliko poboljšalo usvajanje NEO-a.

OnChain razvija privatne i javne blockchain-e za kompanije, koji se mogu spojiti na NEO blockchain, što omogučava pristup decentraliziranoj ekonomiji.

Jedan od OnChain projekata je Ontology, koji koristi istu arhitekturu kao i NEO, no zamišljeno je da radi s kompanijama u stvaranju privatne, enkriptirane podatkovne mreže.
Što je vrlo korisno kad je potrebno očuvati sigurnost i privatnost informacija na blockchainu.

OnChain ima razna partnerstva s tvrtkama kao što su *Microsoft China*i *Alibaba*.
Također je prva Kineska blockchain tvrtka koja se pridružila [Hyperledger] projektu.
Projekt koji radi na integraciji blockchain tehnologije u postojećim kompanijama.

Ethereum ima svoju ekvivalentu po imenu Enterprise Ethereum Alliance (EEA).
Neki od članova EEA su Intel, Microsoft, J.P. Morgan, Mastercard, Toyota, Samsung itd.

## Zaključak

Sve u svemu, NEO i Ethereum su vrlo slične platforme, funkcionalno, najveća razlika je da je NEO građen s određenim ciljem, a to je da postane de facto standard takozvane pametne ekonomije.

Dok je Ethereum platforma koja je "free for all", u smislu inovacije i razvoja na platformi i može krenuti u bilo kojem smjeru ili smjerovima.

No bez sumnje je da obje platforme imaju svoje mjesto i svoju svrhu za što će se koristiti.

[NEO]: https://neo.org
[crypto]: https://bitfalls.com/hr/glossary/#cryptocurrency
[Ethereum]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
[blockchain]: https://bitfalls.com/hr/glossary/#blockchain
[fork]: https://bitfalls.com/hr/glossary/#fork
[genesis block]: https://bitfalls.com/hr/glossary/#genesis-block
[ICO]: https://bitfalls.com/hr/glossary/#ico
[POW]: https://bitfalls.com/hr/glossary/#proof-of-work
[POS]: https://bitfalls.com/hr/glossary/#proof-of-stake
[dBFT]: https://en.wikipedia.org/wiki/Byzantine_fault_tolerance
[SegWit]: https://bitfalls.com/hr/2017/11/07/segwit2x-fork-can-expect-whos-behind/
[blockchain]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[hash]: https://bitfalls.com/hr/glossary/#hash
[Hyperledger]: https://www.hyperledger.org