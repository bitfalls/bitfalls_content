U [ovom članku][hw wallets] smo objasnili kako funkcioniraju hardverski novčanici  kao što su Ledger, Trezor i Keepkey , no i dalje se susrećemo s raznim zabludama u vezi ovakve vrste novčanika. 

Objasnimo dvije najpopularnije.

##  Zabluda 1: Kriptovalute su spremljene na novčaniku

Najveća zabluda je da su npr. naši Bitcoini spremljeni na novčaniku.
To je kao da kažemo da u džepu imamo auto, a u džepu zapravo imamo ključeve auta.

Isto tako sami Bitcoini nisu spremljeni na novčanik nego se nalaze na [blockchainu][blockchain], a novčanik sadrži **privatne** ključeve koji su potrebni da bi mogli te Bitcoine prebaciti s jedne na drugu adresu.

Na blockchain  možemo gledati kao na knjigu koja bilježi tko ima koliko Bitcoina.
Ovo vrijedi i za hardverske i za softverske novčanike.

Više o privatnom / javnom ključu [ovdje][privkey], ili detaljno [ovdje][blockchain].

## Zabluda 2: imam Ledger novčanik, ali nema dovoljno mjesta za sve aplikacije?

Razlog zašto Ledger ne može imati više od 5 instaliranih aplikacija istovremeno je sprječavanje instalacije zloćudnog softvera.

_Dobro, sigurnost je bitna, no neću li izgubiti coine ako izbrišem neku od aplikacija?_

Ne, možemo instalirati i deinstalirati aplikacije po želji bez da gubimo valute koje novčanik čuva. Za to je zaslužan [BIP 39] (prijedlog za poboljšanje Bitcoina):

Kad prvi put upalite Ledger Nano S ili Trezor, dobiti ćete listu riječi koju morate zapisati. Kao što je to objašnjeno [ovdje][hw wallets], matematičkim putem se iz te liste riječi generira glavni privatni ključ koji dalje generira privatne i javne ključeve ovisno o pravilima pojedine kriptovalute koju novčanik podržava.

*NAPOMENA: Od presudne važnosti je da tu listu riječi zapišete i sačuvate, jer u slučaju da se vaš novčanik na neki način pokvari, s tom listom riječi ćete moći povratiti sredstva, bilo na drugi isti takav novčanik ili koristeći se softverskim novčanikom na vašem računalu.*

Ako obrišemo npr. Litecoin aplikaciju s novčanika i nakon nekog vremena je vratimo nazad, kad otvorimo novčanik, BIP39 će generirati iste privatne i javne adrese i imat ćemo pristup svim sredstvima koja su bila dostupna i prije brisanja aplikacije. Također će se prikazati i sredstva koja su došla za vrijeme dok je aplikacija bila izbrisana.

## Zaključak

Hardverski novčanici su jedna od, ako ne i najsigurnija metoda čuvanja kriptovaluta. Puno vremena i truda je uloženo u tehničku pozadinu i maksimalno pojednostavljenje korisničkog sučelja. No, nadamo se da je misterija o tome kako oni rade barem malo razbijena.

Za više informacija o tome kako rade s matematičko/tehničke strane, ali objašnjeno na pristupačan način, pogledajte [ovaj članak][hw wallets].




[hw wallets]:https://bitfalls.com/hr/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[blockchain]:https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[BIP 39]:https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki
[privkey]: https://bitfalls.com/glossary/#private-key
