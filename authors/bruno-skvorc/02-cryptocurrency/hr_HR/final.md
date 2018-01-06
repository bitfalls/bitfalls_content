Čuli ste za Ethereum, Bitcoin, možda i Tezos, Zcash, Onecoin ili Dash? U ovom uvodnom članku ćemo ukratko predstaviti generalni koncept kriptovaluta na svima razumljiv način. Pogledajmo prvo kako je novac funkcionirao do sada.

## Prošlost novca

*Ovaj dio slobodno preskočite ako vas ne zanima __zašto__ je došlo do razvoja kriptovaluta.*

U prošlosti, ljudi su za razmjenu dobara koristili druga dobra. Jedan vol, primjerice, vrijedio je tri trokuta sira. 

<img src="/wp-content/uploads/2017/08/cryptocurrencies02.png" alt="Razmjena dobara" width="550">

Ta razmjena je funkcionirala jer su obje strane imale direktnu korist od dobra koje primaju. Primatelj sira dobio je zalihe hrane koje su mu bile potrebne da prehrani bližnje, dok je novi vlasnik vola dobio radnu snagu i dobar roštilj kad ta radna snaga oslabi.

S vremenom je došlo do situacije u kojoj je jedna strana transakcije jako htjela ono što druga nudi, ali nije imala dobara za ponuditi za uzvrat. Srećom, do tada se već znalo za plemenite metale i njihovu rijetkost, te se tim materijalima označavalo dugovanje. 

"Dati ću ti ovaj komad zlata kojeg malo tko ima i kojeg samo kraljevi nose oko vrata, ako mi danas daš dvanaest vagona sira."

<img src="/wp-content/uploads/2017/08/cryptocurrencies03.png" alt="Trapa sira za zlato" width="550">

S vremenom su se pojavile banke koje su za ljude čuvale to zlato u sefovima. Umjesto da netko sa sobom nosi teške metale, nosio je papir na kojem mu je banka koja njegovo zlato čuva napisala "Da, ova osoba stvarno ima 15g zlata kod nas". Taj papir se tada davao drugima u svrhu plaćanja, koji su pak u toj istoj banci taj isti papir mogli zamijeniti za to čuvano zlato u bilo kojem momentu.

To je s vremenom rezultiralo uvođenjem "[zlatnog standarda](https://hr.wikipedia.org/wiki/Zlatni_standard)" u kojem se valuta neke nacije povezala s protuvrijednosti u rijetkim metalima. Država je preuzela svo zlato pod prijetnjom zakonskih progona, i svima koji su svoje zlato predali dala takve papirnate zadužnice. Drugim riječima, papirnati novac. No u to vrijeme, papirnati novac bio je direktno vezan za zalihe zlata neke države, te se tako inflacija držala pod kontrolom - zalihe zlata rasle su veoma polako i sve sporije, te se time ekonomska vrijednost društva jednostavno nije mogla prenapuhati. Ljudi su živjeli unutar svojih mogućnosti, i društvo nije trošilo više nego je imalo jer to jednostavno nije bilo moguće.

No, kako je napućenost rasla i ekonomija u SAD tokom 1930-ih stagnirala za vrijeme Velike Depresije, tadašnji predsjednik Franklin Roosevelt odlučio je prekinuti dolar-zlato vezu i naštampati velike količine novog novca (efektivno papirnatih zadužnica) kako bi stimulirao ekonomiju. Mnogi ekonomisti slažu se da je to izbavilo SAD iz depresije, ali je ujedno uzrokovalo nove probleme. Prvo, štampanje novog novca uzrokovalo je ubrzanu inflaciju, jer je u cirkulaciji bilo mnogo više novca nego prije - novca koji nije bio garantiran nikakvom konkretnom vrijednošću već samo dobrom voljom i vjerom građana u svoju državu. Drugo, budući da je do 1971 bilo dopušteno mijenjati dolare za državno zlato a dolari su se tada već na veliko štampali bez pokrića, kešom-bogati građani i stranci počeli su dramatično prazniti državne rezerve zlata.


<img src="/wp-content/uploads/2017/08/cryptocurrencies04.png" alt="Prazne rezerve zlata u banci" width="550">

S modernizacijom i informatizacijom, to štampanje bez pokrića dobilo je nove razmjere - sada je za "proizvodnju" novog novca bilo potrebno kliknuti gumb na sučelju softvera državne banke. Papir, koji se koristio sve manje, nije ni bilo potrebno štampati u nekim velikim količinama. Taj *digitalni novac* koristimo danas svaki put kad plaćamo karticama, preko PayPala, i slično.

