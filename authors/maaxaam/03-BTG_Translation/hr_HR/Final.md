


# Analiza sumnji oko nadolazećeg Bitcoin Gold fork-a

> Nedavno je [news.bitcoin.com] najavio kako se planira hard [fork] na Bitcoin mreži 25.-og Listopada. Ime "novog" coina je Bitcoin Gold (BTG). Cijelu najavu okružuje dosta kontroverze jer je BTG tim vrlo neorganiziran te je povezan sa NO2x *(Ne za Segwit 2x)* pokretom. 
> 
Pročitajte i [Another Fork? Bitcoin Gold Project Plans to Fork Bitcoin Next Month]

## Bitcoin Gold: Vrlo neorganiziran plan za hard fork Bitcoina koji je direktno povezan sa NO2x pokretom

U Bitcoin sferi postoji dosta [tenzija] na relaciji između onih koji podržavaju Core Software i onih koji preferiraju Segwit2x. Dok Segwit2x developeri i [mineri] planiraju povećati veličinu transakcijskog [bloka] na 2MB, grupa koja podržava Bitcoin Core je pokrenula inicijativu "NO2x". Njihov je cilj pokrenuti zajednicu kako bi se suprotstavili Segwit2X-u, a pridružuju im se čak i neki [social influenceri]. Čini se kako je jedan od članova NO2x pokreta, Robert Kuhne, uključen u upravljanje Bitcoin Gold timom. Naime Kuhne koristi "rbtkhn" ime na Slack kanalu te odgovara na mnoga pitanja posjetitelja kao i kriptomedija. Kuhne-ov službeni Twitter kanal (gdje je kraj imena dodao NO2x), također oglašava [btcgpu.org] i prikazuje kako je uključen u projekt. 

Postoje mnoge mane koje su povezane sa projektom, koji se nada izvesti hard fork Bitcoin mreže u samo nekoliko tjedana. Ranije smo objavili kako tim nema testnet mrežu spremnu gdje bi [mineri] mogli testirati sustav. Dodatno, za razliku od mreže BCC (Bitcoin Cash), BTG projekt ima u svom [kodu] implementiranu istu zahtjevnost za *mining* blokova kao i BTC, te nema znakova koji bi dali naslutiti da postoji EDA (Emergency Difficulty Adjustment – što znači da ukoliko nema dovoljno podrške od strane mreže, zahtjevnost koja je potrebna za računanje [hasha] blokova se smanjuje kako bi coin opstao). Za razliku od tvrdnji koje se mogu pronaći na webu projekta, ne postoji [Replay Attack] zaštita unutar protokola. Uznemirujuća činjenica povezana uz BTG projekt je postojanje pre-mine protokola kojim se planira obraditi 1600 blokova. U kodu se naziva: "PoW retargeting change for BTG hard fork pre-mine period."

