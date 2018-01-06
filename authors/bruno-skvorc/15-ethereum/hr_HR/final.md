_U ovom ćemo članku objasniti Ethereum na laicima pristupačan način, te ga usporediti s najpopularnijim: bitcoinom. Članak je napisan na način da bude razumljiv svima, no svejedno je preporučljivo da apsorbirate sadržaj iz [uvoda u kriptovalute][cc] i [uvoda u blockchain][bc] kako bi vam terminologija iz ovog teksta bila čim poznatija._

---

Ethereum, kojeg je 2015 lansirao Vitalik Buterin, je posebni [blockchain][bc] s posebnim tokenom. Taj token zove se Ether (simbol ETH na mjenjačnicama) i koristi se kao "benzin" - doslovno _gas_ - za pogonjenje Ethereum mreže i izvršavanje _pametnih ugovora_ (vidi dolje). Ether se troši za ostvarenje dolje navedenih svojstava i time nije kripto**valuta** koliko kripto**nafta**.

 Evo po čemu se konkretno razlikuje od bitcoina, i po čemu se ističe u kripto svijetu.

## Konačnost

Bitcoin ima [teoretski limit od 21 miljun ukupno ikad proizvedenih bitcoina][finite] i time je deflacijska valuta: njegova količina se smanjuje s vremenom kako ljudi gube pristup svojim [novčanicima][wallet], drugi ga skupljaju u enormnim količinama, itd.

Ether nema limit, ali ima fiksni omjer proizvodnje. Trenutno se rudari (proizvodi) malo više od 15.5 miljuna Ethera godišnje, ili 5 ETH svake sekunde. Nakon što Ethereum promijeni način rudarenja na PoS (vidi dolje), proizvodnja će se dramatično smanjiti - blizu nuli.

