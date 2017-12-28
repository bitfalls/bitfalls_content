Troškovi transakcija u [Bitcoin][cc] (BTC) sustavu danas [znaju doseći][fees] i do $60 bez obzira na iznos koji šaljemo. Sam [protokol][bc] redovito ima više od [200,000 nepotvrđenih transakcija][unconf] u redu čekanja koje znaju biti zaglavljene i po tjedan dana. Sve više tvrtki i pružatelja platnih usluga na kriptovalutama [preferira alternative][bchalt] ili [kompletno napušta][steam] kripto sferu. 

Bitcoin je postao neupotrebljiviji od tradicionalnih SWIFT prijenosa. Mnogi, pa čak i [Bitcoin maksimalisti][max], prestaju Bitcoin smatrati transakcijskim sredstvom ili zamjenom za fiat valute i gledaju ga kao _Store of Value_ ili sredstvo pohrane vrijednosti kao što je to zlato.

U ovom ću članku iznijeti argumente zašto Bitcoin nikada ne može postati **digitalno zlato**.

## 1. Zlato se ne mrvi kad ga mičete s jednog kraja stola na drugi

Ako zlato imate na jednom kraju stola i pomaknete ga na drugi kraj, zlato ostaje u jednom komadu. Kod BTCa s ovakvim troškovima transakcija zlato kao da se mrvi. 

