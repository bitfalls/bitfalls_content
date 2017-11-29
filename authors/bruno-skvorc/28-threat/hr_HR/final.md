U svibnju 2017. Maria Apostolaki, Aviv Zohar i Laurent Vanbever objavili su [analizu][paper] u kojoj [opisuju][page] dva nova moguća napada na Bitcoin mrežu s strane infrastrukture. Ti su vektori napada još uvijek neriješeni. 

U ovom ćemo članku ukratko objasniti te potencijalne napade i prijetnju koju predstavljaju. Za razumijevanje sadržaja nije potrebno nikakvo predznanje, no osnove [kriptovaluta][cc] i [blockchain][bc] tehnologije mogle bi pomoći kod razumijenjavanja nekih pojmova.

## (De)Centraliziranost mreže

Kao što smo to opisali u našem [objašnjenju nodeova][nodes], Bitcoin nodeova je trenutno samo oko 10000.

![10000 nodeova](https://bitfalls.com/wp-content/uploads/2017/11/02-3.png)

 No, prema originalnoj definiciji Satoshijevog whitepapera (prezentacijskog papira originalnog Bitcoin protokola), _punih nodeova_ (nodeovi koji validiraju i rudare) je danas samo 20ak - i to su sve [mining pools][pool]. 

Zbog kompetitivnosti u [rudarenju][pow] i neisplativosti solo rudarenja sve dok postoje te velike grupe, individualni rudari više ne postoje - oni samo šalju svoje pokušaje pogodaka u pool, bez da sami formiraju blokove i odlučuju koje transakcije uključiti u njih.

Rudarenje nije više decentralizirano.

Da bi sama mreža ostala decentralizirana, ovisimo o [validacijskim nodeovima][nodes] koji validiraju "proizvode" nodeova koji rudare. No, većina korisnika jednostavno nije zainteresirana za održavanje vlastitog nodea jer je to prekomplicirano i skupo - samo za [Bitcoin Core][bcore] (najuobičajeniji softver za održavanje validation nodea) potrebno je cca 150 GB diskovnog prostora i barem 2GB radne memorije.

Zbog te prepreke, većina prosječnih korisnika odabire jednostavniji način držanja valuta - ili na [papiru][paperwallet], ili na nečemu tipa [Ledger Nano S][ledger], što samo drži ključ za pristup kriptovalutama na nekoj [adresi][address], ili na centraliziranim web stranicama i kripto-bankama poput Bittrex, Coinbase, itd. Nijedan od tih načina držanja kriptovaluta nije ni _full node_ po standardnoj definiciji, ni _validation node_ - nije uopće node. Coinbase vrti svoj node, ali vi kao korisnik se samo spajate na taj jedan te isti. Velika većina sudionika kripto ekosustava, posebice Bitcoin ekosustava, uopće ne sudjeluje u mreži. Zato je od miljuna korisnika Bitcoina samo 10000 njih koji vrte nodeove.

Ako je, dakle, rudarenje centralizirano i validacija nije decentralizirana koliko bi trebala biti, kako to da sustav uopće još stoji ako ide protiv svih koncepata definiranih u originalom Bitcoin whitepaperu? Postoji li uopće opasnost ako smo očito imuni na kršenje fundamentalnih koncepata Bitcoina?

## Napadi

Problem je zapravo mnogo opasniji i dublji. Osim [standardnih načina zaustavljanja Bitcoina][unstop], autori gore navedenog [rada][paper] otkrili su sljedeće zabrinjavajuće brojke:

- samo 13 svjetskih ISPova (pružatelja internetskih usluga) poslužuje promet od preko 30% Bitcoin mreže. Drugim riječima, 13 ISPa je odgovorno za održavanje servera 30% full nodeova:

  ![30% mreže je na 13 ISPova](https://bitfalls.com/wp-content/uploads/2017/11/01-5.png)

- 60% Bitcoin prometa prolazi kroz 3 od tih 13 ISPova.

  ![60% prometa prolazi kroz 3 ISP-a](https://bitfalls.com/wp-content/uploads/2017/11/04-1.png)

Ove brojke u cijelu priču uvode još jedan faktor centralizacije - centralizaciju internetskog prometa. Takva centralizacija omogućava _BGP hijack_ napad.

### BGP

BGP ili _Border Gateway Protocol_ je mrežni standard koji služi za dijeljenje uputa routerima kako doći do koje IP adrese.

BGP hijack se dešava kad neki ISP dijeli lažne informacije da bi preusmjerio promet. Time efektivno krade promet nekog uređaja spojenog na internet. Takvi su napadi veoma česti. U Bitcoinu trenutno najveći zabilježeni napad je 447 različitih nodeova u studenom 2015, kada ih je bilo samo oko 5000, dakle napad od gotovo 10%.

Što se konkretno može desiti prilikom takvih BGP routing napada?

### Fragmentacija Bitcoin mreže

Prvi napad koji postaje moguć je fragmentacija Bitcoin mreže.

U Bitcoin mreži, svi nodeovi pričaju međusobno. No, budući da ih je toliki postotak na istom servisu, sprječavanje komunikacije između dva takva servisa uzrokovalo bi cjepkanje lanca na dva dijela koji se istovremeno razvijaju dalje. Bitcoin protocol je osmišljen na takav način da nestanak nodeova iz mreže ne utječe na one koje su ostale na životu. Nestale nodeove se smatra mrtvima, ugaslima, iako su oni možda u svom lancu koji jednostavno nema kontakt s onim drugim, i svaki lanac za onog drugog misli da je izgubio vezu.

Svaki lanac se tako razvija u svom smjeru sve dok napad traje. Budući da je u Bitcoin protokolu pravilo da kada se razdvojeni lanci ponovno spoje onaj duži prevladava a onaj kraći preuzima njegove blokove i odbacuje svoje, takav bi napad imao sljedeće posljedice:

- kraći lanac bi izgubio sve BTC [nagrade][rew] koje su rudari dobili od mreže, uzrokovavši tako ogromni trošak
- kraći lanac bi izgubio sve transakcije iz tih izgubljenih blokova, efektivno poništivši određeni period trgovanja i korištenja BTCa u tom dijelu mreže

Taj napad može biti ne samo izuzetno skup za rudare, nego i katastrofalan za poduzeća koja su odlučila baviti se kriptovalutama i primati i vršiti isplate u istima.

### Usporavanje Bitcoin mreže

Drugi napad je nedetektirano usporavanje mreže.

Cilja se na određeni node, no kao što smo prije spomenuli, jedan node može biti jedan mining pool koji zapravo obuhvaća 1/20 snage bitcoin mreže. Proces ide ovako:

- neki node A šalje podatke nodeu B prema potraživanju nodea B
- napadač presreće signal i šalje zastarjeli block u node B umjesto najnovijeg
- node B provjerava block uzaludno, i tik prije isteka 20 minuta šalje se pravi block

Zbog programskih ograničenja u Bitcoin protokolu, jedan node se ne odpaja od drugog osim ako se ne radi o miskomunikaciji duljoj od 20 minuta, što napadač namjerno izbjegava. Time je usporio komunikaciju na mreži i natjerao node B da radi uzaludni posao.

Posljedice ovakvog napada mogu biti veliki uzaludni trošak resursa od nekog poduzeća koje se bavi rudarenjem Bitcoina, zaustavljanje validacije ako se radi o individualnom validacijskom nodeu, što omogućuje sprječavanje signaliziranja želje da se pređe na neku softversku nadogradnju u Bitcoin protokolu (vidi [forks][forks]), ili u najgorem slučaju _double spend_ greška kod nekog trgovca koji posluje u Bitcoinu. Double spend je kad je moguće više puta potrošiti isti iznos novca, jer se prva transakcija nije proknjižila na vrijeme. 

## Zaključak

Pojavljuje se sve više i više znakova da Bitcoin nije ni neranjiv, ni otporan na cenzuru, ni [neuništiv][unstop] kao što je trebao biti. 

Najbolji način za osiguranje od ovakvih napada sastoji se od više koraka:

- spremite svoje kriptovalute izvan dometa centraliziranih pružača usluga poput burzi za kriptovalute ili raznih kripto-banaka poput Coinbase. Kad god su vaše kriptovalute spremljene na usluzi koja ima pristup internetu, to je loše.
- ako imate financijske mogućnosti, pokrenite validation node kod kuće i pripomognite decentralizaciji sustava

Ovakvi su problemi osobitno bitni sada, u vrijeme guranja kriptovaluta u širu javnost, kada mnogo ljudi ima velik potencijal gubitka ogromne količine novca zbog grešaka u sustavu ili zbog ljudske prirode.

_Za znatiželjne, prototip napada opisanog gore implementiran je u [ovom repozitoriju][repo]._


[paper]: https://btc-hijack.ethz.ch/files/btc_hijack.pdf
[page]: https://btc-hijack.ethz.ch/
[cc]: https://bitfalls.com/hr/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/hr/2017/08/20/blockchain-explained-blockchain-works/
[nodes]: https://bitfalls.com/hr/2017/11/26/whats-bitcoin-node-mining-vs-validation/
[pool]: https://bitfalls.com/hr/glossary/#mining-pools
[rew]: https://bitfalls.com/hr/glossary/#block-reward
[ledger]: https://bitfalls.com/hr/2017/09/08/hardware-wallets-like-ledger-nano-s-work/
[paperwallet]: https://bitfalls.com/hr/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[address]: https://bitfalls.com/hr/2017/08/31/what-cryptocurrency-wallet/
[forks]: https://bitfalls.com/hr/2017/11/07/segwit2x-fork-can-expect-whos-behind/
[unstop]: https://bitfalls.com/hr/2017/08/21/is-bitcoin-unstoppable/
[pow]: https://bitfalls.com/hr/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[bcore]: https://bitcoin.org/en/download
[repo]: https://github.com/nsg-ethz/hijack-btc/tree/master/delay_attack