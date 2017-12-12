Za bolje razumijevanje informacija u ovom članku preporučamo pročitati sljedeće uvodne materijale:

- [Što su to kriptovalute][cc]
- [Što je to blockchain i kako funkcionira?][bc]
- [Što je to Ethereum i kako se razlikuje od Bitcoina?][eth]
- [Što je rudarenje, i kako se PoW razlikuje od PoS rudarenja?][pow]

Osnove programerskih pojmova (varijabla, petlja) također će biti korisne za potpuno razumijevanje.

---

Kada šaljete Bitcoin transakciju, ona košta onoliko koliko je sama transakcija velika (u kilobajtima - čim više [izlaznih i ulaznih adresa][blockex], tim je transakcija skuplja), umnoženo za faktor zakrčenosti mreže - ako mnogo transakcija [čeka na red][pendingbtc], tada će standardni trošak transakcije rasti.

Kod Ethereuma, budući da se radi o programskom jeziku u samom protokolu, moguće je s vrlo malo _teksta_ (nešto što bi u BTC svijetu bilo jeftino) izvršiti vrlo kompleksne upute, i time zagušiti računala na kojima se te upute izvršavaju. 

Pogledajmo petlju:

```sol
while (i++ < 1000) {
    j = j + i;
}
```

Ova petlja kaže "sve dok varijabla `i` nije veća od 1000, povećaj varijablu `i` za jedan, zatim zbroji varijablu `i` i varijablu `j`, spremi rezultat u `j` i ponovi petlju". Ova će se petlja izvršiti 1000 puta ako je `i` 0, ili više ako je `i` negativan broj.

Da bi se ovakva kompleksnost mogla realno naplatiti (jer troši struju i vrijeme Ethereum rudarima), Ethereum protokol je osmišljen na način da se prilikom izvršavanja Ethereum programa (tzv. _pametnog ugovora_) unutar EVM-a takve upute naplaćuju u jedinicama zvanim _gas_. Npr., gore navedeni zbroj `i` + `j` bi koštao 3 _gasa_ svaki puta kada se izvrši - dakle 3000 _gasa_ za 1000 izvršenja.

Da bismo objasnili _gas_, prvo trebamo objasniti pojam EVM.

## EVM

EVM je Ethereum Virtualna Mašina. No, što je _virtualna mašina_?

### Virtualna Mašina

Virtualna mašina je softver koji se vrti na određenom računalu, a u kojem je sadržan potpuno odvojen i nezavisni operativni sustav. Virtualna mašina omogućava pokretanje Windows operativnog sustava unutar Linux sustava, ili Linux unutar Windowsa, Windows unutar OS X-a kao na slici dolje, ili neku drugu kombinaciju.

