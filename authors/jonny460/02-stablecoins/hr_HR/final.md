Volatilnost cijena je poznata karakteristika [kriptovaluta](https://bitfalls.com/hr/2017/08/20/cryptocurrency/). U neku se ruku to pokazalo pozitivnim, privukavši velike investicije, no na mnoge je načine ta volatilnost usporila razvoj nekih [blockchain](https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/) servisa.

Preteško je poslovati u kriptovalutama, posebice u tradicionalnom svijetu izvan blockchaina. Koliko god to klijenti željeli, rizik je prevelik. Volatilnost isto tako usporava i razvoj usluga za [decentralizirane financije](https://bitfalls.com/hr/tag/defi/) poput blockchain kredita, osiguranja, i slično. Kako bi neki posao mogao funkcionirati na mediju kojem vrijednost može preko noći pasti za 30%?

Stabilnost je ključna. Mnogi smatraju _stablecoinove_ vitalnim korakom za napredak u rastućem području kriptovaluta. _Stablecoin_ je kriptovaluta koja je fiksirana na vrijednost nekog stabilnog dobra.

Trenutno u svijetu postoji desetak stablecoinova koji vrijednost fiksiraju na sve od fiat valuta do zlata i čak drugih kriptovaluta. Najpoznatiji (i ujedno najnotorniji) je Tether USDT.

U rujnu 2018., Gemini Trust Company pokrenuli su svoj ERC-20 token GUSD koji vrijednost fiksira na USD. Razlika od ostalih je u tome što je ovaj pod potpunim nadzorom regulatora.

Neki tvrde da je regulatorni nadzor ovih projekata i pojačano proganjanje nepravilnosti kakvo vidimo u nedavnom slučaju [NYAG vs Bitfinex](https://www.youtube.com/watch?v=UjQjq1eWqCc) veoma pozitivan pomak. No, ako ta ideja nije nova, zašto je takav razvoj događaja toliko bitan? Da odgovorimo na to pitanje moramo pogledati neke od trenutno dostupnih stablecoinova.

## Kolateral u fiat valuti

Najveći udio tržišta stablecoinova uzimaju valute koje su kolateralizirane fiatom. Ti su tokeni zapravo zadužnice: svaki token je podupren određenom količinom fiat valute koja stoji u rezervi kompanije koja tim coinom upravlja. U nekim slučajevima korisnici tih stablecoinova mogu izravno zamijeniti fiat za stablecoin i obrnuto, a saznanje da je svaki token pokriven nekom stvarnom vrijednošću (ili potpuno kolateraliziran) održava cijenu stabilnom. Jednostavan koncept no kompromis je u tome da je potrebna određena količin povjerenja prema onima koji upravljaju tim stablecoin projektom.

### Tether (USDT)

![Tether logo](https://bitfalls.com/wp-content/uploads/2018/10/tether.png)

[Tether](https://tether.to), o kojem [smo već pisali](https://bitfalls.com/hr/2017/10/21/the-curious-tale-of-tethers/), je najveće ime u stablecoin prostoru. Pokrenut 2015. pod imenom Realcoin, Tether štampa USDT, stablecoin kolateraliziran fiatom. To znači da za svaki od 2.8 milijarde USDTa koji postoje u cirkulaciji u teoriji postoji 1 USD na bankovnim računima Tethera za koje korisnici mogu zamijeniti svoj USDT. Ta tvrdnja cijenu drži stabilnom oko $1.

Kao prvi stablecoin široke upotrebe, Tether je prvi dopustio lako osiguravanje sredstava u padovima tržišta i besplatno micanje sredstava s jedne na drugu mjenjačnicu i iz jedne kriptovalute u drugu. 24-satni volumen Tether trgovanja redovito prelazi 75% ukupne količine u cirkulaciji, što pokazuje da većina trgovaca drži USDT samo na kratke periode.

Tether je ono što podmazuje kotačiće mnogih mjenjačnica, no privlači i pažnju budnih promatrača. [Pitanje oko kolateralizacije](https://bitfalls.com/hr/2017/10/21/the-curious-tale-of-tethers/) je postavljeno mnogo puta i još nije dan uvjerljiv odgovor. Nakon mukotrpnih pokušaja revizije rezervi, Tether je unajmio tvrtku Freeh Sporkin & Sullivan za tu svrhu. FSS su razmotrili račune Tethera na dan 1.6.2018. i zaključili da pronađene rezerve od 2.55 milijardi pokrivaju 2.54 milijarde USDTa tada u cirkulaciji. Izvještaj koji je tvrtka proizvela bio je pun kvalifikacija, no nije producirao nikakve garancije o punoj kolateralizaciji. Uz to, sve podatke tvrtci je dao sam Tether, pa je točnost istih upitna. Bitfinex (vlasnik Tethera) i Tether trenutno prolaze kroz drugu vrstu drame - državni tužitelj New Yorka optužio ih je da su [sakrili gubitak od gotovo milijarde dolara](https://www.youtube.com/watch?v=UjQjq1eWqCc) vrijednosti kriptovaluta iz 2016, sakrivši to sredstvima vlastitih klijenata. Izgleda da će situacija postati puno gora prije nego postane bolja.

Ove rezervacije možda se ne čine suviše bitnima gledano izdaleka, posebice ako koristite USDT samo za slanje vrijednosti među mjenjačnicama, no razmišljajte o tome ovako - Tether kreira USDT prema svojim rezervama USD-a. To ga čini drukčijim od odstalih kriptovaluta koje baziraju svoju injekciju na matematičkoj predvidljivosti i strogim pravilima. Ako USDT nije potpuno kolateraliziran dolarima, Tether u biti štampa svoj vlastiti novac koji uopće nema podlogu. Ako Tether padne (i mnogi vjeruju da je to pitanje "kada" a ne "ako"), eliminirati će ogroman dio kripto likvidnosti te potencijalno otjerati mnoge mjenjačnice u bankrot. Mjenjačnice poput Bitfinexa, Poloniexa i Bittrexa će biti prve na meti jer je USDT jedini stablecoin kojeg imaju u ponudi.

Kao što ste vjerojatno shvatili iz opisa gore, fiat-kolateralizirani stablecoinovi su centralizirani i zahtjevaju ogromnu količinu povjerenja prema tvrtci koja ih izdaje. Postoje alternative koje pak igraju na transparentnost kako bi dobili potrebnu prednost nad USDTom.

### TrueUSD (TUSD)

![TrueUSD logo](https://bitfalls.com/wp-content/uploads/2018/10/tusd.png)

[TrueUSD](https://www.trusttoken.com/trueusd/) je ERC-20 token kolateraliziran USDom, kao i Tether. Proces dobivanja TUSDa je jednostavan: nakon slanja dolara u neku od unaprijed odobrenih banaka i prilaganja Ethereum adrese, TUSD stiže na adresu čim je uplata registrirana. Korištenje trećih strana je bitna razlika između Tethera i TrueUSD-a. TrustToken (vlasnici TrueUSDa) ne drže novac kod sebe već su iznosi u potpunosti rezervirani kod banaka partnera. Isto tako, oni se brinu za transparentnost pa je stanje rezervi stalno dostupno na uvid kroz partnerstvo s revizorskom kućom Cohen & Co koja svaka dva mjeseca izdaje novi izvještaj. TrueUSD je privukao zdravu dozu skepticizma kad su odredili da je za izvlačenje sredstava iz TUSD u USD za vrijeme alpha perioda potrebna netrivijalna suma od minimalno 10000 USD.

### Alprockz (ROCKZ)

![Alprockz logo](https://bitfalls.com/wp-content/uploads/2018/10/alprockz.png)

Sličan pristup ima i [Alprockz](https://alprockz.ch) koji prodaju ROCKZ, stablecoin u 1:1 odnosu s švicarskim francima. Njihov pristup se od Tethera razlikuje na sljedeća dva bitna načina: prvo, puna transparentnost s redovitim revizijama. Drugo, Alprockz izdaje ROCKZ, no kad netko želi kupiti ROCKZ, prebaciti će novac Alprockzu koji će ga držati pod fiducijarnim mandatom, tj. u posebnom osiguranom računu do kojeg depozitori mogu i u slučaju da Alprockz propadne.

### Gemini (GUSD)

![Gemini logo](https://bitfalls.com/wp-content/uploads/2018/10/gemini.png)

Burza [Gemini](https://gemini.com/dollar/) pokrenula je svoj vlastiti stablecoin poduprijet dolarom: Gemini Dollar (GUSD). Velika novost oko ovog coina je to da je odobren od strane vladinog regulatornog tijela - New York Odjela za Financijske Servise. GUSD je ERC-20 token koji radi slično kao i ostali stablecoinovi s ponekim razlikama. Set pametnih ugovora dozvoljava Geminiju kontrolu nad emisijom GUSDa te služi kao kontrolni sloj nad drugim slojevima što Geminiju daje ultimativnu kontrolu nad GUSDom. Korištenje hibridnog online i offline starateljstva sredstava kontrolira potpuni iznos GUSD-a u cirkulaciji, što u neku ruku rezultira mehanizmom konsenzusa umjesto da tvrtka štampa coinove kad god im trebaju.

Ponovno susrećemo problem centralizacije. Nedavno publicirani [izvještaj](https://blog.goodaudience.com/gemini-can-make-gusd-non-transferrable-at-any-moment-code-review-a28d58ef6a61) nakon pregleda izvornog koda GUSDa otkriva da kompanija ima mogućnost preuzimanja i zamrzavanja bilo čijih GUSD tokena. Nadalje, neki vlasnici većih količina GUSDa natuknuli su na probleme oko pretvaranja većih količina GUSDa u USD.

Postoji mnoštvo fundamentalnih problema s fiat-kolateraliziranim stablecoinovima. Dok neki očito ciljaju na jaču transparentnost, svi imaju istu vrstu rizika različitih stupnjeva - nestanak same tvrtke iza tog stablecoina. Miče li se trend na bolje od Tethera? Svakako. No to nije dovoljno i mnogi od spomenutih rizika ostaju.

## Kripto-kolateralizirani stablecoin: MakerDAO (DAI)

![MakerDAO logo](https://bitfalls.com/wp-content/uploads/2018/10/maker.png)

Jedan od načina za zaobilaženje rizika centralizacije je pomaknuti cijeli proces na sam blockchain, izvan kontrole centralnih entiteta. Takvi su stablecoinovi poduprijeti vrijednošću kriptovaluta. Iako se to možda čini kontraintuitivno (kako je moguće imati stabilni coin ako ga vežemo za nestabilnu valutu?), taj se problem rješava pre-kolateralizacijom, tj. stavljanjem pologa daleko većeg od onog iznosa koji želimo izvući u stabilnoj valuti. Taj je odnos često 2:1 ili 3:2.

Jedan takav projekt je [MakerDao](https://makerdao.com) i njihov DAI token. DAI je ERC-20 token koji je vezan za 1 USD ali bez rezervi u dolarima. Stabilnost mu nije garantirana legalnim sustavom ni nekim trećim stranama, već kroz set pametnih ugovora.

Najbitniji pametni ugovor koji upravlja MakerDAO sustavom je CDP - collateralized debt position ili kolateralizirani dug. Korsnik ostavlja polog u Etheru (uskoro i drugim valutama), i dobiva DAI za uzvrat. CDP je zapravo zalagaonica. Omjer DAI-Eth je takav da se za $100 vrijednosti Ethera dobiva 66 DAI. Ako korisnik želi svoj Ether nazad, vraća svih 66 DAIa plus proviziju za taj dug i odmah dobiva svoj Ether.

Pitanje koje nam prvo pada na pamet je - zašto bi netko zaključao svoj Ether u CDP? Najočitiji razlog je oklada na dugoročni rast vrijednosti Ethera - ako vjerujete da će cijena rasti, mijenjanje za DAI dopušta vam da koristite dio likvidnosti svog Ethera bez da ga prodate. DAI koji dobivate moguće je isto tako zamijeniti za još Ethera i time uzeti _margin long_ poziciju na Ether s još većom okladom na pozitivan ishod u budućnosti.

U slučaju da cijena DAIa preraste ili padne ispod $1, postoji automatski mehanizam za stabilizaciju. Ako DAI padne na, npr. 90 centi, ima smisla da vlasnici CDPa kupe jeftini DAI kako bi otključali $1 vrijednosti Ethera, time si osigurajući profit. To je racionalno tržište na djelu. S druge strane, ako cijena DAIa previše poraste, korisnici su incentivizirani da otvore CDPove i prodaju DAI na slobodnom tržištu za profit. Ta dva mehanizma u tandemu čine cijenu relativno stabilnom.

No, nije sve tako jednostavno - zadnjih nekoliko tjedana DAI je ispod $1. Rješenje je povećati proviziju za držanje CDPa otvorenima, čime se tjera korisnike CDPa da ih zatvaraju. Ta provizija plaća se prilikom zatvaranja CDPa i računa se godišnje. Povećanja te provizije izglasavaju se na glasačkom portalu MakerDAO-a na kojem svi vlasnici MKR tokena imaju pravo glasa. Hoće li nova provizija od vrtoglavih 16% godišnje pomoći pri stabilizaciji DAIa, vidjeti ćemo.

Najveći nedostatak kripto-kolateraliziranih stablecoinova u usporedbi s nečime poput Tethera je to da je Tether neusporedivo jednostavniji proces za razumijeti, pa je stoga i mnogo pristupačniji "smrtnicima". DAI je također mnogo podložniji _black swan_ događaju u kojem bi cijena Ethera pala toliko da ga nema dovoljno da pokrije sav DAI u cirkulaciji. U tom slučaju MakerDAO ima mehanizam "globalnog podmirivanja" koji bi koristeći MKR tokene kupio sav DAI po određenoj cijeni te garantirao da korisnicima ostane barem toliko koliko su imali u DAIu. Ta ideja stoji u teoriji, no još nije iskušana u praksi - čak ni za vrijeme velikog pada tržišta u 2018. godini, što je dokaz DAIove otpornosti na manipulacije cijenama.

Fiat-kolateralizirani stablecoinovi su izgleda osuđeni na neki udio centralizacije. To se možda ne čini kao veliki problem, no s obzirom na probleme oko transparentnosti nekih od najvećih pružača stablecoinova, situacija ne ulijeva povjerenje. Kripto-kolateralizacija u teoriji nudi rješenje, no tokeni poput DAIa još uvijek imaju jako mali volumen i ne znamo hoće li preživjeti sljedeće padove tržišta.