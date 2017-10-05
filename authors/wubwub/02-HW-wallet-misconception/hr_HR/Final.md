U [ovom članku][hw wallets] smo objasnili kako funkcioniraju hardverski novčanici  kao što su Ledger, Trezor i Keepkey , no i dalje se susrećemo s raznim zabludama u vezi ovakve vrste novčanika. 
Danas ćemo razotkriti koje su to najčešće zablude i što se krije iza njih.

##  Kriptovalute su spremljene na novčaniku.

Možda čak i najveća zabluda je da su npr. naši Bitcoini spremljeni na novčaniku.
To je kao da kažemo da u džepu imamo auto, a u džepu zapravo imamo ključeve auta.

Isto tako sami Bitcoini nisu spremljeni na novčanik nego se nalaze na [blockchainu][blockchain], a novčanik sadrži **privatne** ključeve koji su potrebni da bi mogli te Bitcoine prebaciti s jedne na drugu adresu.

Na blockchain  možemo gledati kao na knjigu koja bilježi tko ima koliko Bitcoina.
Ovo vrijedi i za hardverske i za softverske novčanike.

## Imam Ledger novčanik, ali nema dovoljno mjesta za sve aplikacije?

Razlog zašto Ledger ne može imati više od 5 instaliranih aplikacija istovremeno je sprječavanje instalacije zloćudnog softvera.

### Dobro, sigurnost je bitna, no neću li izgubiti coine ako izbrišem neku od aplikacija?

Ne, možemo instalirati i deinstalirati aplikacije po želji bez da gubimo coine.
Za to je zaslužan [BIP 39] (prijedlog za poboljšanje Bitcoina).

### BIP 39

Kad prvi put upalite Ledger nano s ili Trezor, dobit će te listu riječi koju morate zapisati, matematičkim putem se iz te liste riječi generira glavni privatni ključ koji dalje generira privatne i javne ključeve ovisno o pravilima pojedine kriptovalute koju novčanik podržava.

*NAPOMENA: Od presudne važnosti je da tu listu riječi zapišete i sačuvate, jer u slučaju da se vaš novčanik na neki način pokvari, s tom listom riječi će te moći povratiti sredstva.*
 
*Bilo to na drugi isti takav novčanik ili koristeći se softverskim novčanikom na vašem računalu.*

Iako obrišemo npr. Litecoin aplikaciju s novčanika i nakon nekog vremena ju vratimo nazad, kad otvorimo novčanik, BIP39 će generirati iste privatne i javne adrese i imat ćemo pristup svim sredstvima koja su bila i prije brisanja aplikacije, također će prikazati i sredstva koja su došla i za vrijeme dok je aplikacija bila izbrisana.

## Zaključak

Hardverski novčanici su jedna od, ako ne i najsigurnijih metoda čuvanja kriptovaluta, puno vremena i truda je uloženo u tehničku pozadinu i maksimalno pojednostavljenje korisničkog sučelja. No, nadamo se da je misterija o tome kako oni rade barem malo razbijena.






[hw wallets]:https://bitfalls.com/hr/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[blockchain]:https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[BIP 39]:https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki