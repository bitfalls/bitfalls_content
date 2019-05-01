Želite se prodružiti Ethereumu a ne znate kako? Koji novčanik koristiti i kako ga podesiti ako niste tehnički potkovani? Evo uvoda u sve to.

Prije nego uletite u donji tekst, pročitajte [uvod u Ethereum](https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/).

## Softver i tipovi čvorova

Ethereum je blockchain. To znači da se pokreće na softveru koji nazivamo čvor (eng. _node_). Svi čvorovi međusobno komuniciraju kako bi imali identične podatke. Ti su čvorovi bazirani na uglavnom dvije najpopularnije inačice: Geth i Parity.

Postoje tri tipa čvora: puni (full), arhivni (archive) i lagani (light). Tako postoji primjerice puni Geth i arhivni Geth, itd.

**Arhivni čvor** će izgraditi cijeli blockchain iz nule, od samog početka. Neće čekati potrebno vrijeme po bloku (15 sekundi) već će ih procesuirati čim brže može, prošavši čak i kroz mrtve forkove koji su se odvili u međuvremenu. Taj proces traje tjednima i zahtijeva više od 2 TB diskovnog prostora. Sprema sva prošla stanja Ethereum blockchaina i daje uvid u stanje bilo koje Eth adrese u bilo kojem trenu u prošlosti. Sinkronizirati arhivni čvor do 100% nije moguće na HDD-u, tradicionalnom tvrdom disku, već je potreban SSD. HDD se jednostavno ne može okretati dovoljno brzo. Dobra vijest je to da vam vjerojatno ne treba arhivni čvor (vidi dolje).

**Puni čvor** je sličan - sinkronizacija isto tako zahtijeva mnogo vremena jer sve gradi od prvog bloka, no u ovom slučaju zadržava se samo zadnje stanje i _dokazi_ o postojanju prošlih stanja. Zbog toga puni čvor ima 80 do 130 GB, ovisno o tome koga pitate, no ne možete saznati informacije o prošlim stanjima bez da izgradite blockchain do tog trena koji vas zanima. Dobra vijest je to da puni čvor može postati arhivni čvor jer ima sve podatke koji su mu potrebni u svakom momentu, samo nisu "aplicirani".

**Lagani čvor** (poznat i kao **lagani klijent** - light client) čita samo nedavnu prošlost o kojoj svjedoče određeni puni ili arhivni čvorovi, preuzima blokove od te točke nadalje, i tada provjerava taj dio nakon što ga izgradi. Vjeruje čvorovima koji mu daju originalne podatke da su isti istiniti i ako jesu, tada je i izračunato zadnje stanje istinito.  

Lagani čvorovi mogu imati problema kod pokušaja spajanja s mrežom jer se vrlo malo punih čvorova pokreće s opcijom za dozvoljeno spajanje laganih čvorova. Takvo pokretanje zahtijeva malo više resursa a ne nudi ništa zauzvrat.

