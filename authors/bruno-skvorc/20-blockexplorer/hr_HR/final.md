U jednom od [prošlih članaka][anon] spomenuli smo da su Bitcoin transakcije javne, i da ih se može pratiti. U ovom ćemo članku objasniti gdje i kako transakcije pregledati, i kako interpretirati podatke koji nam se nude u jednostavnom web sučelju.

## Blockexplorer

Postoji mnogo web stranica za istraživanje Bitcoin [blockchaina][bc], no najpopularnijom se lako može smatrati [Blockexplorer][be].

![Blockexplorer polje za unos](https://bitfalls.com/wp-content/uploads/2017/10/01.png)

Na Blockexplorer stranici u polje za unos možete ukucati sljedeće vrijednosti:

- unosi se transakcijski kod poput ovoga: 57309a5cf004fd4746ab508deb0093a5181fb93ead1fbf0b0ebf375b2e817fb6 da biste pregledali transakciju.
- javni [ključ][wallet] nečije adrese unosite da saznate stanje te adrese i pogledate transakcije koje tu adresu imaju kao krajnju ili početnu.
- broj [bloka][block] upisujete kada želite saznati kada je točno [_izrudaren_][mining], te koje je transakcije kojih adresa taj block potvrdio.

Pogledajmo, na primjer, gore spomenutu transakciju. U polje kopirajte sljedeće, i potvrdite: 57309a5cf004fd4746ab508deb0093a5181fb93ead1fbf0b0ebf375b2e817fb6

To je identifikacijski kod transakcije. Nakon potvrde, Blockexplorer vraća podatke o toj transakciji, i svim povezanim podacima.

## Analiza Transakcije

U prvom dijelu ekrana biti će osnovne informacije o transakciji:

![Ekran s prvim podacima oko transakcije](https://bitfalls.com/wp-content/uploads/2017/10/02.png)

Ova tablica nam govori sljedeće:

- koliko je ova transakcija sadržavala bajtova (3873 bytes). Ako uzmemo u obzir da je veličina bloka Bitcoin mreže trenutno 1MB, to znači da u jedan blok stane cca 258 takvih transakcija. Ako znamo da se jedan blok pojavljuje otprilike svakih 10 minuta, možemo zaključiti da Bitcoin mreža ima kapacitet od otprilike 2-3 transakcije na sekundu. Daleko od nekoliko tisuća koje vrti Visa.
- _Fee Rate_ je cijena koju je izvršitelj transakcije platio Bitcoin mreži (i time samim rudarima) da bi se transakcija potvrdila. 0.001305959204750839 BTC / kB (1 kB = 1000 bytes), znači da je ova transakcija pošiljatelja koštala 0.00505798, ili $22.20 po trenutnoj BTC cijeni od $4368/BTC.
- Received Time i Mined Time su vremena kada je blok potvrđen, i kada je primljen u Blockexplorer (ta vremena su obično identična).
- _Included in Block_ je identifikacijski kod bloka u kojem je ta transakcija potvrđena. Prisjetimo se - rudarenje je kompetitivni sport. Više jakih računala se utrkuje tko će prvi potvrditi blok i njegove transakcije, jer taj dobiva nagradu - gore navedeni _fee_, i besplatne Bitcoine koje [rudarenje proizvodi][bc]. Kasnije ćemo pogledati taj block, usredotočimo se sada na donju tablicu.

![Tablica s detaljima transakcije](https://bitfalls.com/wp-content/uploads/2017/10/03.png)

U ovoj detaljnoj tablici (koja se proteže do dna ekrana i može se raširiti u visinu pritiskom na "Show More") ispisani su svi prijenosi unutar jedne transakcije. 

Naime, kad se u Bitcoinu šalju sredstva, moguće je imati više ulaznih adresa, i više izlaznih adresa. Mnogi [programi za slanje][wallet] taj proces automatiziraju i korisniku prikazuju samo jedan iznos na ekranu, ali taj iznos je zapravo spremljen na više adresa u samom [uređaju][ledger] ili programu.

Kada isti korisnik poželi poslati sredstva, on ih može slati na jednu adresu, ili na više njih istovremeno uštedivši tako vrijeme i nerijetko transakcijske troškove. Nadalje, zbog [ne-anonimnosti Bitcoina][anon], često se predlaže da se prilikom slanja uvijek koristi nova adresa za ostatak sredstava koja nisu namijenjena primatelju, tako da adresa s koje se šalje ostane potpuno prazna i može se odbaciti. Mnogi programi to rade automatski, pa time često transakcije u Bitcoinu imaju minimum od dvije odlazne adrese. U ovom slučaju naše transakcije, radi se o prijenosu s mjenjačnice Bitstamp na njihove korisnike pa je i broj adresa i finalni iznos malo veći.

U samoj tablici, lijevo su ulazne adrese - dakle adrese s kojih je Bitstamp slao sredstva - dok su desno odlazne. Ne zna se s koje je točno adrese koji iznos poslan na koju - zna se samo finalna distribucija.

Skroz desno kraj svakog retka u tablici, primjetit ćete slovo `U` ili `S`. `U` znači "unspent" - nepotrošeno. `S` je "spent" - potrošeno. Ti pojmovi odnose se na to da li su sredstva ostala u toj adresi na koju su stigla, ili su već pomaknuta na neku drugu adresu.

Na dnu tablice vidimo zbrojeve raznih atributa te transakcije. 

![Dno tablice](https://bitfalls.com/wp-content/uploads/2017/10/04.png)

Najbitnije, vidimo:

- koliko je _confirmationa_ (potvrda) block do sada imao. Sjetimo se, kada se [blok izrudari][bc], nađeni podaci šalju se svim ostalim računalima sudionicima kako bi ga i oni mogli uključiti u svoj preuzeti blockchain. Kada neki _node_ (čvor, računalo sudionik, rudar) prihvati novi blok, ono ga **mora** potvrditi prije nego može nastaviti sudjelovati u izgradnji blockchaina, pa tako čim više _confirmationa_ blok ima, možemo biti sigurni da ga je više raznih računala potvrdilo, i da je transakcija validna.
- ukupni broj Bitcoina koji su bili preneseni u ovoj jednoj transakciji. Kao što smo napomenuli, iznos je malo veći jer se radi o mjenjačnici. Ako uzmemo u obzir cijenu BTCa i cijenu troškova transakcije, možemo izračunati da se za prijenos $167,312.42 platilo $22.20. To je 0.0001326859 tj. malo više od stotinke postotka.

## Analiza Bloka

Kliknete li na [_hash_][hash] bloka u prvoj tablici podataka oko transakcije, ili ako unesete broj bloka u polje za unos na vrhu - npr. 487978 - vidjeti ćete svojstva tog bloka u potpunosti.

![Prva tablica na block ekranu](https://bitfalls.com/wp-content/uploads/2017/10/05.png)

Prije same tablice nalazi se `BlockHash` - identifikacijski kod bloka 487978. Bilo koja od te dvije vrijednosti može se unijeti u polje unosa za inspekciju bloka. Kako se do tog hasha došlo, pročitate [ovdje][bc].

Pod tablicom `Summary`, vidimo sljedeće podatke:

- Number of Transactions je broj transakcija koje su bile uključene u taj block. Bitno je napomenuti da su transakcije obično mnogo manje od onih koju smo gore analizirali, pa ih time stane više od prije izračunatih 258. U ovom je bloku bilo potvrđeno 2712 transakcija diljem svijeta.
- Height - broj blocka
- Block reward - [nagrada][reward] koja se daje rudaru koji je taj block izrudario. Trenutno to je 12.5 BTC, ili malo više od $53,000. Ta nagrada dobiva se bez obzira na transakcijske troškove - to je 12.5 [djevičanskih bitcoina][reward].
- Timestamp je točan datum i vrijeme kad se pronašao hash ovog blocka.
- Mined by je osobni identifikator rudara koji je pronašao hash. U ovom slučaju rudar je nepoznat - znači da block nije potpisan od nijednog poznatog aktora. Identifikacija je proizvoljna, pa time mnogi odabiru biti anonimni, posebice privatni mineri koji nemaju velike tvrtke iza sebe. Jedan od najvećih rudara u Bitcoin svijetu je kineska tvrtka Bitmain koja proizvodi [ASIC][asic] i identificira se kao AntMiner (tako im se zove uređaj kojim rudare). Ako odete na [glavni popis][blockslist] svih nedavno izrudarenih blokova, dominacija te tvrtke postaje očita.
- Merkle root je [hash] svih transakcija iz tog blocka i njihovog redoslijeda. Merkle root se koristi kod validacije *sadržaja* bloka, a ne samih transakcija.
- Next i previous block su direktne poveznice na prijašnji i sljedeći block.
- Difficulty je težina izračuna hasha ovog blocka. [Difficulty][diff] se radi balansiranja inflacije i održavanja prosjeka od 10 minuta po bloku automatski pomiče i ponovno izračunava svakih 2016 blokova. Rudarenje postaje sve teže s vremenom, osim u slučajevima kad neki [rudari][mining] napuste mrežu i težina se smanji.
- Bits su heksadecimalna reprezentacija gore navedene težine. Svaki blok sprema komprimiranu verziju svoje težine u obliku Bitsa prema [ovoj formuli][bits].
- Size (bytes) je ukupna veličina bloka. U ovom slučaju radi se o 991124 bytova, ili 0.991MB, što je gotovo do granice napunjen block podacima (granica je 1MB). Block ne mora biti napunjen do kraja da bi se rudario - nerijetko je da se rudare i prazni blokovi ako jednostavno u to vrijeme nema transakcija. Rudari neće stati s radom.
- Version je posebni set brojeva kojim softver rudara [signalizira ostalima][version] za koje izmjene Bitcoin protokola glasuje.
- Nonce je ključni podatak u izračunu block [hasha][hash]. To je broj koji rudari nasumično mijenjanju nakon što mu u [mining] algoritmu poput SHA256 pribroje broj transakcija, njihove podatke, Merkle root, i neke druge informacije, i time pokušaaju dobiti hash koji ima više nula na početku od prijašnjeg ili isto toliko. Cilj je dobiti hash koji je manji od težine. Kada se takav dobije, block se smatra potvrđenim, tj. izrudarenim.

U tablici ispod, vidimo popis svih transakcija u tom bloku. Kao što smo prije spomenuli, transakcije su obično daleko manje od onih iz prvog primjera, pa tako ovdje vidimo mnogo transakcija koje imaju samo jednu ulaznu adresu i dvije izlazne. Pogledajmo primjerice ove tri transakcije:

![Tri transakcije bloka](https://bitfalls.com/wp-content/uploads/2017/10/06.png)

Prva transakcija šalje 29.44 bitcoina na dvije adrese. Budući da nijedan izlazni iznos nije okrugli broj, a ovaj veći je potrošen `(S)`, možemo zaključiti da se radilo o FIAT protuvrijednosti. Ako pogledamo datum - 02.10. - i provjerimo cijenu BTCa taj dan ($4400), možemo zaključiti da se radilo slanju o okruglih $130,000. Druga adresa je očito _change address_, tj. adresa s ostatkom.

Pogledajmo sada sljedeće dvije transakcije. Obje imaju istu polaznu adresu, i u oba slučaja se radi o slanju pola BTCa. Tih pola BTC poslano je na dvije druge adrese - razdijeljeno je u dva puta po 0.25 BTC. Vidimo da je okrugli broj (0.25) odmah potrošen `(S)` dok je iznos od 0.2485 u oba slučaja zadržan na adresi na koju je poslan. Razlog zašto iznos na adresama ostatka nije okrugao je zbog transakcijskog troška od 0.0015 BTC, vidljivo u donjem lijevom kutu svake transakcije. tog bloka.

Konačno, pogledajmo malo te adrese.

## Analiza Adrese

Ako kliknemo na bilo koju od adresa u ovim transakcijama, dobiti ćemo informacije o istoj. Pogledajmo prvo ulaznu adresu gornje dvije transakcije: `1ArB3Sn8kNt236fh1CHcvYaEz7RnnV9qq7`.

![Početna adresa](https://bitfalls.com/wp-content/uploads/2017/10/07.png)

Vidimo da je ukupno preneseno cca 12.4 BTC preko te adrese - primljeno 7.37, poslano 5.03 kroz ukupno 28 transakcija. Na adresi je u momentu pisanja ovog članka još 2.34 BTC.

Korisnik ove adrese trudi se održati okrugle iznose, i cilja na 0.5 BTC. Redovito nakon slanja ciljane količine koristi istu adresu za ostatak: `1CBk5dAsbC3ZzDSLC2nBq9kYXjfvQk5WGZ`. Ta adresa je ujedno i jedna od dvije izlazne na transakcijama koje smo gledali prije. Znači možemo biti sigurni da naš korisnik nastavlja koristiti blockchain s te adrese, dok su ostale vjerojatno adrese nekih njegovih klijenata ili poznanika koji [HODLaju][hodl]. 

Ako provjerimo odakle adresi na kojoj se trenutno nalazimo sredstva, vidjet ćemo da je redovito primala uplate od višestrukih unosa, i bila dio višestrukih izlaza, što obično upućuje na mjenjačnicu ili tumbler - servis koji "pere" Bitcoine tako da ih sve baci u jedan bazen, i dijeli vlasnicima iz toga bazena kako bi im se izgubio trag.

Ako provjerimo gore identificiranu _change_ adresu (adresu ostatka), primjetiti ćemo da je i sama u svojih 95 transakcija za 33.44 BTC bila korištena i kao izlaz i kao ulaz, u nekim transakcijama kao višestruki. Budući da je adresa koja je na ovu slala sredstva bila dio višestrukog izlaza, a u nju su sredstva došla s višestrukog ulaza, vrlo je vjerojatno da se radi o _tumbler_ setu adresa koji su namjerno napravljeni da sakriju trag bitconu, ili da se radi o adresama mjenjačnice/burze, ili da se radi o [kitu][whale] koji koristi [programe][wallet] za podijeljeno spremanje bitcoina.

## Alternative

Alternativa Blockexplorer sučelju je sam API (programski pristup) Blockexplorera koji vam omogućava direktno spajanje na blockchain podatke, ili neka druga od gotovih sučelja (od kojih mnoga nude svoj API) poput:

- https://tradeblock.com
- https://insight.bitpay.com/
- https://chain.so/
- https://www.blocktrail.com/
- https://www.walletexplorer.com/
- https://bitcoinchain.com/block_explorer
- https://live.blockcypher.com/btc/
- https://bitinfocharts.com/bitcoin/explorer/
- https://www.coinprism.info/
- http://srv1.yogh.io/
- https://www.smartbit.com.au/
- http://explorer.coinpayments.net/index.php?chain=1
- https://webbtc.com/

## Zaključak

Čitanje blockchain podataka možda je u početku zbunjujuće, no jednom kada znate što koji podatak znači, sve sjeda na svoje mjesto. S novim saznanjima iz gornjeg teksta i metodama opisanim u [ovom članku o anonimnosti][anon], jasno je vidljivo kako je lako ući u trag digitalnom novcu na javnom [blockchainu][bc], posebice ako se može identificirati jedan ili više aktora u lancu i njihove adrese zamijeniti pravim identitetima. Pokušajte sami s nekim adresama - lako ih je naći na raznim forumima, ili na platformama poput [Steemita][steem] gdje ljudi često mole za donacije.

[anon]: https://bitfalls.com/hr/2017/09/18/anonymous-cryptocurrencies-like-bitcoin/
[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[be]: https://blockexplorer.com
[wallet]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[block]: https://bitfalls.com/hr/glossary/#block
[mining]: https://bitfalls.com/hr/glossary/#mining
[ledger]: https://bitfalls.com/hr/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[hash]: https://bitfalls.com/hr/glossary/#hash
[virgin]: https://bitfalls.com/hr/glossary/#virgin-coins
[reward]: https://bitfalls.com/hr/glossary/#block-reward
[blockslist]: https://blockexplorer.com/blocks
[diff]: https://bitfalls.com/hr/glossary/#difficulty
[bits]: https://stackoverflow.com/questions/22059359/trying-to-understand-nbits-value-from-stratum-protocol/22161019#22161019
[version]: https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki
[hodl]: https://bitfalls.com/hr/glossary/#hodl
[whale]: https://bitfalls.com/hr/glossary/#whale
[asic]: https://bitfalls.com/hr/glossary/#asic
[steem]: https://steemit.com