![Coinmarketcap graf Ethereuma trenutno](https://bitfalls.com/wp-content/uploads/2017/09/01-3.png)

Time vrijednost Ethereuma neće [disproporcionalno rasti][bubble] u nedogled kao kod bitcoina, već će zbog stalno obnavljane zalihe Ether postići stabilnost na tržištu, što je bitno za njegove praktične upotrebe (vidi dolje).

## Pametni Ugovori

Iako se bitcoin može skriptirati - tj. mogu se pisati mali programi koji uzrokuju da neke transakcije izvrše neku dodatnu operaciju, npr. kreiranje transakcija koje imaju više polaznih adresa odjednom, ili implementiranje platnih sustava koji lakše konzumiraju dolazni bitcoin - programski jezik koji se pritom koristi nije _Turing complete_ jer nema petlje _(ako ne znate što to znači, nije bitno)._

S druge strane, Ethereum skripte se pišu u jeziku zvanom _Solidity_. Solidity podržava petlje, i time dozvoljava da se u njemu piše bilo kakav moderni program - u granicama normale. Naime, kad se napiše neki Solidity program, da bi ga se izvršilo na Ethereum mreži mora ga se poslati u blockchain. Svaki podatak koji se šalje u blockchain treba platiti određednom količinom Ethera. Veći i ne-efikasniji program više košta, pa je ljudima u interesu održavati te programe vrlo malima. Ti se programi zovu pametni ugovori, ili smart contracts.

Sam Vitalik najbolje je objasnio pametni ugovor:

_"Zamislite automat za gazirana pića. To je uređaj koji prati i poštuje neke uvjete dogovora. Uvjeti u tom slučaju su jednostavni: ako ubacite $2, iz uređaja izlazi piće. Ako ne ubacite $2, piće ne izlazi. Ako ne stavite $2 i piće svejedno izađe, to nije dobro i netko nije napravio dobar program. Taj uređaj koji poštuje ta pravila također dolazi s sigurnosnim mehanizmom koji sprječava krađe - barem dovoljno sigurnim za boce pića od $2."_

<iframe width="560" height="315" src="https://www.youtube.com/embed/r0S4qIMf4Pg" frameborder="0" allowfullscreen></iframe>

Kod Ethera, iznos koji mi uplatimo u neki smart contract je tada pod kontrolom tog ugovora, i taj ugovor s tim iznosom može što god želi - slati iznos na drugu adresu, provjeriti uvjete i slati ga nekamo tek u budućnosti, vratiti ga na odredište, zaključati na neko vrijeme, pozvati neku vanjsku funkciju koja aktivira neko svojstvo u stvarnom svijetu, itd. 

Jedan praktični primjer implementacije je Kickstarter: stranica preko koje se skupljaju novčana sredstva za nove projekte. Pravilo Kickstartera je: ako se u danom periodu skupi dovoljno sredstava, projekt je uspio i novac se šalje organizatoru. Ako novac nije skupljen, sudionicima se vraćaju položena sredstva. Tako nešto je vrlo lako implementirati i automatizirati na Ethereum mreži, i time kompletno eliminirati ne samo posrednika, nego i ljudsku pohlepu i greške iz sustava.

Aplikacije koje funkcioniraju na bazi smart contracta nazivamo decentralizirane aplikacije, ili _dapps_.

## Što su ERC20 tokeni?

Jedno veoma bitno svojstvo Ethereuma je mogućnost kreiranja tokena na samoj Ethereum mreži. Tokeni su proizvoljne "kriptovalute" koje se grade posebnim smart contractom, i koriste kao i svaka druga: mogu se slati s jedne adrese na drugu, ali te [adrese][wallet1] su Ethereum adrese, ne adrese nekog novog blockchaina. Zbog toga tokeni nisu doslovno kriptovalute, već rezultat smart contracta, rezultat logike koja se vrti na Ethereum mreži. Reći da je neki token kriptovaluta jer jednako nepravilno kao i tvrditi da je neki program zapravo programski jezik.

Token primjerice može biti karta za koncert, bod za lojalnost u dućanu, valuta u nekoj računalnoj igri, i drugo.

![Kartica vjernosti](https://bitfalls.com/wp-content/uploads/2017/09/02-3.jpg)

Kako se sve više i više tokena počelo pojavljivati, tako se njihov oblik standardizirao u [ERC20 standard][erc20] koji omogućava raznim mjenjačnicama da ga lako uvrste u svoju ponudu.

Kreiranje ERC20 tokena na Ethereum mreži u kombinaciji s smart contractima je revolucionarno svojstvo ovog blockchaina koje će potpuno promijeniti način na koji poslujemo. Tokeni omogućavaju automatizaciju tvrtki, parcijalno kupovanje svega od digitalnih dobara do zemlje, ili čak autonomne automobile koji se sami voze, skupljaju klijente, naplaćuju vožnje i, na kraju, sami sebe _otplaćuju_. Potencijalnih scenarija je toliko da ih se još većine nismo ni sjetili.

## PoS

Treća najveća razlika je to da Ethereum u bliskoj budućnosti prelazi na sustav rudarenja zvan PoS (Proof of Stake - dokaz uloga) umjesto PoW (Proof of Work - dokaz rada).

Kod [bitcoina][bc], _dokaz rada_ je hash koji se dobiva mnogim kalkulacijama mnogih jakih računala. Imati ćemo poseban članak koji uspoređuje PoW i PoS detaljno, no za sada je dovoljno reći da u PoS sustavu nema potrebe za ogromnom potrošnjom struje. To centralizaciju na razini države kakvu sada recimo vidimo [u Kini][finite] eliminira. 

![Farma za rudarenje kriptovalute](https://bitfalls.com/wp-content/uploads/2017/09/03-3.jpg)

PoS, naravno, nije bez svojih problema. U tom sustavu, korisnik Ethereum blockchaina koji poželi biti "node", tj. nova vrsta rudara, _ulaže_ svoj Ether i njime garantira da će transakcije koje potvrdi biti istinite. Ako napravi grešku i igra protiv sustava (tj. drugi node-ovi ga okrive za krive informacije), on gubi svoj ulog. Ako sve bude OK, on dobiva svoj ulog nazad za nekoliko mjeseci, plus zaradu od troškova u obliku potrošenog Ethera od strane korisnika Ethereum mreže, za transakcije i izvršavanje logike pametnih ugovora. Zbog veličine uloga, nepoželjno ponašanje biti će veoma skupo: minimum 1000 Ethera.

## Zaključak

Da rezimiramo, Ethereum je različit od bitcoina na sljedeće načine:

- uskoro prelazi na [Proof of Stake][pos] umjesto [Proof of Work][pow] 
- uskoro će biti otporan na kvantna računala (članak o tome uskoro)
- podržava kreiranje drugih proizvoljnih tokena u Ethereum mreži (upute kako napraviti svoj token u skorom članku!)
- podržava kreiranje logike koja se pod određenim uvjetima sama izvršava (smart contracts)

Tu je i još jedna paralela koju volimo povući:

- Bitcoin je zlato. Kompliciran za nabaviti, skup i spor za prenijeti, ali strogo deflacionaran ([za sad][finite]) i time vrijedan te dobra investicija na duge staze, ovisno o tome koga se pita.
- Ethereum nije srebro za bitcoinovo zlato kako to mnogi pretpostavljaju. Ethereum je nafta. Iz njega se pomoću ERC20 tokena grade ostali derivati: plastika, benzin, šminka, boja, guma. Ethereum je baza cijele nove industrije i dok postoje razne alternative (Tezos, EOS, Rootstock, NEO), ni jedna za sada nema toliko rasprostranjenu upotrebu ni toliko iskusan i velik tim razvojnih inženjera iza sebe.

Ako želite kupiti Ethereum, slobodno nam se [obratite][mail], a sva pitanja slobodno ostavite u komentarima!

[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[finite]: https://bitfalls.com/hr/2017/09/17/bitcoin-finite-just-myth/
[bubble]: https://bitfalls.com/hr/2017/09/06/bitcoin-bubble/
[wallet]: https://bitfalls.com/hr/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[wallet1]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[mail]: mailto:contact@bitfalls.com
[erc20]: https://github.com/ethereum/EIPs/pull/610
[pos]: https://bitfalls.com/hr/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[pow]: https://bitfalls.com/hr/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
