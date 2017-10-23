I u pojmovniku i u drugim člancima dotakli smo temu rudarenja kriptovaluta i dvije glavne metode kojima se ono izvršava: PoW i PoS. U ovom ćemo članku malo detaljnije razraditi svaku metodu. Za razumijevanje teksta ispod nije potrebno tehničko predznanje, no bilo bi korisno kada biste bili upoznati s našim osnovnim tekstovima: [uvod u kriptovalute][cc] i [uvod u blockchain][bc].

## Proof of Work (PoW)

Kod Proof of Work (_dokaz rada_), vaš rudar (minerom/rudarom smatramo računalo ili skup računala pod vašom kontrolom) radi sljedeće:

- s interneta preuzima nalog za odobravanje određenog skupa transakcija. Drugim riječima, od drugih minera s kojima je u kontaktu (ovisno o geografskoj blizini čiji će se signal prije poslati do koga) dobiva podatke u kojima je zapisano tko kome šalje koliko neke [kriptovalute][cc].

- računalo tada gradi [block][block], tj. popis transakcija koje treba potvrditi. Koliko transakcija će biti u bloku ovisi o njihovoj veličini - transakcije s mnogo adresa na mnogo adresa su veće od onih koje šalju s jedne adrese na jednu-dvije, kao što smo to objasnili [u ovom članku][blockex].

- računalo spaja sve te podatke iz svih transakcija (doslovno ih zalijepi u jednu cjelinu), doda im još neke druge podatke, i tada pogađa zadnji dio podataka. Traži vrijednost koja, kada se pribroji tom skupu slijepljenih podataka i [hašira][algo], daje [hash][hash] koji odgovara nekim pravilima (npr. u Bitcoinu, hash mora imati određeni broj nula na početku). Računalo dakle doslovno radi sljedeće: "Pokušaj zbrojiti ovo sve i broj 1. Nije točno? Ok, pokušaj zbrojiti ovo sve i broj 2. Nije točno? Ok, pokušaj..."

- jačina računala ovisi o tome koliko tih pokušaja pogodaka na sekundu ono može izvesti.

- nakon pogotka, računalo koje je uspjelo u zadatku dobiva [nagradu za block][bw], koja trenutno iznosi 12.5 BTC kod bitcoin rudarenja, ili npr. 6.18 XMR ako se rudari Monero.

Isplativost rudarenja na ovaj način varira, kao što smo to objasnili u [ovom članku][mining]. Proof of Work trenutno koriste gotovo sve kriptovalute.