Takve valute - bilo digitalne ili štampane - koje koristimo i danas, zovemo *fiat* od latinskog "neka bude". To je novac koji nema neku potporu ni intrinzičnu vrijednost pored one koju je država obznanila. Drugim riječima, novac vrednujemo jer nam je institucija pod kojom živimo zapovijedila da ga smatramo vrijednim. Novac današnjice je u potpunosti centraliziran i pod kontrolom države.

Kriptovalute su nastale kao odgovor na taj problem.

## Kriptovalute

Kriptovalute su jedinstveni digitalni tokeni (digitalni novčići) koje **_nije moguće kopirati ni svojevoljno proizvesti_**, a koji služe određenoj svrsi kada se pošalju s jedne elektroničke adrese na drugu.

_"Čekaj malo"_, možda ste pomislili. _"Pa to zvuči isto kao gornji primjer digitalnog fiat-a, ili kao novčići u raznim mobilnim ili Facebook igrama koje mogu osvojiti ili kupiti za pravi novac da bih brže postigla rezultat!"_.

<img src="/wp-content/uploads/2017/08/dino-land.png" alt="Primjer igre s takvom ekonomijom" width="650">

Ključna razlika je u ovom dijelu: **_nije moguće kopirati ni svojevoljno proizvesti_**. Novčići u igri su *digitalna valuta* i razlikuju se od kriptovaluta na sljedeći način:

- novčići na kakve ste navikli su _**centralizirani**_. Drugim riječima, svu zalihu kontrolira jedna korporacija, kao i s fiat valutom - korporacija koja je vlasnik igre. Kod kriptovaluta, zalihu kontrolira zajednica (tj. [blockchain][blockchain], više o tome kasnije), i svi mogu provjeriti i potvrditi koliko je "novčića" preostalo na kojem računu u bilo kojem momentu, kao i kamo i kada ih je koliko poslano.

- novčići na kakve ste navikli mogu se stvoriti iz ničega i nisu jedinstveni. Daju se kopirati. Količina im nije konačna, i jedino što je potrebno da se promijeni stanje računa nekog igrača je promjena u bazi podataka, bez da se ukupni iznos novčića negdje drugdje smanji - isto kao i s fiat valutama. Ne postoji trošak za proizvodnju novih novčića. Kod kriptovaluta vrijedi suprotno - ukupna količina se zna, i nije moguće stvoriti više novčića na nekom računu bez da se količina na nekom drugom računu za jednako toliko smanji, osim u veoma posebnim situacijama koje objašnjavamo u [blockchain][blockchain] članku.

Znači... radi se samo o softveru? 

Tako nekako.

## Kriptovalute su softver

Kao što na svom računalu ili mobilnom uređaju imate neku aplikaciju (web preglednik, uredski softver, neke igre...), tako je i pojedina kriptovaluta samo softver. Razlika kod kriptovaluta je u riječi _kripto_. Prevedeno na laički, riječ _kripto_ u kriptovalutama znači da ih je nemoguće duplicirati i falsificirati.

> Kriptovalute nije moguće duplicirati ni falsificirati

Dok aplikacije, digitalne dokumente, čak i stanje računa u banci možemo kopirati i prenijeti na drugu lokaciju bez da original nestane, kod kriptovaluta to nije moguće zbog nečega što se zove _blockchain_ (lanac blokova).

Blockchain zaslužuje [svoj posebni članak][blockchain]. Predlažemo da se na taj članak osvrnete odmah nakon ovog kako biste shvatili na koji se način ta postojanost ostvaruje i garantira u nedogled.

## Kriptovalute nisu valute

Bitno je shvatiti da kriptovalute uopće nisu valute u pravom smislu riječi.

Definicija riječi "protokol" je: "set pravila koji definira razmjenu podataka između krajnjih točaka". Da bi vam sljedeći paragraf bio jasniji, povucimo (jednu veoma nekonvencionalnu) usporedbu. Svi koristimo vodovodnu mrežu. Način na koji se voda šalje s jednog mjesta na drugo je da se s jedne strane cijevi vodu gura, dok s druge strane izlazi. Takav sustav prijenosa vode možemo nazvati **protok**olom - protokol za prijenos vode je gurkanje kubika vode (jedinica prijenosa) kroz cijev (medij prijenosa).

