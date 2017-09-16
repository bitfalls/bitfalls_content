Čest argument protiv prihvaćanja kriptovaluta, posebice od financijskih institucija, regulatora, i političara, je to da je anoniman i da će ga koristiti teroristi i kriminalci.

## Stavimo na stranu...

Stavimo za sada na stranu to da se keš nikada neće moći kompletno odstraniti iz cirkulacije. Može se eventualno kriminalizirati sve keš transakcije ili [preko noći kompletno demonetizirati 85% novčanica neke države][india] ali onda svi postaju kriminalci i živimo pod odbjeglim diktatorstvom. Mijenjanje načina na koji novac funkcionira kažnjava one koji nemaju kriminalnih tendencija, dok će kriminalci bez problema naći drugu valutu.

Stavimo na stranu i to da čak i ako se makne keš, kriminalci kakvih se vlade navodno boje mogu trgovati ne samo u gotovini, već i u zlatu, srebru, nafti, dijamantima, ili čak [Tide deterdžentu][tide].

Ignorirajmo i to da crno tržište u većini zemalja ne postoji jer ljudi žele činiti kriminalna djela, nego jer ih je "bijelo" tržište izdalo - primjerice, u Venezueli postoji [crno tržište za hranu](http://www.npr.org/sections/thesalt/2017/01/09/508986586/as-venezuelan-go-hungry-the-military-is-trafficking-in-food) jer hrane _jednostavno nema_, dok je za vrijeme depresije u Rusiji postojalo [crno tržište za kupnju američkih dolara][dollarus]. Vrijedno je napomenuti da kad se crno tržište nekog okruženja zasniva na opijatima, pornografiji, ili drugoj vrsti rekreacije, znači da je stanje u tom okruženju toliko komforno da nema legalnih potreba koje bijelo tržište ne zadovoljava. To je zapravo dobar pokazatelj ugodnog života u tom društvu.

Okrenimo leđa i činjenici da se od nas traži da potpuno vjerujemo entitetu koji upravlja našim novcem da će biti pošten, a istovremeno mu dopuštamo da sam sebe regulira. Kad se radi o takvim slobodama, je li iznenađujuće da su vlade [zapravo one koje financiraju najviše terorizma][terror] zbog ratne industrije? No ignorirajmo i to.

Osvrnimo se na samu _anonimnost_ koja one na vrhu navodno toliko plaši.

## Anonimnost i Bitcoin

Prije nego krenemo na anonimnost, moramo definirati razliku privatnosti i anonimnosti.

Kad kupite nešto a nije nigdje specifično zapisano što ste kupili niti za koliko, takva transakcija je _privatna_.

Kad kupite nešto a nije nigdje specifično zapisano da ste to upravo vi kupili, transakcija je _anonimna_.

Primjerice, direktna razmjena dobara ili dobara/usluga i gotovine je i privatna i anonimna, pogotovo ako ne postoji račun i sudionici u razmjeni se osobno ne poznaju.

Kupnja preko kreditne kartice nije ni anonimna ni privatna, jer se jasno vidi tko je vlasnik kartice i kada je što kupio, te za koliko.

Bitcoin je _donekle anoniman_, ali _nimalo privatan_ zbog načina na koji [blockchain][bc] radi.

Zašto donekle? Jer većina ljudi ne ulazi u bitcoin svijet anonimnim putem. Zbog relativno kompliciranog procesa ulaženja u bitcoin anonimnim putem (generiranje [walleta][wallet], nabavljanje bitcoina od nekog izvora, sigurno spremanje bitcoina, učenje kako ga [početi koristiti][startbtc]...), velika većina novih korisnika prvi bitcoin kupuje preko platformi poput [Coinbase][coinbase], [Litebit][litebit], ili [Cex][cex] gdje je taj proces najjednostavniji.

No, na tim platformama za bilo kakav ne-trivijalni iznos potrebno je poslati identifikaciju zbog KYC i AML zakona (know-your-customer - poznaj svog kupca, i anti-money-laundering - protiv pranja novca). Identifikacija se obično sastoji od slanja slike ili kopije osobnog dokumenta poput putovnice ili osobne iskaznice, i fotografije korisnika s istim. Neke platforme zahtjevaju i da se korisnik fotografira s bankovnom karticom koju misli koristiti za uplate. U momentu slanja tih podataka na odabranu platformu, bitcoin za te korisnike postaje jednako toliko anoniman kao bankovni račun. Drugim riječima, bilo kakvo svojstvo anonimnosti se gubi. Stoga, možemo zaključiti da će svi korisnici koji bitcoin žele legalno koristiti i nemaju ništa za skrivati i ući u taj sustav na tako javan način.

Ako korisnik nekako uđe u bitcoin ekosustav na način koji ne uključuje slanje osobnih podataka na razne platforme i time zadrži anonimnost te kriptovalute (npr. rudarenjem, keš razmjenom, ili primi BTC od nekog prijatelja ili klijenta), anonimnost opet nije dugoročno garantirana. Može je se izgubiti na sljedeće načine.

## Gubitak anonimnosti

### Nepažnja

Budući da je stanje cijelog bitcoin [blockchaina][bc] javno, dovoljno je da korisnik neke adrese samo jednom napravi grešku i javno obznani da mu ista pripada. Možda se radi o kupnji robe bitcoinom na nekoj web stranici koja zahtjeva korisnički račun, ili korisnik pogleda stanje svoje adrese na javnom računalu - nebitno. Jednom kad se nečiji identitet spoji s adresom, kretanje njegovih kriptovaluta je lako pratiti (vidi transakcijski graf, dolje).

### IP identifikacija

Kad neki bitcoin korisnik generira i šalje transakciju s svog računala, njegova transakcija šalje se svim ostalim bitcoin programima (rudarima) koji sudjeluju u bitcoin protokolu i žele tu transakciju potvrditi.

Zbog geografske udaljenosti, taj signal kada putuje kroz žicu kasnije stiže do nekih rudara nego do ostalih. Svaki rudar koji primi transakciju ujedno zna (i bilježi) IP adresu s koje transakcija dolazi. IP adresa je doslovna adresa u _prostoru interneta_ koja govori gdje se koje računalo nalazi. Svaki uređaj spojen na internet ima svoju IP adresu.

Ako neko nadležno tijelo uđe u zapise transakcija na dovoljno velikom broju rudarskih računala i usporedi te zapise s vremenima kada su stigli na koji od tih servera, lako je identificirati geografsku početnu točku signala transakcije praćenjem njegovih skokova preko bitcoin mreže. U najgorem sljučaju, IP identifikacija će malo suziti područje pretrage, a u najboljem identificirati će točan stan ili kuću iz koje signal potiče. [Ovaj istraživački rad][bitip] opisuje potpuni proces.

IP adresu se može djelomično sakriti pomoću anonimnog preglednika Tor, no ni to [nije baš sigurno][tor].

Naravno, direktna IP identifikacija nije faktor ako se šalje sa i na mjenjačnice. No, kod centraliziranih mjenjačnica korisnik može biti identificiran putem zahtjeva nadležnih tijela u području gdje se centrala te mjenjačnice nalazi, ako mjenjačnica sprema IP adrese svojih korisnika.

### Transakcijski graf

Najnaprednija metoda, [transakcijski graf][tg], uključuje praćenje samog blockchaina.



Spojem sve tri metode, uhvaćen je tvorac stranice Silkroad preko koje se svojevremeno prodalo mnogo droge, oružja, i drugih zabranjenih materijala. Programeri se mogu i sami poigrati praćenjem transakcijskih grafova alatima poput [ovih][sparkx].

## Zaključak

Bitcoin nije privatan, i samo djelomično je anoniman. Postoje mnoge alternative bitcoinu što se tih aspekata tiče - najpopularnije su Dash, Monero, ZCash, Vergecoin, uskoro Ether, itd.

Transakcije u Bitcoinu lako se prate, no čak i da su teške za slijediti i identificirati, pokušati se boriti protiv kriptovaluta zbog potencijalne anonimnosti biti će jednako toliko efikasno kao i rat protiv droge. Drugim riječima, spriječit će poštene građane koji su htjeli korisitit novu valutu i štediti u njoj da je koriste, gurnuti će kriptovalute u podzemlje i isključivo u crno tržište gdje će se koristiti kao i do sada od strane svih koji ih znaju koristiti, rezultirati će brojnim prevarama, pljačkama, i opasnim scenarijima, i na kraju neće biti ubrano ni 0% poreza.

Jedini pravi put za države što se kriptovaluta tiče je:

- jasno definirati porezne obaveze korisnika

i 

- priznati fungibilnost kriptovaluta (drugim riječima, prihvatiti da nije bitno odakle je jedinica kriptovalute došla nakon što dođe)

Jedini način za borbu protiv kriminalne upotrebe kriptovaluta je njihovo priznanje na državnoj razini i potpuna dekriminalizacija u svim aspektima. Bilo kakve zabrane uzrokovati će guranje valute u podzemlje i pospješiti kriminalne akcije, istovremeno negirajući sve potencijalne pozitivne efekte.

[terror]: http://www.balkaninsight.com/en/article/the-pentagon-s-2-2-billion-soviet-arms-pipeline-flooding-syria-09-12-2017
[tide]: http://nymag.com/news/features/tide-detergent-drugs-2013-1/
[india]: https://www.bloomberg.com/news/articles/2016-11-23/india-s-cash-canceling-experiment
[dollarus]: http://www.nytimes.com/1987/07/22/world/in-soviet-rubles-coupons-and-real-money.html?mcubz=0
[tor]: https://arxiv.org/abs/1410.6079
[blockchain]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[wallet]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[startbtc]: https://bitfalls.com/hr/2017/09/01/send-receive-bitcoin/
[litebit]: https://www.litebit.eu?referrer=111550
[coinbase]: https://www.coinbase.com/join/542b0423734ab06764000001
[cex]: https://cex.io/r/0/up108919585/0/
[bitip]: https://arxiv.org/pdf/1405.7418.pdf
[tg]: https://arxiv.org/abs/1502.01657
[sparkx]: https://github.com/ZuInnoTe/hadoopcryptoledger/wiki/Using-Spark-Scala-Graphx-to-analyze-the-Bitcoin-transaction-graph