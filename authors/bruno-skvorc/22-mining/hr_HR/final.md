Rudarenje - na prvi pogled legalna proizvodnja novca kod kuće, koristeći samo vlastito računalo. No, je li to zaista tako? U ovom ćemo članku razbiti česte zablude oko rudarenja, i navesti primjer isplativosti.

Bitno je napomenuti da u ovom članku pričamo o rudarenju [PoW] konsenzusom - znači rudarenje na način opisano u [ovom uvodu u blockchain tehnologiju][bc].

## Vrste rudarenja

Postoje tri glavne vrste rudarenja (u daljnjem tekstu mining):

- rig mining, koji se dodatno dijeli na pool (grupni) mining, i solo mining
- cloud mining
- browser mining

Kod bilo koje od tih vrsta, od kojih će svaka biti pojašnjena u tekstu dolje, radi se o sljedećem procesu:

- rudar (računalo) dobiva nalog za odobravanje određenog skupa transakcija. Tehnički, dobiva podatke s interneta u kojima je zapisano tko kome šalje koliko neke [kriptovalute][cc].
- to računalo gradi [block][block], tj. popis transakcija koje treba potvrditi. Koliko transakcija će biti u bloku ovisi o njihovoj veličini - transakcije koje šalju s mnogo adresa na mnogo adresa su veće od ostalih, kao što smo to objasnili [u ovom članku][blockex].
- računalo spaja sve te podatke iz svih transakcija (doslovno ih zalijepi u jednu cjelinu), još neke druge podatke, i tada pogađa zadnji dio te zagonetke - vrijednost koja, kada se pribroji tom skupu slijepljenih podataka i [hašira][algo], daje [hash][hash] s određenim brojem nula. Računalo doslovno radi sljedeće: "Pokušaj zbrojiti ovo sve i broj 1. Nije točno? Ok, pokušaj zbrojiti ovo sve i broj 2. Nije točno? Ok, pokušaj..."
- jačina računala ovisi o tome koliko tih pokušaja pogodaka na sekundu ono može izvesti.
- nakon pogotka, računalo koje je uspjelo u zadatku dobiva [nagradu za block][bw], koja trenutno iznosi 12.5 BTC kod bitcoin rudarenja, ili npr. 6.18 XMR ako se rudari Monero.

Snaga računala mjeri se u broju pogodaka na sekundu: H/s (hash / sec). Ovisno o algoritmu koji se koristi, često je isplativije rudariti grafičkim karticama nego procesorom, pa mnogi kupuju grafičke kartice i grade rudarske strojeve samo od njih.

Čim je računalo (dakle zbroj tih kartica) jače, tim veću šansu ima doći do rješenja te "zagonetke". Upravo u ovome je prva zabluda.

## Zabluda 1: strpljivost se isplati