![Zlato se mrvi](https://bitfalls.com/wp-content/uploads/2017/12/01-1.jpg)

Ako imam 2 grama zlata koji vrijede $100 i da ih pomaknem metar u stranu moram odvojiti $60 (dakle 60%) koje nikada više neću vidjeti, ne bih to zlato nikad micao. Obrana protiv ove tvrdnje često se svodi na "_prenijeti kilu zlata iz Brazila u Njemačku je isto skupo_". Da, ali udaljenost prijenosa je proporcionalna cijeni.

Kod BTCa, slanje bitcoina na adresu osobe koja je u istoj sobi košta isto toliko koliko biste platili da ih šaljete na drugi kraj planete. To čini bilo kakve transakcije u dućanima nemogućima, i to ne samo zbog cijene transakcije nego i jer transakcije trenutno znaju trajati po nekoliko dana prije nego se potvrde. Ni jedan dućan - bez obzira na to koliko mu je roba skuplja od tih transakcija - ne može tako funkcionirati.

To nas dovodi do drugog argumenta protiv teorije o pohrani vrijednosti.

## 2. Da zlato ostane u vašem vlasništvu, gravitaciji ne plaćate najam

Da bi Bitcoin kao sustav opstao, ovisi o [rudarima][powpos]. Rudari su računala koja vrte [_full nodes_][nodes] i obrađuju transakcije Bitcoin sustava. Rudari za svoj radi bivaju nagrađeni [block reward][bw]-om koji trenutno iznosi 12.5 BTC po [bloku][block]. Blokovi se otkrivaju u prosjeku svakih 10 minuta, što znači da se 12.5 novih BTC proizvede svakih 10 minuta i ta nagrada ide rudaru koji je izrudario taj block (više o tom procesu [ovdje][bc]). 

[![Ilustracija iz članka https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/](https://bitfalls.com/wp-content/uploads/2017/08/blockchain-08.png)](https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/)

Uz block reward, rudari dobivaju i nagradu u visini troška transakcije za sve transakcije u tom bloku. Tako recimo ukoliko je u [jednom bloku 1000 transakcija][blockex] a svaka od njih košta $60, rudar koji otkrije taj blok biva nagrađen s $60000 + 12.5 * $16000 (trenutna cijena BTCa), ili ukupno nekih $260,000.

No, svakih 4 godine block reward se smanjuje na pola. To je pravilo koje je ugrađeno u sam Bitcoin protokol. Tako će već 2048 (gotovo punih 100 godina prije nego će ["zadnji"][finite] bitcoin biti izrudaren) nagrada za rudareni block biti samo 0.025 BTC, a 2052 0.0125 BTC. Čak i uz BTC cijenu od $1,000,000, nagrada od 0.0125 BTC je samo $12500 - manje od današnje cijene jednog bitcoina.

Ako nitko ne miče svoje bitcoine jer se sve sudionike sustava [ohrabruje][finite] da ih zbog potenijala rasta vrijednosti samo čuvaju, u sustavu nema transakcija. Ako nema transakcija, nema ni provizija kojima rudari bivaju nagrađeni kada block reward postane ovako zanemarivo malen. Ako se rudarima - koji će do 2048 imati rudarske postrojbe u visinama nekoliko miljardi dolara (bliže se tim ciframa već sada) - obeća nagrada od jedva $25,000 svakih 10 minuta, to nije ni blizu isplativosti. Rudari će izaći iz sustava i preći na druge valute koje su isplativije. Bez rudara ne može biti transakcija jer ih nema tko obraditi, i to "zlato" postaje nepomično i bezvrijedno. Uz to, s malim brojem rudara [problem centralizacije][isps] postaje još ozbiljniji. Bitcoin ulazi u spiralu smrti.

![Spirala smrti](https://bitfalls.com/wp-content/uploads/2017/12/02.jpg)

Situacija u Bitcoinu je ekvivalentna plaćanju najma gravitaciji da vaše zlato zadrži na mjestu. Bez da nastavite plaćati taj najam (vi ili netko drugi - u slučaju BTCa to plaćaju rudari koji imaju ogromne operacijske troškove), vaše "zlato" će ispariti i nestati. Da bi BTC opstao kao sredstvo pohrane vrijednosti **rudari moraju rudariti na prazno**. Zato BTC nikada neće biti digitalno zlato osim ako ne prihvate jedno od sljedećih rješenja:

1. Postepeno povećavati blokove po potrebi i time smanjiti problem propusnosti mreže. Čest argument protiv toga je da su računala potrebna za vrtnju [_full node_][nodes] softvera tada prezahtjevna i nepristupačna nerazvijenim dijelovima svijeta što bi uzrokovalo centralizaciju. S obzirom na to da 60% cijelog Bitcoin prometa prolazi kroz samo 3 ISP-a (više o tome [ovdje][isps]) i da su transakcijski troškovi trenutno u visini tjedne plaće tih nerazvijenih dijelova svijeta, smatram da je taj argument nevažeći. Ovo je pristup za koji se odlučio [Bitcoin Cash][cash].
2. Preći na [PoS][powpos] sustav na koji prelazi Ethereum a koji ne zahtjeva rudarenje i time miče ogromni infrastrukturni trošak iz cijele jednadžbe. Ovo kod BTC nije vjerojatna opcija jer ugrožava velike industrijske rudare i tvrtke kojima je u interesu da je Bitcoin mreža spora i neupotrebljiva, a oni su preveliki i pre moćni da propadnu.
3. Promijeniti Bitcoin softver na način da se makne limit od ukupno 21 miljun bitcoina ili prekine smanjivanje block rewarda. [Smatram][finite] da je to najvjerojatniji ishod jer su tvrtke koje kontroliraju proizvodnju BTCa (industrijski rudari) i tvrtke kojima posao ovisi o sporosti i skupim naknadama Bitcoin mreže prevelike da propadnu i u interesu im je održati status quo u nedogled.

![Korupcija](https://bitfalls.com/wp-content/uploads/2017/12/03-2.png)

Ako mislite "_ali 2048 je 30 godina daleko, svašta će se do tada promijeniti_" sjetite se samo da je Bitcoin već sada star 10 godina, a politički rat oko povećanja blokova i ubrzanja mreže traje već 3 godine. Tehnologija ne napreduje ni približno tom brzinom kojom bi trebala ako želimo stići do praktičnih rješenja do 2048, a problemi će ionako postati očitiji mnogo prije.

## Zaključak

Bitcoin maksimalisti često daju dvije tipične obrane na ove argumente:

1. "Lightning Network (specifična nadogranja BTC mreže) će omogućiti instantno i besplatno trgovanje u Bitcoinu i donijeti transakcijske brzine od nekoliko miljuna transakcija u sekundi". Taj argument pobijamo u našem nadolazećem članku o Lightning Networku.
2. "Koristite nešto drugo za plaćanje, poput Litecoina, a BTC koristite kao sredstvo pohrane vrijednosti". Ovaj argument nema smisla jer ne samo da ne rješava probleme iznesene gore, nego i jasno daje do znanja da je BTC mreža neupotrebljiva. Ako je odgovor na "sustav A ne radi" "koristite sustav B", onda to nije rješenje problema sustava A, nego priznanje da isti više nije upotrebljiv za svoju originalnu svrhu. 

Ako spojimo navedene nedostatke Bitcoina s činjenicom da na njemu nije moguće programirati kao što je to moguće se [Ethereumom][eth] (čime dokazujemo da Bitcoin nema _upotrebu_), te uzmemo u obzir da je strahovito [ranjiv i centraliziran s infrastrukturne strane][isps] i veoma [ranjiv][unstop], logično je biti skeptičan prema tom protokolu. 

![Skeptik](https://bitfalls.com/wp-content/uploads/2017/12/04.jpg)

No, odakle mu onda ova silna vrijednost? Kako može vrijediti $16000+ po BTCu ako nije upotrebljiv? To smo pokrili u analizi Tethera i njihovog utjecaja na tržište - više o tome [ovdje][tether]. Uz to, zapitajte se što se zapravo dešava kada kupite BTC na nekoj burzi - imate li taj BTC odmah, ili se samo promijeni stanje vašeg računa na njihovoj stranici? Je li BTC zapravo kod vas ako ste ga tako kupili? Kako možete biti sigurni da iza te brojke, koja je samo brojka u njihovoj bazi podataka, stvarno i stoji neka količina pravih bitcoina osim ako ih ne povučete na [vlastiti novčanik][wallet]? Mislite li da bi Coinbase i slične platforme stvarno micali BTC na svaku malu kupnju uz transakcijske troškove od $30-60?

Postoji jasna definicija piramide ili ponzi šeme: ako neki proizvod ne može opstati samom prodajom tog proizvoda, već njegov uspjeh ovisi većinom ili u cijelosti o tome koliko drugih ljudi uđe u taj isti sustav, radi se o piramidi ili u najboljem slučaju mjehuru. Trenutno se čini kao da Bitcoin sve više kreće prema tome. Hoće li se to promijeniti? Kao bitcoin ulagač, nadam se. Kao bitcoin skeptik, davno sam diversificirao svoj portfolio.

[unconf]: https://blockchain.info/unconfirmed-transactions
[max]: https://bitfalls.com/hr/glossary/#bitcoin-maximalist
[eth]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
[isps]: https://bitfalls.com/hr/2017/11/29/new-threat-bitcoin-internet-service-providers/
[bchalt]: https://www.ccn.com/xapo-president-biggest-bitcoin-companies-move-bitcoin-cash-ethereum/
[steam]: https://www.theverge.com/2017/12/6/16743220/valve-steam-bitcoin-game-store-payment-method-crypto-volatility
[tether]: https://bitfalls.com/hr/2017/10/21/fraudulent-tethers-used-margin-trading-bitfinex/
[fees]: https://bitcoinfees.info/
[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[powpos]: https://bitfalls.com/hr/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[nodes]: https://bitfalls.com/hr/2017/11/26/whats-bitcoin-node-mining-vs-validation/
[bw]: https://bitfalls.com/hr/glossary/#block-reward
[block]: https://bitfalls.com/hr/glossary/#block
[finite]: https://bitfalls.com/hr/2017/09/17/bitcoin-finite-just-myth/
[cash]: https://bitfalls.com/hr/2017/10/24/bitcoin-forks-bitcoin-gold-scam-stay-safe/
[wallet]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[blockex]: https://bitfalls.com/hr/2017/10/03/read-bitcoin-blockchain-data-blockexplorer/
[unstop]: https://bitfalls.com/hr/2017/08/21/is-bitcoin-unstoppable/