Evo i prijevoda jednog [Twitter objašnjenja punih i arhivnih čvorova](https://twitter.com/bitfalls/status/1105761796235907072):

> Pretpostavimo da imamo X gdje je `X = n!` (n faktorijela). To znači `X = 1 * 2 * (n(n-3)) * ... * (n-3) * (n-2) * (n-1) * n`. Lagani klijenti pitaju pune čvorove za `X`. Dobivaju `X` i neki `n'` gdje je `n' < n`, iz kojeg je lako izračunati `X` ako znamo da se radi o faktorijeli. Puni čvorovi imaju `n` i imaju `X` i mogu u bilo kojem momentu provjeriti je li `X = n!` jer znaju da se radi o faktorijeli. Arhivni čvorovi spremaju sva stanja između koraka u računanju. Razlika prema punim čvorovima? Arhivni čvorovi znaju točno koliko je `X` bio u, primjerice, trećem bloku: 6 (`1 * 2 * 3`). Ako se pune čvorove to pita, oni moraju to ponovno izračunati iz `n = 1`. Dakle ukratko, puni čvorovi mogu biti arhivni bez da preuzimaju podatke od drugih. Arhivni čvorovi korisni su samo ako želite brzi pristup podacima iz prošlosti, no to je vjerojatno bolje spremiti u posebnu bazu podataka koja je optimizirana za tako nešto, nego vrtjeri 2TB blockchaina. Ethereum mreža ne **treba** arhivne čvorove, treba pune čvorove.

Pa, što je onda Ethereum novčanik?

Čvorovi koje smo gore opisali mogu se smatrati "back endovima", serverima blockchaina, tj. serverskim programima koje vrtimo na našim računalima. Oni **nisu novčanici**, no mogu postati novčanici ako u njih unesemo privatni i javni ključ neke Ethereum adrese. Da se spojite s njima, koristi se alat poput Mist-a (više se [ne održava](https://medium.com/@avsa/sunsetting-mist-da21c8e943d2) pa ga nemojte koristiti), [MetaMask](https://bitfalls.com/hr/2018/02/16/metamask-send-receive-ether/), [MyCrypto](https://mycrypto.com), [MyEtherWallet](https://myetherwallet.com) ili neki od novčanika spomenut na[Wallets.Review](https://wallets.review). Tada ti čvorovi pričaju s blockchainom za vas - potpisuju transakcije i čitaju stanje - i prosljeđuju informacije korisničkom sučelju.

Pa, kada trebamo koji alat? Je li to teško podesiti?

## Rudarenje

Moramo napomenuti da ni jedan od gore spomenutih čvorova ni tipova rada nije _rudar_. Za rudarenje kriptovaluta potreban vam je dodatni hardver (skupe grafičke kartice ili specijalizirani ASIC strojevi) i program koji radi rudarenje šalje pogotke jednom od gore navedenih čvorova ako je isti pokrenut u načinu rada koji podržava rudarenje. Rudarenje je izvan konteksta ovog članka.

## Trebam samo novčanik

Ako trebate samo novčanik, sve što vam treba je par privatog i javnog ključa. Ako želite znati više o kriptografskim ključevima, pročitajte ovaj [pristupačni uvod u kriptografiju za smrtnike](https://bitfalls.com/hr/2017/11/16/cryptography-mortals-lets-explain-public-private-keys/). Ključeve možete generirati s bilo kojim sučeljem za novčanike, no najlakše je to učiniti s [MetaMask](https://bitfalls.com/hr/2018/02/16/metamask-send-receive-ether/), [MyCrypto](https://mycrypto.com) ili [MyEtherWallet](https://myetherwallet.com). To će rezultirati _keystore_ datotekom (tekstualna datoteka koja završava s `.json`) koju tada možete unijeti u bilo koje sučelje za novčanike i koristiti svoju Ethereum adresu bilo gdje. Ta datoteka je efektivno vaš novčanik, pa je držite na sigurnom.

Svaki softver za novčanike može koristiti tu datoteku (privatni ključ) da za vas potpisuje tranakcije i jednom kada se takva transakcija emitira _u eter_ bilo preko MetaMaska, Mista, golubova ili dimnih signala, ta transakcija se izvršava. Posjedovanje javnog ključa (izgleda ovako: `0x4522bc91fd54982938...`) pak vam dopušta primanje sredstava u bilo kojem momentu i bez spajanja na internet. Posjedovanje javnog ključa (tzv. adrese Ethereum računa) dopušta vam i da pregledate stanje računa u bilo kojem momentu bez da riskirate curenje svog privatnog ključa unošenjem istog u neko sučelje za novčanike. Zapamtite: ako izgubite svoj privatni ključ, izgubili ste svoj novac. Ako vam ga netko ukrade, ukrao je vaš novac. Sakrijte ga i koristite ga SAMO kad šaljete transakcije, na vlastitoj internetskoj vezi, i u pregledniku bez dodataka.

Alternativno, koristite hardverski novčanik poput [Ledger Nano X](https://www.ledger.com/?r=7410) koji rješava većinu tih problema držeći privatni ključ na osiguranom čipu u samom uređaju. Hardverski novčanici obično dolaze i sa svojim softverom za novčanik pa su spremni za korištenje odmah čim se izvade iz pakiranja.

Predlažemo sljedeći pristup za posjedovanje novčanika na Ethereumu:

- za svakodnevno korištenje na webu (to $50 vrijednosti), koristite [MetaMask ekstenziju](https://metamask.io).
- za dugoročno posjedovanje kriptovalute, koristite [hardverski novčanik poput Ledger Nano S ili X](https://www.ledger.com/?r=7410) ili isprintajte keystore datoteku na papir ili je ugravirajte na metalnu pločicu, pa isto sakrijte na sigurno.

U svakom slučaju predlažemo da **nikako ne držite sredstva na mjenjačnici** jer ista može preko noći nestati, kao što smo to vidjeli već nekoliko puta. U kripto svijetu ne postoji mjenjačnica koja je prevelika da propadne.

"Koliko je to sigurno ako koristim nečiji website za svoj novčanik?", možda se pitate. Tako dugo dok je privatni ključ u vašem vlasništvu, siguran je. Web stranice za korištenje novčanika su tu samo za interakciju s blockchainom i zapravo su otvorenog koda te ih se može pokrenuti i na vlastitom računalu na siguran način. U ovom (sada već zastarjelom) članku demonstriramo kako pokrenuti MyEtherWallet lokalno na vlastitom računalu: [Lokalno pokretanje MyEtherWalleta](https://bitfalls.com/2018/04/24/how-to-run-your-own-copy-of-myetherwallet-for-maximum-security).

## Želim koristiti mrežu

Ako želite uskočiti u Ethereum kao korisnik tog blockchaina, gornje upute oko novčanika jednako su aplikabilne s time da bismo naglasili da je korisno instalirati i neke od mobilnih novčanika, npr. neke spomenute na [Wallets Review](https://wallets.review), jer je web3 ekosustav u zadnjih godinu dana zaista procvao.

Osim toga, ako se želite pridružiti mreži kao korisnik koji vrti svoj vlastiti čvor - radi povjerenja ili bilo kojeg drugog razloga - svaki od alata spomenutih gore ima "Custom network" funkcionalnost koja dozvoljava spajanje na vlastiti čvor. Ako vrtite svoj čvor, što je [i jeftino i jednostavno](https://blockandmortar.io), možete se spojiti na njega ukucajući IP adresu i port vašeg čvora u Custom Network sučelje nekog novčanika poput MetaMask, MyEtherWallet ili MyCrypto.

Prednosti pokretanja vlastitog čvora:

- pomažete Ethereum mreži diversifikacijom čvorova
- dobivate neopovrgiv izvor istine o vašim i tuđim transakcijama, ne vjerujete nikome drugome da vam te podatke prenosi
- pomažete laganim klijentima da se spoje ako vrtite čvor s otvorenim utorima za lagane klijente. To je strogo altruistički, no postoje i metode monetizacije istog, poput [VipNode](https://vipnode.org).

## Spajanje s privatnim blockchainom

Ako pokrećete privatni blockchain na nekom udaljenom serveru, možete spojiti sučelje poput MetaMask-a, MyCrypto-a ili MyEtherWalleta s istim tako dugo dok ste čvor pokrenuli s potrebnim RPC opcijama (remote procedure call - svaka implementacija čvora ima svoje naredbe za taj proces, pogledajte dokumentaciju za detalje). Osim toga, vjerojatno ćete trebati otvoriti i portove na vatrozidu i routeru koji se koristi za spajanje tog čvora s internetom.

Za najbolje rezultate kod privatnog blockchaina, pokrenite čvor na istoj, vlastitoj mreži. Pokrenuti vlastiti čvor bilo kakve vrste [lako je i jeftino](https://blockandmortar.io). Za primjer takve implementacije, pogledajte [Lisinski](https://lisinski.online) testnu mrežu čiji se čvorovi vrte na svemu od AWS-a do privatnih mikro-računala i uredskih laptopa.

Za više detalja o tome kako se spojiti s privatnim blockchainom, pogledajte [ovaj članak](https://bitfalls.com/2018/03/26/connecting-myetherwallet-mist-metamask-private-blockchain/).

## Želim se pridružiti kao developer

Najbolje je vjerojatno početi s nečime poput [Truffle Frameworka](https://truffleframework.com) ili [Embarka](https://embark.status.im). Oba imaju detaljnu dokumentaciju koja predivno objašnjava kako početi razvijati na Ethereumu, i oba imaju aktivne kanale na socijalnim medijima u kojima je lako potražiti pomoć.

Ako biste rado čitali blockchain podatke s blockchaina ili slali transakcije brzo i sigurno bez da ovisite o trećoj strani poput velikih centraliziranih pružača usluga kao što je Infura, pokrenite svoj vlastiti čvor - [lako je i jeftino](https://blockandmortar.io).

Prednosti pokretanja vlastitog čvora:

- pomažete Ethereum mreži diversifikacijom čvorova
- dobivate neopovrgiv izvor istine o vašim i tuđim transakcijama, ne vjerujete nikome drugome da vam te podatke prenosi
- pomažete laganim klijentima da se spoje ako vrtite čvor s otvorenim utorima za lagane klijente. To je strogo altruistički, no postoje i metode monetizacije istog, poput [VipNode](https://vipnode.org).

## Želim biti investitor

Prvo se pridružite _kao korisnik_, a zatim:

- ako ste investirali [preko mjenjačnice](https://www.binance.com/?ref=10883771), stavite novac u hladno spremište (printano ili ugravirano) ili u hardverski novčanik.
- ako ne koristite mjenjačnicu (npr. [Binance](https://www.binance.com/?ref=10883771)), tada uzmite u obzir brokeražu poput [Coinvendor.io](https://coinvendor.io) koja može poslati kriptovalute izravno na vašu kripto adresu.
- koristite alate za čitanje blockchaina da provjerite stanje svog računa - ne unosite privatni ključ bez razloga! Dobri alati za provjeru stanja su [Etherscan.io](https://etherscan.io) i [Ethview.app](https://ethview.app).

## Ethereum 2.0 i Proof of Stake (dokaz uloga)

Ethereum 2.0 je još daleko. Držite oko na [našem 2.0 serijalu](https://bitfalls.com/hr/tag/two-point-oh/) ili na [Ethhub.io](https://ethhub.io). Za razliku Proof of Work i Proof of Stake pogledajte [ovdje](https://bitfalls.com/hr/2018/04/24/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/).