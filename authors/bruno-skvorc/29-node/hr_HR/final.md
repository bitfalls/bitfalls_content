U sustavu [kriptovaluta][cc] i blockchaina, često ćete čuti rijeć _node_ ili "čvor". Ako ste čitali naš [uvod u blockchain][bc] (svakako preporučamo, ako još niste), node je jedan od onih likova iz stripa s papirima na koje se zapisuju transakcije. No, taj je uvod pojednostavljen i u stvarnosti postoje dvije glavne vrste _node_-a. U ovom ćemo ih članku pojasniti.

## Validation Node

Jedan node je računalo koje vrti određeni softver. U Bitcoinovom slučaju, jedan node je Bitcoin program koji se spaja s drugim Bitcoin nodeovima, tj. drugim Bitcoin programima na istom računalu ili drugim računalima - bilo to preko ceste ili na drugom kraju svijeta. Postoji više vrsta i verzija Bitcoin softvera. Odabirom verzije softvera vlasnik node-a "glasa" za određene promjene protokola. Na primjer, ako se predloži da se limit od [21 miljun ukupno proizvedenih bitcoina pomakne na 42 miljuna][finite], potrebna je većina mreže koja glasa "da" nadogradnjom softvera na određenu verziju. Većina mreže u ovom slučaju znači "većina nodeova u mreži"; odlukama u softveru pristupa se demokratski.

Ono kod čega taj koncept malo pada u vodu je relativno mali broj Bitcoin nodeova - trenutno ih je na svijetu samo 10000:

![10000 Bitcoin nodes](https://bitfalls.com/wp-content/uploads/2017/11/01-4.png)

... dok ih [Ethereum][eth] - kriptovaluta koja je 5 godina mlađa - ima čak dvostruko više:

![20000 Ethereum nodes](https://bitfalls.com/wp-content/uploads/2017/11/02-2.png)

Ni jedan ni drugi broj, globalno gledano, nisu impresivni. Prema [nekim računicama][awsnode], pokrenuti Bitcoin node na AWS (Amazonovom cloud sustavu) košta otprilike $10 na mjesec. To znači da bi netko preuzeo većinu i napravio 10000 novih Bitcoin nodeova na AWSu potrebno mu je 100000 mjesečno, ili samo $1.2 miljuna godišnje - trivijalan iznos za velike igrače Bitcoin sustava koji su [ušli dovoljno rano][finite].

Popis softvera koji se mogu instalirati i koristiti za sudjelovanje u BTC mreži možete vidjeti [ovdje][list], zajedno s njihovim prednostima, nedostacima, i dodatnim mogućnostima.

Bitno je napomenuti da validation nodes sami po sebi bivaju isključivo trošak svojim korisnicima - npr. Bitcoin Core zahtjeva 150 GB diskovnog prostora, 2GB RAM, i brzu internetsku vezu s dopuštenih barem 200 GB prometa _uploada_ mjesečno. Validacijski nodeovi su volonterski, i služe za decentralizaciju sustava. Ako uzmemo u obzir da je [bankarski sustav preuzeo financiranje razvoja Bitcoina][bankers], i da se cijena [umjetno napuhava kriminalnim operacijama][tether] nije ni čudno da sve više i više ljudi gubi entuzijazam i prebacuje se na druge blockchaine i kriptovalute uvidjevši korumpiranu prirodu Bitcoin sustava. Broj nodeova pada - prije samo mjesec dana bilo ih je 20% više: 12000. S padom broja nodeova, preuzimanje većinske kontrole postaje sve vjerojatnije.

## Mining Node

Mining Node je softver koji rudari. To je softver koji koristi hardver vašeg ili iznajmljenog računala da bi pogađao kombinacije koje dovode do otkrića novog [blocka][block]. Mining node može raditi u kombinaciji s drugim mining nodeovima kako bi isti rudarili zajedno ([pool mining][pool]).

Mining node također validira transakcije i time je istovremeno validation node. Budući da se danas većina rudarenja obavlja u _poolovima_, tj. zajednički tako da više nodeova šalje svoje pokušaje pogodaka u jedan, takav jedan pool se broji kao jedan node. Zbog tendencije da se novi rudari pridružuju najvećim poolovima jer takvi ujedno najčešće otkrivaju blokove i time dobivaju nagrade, dešava se velika tehnološka centralizacija rudarenja u kojoj 20ak najvećih poolova kontroliraju gotovo cijeli sustav rudarenja Bitcoina.

[Ovdje][pool-list] je popis najvećih poolova, od kojih prvi rudari čak 25% svjetskog Bitcoina.

![Antpool postrojba](https://bitfalls.com/wp-content/uploads/2017/11/03-2.png)

Mining node je jedini softver koji može "proizvesti" novi Bitcoin, i za pokretanje i isplativost istog potrebna je izuzetno velika računalna moć ili besplatna struja. Popis Bitcoin softvera koji se koristi za rudarenje - ukoliko želite pokrenuti vlastitu operaciju - nalazi se [ovdje][minesoft].

## Zaključak

Mining node - ili čvor koji rudari - je čvor koji sudjeluje u mreži na način da pogađa rješenja potrebna za validaciju jednog bloka transakcija u Bitcoin mreži. Validation node validira te podatke i prosljeđuje ih drugim nodeovima, što širi transakcije po mreži i osigurava prijenos vrijednosti s mjesta A na mjesto B. Mining nodeovi su _podskup_ validation nodeova, jer svaki mining node također i validira.

Ova razlika manifestira se samo u [Proof of Work][pow] načinu rada nekog blockchaina, i postaje tehnički nepotrebna u PoS sustavu. Kod PoS sustava svaki node može biti validation node, a mining nodeovi kao takvi ne postoje jer se novi tokeni stvaraju na drugom principu. Za više o tome, pročitajte naš [PoW vs. PoS][pow] članak.

[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[pow]: https://bitfalls.com/hr/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[finite]: https://bitfalls.com/hr/2017/09/17/bitcoin-finite-just-myth/
[awsnode]: http://calculator.s3.amazonaws.com/index.html#r=IAD&s=EC2&key=calc-7C655B73-FA35-40F0-9518-4773E3E4A8C7
[list]: https://en.bitcoin.it/wiki/Clients
[block]: https://bitfalls.com/hr/glossary/#block
[pool]: https://bitfalls.com/hr/glossary/#mining-pools
[pool-list]: https://www.buybitcoinworldwide.com/mining/pools/
[bankers]: https://np.reddit.com/r/btc/comments/743qb8/is_segwit2x_the_real_banker_takeover/
[tether]: https://bitfalls.com/hr/2017/10/21/the-curious-tale-of-tethers/
[minesoft]: http://www.bitcoinx.com/bitcoin-mining-software/
[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[eth]: https://bitfalls.com/hr/2017/09/19/what-ethereum-compare-to-bitcoin/