![Pre-mine 1600 blokova](https://news.bitcoin.com/wp-content/uploads/2017/09/GGOOLhha.jpg)

## Detaljan *interview* sa BTG lead developerom H4x3

[news.bitcoin.com] je primio neke odgovore na pitanja koja su bila upućena anonimnom lead developeru "H4x3". On pojašnjava kako je website u izgradnji a kako se službene informacije mogu pronaći na službenim Twitter stranicama projekta. 

Dalje u tekstu možete pročitati cjelokupan prenos odgovora na postavljena pitanja koja su bila poslana prije pisanja ovog [članka].

Bitcoin.com = BC

BC: Koji su vaši razlozi za *fork-om* Bitcoina 25.-og listopada i planirate li promijeniti algoritam na Equihash? 

H4x3: Da, implementiramo [Proof-of-Work] izmjene na Equihash-u prema GPU *mineable* algoritmu - jer vjerujemo u Satoshijevu viziju: "Jedan CPU jedan glas". Trenutna situacija gdje jedna kompanija ima totalitarističku i monopolističku kontrolu nad proizvodnjom mining 
HW-a koji je potreban za sigurnost globalne mreže - jednostavno nije prihvatljiva bilo kome, tko razumije koliko je decentraliziranost važna za Bitcoin, a da situacija bude gora ta ista kompanija je negativno nastrojena prema Bitocoinu. 

BTG se može promatrati kao replikacija Bitcoin protokola i distribucije coina koja koristi drugačiji tip kompjutorskog HWa za sigurnost. Ova kopija BTCa na drugačijem HW-u može služiti kao polica osiguranja ili backup originalnog lanca ukoliko originalna SHA-256 mreža bude uništena ili oštećena. Isti "backup" plan je bio korišten kao osnovica za vrednovanje Litecoina, ali BTG je bolja verzija funkcionalnosti od Litecoina. Distribucija je identična kao i izvor vrijednosti BTC-a; naime vlasnička struktura LTC-a je mnogo uže distribuirana što ga čini nepraktičnim za univerzalnu pohranu vrijednosti kao i rezervnu valutu. 

BC: Da li Vaš tim ima išta protiv Bitcoin Core-a, Segwit2x-a ili BCC protokola?

H4x3: Mi nemamo ništa protiv Bitcoin Core-a. Naprotiv, svjesni smo da najbolja razina sigurnosti kao i najvažnija inovacija u svijetu [kriptovaluta] dolazi od strane Bitcoin Core tima. To je ujedno i razlog zašto će BTG pratiti Core *roadmap* za *on-chain scaling* te jaču sigurnost i jednakost vrijednosti između kriptovaluta (*[fungibility]*). Ako ikada ponovno dođe do situacije gdje evolucija protokola BTC-a bude blokirana jednom udruženom skupinom minera - BTG će implementirati taj protokol. 

>Bilo tko može *fork-ati* Bitcoin u bilo kojem trenutku, a *community* će u konačnici odlučiti da li [fork] ima vrijednost ili ne. Mnogi članovi BTC zajednice vjeruju kako su BCC i 2X napadi na BTC, dok ostali vjeruju kako su *fork-ovi* korisni i dobronamjerni. Mi nećemo zauzeti poziciju moralne vertikale i praviti se kako imamo mogućnost čitati umove naše konkurencije, ali ćemo otvoreno kritizirati manjkavost konkurentskih inženjerskih rješenja i objasniti kako je BTG bolji.

Negativan aspekt druga dva navedena *fork-a* je da su dizajnirani kako bi *leech-ali* (uzeli, oslabili, crpili) SHA256 hash računalnu snagu od Bitcoina. Odabravši zadržati isti PoW algoritam - automatski su se pozicionirali kao trajna konkurencija Bitcoinu. Da stvar bude i gora, BCC je implementirao EDA, koji uzrokuje iznimnu oscilaciju *hash ratea*, nepredvidljiva vremena potvrde blokova (do 12h između blokova) kao i povećanu inflaciju. Mjera povećanja je tolika da se smanjenje vrijednosti nagrade za obradu blokova kod BCC-a može očekivati već u 2018. umjesto 2020. Dodatno, BCC je obrisao Segwit iz njihovog *fork-a* čak i dok nemaju kvalitetno alternativno rješenje za *[transaction malleability]*. Špekulira se kako je ovaj potez isključivo političko prepucavanje u cilju otvorenog protivljenja Bitcoin Core-u, jer nije bilo iole ijednog tehnički opravdanog razloga za taj potez. 

Željeli bismo pohvaliti BCC za dvije stvari. Prvo, cijenimo da su implementirali *replay protection* kako bi zaštitili korisnike i poslovne subjekte od nehotičnog gubitka sredstava. Naime Segwit2x odbija implementirati *r.p.* uopće, što stavlja cijeli ekosustav u rizičnu poziciju i stvara dodatni teret za sve uključene u proces. Drugo, cijenimo što su uspjeli biti prvi *fork* koji je uspio postati nova [kriptovaluta]. Od svog nastanka, 1. kolovoza imao je 6%-22% vrijednosti Bitcoina, što nije uopće loše za novi coin.

BC: Mislite li da će *community* dati potporu Bitcoinu sa GPU mogućnostima (mininga)?

H4x3: Apsolutno. BTG je već zamijetio izrazit interes *community-a*, čak i bez ikakve marketinške kampanje. U tek dva tjedna sakupilo se 1600 pratitelja našeg Twitter profila i 400 novih članova na Slacku. Zajednica se sastoji od članova iz Latinske Amerike preko jugoistočne Azije pa sve do Rusije. Satoshijeva vizija "jedan CPU jedan glas" je snažan koncept koji većina *communitya* vidi kao inspiraciju te kao takva ne zahtjeva plaćen marketing. Kako Ethereum najavio prelazak sa PoW na PoS sustav, mnogi GPU mineri su izrazili interes za prebacivanjem svojih GPU strojeva na BTG *pool*. Ako tome dodamo potencijal dolaska novih ljudi u Bitcoin zajednicu kroz nadolazeće godine i koji će biti zainteresirani za mining, trebamo reći kako će GPU biti pristupačnija opcija od [ASIC-a].

BTG je još u razvoju. Vrlo smo otvoreni za *feedback* od strane stručnjaka i *communitya*. Predani smo maksimalnoj transparenciji, dok istovremeno poštujemo razumna očekivanja zaštite privatnosti ljudi koji su uključeni u ovaj *open source* projekt. 

## Opaska news.bicoin.com

Kako smo naveli na našem prijašnjem [postu], [news.bitcoin.com] dalje nastavlja istraživati projekt kako bi pravovremeno informirao svoje čitatelje (a i mi naše na [Bitfallsu]) o namjerama BTG tima da provede *hard fork* Bitcoin mreže. Za sada je projekt nepotpun i uključuje mnogo sumnjivih aktivnosti koje su povezane sa dramom Core Vs Segwit2x kampova. Članovi *crypto communitya* također vjeruju kako ovaj projekt treba promatrati sa [oprezom], jer trenutno ima *rating* u rangu [*scama*] s obzirom na sve istaknute manjkavosti.

Koje je Vaše mišljenje o BTG projektu? Da li smatrate kako je ovo dobra stvar za zajednicu ili da je samo *trollanje* protiv Segwit2x-a? Recite nam što mislite u komentarima:

Članak je preuzet sa [news.bitcoin.com] kao i vezane slike.  


[news.bitcoin.com]:https://news.bitcoin.com
[fork]:https://bitfalls.com/hr/glossary/#fork
[A Closer Look at the Suspicious Activity Involved With the Bitcoin Gold Fork]:https://news.bitcoin.com/a-closer-look-at-the-suspicious-activity-involved-with-the-bitcoin-gold-fork/
[Another Fork? Bitcoin Gold Project Plans to Fork Bitcoin Next Month]:https://news.bitcoin.com/another-bitcoin-fork-bitcoin-gold-project-plans-to-fork-bitcoin-next-month/
[tenzija]:https://news.bitcoin.com/bitcoin-software-wars-the-case-against-replay-attack-protection/
[mineri]:https://bitfalls.com/hr/glossary/#mining
[bloka]:https://bitfalls.com/hr/glossary/#block
[social influenceri]:https://twitter.com/SatoshiLite/status/913100888666914816
[btcgpu.org]:http://btcgpu.org/
[kodu]:https://github.com/BTCGPU
[hasha]:https://bitfalls.com/hr/glossary/#hash
[Replay Attack]:https://bitfalls.com/hr/glossary/#double-spending
[članka]:https://news.bitcoin.com/another-bitcoin-fork-bitcoin-gold-project-plans-to-fork-bitcoin-next-month/
[Proof-of-Work]:https://bitfalls.com/hr/glossary/#proof-of-work
[kriptovaluta]:https://bitfalls.com/hr/glossary/#cryptocurrency
[fungibility]:https://en.wikipedia.org/wiki/Fungibility
[transaction malleability]:https://en.bitcoin.it/wiki/Transaction_Malleability
[ASIC]:https://bitfalls.com/hr/glossary/#asic
[postu]:https://news.bitcoin.com/another-bitcoin-fork-bitcoin-gold-project-plans-to-fork-bitcoin-next-month/
[Bitfallsu]:https://bitfalls.com
[oprezom]:https://twitter.com/btcfork/status/913486988828975105
[scama]:https://www.reddit.com/r/btc/comments/734i6s/as_it_turns_out_adam_backblockstream_may_be/