![Rudarenje kriptovaluta](https://bitfalls.com/wp-content/uploads/2017/10/02-2.jpg)

Prednosti ove metode su:

- efekt vanjskog faktora. Kod PoW mehanizma, u samu proizvodnju novog novca i u njegovu cirkulaciju, ulaže se vanjski faktor - struja i hardver. Potrošnju struje ni trošak izrade hardvera nije moguće vratiti. Zašto je to bitno saznati ćemo u PoS dijelu dolje.

- jednostavan [pool mining][mining]. Lako je programski uzeti hasheve jednog rudara, pribrojiti ih drugima, i tako zajednički pokušati rudariti. Mnogo računala tako mogu rudariti zajedno.

- korisno za krajeve s previše električne energije, recimo Kinu s neiskorištenim hidroelektranama.

Nedostaci ove metode:

- PoW rudarenje nije moguće na malim uređajima poput smartphonea. Ne samo što takvi uređaji nemaju stotine gigabajta mjesta koji su trenutno potrebni za cijelu kopiju blockchaina, nego i nisu dovoljno procesorski moćni da rudare - baterija bi im otišla u kratkom roku, ne postignuvši ništa.

- PoW rudarenje blokova je sporo. Kod bitcoina, radi se o jednom bloku svakih 10 minuta, i onoliko transakcija koliko stane u taj blok će se obraditi. Sve ostale čekaju, što dovodi do dugih perioda čekanja za potvrdu transakcije, ili skupe troškove slanja (skuplje transakcije prioritiziraju se i bivaju uključene u blok prije jeftinijh).

- PoW rudarenje već danas troši nevjerojatne količine struje. Samo rudarenje jednog bloka košta više struje nego je nekim državama potrebno kroz cijelu godinu ukupno. To će se samo još pogoršati. Ovisnost kriptovalute o velikim količinama električne energije je neodrživa, i može opstati samo u ultra-stabilnom svijetu. Također, ovisnost kriptovalute o struji znači da poskupljenje struje ili limit na trošenje struje za rudarenje može [zaustaviti cijelu mrežu][unstoppable].

  ![Pollution](https://bitfalls.com/wp-content/uploads/2017/10/01-2.jpg)

- PoW rudarenje omogućava centralizaciju valute. Npr. Kina već sada ima preko 80% hashing moći bitcoin mreže, što znači da je 80% svih blokova izrudareno u Kini. Ako se njihovi karteli udruže, imamo _80% napad_, ne [51% napad][51].

- Jer se [block nagrada][bw] postepeno smanjuje, rudari dobivaju manje i manje tokena nekog [blockchaina][bc]. Ujedno, kako više ljudi rudari, [težina][bd] rudarenja se povećava, dakle rudarenje postaje sustavno skuplje. Kako rudarenje postaje skuplje u odnosu na zaradu, manje rudara se trudi oko te valute i izlaze iz sustava. Valuta samu sebe sabotira. Manje računalne moći među rudarima neke valute znači više šanse za [51% napad][51]. 

  Zbog oskudnosti će vrijednost Bitcoina rasti još do nekih $25000, možda $50000 kroz sljedećih 5 godina, ali kako se transakcije počnu micati s glavne mreže na Lightning Network i slična "off chain" rješenja (nadogradnje bitcoina koje u svrhu povećanja kapaciteta i brzine mreže miču transakcije u sekundarni lanac i time odstranjuju transakcijsku proviziju iz glavnog, pa time rudarenje postaje još neisplativije), rudari će napuštati svijet kriptovaluta u povećanom broju, time još više omogućivši _51% napad_ ili potpunu stagnaciju mreže.

## Proof of Stake (PoS)

![Dokaz uloga](https://bitfalls.com/wp-content/uploads/2017/10/03-3.png)

Kod Proof of Stake (_dokaz uloga_), više se ne pogađaju kompleksne jednadžbe pa samim time nisu potrebna jaka računala, niti velike količine struje. 

Primjeri: Ethereum (uskoro), BlackCoin, CoinMagi, Diamond, Mintcoin, OKCash, HyperStake, Quotient, itd.

Uzmimo Ethereum za primjer. Proof of Stake funkcionira tako da se nasumično odredi "validator" - vlasnik dovoljno Ethera da bi ga se smatralo vjerodostojnim. U inicijalnim planovima, to bi bilo 1000 Ethera, a čim više Ethera potencijalni validator ima, i čim je taj Ether dulje na računu tog kandidata, tim više šanse postoji za odabir tog validatora. Taj validator tada ulaže svoj Ether (koliko god, ali najmanje 1000) i garantira da će istinito potvrditi transakcije - neće ih lažirati ili mijenjati. Njegov Ether je pritom zaključan u sustavu na nekoliko mjeseci. Time, kad stigne nova transakcija, validator je ovjerava i šalje na mrežu svim drugim validatorima koji potvrđuju tu informaciju. Za taj posao potvrđivanja transakcija, validator uzima transakcijske troškove (provizije) koje dolaze s transakcijama. 

Zbog nestanka potrebe za pogađanjem kombinacija, to procesuiranje je brzo i lako, pa je time lako generirati lažne transakcije. No, jer validatori moraju potvrditi informacije jedni drugima (kao u školi kada učenici jedni drugima ispravljaju ispite), gotovo je nemoguće da će većina validatora odlučiti da je transakcija malicioznog validatora vjerodostojna. Da bi se to desilo, skupina koja validira ilegalnu transakciju mora ne samo biti istovremeno nasumično odabrana (matematički nemoguće), nego i imati više od 51% Ethera u skupu tih validatora, što je ogromna količina novca. 

Nadalje, ako je maliciozni validator u prekršaju, on gubi svoj ulog - time varanje postaje izuzetno skup sport. Netko tko ima dovoljno novca uloženog u Ethereum ekosustav da postane validator ujedno nema razloga da taj sustav sabotira, jer njegov novac time gubi vrijednost (zbog skandala koji je sam uzrokovao ako uspije, ili gubitka uloga ako nije).

Prednosti ovog načina rada su:

- brzina obrade transakcija
- nije štetno za okoliš za razliku od PoW konsenzusa
- nije ranjivo od strane države - ogromne količine struje nisu potrebne
- može se odrađivati na manjim i slabijim uređajima, jer se ne treba preuzeti cijeli blockchain od nekoliko stotina gigabajta, i ujedno nema tolike potrošnje struje pa se lako odrađuje validacija i na mobilnim uređajima. To dramatično pospješuje ulaz kriptovalute u širu javnost.

Nedostaci su:

- nema eksternih faktora. Budući da se za ulog jamči samim dijelom sustava (npr. da bi se verificirale transakcije Ethereum blockchaina potrebno je uložiti Ether), cijela igra je "interna". To znači da netko s dovoljno sredstava da uloži isključivo u uništenje tog sustava (banke, vlade, itd.) može žrtvovati samo novčanu vrijednost za efektivni napad na sustav. To se razlikuje od Bitcoina kod kojeg je potrebno uložiti trud, znanje, hardver, struju, i vrijeme - sve eksterni faktori.

- bogatiji se bogate. Npr. oni koji najdulje imaju najviše Ethera (boduje se starost Ethera na računu i količina) imaju i najviše šanse da postaju validatori, i time najviše šanse da služe dodatne Ethere na svojoj trenutnoj zalihi. To je drukčije od "bogatiji se bogate" sustava kod Bitcoina, u kojem bogatiji moraju uložiti svoje bogatstvo u vanjski faktor - struju i hardver - i time imaju malo opipljiviji ulog koji će ih više ozlijediti ako sabotiraju mrežu.

## Delegated Proof of Stake (dPoS)

![Glasovanje i politika](https://bitfalls.com/wp-content/uploads/2017/10/04-1.jpg)

U ovoj vrsti PoS sustava odabire se 101 delegata (obično 101, neke kriptovalute će promijeniti taj broj), korisnika koji će imati moć verifikacije i izrade novih blokova, ali odabire ih zajednica glasanjem na izborima, a ne sam sustav nasumično.

Delegati nemaju mogućnost modifikacije transakcija, ali mogu odbiti njihovo uključenje u neki blok i time usporiti određenu transakciju. No, to je jedina tehnička moć koju imaju, i ista ima ograničenu korist za maliciozne aktore jer je u dPoS sustave ugrađena metoda za izbjegavanje takvih kočenja na dulje staze. Ukoliko se neki delegati počnu ponašati štetno prema sistemu i kočiti transakcije, zajednica ima mogućnost izbacivanja istih glasanjem. 

Delegati dobivaju nagrade za potvrde bloka, kao u svakom drugom sustavu rudarenja, pa time nemaju koristi od varanja jer imaju velike šanse izgubiti svoj ulog - i ulogu. Nagrade koje dobivaju, delegati mogu koristiti za lobiranje, dijeljenje svojim glasačima, širenje svijesti o kriptovaluti puštajući je u javni promet, itd. 

Neki DPoS sustavi funkcioniraju na način da delegat može odrediti _burn rate_, tj. postotak spaljivanja tokena. Tako na primjer delegat koji odredi 40% burn rate automatski **uništava** 40% tokena koje prikupi od validacije transakcija. Uništenjem tokena dolazi do [deflacije][finite], i time tokeni svih ostalih korisnika mreže koji ih posjeduju postaju vrijedniji, jer su rjeđi. To je ekvivalentno isplaćivanju dividenda investitorima u neki sustav. Preostalih 60% validator može još uvijek koristiti na gore navedene načine. 

Prednosti:

- ravnopravnija podjela nagrada od potvrđivanja blokova - ljudi će izabrati delegate koji najviše svojih nagrada daju među glasače, pa će time i korisnici s malo kriptovalute biti nagrađeni, ne samo oni s enormnim količinama kao u PoS.

- sigurnost zbog glasanja u stvarnom vremenu. Svaka maliciozna akcija od strane delegata odmah se može identificirati, i u istom momentu delegat može biti izglasan iz sustava.

- isto kao kod PoS, prijateljski za okoliš i lako za izvršavati na manjim i slabijim uređajima. Teže za zaustaviti jer ne ovisi o vanjskom trudu kojeg kontrolira nadležno tijelo (država može blokirati električnu energiju, npr.)

Nedostaci:

- moguće je da se delegati organiziraju u kartele. Tako nešto se već desilo s LISK blockchainom koji, iako još nije ni pušten u javnost kao gotov proizvod, već ima kartelizirani dPoS u kojem se nekolicina ljudi (prvih 51 njih, više od pola prije spomenutih 101) organizirala u "Lisk Elite Group" koji dogovorno glasaju jedni za druge, i koji ukoliko neki glasač ne glasa za svakog od njih ne dijele Lisk tom glasaču kad dođe vrijeme podjele novo rudarenog Liska. Identično političkoj stranci.

- zbog manjeg broja odgovornih ljudi za održavanje mreže na životu, lakše ju je zaustaviti ili organizirati [51% napade][51].

DPoS koriste kriptovalute poput Bitshares, Crypti, Lisk, RISE, ARK, itd.

## Zaključak

Postoje i druge metode potvrđivanja transakcija, poput Proof of Importance (dokaz važnosti) koji koristi NEM, gdje se umjesto glasanja, vlasnicima 10000+ XEM tokena pridodaje bodovna važnost, i čim dulje sudjeluju u mreži tim su "važniji", no i to ima svoje očite nedostatke.

Ni jedna metoda nije savršena, i svaka ima velike probleme na kojima iznimno pametni ljudi danonoćno rade. Kada i koliko napredka ćemo u ovim područjima vidjeti ostaje upitno, no jedno je sigurno - napredci dolaze, i taj moment biti će prekretnica u širenju kriptovaluta u javnost.

[51]: https://bitfalls.com/hr/glossary/#51-attack
[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[block]: https://bitfalls.com/hr/glossary/#block
[blockex]: https://bitfalls.com/hr/2017/10/03/read-bitcoin-blockchain-data-blockexplorer/
[hash]: https://bitfalls.com/hr/glossary/#hash
[algo]: https://bitfalls.com/hr/glossary/#sha-256
[bw]: https://bitfalls.com/hr/glossary/#block-reward
[pos]: https://bitfalls.com/hr/glossary/#pos
[pow]: https://bitfalls.com/hr/glossary/#pow
[bd]: https://bitfalls.com/hr/glossary/#difficulty
[mail]: mailto:contact@bitfalls.com
[wtm]: http://whattomine.com
[asic]: https://bitfalls.com/hr/glossary/#asic
[am]: https://www.bitmain.com/
[tpb]: https://bitfalls.com/hr/2017/09/17/thepiratebay-steals-cpu-mine-cryptocurrency/
[money]: https://bitfalls.com/hr/money/
[nanopool]: https://xmr.nanopool.org
[mining]: https://bitfalls.com/hr/2017/10/12/mining-investing-cryptocurrency-better/
[unstoppable]: https://bitfalls.com/hr/2017/08/21/is-bitcoin-unstoppable/
[finite]: https://bitfalls.com/hr/2017/09/17/bitcoin-finite-just-myth/