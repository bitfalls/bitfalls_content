Čar [blockchaina][bc] je ta da se u bilo kojem trenutku netko može odlučiti na grananje u novi ako se ne slaže s smjerom u kojem se neki blockchain razvija. 

Takva je situacija bila u kolovozu s nastankom Bitcoin Casha koji je htio povećati [veličinu blokova][blockex] kako bi u njih stalo više transakcija, za razliku od "glavne" Bitcoin Core ekipe koja je htjela odstraniti određeni dio podataka iz transakcija u posebni lanac. Time bi se smanjila veličina transakcija i postiglo  to da ih više stane u postojeći [blok][block].

Kad se takvo grananje desi, granu koja se odcijepila od glavnog lanca zovemo _spornom granom_ ili _contentious fork_-om. Više o samom činu _forkanja_ u nadolazećem članku.

## Segwit2x i BTG

![Grananje puta](https://bitfalls.com/wp-content/uploads/2017/10/01-3.jpg)

Uskoro se dešavaju dvije nove takve grane. Objasnimo ih ukratko.

### Segwit2x

U studenom (cca 18.11.) će vjerojatno doći do Segwit2x grane. Segwit2x grana se navlači još od Bitcoin Cash debakla, a radi se o političkim razlozima i neslaganjima. Kao što smo rekli, Bitcoin Cash grana se desila jer se jedna ekipa protivila Segwit nadogradnji (odvajanju dijela transakcija kako bi se smanjilo njihovu veličinu i više ih stalo u blokove) i zagovarala je povećanje blokova. Ta grupa je formirala Bitcoin Cash. Bitcoin Core pak je ostao pri svome, i implementirali su Segwit transakcije, no postotak ljudi koji ih koristi i softvera koji ih je implementirao je razočaravajuće malen, dok su transakcije i dalje skupe i spore. Zato na Bitcoin mreži slanje 5kn može koštati 50kn i trajati 12h, što je naprosto neupotrebljivo.

S tehničke strane, jedna grupa želi povećati veličinu blokova, dok se druga tome protivi. Ako blokovi ostanu mali, mora se raditi na rješenjima koja miču transakcije iz glavnog blockchaina u takozvane _sidechains_, sestrinske lance u kojima se u posebnom kontekstu obavljaju određene transakcije. Primjerice, u dućanu nije potrebno potvrditi svaki najmanju transakciju na glavnom blockchainu jer je to skupo i sporo (minimalno 10 minuta). Umjesto toga, otvara se posebni platni kanal u kojem se transakcije agregiraju između više stranaka, recimo dućana i mušterija, i tada se sve zajedno potvrdi na kraju dana kao jedna transakcija. Sustav još uvijek ostaje siguran, ali je brži i jeftiniji. 

![Stara kasa](https://bitfalls.com/wp-content/uploads/2017/10/02-3.jpg)

No, transakcije u sidechainovima miču profite iz glavnog blockchaina. Transakcije koje se ne odvijaju na glavnom lancu ne bivaju potvrđene od rudara, što znači da oni ne dobivaju proviziju od istih i nagrada za rudarenje im se smanjuje. Prebacuje ih se u sestrinske lance, za koje se specijalizira tvrtka Blockstream (više zanimljivosti o tome u tekstu ispod).

S druge strane, ovi koji se zalažu za veće blokove su većinom rudari, jer to najviše njima koristi. Ako više transakcija stane u blok, transakcije koštaju manje, više ih se obrađuje, a rudari svejedno kao i prije primaju nagrade - ponekad i veće jer je u blokovima mnogo više transakcija, svaka od kojih ima svoju proviziju. Idealno bi bilo kombinacija oba sistema, no zbog političkih nesuglasica i prepirki, obje strane su postale ekstremističke i odbijaju bilo kakav kompromis.

Realno gledano, Bitcoin blockchain je tehnološki retardiran kad se usporedi s gotovo bilo kojim drugim blockchainom - jedino zašto se održava na vrhu je jer ima _first mover advantage_ ili prednost prvog pokretača. Bio je prvi, ima brend, prepoznaju ga novine, bake i djedovi, slavne osobe. No s tehničke perspektive, jedna je od najlošijih blockchain tehnologija trenutno na tržištu - Ethereum, recimo, već danas izvršava više transakcija od Bitcoina, a nema samo monetarnu stranu već služi [i za programiranje][eth]. Upravo zbog tih nedostataka razvojni inžinjeri koji rade na poboljšanju Bitcoin sustava ulaze u razne prepirke oko najboljih pristupa.

Uz to, kroz zadnjih godinu dvije, prije spomenuta tvrtka Blockstream organizirala je ne samo cenzuru [/r/bitcoin](https://reddit.com/r/bitcoin) Reddit kanala (online foruma za raspravu o Bitcoinu) i time uzrokovala kreaciju [/r/btc](https://reddit.com/r/btc) kanala, već je izgurala i neke od programera iz tima koji radi na originalnom Bitcoin blockchainu. Ostali su programeri kojima je logika upitne prirode (jedan od glavnih vjeruje, primjerice, da se sunce okreće oko zemlje, između [ostalih bisera](https://www.reddit.com/r/Buttcoin/comments/4936kw/lukejr_is_a_seriously_a_super_crazy_person_quotes/)), i većina ih je plaćena od same tvrtke Blockstream. Dok komercijalna podrška javnom projektu otvorenog koda zvuči sasvim dobro i altruistički, treba samo [malo istraživanja][research1] da se iskopaju [informacije][research2] da je Blockstream pod komandom [Bilderberg grupe](https://en.wikipedia.org/wiki/Bilderberg_Group): grupe koja upravlja većinom banaka i financijskih sustava svijeta, kojima je cilj uništiti kriptovalute jer im predstavljaju egzistencijalnu prijetnju. Samim time postaje mnogo vidljivije da se u razvoj Bitcoina guraju sve neefikasnija rješenja s ciljem uništenja iznutra.

![Silueta čovjeka koji se veseli pred velikim znakom kovanice Eura](https://bitfalls.com/wp-content/uploads/2017/10/03-2.jpg)

Kao što je to bilo s Bitcoin Cash, tako će i novi fork - B2X - dati "besplatni" Bitcoin u istoj količini koju imate sada. Znači ako imate 1 BTC sada, 18.11. imati ćete 1 BTC i 1 B2X. Za upute kako do tih tokena, pogledajte sekciju "Kako do tokena" pri kraju ovog članka.

### Bitcoin Gold

Bitcoin Gold je kao ideja isplivao negdje [u sedmom mjesecu][btgann]. Ukratko, Jack - autor teme na forumu - predložio je da Bitcoin Gold bude "spas" Bitcoina na način da ga oslobodi od firmi poput Bitmaina. 

Bitmain je veliki proizvođač [ASIC][asic] minera, tj. uređaja koji služe za najefikasnije moguće [rudarenje][mining] Bitcoina, i ujedno tvrtka koja ima veliki monopol nad procesnom moći koja upravlja Bitcoin blockchainom. Kalkuliranje Bitcoin hasheva je uvelike centralizirano u Kini, i barem 40% te moći je u rukama te jedne tvrtke.

Njegov je cilj, kaže, da Bitcoin bude otporan na ASIC rudarenje i time bude opet dostupan običnim rudarima s grafičkim karticama.

Dok to zvuči lagano utopistički, Bitcoin Gold ima svojih problema.

1. Do samog dana kada su planirali lansirati svoj proizvod, nisu napravili [gotovo ništa][trello] od tehnološkog razvoja.
2. [Kod][btggh] im je "u banani", softver se ne uspijeva niti pokrenuti
3. Vlasnik projekta je vlasnik tvrtke koja prodaje opremu za mining, nedvojbeno specijaliziranu baš za tip računanja kakav je BTG-u potreban
4. Kažu da će BTG biti otporan na ASIC, no procedura te otpornosti nigdje nije opisana (nemaju ni prezentacijski dokument u kojem objašnjavaju tehničku stranu) a niti je realna, sudeći prema kodu u kojem nema gotovo nikakve zaštite.
5. Fork se već desio, i izrudarili su nešto BTGa prije nego su uopće spremni lansirati BTG. To znači da su lagali na svojoj stranici i na objavama i tajili tu informaciju od mogućih investitora.
6. Isti ljudi koji imaju BTGGPU web domenu na kojoj reklamiraju Bitcoin Gold imaju i [ove][domains] sumnjive domene.
7. Kao što je to otkrio [ovaj redditor][reddit], BTG je izrudaren unaprijed, držan u tajnosti, ponuđen ljudima kao ICO - inicijalnu ponudu tokena - (po cijeni od 10 BTG za 1 BTC), i nakon neuspješnog ICOa kompletno zatajen i predstavljen kao Bitcoin Gold fork.

Zabrinjavajuće.

![Zabrinuta viktorijanska žena, ilustracija](https://bitfalls.com/wp-content/uploads/2017/10/04-4.png)

Sve u svemu, BTG zvuči kao dobro isplanirana prevara koja bi postavila plodno tlo za _replay attack_ napade koji su dizajnirani da kradu sredstva naivnim i/ili pohlepnim investitorima (više o replay attack napadima dolje). Naš je prijedlog da je se klonite u širokom luku, ili barem sačekate 3-4 tjedna do kada se prava istina i svrha ne otkriju. 

Ovo je, začudo, jedna stvar u kripto svijetu oko koje se svi drugi forkovi i blockchainovi slažu.

## Fork Efekt

Nažalost, većina ljudi je izuzetno pohlepna, i kad čuje "fork" odmah pomisli na besplatne tokene. Uz [određene manipulacije][fraud], to uzrokuje mahnito kupovanje BTCa prije forka (zato cijene često rastu), i mahnito prodavanje forkanih tokena nakon forka. Ali... ako svi prodaju, tko kupuje?

Ako ste i vi jedni od tih koji su pokleknuli, pazite da ne završite kao [bagholder].

Do brzih profita nećete doći brže nego da samo [kupite obećavajuću valutu][buycc], i čekate. Forkovi su često zamke i varke s ciljem da vas učine ranjivima na replay attack (napad ponavljanja), i mogu vas ozbiljno oštetiti.

## Replay Attack

Kad se desi _fork_, dio softvera koji potpisuje transakcije i šalje ih na mrežu na potvrde (više [u uvodu ovdje][bc]) često ostaje isti, osim ako lanac koji se odcjepljuje ne zamijeni taj dio u svom kodu. To znači da se svaka transakcija koja bude poslana na lancu A može jednostavno ponoviti na lancu B bez prisutnosti sudionika, jer je već generirana i validna. To kopiranje transakcije s jednog lanca na drugi zove se _replay attack_ ili _napad ponavljanja_.

![Dvije strelice koje se vrte u krug, jedna pokazuje prema kraju druge](https://bitfalls.com/wp-content/uploads/2017/10/05-4.png)

Zamislite ključ od ulaznih vrata vaše kuće. Ako ga netko kopira, kopija isto otključava vaša vrata. Jedini način da svoja vrata osigurate je da promijenite bravu, jer ne znate tko do sada već ima kopiju vašeg ključa, i loviti jednu po jednu nije efikasno.

Bitcoin Cash je odmah prilikom forkanja ugradio _replay protection_ ili _zaštitu od ponavljanja_, time osiguravši mrežu i učinivši transakcije validnima samo na jednom od dva lanca. Mnogo forkova koji se stvaraju napravljeni su upravo iz razloga da skupljaju velike transakcije na jednom lancu softverom poput [Blockexplorera][blockex], i ponove ih, kradući tako sredstva s glavnog lanca.

Bitcoin Core (trenutni glavni lanac Bitcoina) mogao je već odavno uvesti replay protection u glavni lanac, i time učiniti sve buduće forkove bespomoćnima što se napada tiče, no iz nekog razloga nije.

Treba se napomenuti da je veoma teško implementirati replay protection u lance koji već dugo postoje, jer je količina softvera koji je potrebno nadograditi enormna, pa je logičnije da forkovi - koji ionako guraju novi softver da bi se protivili starome - ugrade to u svoj.

### Kako bi BTG mogao iskoristiti Replay Attack?

Napominjemo da BTG tim **tvrdi da su implementirali replay protection** ali je [dokazano da nisu][btgrp].

Evo kako vas replay attack može oštetiti:

- 1. korak: naivni investitor je kupio 2 BTC da dobije besplatnih 2 BTG
- 2. korak: osoba iza BTG projekta (nazovimo je Jack) impersonira kupca BTGa na nekoj burzi, i kupuje BTG po kojoj god cijeni - $500 ili $1500, nebitno.
- 3. korak: Jack uzima kopiju transakcije u kojoj je kupio BTG od investitora
- 4. korak: Jack šalje transakciju u istom obliku na glavni Bitcoin lanac
- 5. korak: ako investitor još uvijek ima 2 BTC na svojoj adresi, tih 2 BTC se šalju na Jackovu adresu. Jack je sada zaradio 2 BTC, minus cijena koju je platio za BTG.

Sada pomnožite ovaj scenarij s brojem ljudi koje ste primijetili da se raspituju o BTG u zadnjih nekoliko tjedana.

![Zabrinuti robot igračka](https://bitfalls.com/wp-content/uploads/2017/10/06.jpg)

Budući da BTG nema replay protection, kako se osigurati?

- opcija 1: pošaljite BTC na neku drugu vlastitu adresu prvo, i tek tada trgujte s BTG
- opcija 2: počekajte dok se ne pokaže finalni cilj BTGa - vjerojatno par tjedana. Ne dajte da vas pohlepa povuče u instantnu prodaju.

## Kako do tokena

Jedini **100% sigurni način** za prisvajanje forkanih tokena je taj da imate svoj vlastiti privatni ključ vaše adrese. Ako imate kriptovalute na nekoj mjenjačnici, ta mjenjačnica će odlučiti hoće li vam ili ne dati jednaki iznos forkanog tokena - oni imaju svako pravo zadržati ih za sebe.

Ponavljamo, **jedini** način koji je 100% siguran je taj da ste u potpunoj kontroli svog novčanika.

Ako niste sigurni kako novčanici rade, [ovdje][wallet] smo to objasnili. Da osigurate svoje tokene - i originalne i forkane - koristite jedan od [ovih načina][paranoia] ili [kupite][shop] neprobojni [Ledger Nano S uređaj][ledger]. Ili jednostavno generirajte svoju adresu [ovako][startbtc].

Nakon forka, malo sačekajte (barem tjedan dana) da vidite jesu li _replay attackovi_ prijetnja, i tek tada preuzmite svoj alternativni token. Do tada ćete već znati koja mjenjačnica ga podržava, i s lakoćom ćete ga poslati tamo i zamijeniti za nešto bolje.

Ako ste nesigurni u svoje mogućnosti čuvanja privatnog ključa, ili vam sve to još uvijek zvuči pre-mistično, slobodno nam se javite oko usluga [upravljanja portfeljom][folio]. Uzet ćemo vam proviziju, da, ali ćemo garantirati iznos koji dobivate bez obzira na bilo kakve probleme i odraditi to profesionalno.

## Zaključak

POLAKO!

![Cesta s lažnim znakom djeteta i natpisom "slow" za "polako", kao način usporavanja vozača](https://bitfalls.com/wp-content/uploads/2017/10/07.jpg)

Budite veoma skeptični oko svakog forka, i istražite čim više okolnosti koje su do njega dovele. Pričajte s ljudima, ne sramite se pitati, i ne nasjedajte na senzacionalističke naslove nestručnih publikacija.

Ako ne razumijete o čemu se radi, ili vas neki pojmovi zbunjuju, pitajte - tu smo. U komentarima, na FB, na Twitteru, na mailu - ovdje smo da pomognemo i spriječimo gubitke.

Ne nasjedajte na marketinške kampanje, ignorirajte optimističnu rodbinu, i svemu u kripto svijetu prilazite s zdravom dozom skepse - industrija je još premlada da bi većina ljudi u njoj bila poštena.

Trgujte pažljivo!

[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[eth]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
[research1]: https://www.reddit.com/r/btc/comments/47zfzt/blockstream_is_now_controlled_by_the_bilderberg/
[research2]: https://www.reddit.com/r/btc/comments/4v26v9/is_there_a_source_that_explains_the_whole/
[blockex]: https://bitfalls.com/hr/2017/10/03/read-bitcoin-blockchain-data-blockexplorer/
[block]: https://bitfalls.com/hr/glossary/#block
[buycc]: https://bitfalls.com/hr/how-to-buy-cryptocurrency/
[fraud]: https://bitfalls.com/hr/2017/10/21/fraudulent-tethers-used-margin-trading-bitfinex/
[bagholder]: https://bitfalls.com/hr/glossary/#bagholder
[wallet]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[paranoia]: https://bitfalls.com/hr/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[ledger]: https://bitfalls.com/hr/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[shop]: https://bitfalls.com/shop
[folio]: https://bitfalls.com/portfolio-management/
[btgann]: https://bitcointalk.org/index.php?topic=2046790.0
[asic]: https://bitfalls.com/hr/glossary/#asic
[mining]: https://bitfalls.com/hr/2017/10/12/mining-investing-cryptocurrency-better/
[startbtc]: https://bitfalls.com/hr/2017/09/01/send-receive-bitcoin/
[btgrp]: https://github.com/BTCGPU/BTCGPU/issues/51
[trello]: https://imgur.com/a/tZja4
[btggh]: https://github.com/BTCGPU/BTCGPU/commit/e7bfc903d97bb160e13d2674506591aa7878d726
[domains]: [https://i.imgur.com/HG31eie.png](http://viewdns.info/reversewhois/?q=xiangliao%40gmail.com)
[reddit]: https://www.reddit.com/r/CryptoCurrency/comments/757jf4/here_is_why_bitcoingold_is_shady_and_a_scam_you/