Bitcoin i Ethereum su protokoli - načini da se podaci prenesu s jedne elektroničke lokacije na drugu. Svaki protokol ima vrstu podataka koju preko njega šaljemo (kubici vode u primjeru gore). U svijetu kriptovaluta te podatke zovemo *token* nekog protokola pa tako u Bitcoin protokolu imamo istoimeni Bitcoin, ili 1 BTC. U Ethereum protokolu, to je 1 Ether. 1 Bitcoin je token bitcoin protokola. 1 Ether je token Ethereum protokola.

Kriptovalute su dakle tokeni nekog protokola, softver, skupina podataka koju šaljemo s jedne lokacije na drugu na način da svim korisnicima sustava (korisnicima tog protokola) u kojem te podatke šaljemo to **istovremeno i najavimo**. Kada se token šalje s jedne adrese (tj. novčanika) na drugu, broj tokena se na početnoj adresi smanjuje, a na odredišnoj povećava, i svi korisnici tog protokola tome svjedoče i to potvrđuju.

> Slanje kriptovaluta nije ništa drugo nego **javno objavljena i provjeriva informacija** da nekom korisniku nekog protokola šaljemo token tog protokola.
Podaci (tokeni) koji se šalju nemaju neku vrijednost sami po sebi. Tu vrijednost smo im dali mi: korisnici. U slučaju "vodenog protokola" gore, voda sami po sebi nema vrijednost. No jednom kada smo shvatili da je možemo koristiti za sve od pića i kuhanja do pranja i proizvodnje struje, tu vrijednost smo joj sami pripisali. Ponavljamo:

> Kriptovalute imaju vrijednost jer smo mi tako odlučili, a ne neki centralni autoritet

Isto kao što svijet kolektivno može preko noći odlučiti da zlato više ne vrijedi i sada je obični metal (time da ga prestane kupovati), tako bi i svjetski kolektiv mogao smanjiti ili povećati vrijednost neke kriptovalute. Upravo to se i dešava kada vidimo skokove u cijenama. Primjerice, evo grafa cijene Bitcoina u dolarima od 2010 do 15.08.2017.:

<img src="/wp-content/uploads/2017/08/Screenshot-2017-08-20-19.01.57.png" alt="Bitcoin graf 2010-2017">

Dok cijenu uglavnom diktira ponuda i potražnja (ako više ljudi zna za kriptovalute i njihov potencijal, više ljudi ih želi i cijena raste), neki skandali, problemi, napredci, razvoji, i slično također utječu na percipiranu vrijednost. Najbitnije u svemu tome je da *mi* - **društvo** - a ne bankari i političari - određujemo vrijednost ove valute, i da se ista ne može napumpati ako vlada odluči da je nema dovoljno.

## Zaključak

- kriptovalute su "novčići" (tokeni) koje šaljemo preko određenog protokola, i svaki protokol ima svoj token. Bitcoin ima Bitcoin, Ethereum ima Ether, Augur ima REP, itd.
- svaki protokol ima svoju posebnu svrhu. Bitcoin je zamjena za tradicionalne valute, Ethereum je tu da se na njemu grade drugi tokeni, Siacoin je tu za spremanje datoteka, Augur služi za predviđanje budućnosti, Zcash bi trebao biti anonimni Bitcoin, Onecoin je piramidalna šema, itd.
- svaki token je unikatan - nije ga moguće duplicirati
- svaka transakcija na tim protokolima (osim u slučaju Zcash-a, Monera, i slično) je javna (vidi se tko kome što šalje).

## Kamo dalje?

Sada kada imate generalnu ideju o tome što su kriptovalute, naučite kako funkcioniraju i zašto su postale tako popularan pojam. Predlažemo sljedeće članke:

- [Što je blockchain][blockchain] - da biste saznali *kako* kriptovalute funkcioniraju
- [Što su i kako funkcioniraju novčanici za kriptovalute][wallet] - saznajte kako do svog prvog novčanika, te kako ih osigurati
- [Koliko su kriptovalute anonimne?][anon] - saznajte sve o transakcijama i njihovoj anonimnosti
- [Što je Ethereum?][eth] - saznajte osnove o najmoćnijoj kriptovaluti i po čemu se razlikuje od Bitcoina

[blockchain]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[wallet]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[finite]: https://bitfalls.com/hr/2017/09/17/bitcoin-finite-just-myth/
[anon]: https://bitfalls.com/hr/2017/09/18/anonymous-cryptocurrencies-like-bitcoin/
[eth]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