![Pješčani sat](https://bitfalls.com/wp-content/uploads/2017/10/01.jpg)

Mnogi ulaze u rudarenje misleći "pa što - i ako mi računalo možda nije najjače na svijetu, prije ili kasnije ću pogoditi jedan blok i dobiti nagradu. Čak i ako je to za 5 godina, ako dobijem 12.5 BTC to je preko $65,000, isplatilo se, neki ne zarade toliko u 10 godina!"

Ovo je zabluda ne samo jer za 5 godina nagrada neće biti ni blizu te koja je danas, nego i jer mnogi ne shvaćaju da je rudarenje **kompetitivni sport**.

Kada se traži potvrda bloka, razni rudari se zapravo utrkuju - cilj je biti *prvi* koji uspješno pogađa, ne "jedan od". Onaj tko pogodi drugi, treći, deseti - ne dobiva ništa (osim u Ethereumu gdje drugi nekad dobiva manje Ethera kao utješnu nagradu). Stoga, natjecanje s jakim računalima drugih ljudi ima veoma malo smisla, pogotovo kod već popularnih kriptovaluta poput Bitcoina.

Taj se problem može zaobići prelaskom na _pool mining_, gdje se pokušaji pogotka šalju u "bazen" (pool) svih pokušaja od svih ostalih rudara spojenih na tu mrežu. Taj pool onda funkcionira kao "solo" rudar, i nakon što osvoji nagradu, podijeli je u poštenim omjerima svim sudionicima ovisno o tome tko je poslao koliko pokušaja pogodaka.

Pool koji upravlja operacijom obično uzima 1% profita za sebe. To malo umanjuje nagradu za sudionike, ali u prosjeku je povećava jer je zajednička snaga obično isplativija od privatne.

## Zabluda 2: dugoročno, povratiti ću uloženo

"Ne želim se pridružiti poolu, želim sav profit za sebe", neki će pomisliti, i zaputiti se u kupnju desetak grafičkih kartica da izgrade veoma moćan mining stroj.

![Stroj za rudarenje](https://bitfalls.com/wp-content/uploads/2017/10/02.jpg)

#### Primjer: 

Jedan od naših čitatelja čuo je od prijatelja da rudarenjem Ethera može zaraditi. Razmišljao je o tome da uloži 9000 eura u opremu (4 stroja), jer su mu rekli da takvom opremom može dobiti cca 330 eura mjesečno u Eth po stroju, od kojih 50 eura ode na trošak struje. Čini se jednostavno, zar ne? 280 * 4 profita na mjesec (cca vrijednost 4.8 Eth) nadoknađuje onih 9000 za cca 9 mjeseci, i to ako Eth ostane na istoj cijeni, a velika je vjerojatnost da će rasti. Ako uzmemo za primjer da će Eth porasti konzervativnih 50% u sljedećih godinu dana, i da naš čitatelj ne mora odmah prodati rudareni Ether nego ga može do tada držati, to je onda 13300 nakon prve godine, znači solidan profit. Zvuči još bolje, zar ne?

Postoje sljedeći problemi:

- Ethereum prelazi na [PoS][pos] sustav rudarenja, pa jaka računala više neće imati smisla
- [Nagrada za block][bw] u Ethereum sustavu se postepeno smanjuje. Sada je 5, uskoro će biti 3, kasnije će biti još manje. Redukcija od 40% nije trivijalna.
- [Težina rudarenja][bd] se postepeno povećava kako se nagrada smanjuje - s ciljem prelaska na PoS konsenzus. To znači da strojevi ne samo dobivaju manje nagrade, nego i postaju manje efikasni u rudarenju.
- Struja košta, i može poskupiti svakog trena, i time pomaknuti profitne marže u nepovoljnom smjeru. Koliko puta ste doživjeli da je struja pojeftinila? A koliko puta je poskupila? Solarno napajanje ili napajanje na vjetar su opcije, ali količina struje koja je potrebna prelazi razumne granice ulaganja ako će biti korištena samo za rudarenje - da ni ne spominjemo dodatne troškove održavanja takvog sustava, ili poreze na obnovljivu energiju za koje lobira naftna industrija.
- hardver može pregoriti. Grafičke kartice koje su stalno na 120% kapaciteta i upotrebe imaju daleko manji rok trajanja od prosječnih, a garancija grafičke kartice za prosječnog korisnika je obično 2 godine. Ako proizvođač očekuje da će grafička kartica trajati cca 2 godine na normalnoj upotrebi, koliko može trajati kada bude na 120% više godina za redom? Tu su i napajanja i ostale komponente takvog sustava - svaka od njih može stati s radom u svakom momentu.

Sada pogledajmo isplativost ulaganja tih 9000 eura u Eth direktno. Nakon godinu dana, porast od 50% znači da naš čitatelj sada ima 13500 eura. Ostvario je isti profit u istom roku, bez stresa oko struje, strojeva, održavanja, poreza, i slično. Sada može uložiti u nešto drugo, ili uživati.

"Ali", možda mislite, "ako se Eth težina rudarenja promijeni ili pređe na PoS, možemo jednostavno rudariti nešto drugo, zar ne?". Tu je treća zabluda.

## Zabluda 3: uvijek će biti neke kriptovalute za rudariti

Ovisno o algoritmu koji se koristi, neku valutu će biti lakše ili teže rudariti određenom opremom. Neki algoritmi bolje prolaze na rudarenju procesorom, te u tom slučaju grafičke kartice nisu toliko korisne ni isplative. Neki algoritmi rade posebno dobro na AMD grafičkim karticama, a neki na Nvidia karticama. Neki pak su toliko neefikasni na hardveru koje prosječni korisnik može kupiti u maloprodajnim dućanima, da je jedina opcija [ASIC] uređaj - posebni stroj napravljen samo za rudarenje posebne kriptovalute na posebni način, potpuno optimiziran za tu jednu stvar. Takav je slučaj primjerice s Bitcoinom kojeg je najbolje rudariti [AntMiner][am] uređajima tvrtke Bitmain.

![Stari rudnik](https://bitfalls.com/wp-content/uploads/2017/10/03.jpg)

Koju god valutu odabrali za rudarenje, dobro proučite njene dugoročne planove razvoja i potencijalnih promjena algoritma, kao i ponudu hardvera koji je najbolji za rudarenje iste.

## Isplativost

Zaključili smo dakle da se solo mining ne isplati. No, ako već imate opremu ili strahovito želite rudariti, pool mining je opcija koja je sasvim u redu. Ako nemate svoj stroj a svejedno biste željeli sudjelovati u ovoj zlatnoj groznici, postoje mnogi pružatelji **_cloud mining_** usluge kod koje kupac unajmi opremu za mining (na daljinu - ne u vlastitom prostoru) i plaća mjesečnu cijenu za korištenje iste. Ostatak procesa je isti kao pool mining - ti unajmljeni strojevi rudare zajedno i dijele profit, samo je on tada umanjen za cijenu najma stroja.

Konačno, postoji i novi pristup: browser mining, ili rudarenje u pregledniku. To je metoda koju je nedavno [koristio PirateBay bez da obavijesti svoje posjetitelje][tpb], a u kojoj smo se [i mi okušali][money] kako ne bismo morali prodavati oglase. Taj CoinHive pristup je zapravo _pool mining_ ali umjesto da rudarite vi na svom računalu, rudare ljudi koji posjećuju vašu web stranicu, malo po malo, kap po kap. S dovoljnim brojem posjetitelja, to može postati jače od jakog vlastitog stroja.

Koja od ovih metoda je najisplativija? Evo nekih brojki koje možemo podijeliti.

Bitfalls.com trenutno ima cca 8000 posjetitelja dnevno. S CoinHive minerom (browser mining metoda) u dva tjedna poslali smo 152.5 miljuna hasheva, što je zaradilo 0.02 XMR, ili prema cijeni od $90/XMR nekih $1.8, tj. 11kn. Po toj posjećenosti, zarada od CoinHive rudarenja bila bi nam 20kn na mjesec. S obzirom na neugodnosti koje takva metoda uzrokuje mnogim posjetiteljima - mnogi su nam javili da im se stranica ruši na mobilnim uređajima, ili da im antivirusni programi označavaju našu stranicu štetnom - nije moguće ni govoriti o isplativosti.
    
![Ukupno hasheva na coinhive](https://bitfalls.com/wp-content/uploads/2017/10/04-1.png)
  
Za usporedbu, upalili smo jednu GTX1080 Strix grafičku karticu i spojili se na [nanopool] za pool mining. U tjedan dana, kartica je zaradila 0.06 XMR. Čisto matematički, rudarenje jednom grafičkom je 6 puta isplativije od web stranice s 8000 posjeta dnevno - ako je struja besplatna. Ako uračunamo troškove struje koji ispadaju nekih 90kn ($15) na mjesec za ovako neoptimizirani stroj, ispada da imamo neto zaradu od $10 na mjesec, ako je XMR na $90.

![Ukupno hasheva nanopool](https://bitfalls.com/wp-content/uploads/2017/10/05-1.png)
  
Možemo primjetiti da je isplativost u najboljem slučaju upitna, osim ako ne koristite strogo specijalizirane uređaje (ASIC) ili imate besplatnu struju. Ako se nađete u prilici da imate oboje, tada postajete konkurentni.

Gornji primjer odnosi se samo na Monero kriptovalutu - jedinu koja se trenutno može rudariti preko preglednika - no isplativost je slična ili gora za druge value.

## Zaključak

Osim ako nemate besplatnu struju ili jako optimizirane strojeve za rudarenje, ono je stresan, zahtjevan, i većinom neisplativ posao - kako za računala, tako i za one koji njima upravljaju. Nosi mnogo rizika, a malo opipljivih nagrada - naš je stav da je pametno ulaganje mnogo bolji način zarade, a pomaže potencijalno odličnim projektima da dobiju potrebna sredstva za sljedeće čudo tehnologije.

Ako pak se ipak odlučite za rudarenje, ili samo želite probati, [What to Mine][wtm] će vam biti od velike koristi za usporedbu isplativosti. Sretno!

P.S. Ako rudarite i imate iskustva s time, željeli bismo čuti vaše dojmove. Javite se u komentarima ispod, ili [na mail][mail] - zanima nas isplativost, uređaji koje koristite, troškovi, trikovi za optimizaciju procesa, i drugo.

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