![Windows inside OS X](https://bitfalls.com/wp-content/uploads/2017/12/01.jpg)

Virtualne mašine se koriste za odvajanje okoline u kojoj razvijate ili isprobavate neki softver od one koju koristite za svakodnevni rad. To onemogućava virusima da pređu iz jednog sustava u drugi, beskonačnim petljama da sruše glavni procesor, ili čak softverskim grešakama da korumpiraju disk. To ujedno omogućava i primjerice, pokretanje Windows igara na Linux računalima, programiranje u više verzija programskog okruženja istovremeno, i slično.

### EVM

EVM ili _Ethereum Virtualna Mašina_ je virtualna mašina Ethereum protokola koja služi za izvršavanje raznih Ethereum programa (pametnih ugovora). Ona je sadržana u softveru kojeg vrte [full nodes][nodes] Ethereum mreže, i unutar istog izvršava Ethereum programe.

Ethereum programi pišu se u Solidity programskom jeziku i bilo koji [rudar][mining] koji rudari Ethereum istovremeno izvršava kod tih programa. To znači da se Ethereum programi (tzv. dapps - decentralizirane aplikacije) izvršavaju na svačijem računalu istovremeno (decentralizirano).

Izvršavanje programa nije besplatno - rudari koji ga omogućuju troše vlastitu električnu energiju, vrijeme i resurse svog računala. Zbog toga svaka instrukcija (uputa u programu, kao na primjer "spremi broj 5 u varijablu X") košta određenu količinu _gasa_.

## Gas, Ether i GWei

Gas je jedinica troška neke operacije koju računalo mora izvršiti, a izvršava je kada pošaljemo transakciju koja sadrži Ethereum program u sebi, kako bismo pokrenuli neki _dapp_. Npr. zbroj dvije brojke košta 3 _gasa_. Množenje dvije brojke košta 5 _gasa_. Spremanje jedne riječi od 256 bita u blockchain košta 20,000 _gasa_, što znači da bi podaci duljine jednog kilobajta koštali 640,000 _gasa_. 

Kao što dolar ima cente, tako je i kod ethera najmanja jedinica ethera _wei_. Ako uzmemo jedinicu _wei_ kao osnovnu i iz nje izvodimo ostale jedinice dok ne dođemo do ethera, dobivamo sljedeću tablicu:

|jedinica                             | wei |
|-------------------------------------| --- |
|**wei**                              | 1   |
|kwei / ada / femtotether             | 		1.000| 
|mwei / babbage / picoether           | 		1.000.000| 
|**gwei** / shannon / nanoether / nano| 	1.000.000.000| 
|szabo / microether / micro           | 		1.000.000.000.000| 
|finney / milliether / milli          | 		1.000.000.000.000.000| 
|**ether**                            | 		1.000.000.000.000.000.000| 

Prema [ovoj informativnoj stranici][ethgas], trenutna prosječna cijena gasa je 10 GWei-a (10 giga-weia). Budući da je 1 GWei miljardu puta manji od Etha, to znači da je gore spomenuti sadržaj od 640,000 _gasa_ skup 6,400,000 GWeia. 6.4 miljuna GWeia je 0.0064 Eth a po trenutnoj cijeni ($450) to je $2,88.

Tekst od početka tablice gore pa sve do **>>ovog markera<<** ima cca 1 kilobajt. To znači da da bi ga se spremilo u Ethereum blockchain, potrebno je $2.88 ili nekih 18.5kn. Ali to je samo spremanje tog teksta - u trošak se treba uračunati i druga logika. Primjerice, možda naš pametni ugovor treba filtrirati neke riječi iz tog teksta, možda ujedno treba pomnožiti i spremiti neke brojke, možda treba podesiti okidače za pojedine događaje u Ethereum sustavu, kao npr. slanje neke poruke kada se otkrije određeni blok, itd. Prema tome, vidimo da je potpuno neisplativo spremati nepotrebne podatke u Ethereum blockchain - podaci se spremaju izvan blockchaina u spremište poput BigchainDB ili [IPFS], dok se blockchain koristi za globalnu obradu i verifikaciju istinitosti informacija.

### Zašto Gas?

Zašto se trošak transakcije naplaćuje u _gas_ a ne direktno u etheru?

Trenutno su sve _gas_ cijene raznih instrukcija koje EVM može izvršiti definirane u kodu Ethereum protokola, tj. u kodu [programa][cli] koje spajamo na Ethereum mrežu - programa poput Geth, Eth, Parity, itd. Kada bi bile definirane u etheru, morali bismo mijenjati izvorni kod tih programa pri svakom pomaku cijene ethera, što bi značilo strahovito nepredvidljive troškove izvršavanja programa.

Uvođenjem dodatnog sloja u kontekst naplate izvršenja programa time da *gasu* pridodajemo cijenu u GWeiu, omogućeno nam je da prilikom slanja neke transakcije na Ethereum mrežu sami odredimo koliko ćemo _gasa_ poslati s transakcijom, i koliko ćemo platiti pojedinu jedinicu *gasa*. Time upravljamo cijenom transakcija i brzinom izvršenja.

To nas dovodi do zadnje teme.

### Limit / Cost vs. Price

_Gas limit_ je količina _gasa_ koju smo spremni potrošiti na izvršenje neke transakcije. Obično softver kojim vršite transakcije zna sam procijeniti koliko će otprilike _gasa_ biti potrebno, i predlaže neku cifru. Jednostavne monetarne transakcije obično koštaju samo 21000 _gasa_, dok kompliciranije, koje pozivaju neke funkcije pametnih ugovora tj. Ethereum programa, mogu koštati nekoliko stotina tisuća ili miljuna _gasa_. Mi kao korisnik možemo promijeniti taj _gas limit_ i smanjiti ga, ali ukoliko transakciji za vrijeme pokušaja izvršenja instrukcija ponestane _gasa_ jer smo odabrali pre nizak limit, naša transakcija se proglašava neuspjelom i mi gubimo do tada potrošeni _gas_. S druge strane, ako stavimo više _gasa_ nego bi transakcija mogla trebati, vraća nam se sav višak - stoga je uvijek bolje pretjerati na `gas limit` postavkama, jer sav nepotrošeni višak ionako dobivate nazad. Potrošeni dio _gasa_ naziva se _gas cost_.

_Gas Price_ je **jedinična cijena** _gasa_, tj. koliko GWeia po jednom _gasu_ smo voljni platiti.

Dakle, ukupna cijena transakcije će biti ukupna količina _gasa_ potrebna za njeno izvršenje umnožena za cijenu gasa koju smo voljni platiti. To će biti **maksimalna** cijena transakcije, jer je moguće da će transakcija trebati manje _gasa_ te će nam se ostatak vratiti.

Pogledajmo to na primjeru:

![25 Gwei](https://bitfalls.com/wp-content/uploads/2017/12/02.png)

U primjeru gore izvršavamo transakciju koja se zbog svoje kompleksnosti procjenjuje na 135963 *gasa*. S cijenom od 25 GWei, maksimalni trošak naše transakcije je $1.57, što je relativno zanemarivo kada pogledamo ukupni iznos transakcije (šaljemo 0.387617 Eth, što je cca $178.74). Ako pak podignemo cijenu _gasa_ u GWei na 250, cijena transackije postaje proporcionalno skuplja:
![250 GWei](https://bitfalls.com/wp-content/uploads/2017/12/03.png)

S većom cijenom mi efektivno prisiljavamo rudare da našu transakciju uključe prije drugih, i da se brže izvrši. Ako nismo u žurbi, možemo ostaviti cijenu _gasa_ na početnim postavkama i izvršenje transakcije ne bi trebalo trajati dulje od 10ak minuta. No, ako nam se žuri i želimo biti gotovi u roku od nekoliko sekundi (recimo da se radi o nekoj aukciji u kojoj moramo biti prvi), lako je povisiti cijenu _gasa_ u GWei-u i time žrtvovati trošak u naplati transakcije, ali postići garantirani uspjeh.

## Zaključak

Gas je mjera cijene određenih računalnih operacija u Ethereum Virtualnoj Mašini (EVM). Gas se plaća u etheru - valuti Ethereum protokola - i jedinica gasa ima određenu cijenu koja varira ovisno o zakrčenosti mreže i korisnikovim preferencama.

Za pametni ugovor koji pošaljemo u Ethereum mrežu bitne su dvije stavke: gas cost (potrošnja gasa) i gas price (cijena gasa). Gas cost je količina gasa koja je potrebna da se logika iz ugovora odradi - doslovno "benzin" koji se potroši na izvršenje programa. Gas price je cijena koju plaćamo za gas cost. Transaction fee (trošak transakcije) je dakle umnožak gas cost-a i gas price-a. Budući da je teško točno procijeniti koliko će gasa određeni ugovor trebati za izvršenje, korisnike se ohrabruje da pošalju više gasa uz svoju transakciju nego misle da je potrebno, jer sav gas koji se ne potroši se vraća pošiljatelju kako bi sustav ostao pošten.

[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[eth]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/
[progeth1]: /
[pow]: https://bitfalls.com/hr/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[mining]: https://bitfalls.com/hr/glossary/#mining
[ethgas]: https://ethgasstation.info/
[blockex]: https://bitfalls.com/hr/2017/10/03/read-bitcoin-blockchain-data-blockexplorer/
[pendingbtc]: https://blockchain.info/unconfirmed-transactions
[nodes]: https://bitfalls.com/hr/2017/11/26/whats-bitcoin-node-mining-vs-validation/
[ipfs]: https://bitfalls.com/hr/2017/10/29/ipfs-just-take-internet-back/
[cli]: https://www.ethereum.org/cli