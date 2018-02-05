_In questo articolo spiegheremo cos'è Ethereum in modo semplice e adatto a chi inizia, confrontandolo con la più popolare criptovaluta del mondo: bitcoin. L'articolo è stato scritto pensando ai principianti, ma è comunque consigliato leggere la nostra [introduzione alle criptovalute][cc] e l'[introduzione alla blockchain][bc] prima di continuare, per riuscire a comprendere meglio il contenuto che segue._

---

Ethereum, lanciato nel 2015 da Vitalik Buterin, è una speciale [blockchain][bc] con uno speciale token chiamato Ether (il cui simbolo negli exchange è ETH). Ether viene usato come carburante (letteralmente, _gas_) per alimentare la rete Ethereum ed eseguire _smart contract_ (vedi di seguito). Ai miner (le persone che fanno funzionare la rete) viene pagato Ether come _costo in gas_ per rendere possibili le caratteristiche che vedremo fra poco; non è quindi tanto una cripto**valuta** quando piuttosto un cripto**carburante**.

Ecco in cosa si differenzia dal bitcoin e cosa lo distingue nel mondo delle criptovalute.

### Finalità

Bitcoin ha un [limite teorico di 21 milioni di bitcoin prodotti][finite], che lo rende una valuta deflazionata: il valore circolante diminuisce nel tempo visto che alcuni perdono l'accesso al proprio [wallet], altri accumulano, ecc.

Ether non ha limiti, ma ha un valore di produzione fisso. Al momento vengono minati poco più di 15,5 milioni di Ether all'anno, corrispondenti a 5 ETH al secondo. Molto di più del valore di produzione dei bitcoin, corrispondente a circa 25 BTC ogni 10 minuti circa. Dopo che Ethereum avrà modificato la modalità di mining, più precisamente nota come tipo di consenso, a PoS (vedi di seguito), il tasso di produzione diminuirà drammaticamente, avvicinandosi allo zero.

![Coinmarketcap: grafico attuale di Ethereum](https://bitfalls.com/wp-content/uploads/2017/09/01-3.png)

Tutto questo farà sì che il valore di Ethereum cessi di [crescere sproporzionatamente][bubble], raggiungendo così una stabilità di prezzo che lo rende adatto agli usi pratici descritti di seguito.

## Smart Contract

Bitcoin supporta il semplice scripting. Ad esempio, è possibile scrivere un piccolo programma che supporta le transazioni che hanno indirizzi multipli come input, e che ha bisogno di multi-sig (la firma di più persone prima che i fondi siano inviati). Il linguaggio utilizzato non è però _turing equivalente_ perché non ha _loop_ (se non sapete cosa siano, non importa).

I programmi su Ethereum sono invece scritti utilizzando Solidity, un linguaggio Turing equivalente che permette di scrivere qualsiasi tipo di programma, in presenza di adeguate risorse (entro limiti ragionevoli). Quando un programma viene scritto con Solidity, deve essere inviato nella blockchain, operazione che costa _gas_, pagato in Ether. Più grande e complesso il programma, più costa _distribuirlo_ nella blockchain. Per questo, l'inefficienza ha un costo: è nell'interesse di tutte le parti in causa fare in modo che tali programmi siano più piccoli possibile.

Lo stesso Vitalik descrive gli smart contract usando un'analogia con un distributore automatico:

"_Un distributore automatico [...] di massima implementa le condizioni di un certo tipo di accordo. E le condizioni dell'accordo sono semplici. Tu inserisci $2, l'acqua esce. Tu non inserisci $2, l'acqua non esce. Se non metti i $2 ma l'acqua esce lo stesso, allora qualcosa non funziona. E un distributore automatico è di massima una codifica di queste regole, oltre a essere dotato di un meccanismo che lo rende sicuro. Sicuro a sufficienza per bottiglie d'acqua da $2._"

<iframe width="560" height="315" src="https://www.youtube.com/embed/r0S4qIMf4Pg" frameborder="0" allowfullscreen></iframe>

Quando paghiamo una certa quantità di Ether per uno smart contract, quello smart contract può decidere cosa fare di questo Ether: inviarlo all'indirizzo A in base a una condizione, all'indirizzo B in base a un'altra, bloccarlo per un certo periodo di tempo, rimborsarlo, spostarlo in base a un input esterno, innescare un output esterno sulla base di questo Ether e via dicendo.

Un esempio pratico sarebbe replicare Kickstarter. Kickstarter è un sito che permette di raccogliere fondi per dei progetti prima che questi vengano lanciati. La regola di base è che, se una certa quantità di soldi viene superata in un certo numero di giorni, il progetto è stato un successo e il denaro può essere inviato ai creatori dello stesso. In caso contrario, i soldi vengono restituiti. Questa semplice condizione è molto semplice da replicare con gli smart contract eliminando dall'equazione errori umani, avidità e intermediari, offrendo un modo completamente decentralizzato di raccogliere fondi.

Le applicazioni create con gli smart contract vengono chiamate app decentralizzate o _dapp_.

## Cosa sono i token ERC20?

Una caratteristica molto importante di Ethereum è la capacità di creare nuovi token sulla blockchain Ethereum. I token sono una sorta di "criptovaluta" creata tramite specifici smart contract e usati proprio come una criptovaluta: vengono inviati e ricevuti da specifici indirizzi. Questi token vengono inviati a indirizzi Ethereum, non a [indirizzi][wallet] della blockchain di una nuova criptovaluta. Questo perché i token non sono una criptovaluta in sé quanto il risultato dell'esecuzione di smart contract. Dire che i token sono una criptovaluta è sbagliato tanto quanto dire che un programma è un linguaggio di programmazione.

Un token può essere un biglietto per un concerto, punti fedeltà in un negozio, valuta all'interno di un gioco e via dicendo.

![Una carta fedeltà](https://bitfalls.com/wp-content/uploads/2017/09/02-3.jpg)

Con la nascita di sempre più token, il loro formato è stato reso standard tramite [ERC20][erc20], un insieme di regole su come svilupparli in modo che siano gestibili da vari exchange e sistemi. Questo significa che tutti i token ERC20 hanno alcune caratteristiche comuni come un simbolo per gli exchange, un'icona, eccetera, che li rende semplici da elencare nei vari siti web riutilizzando lo stesso codice utilizzato per un precedente codice ERC20.

Creare token ERC20 in combinazione con gli smart contract è la caratteristica rivoluzionaria di Ethereum, pronta a cambiare completamente il modo di fare business. I token danno la possibilità alle aziende di essere autonome, permettono acquisti parziali di beni digitali, permettono anche la creazione di macchine autonome in grado di guidarsi da sole, acquisire clienti, lasciarli o raccogliere pagamenti. Il numero di casi possibili è talmente grande che non abbiamo nemmeno scalfito la superficie.

## PoS

La terza, grande differenza da bitcoin è che Ethereum passerà a una modalità di _mining_ diversa e alternativa chiamata PoS (Proof of Stake, prova di partecipazione) invece della PoW (Proof of Work, prova di lavoro).

Tramite [bitcoin][bc], un'unità di prova di lavoro è l'hash ottenuto tramite calcoli massicci. Faremo presto un post su PoS e PoW ma, per adesso, è sufficiente dire che con un sistema PoS non ci sono sprechi a livello di elettricità, caratteristica importante vista la [dominazione cinese sul mining][finite].

![Una mining farm di criptovalute](https://bitfalls.com/wp-content/uploads/2017/09/03-3.jpg)

PoS, ovviamente, ha i suoi problemi. In questo sistema, un utente Ethereum che cerca di essere un _nodo_ (il nuovo tipo di miner) _partecipa_ con il proprio Ether per garantire la correttezza dei calcoli. Se prova a ingannare il sistema eseguendo calcoli falsi che non risultano validi, gli altri nodi lo escludono e la partecipazione va persa. In caso contrario, il nodo torna in possesso del proprio Ether dopo qualche mese (già, mesi!) più una certa quantità raccolta dalle transazioni o dall'esecuzione di smart contract. La dimensione della partecipazione scoraggia eventuali partecipanti malintenzionati: la quota iniziale è di 1000 Ether.

## Conclusioni

Riassumendo, Ethereum è diverso da Bitcoin per questi motivi:

- passerà presto da [prova di lavoro][pow] a [prova di partecipazione][pos]
- ci sarà presto una prova-sulla-quantità (quantum-proof, stiamo lavorando a un post sull'argomento)
- supporta la creazione di sub-token sulla propria rete (le istruzioni su come crearli arriveranno presto con un nuovo post!)
- supporta una logica personalizzata sulla blockchain per una completa automazione finanziaria (smart contract)

C'è un'altra similitudine che ci piace citare parlando di BTC vs. ETH:

- Bitcoin è l'oro. Complicato da ottenere, caro e lento da trasferire ma molto deflazionato e finito ([per adesso][finite]). Questo lo rende un buon investimento nel lungo termine, ma dipende a chi lo chiedete.
- Ethereum, come molti penserebbero, non è l'argento. L'Ethereum è il petrolio. Con l'aiuto dell'Ethereum vengono creati altri prodotti, e i token ERC20 corrispondono a plastica, cosmetici, vernici, gomma... Ethereum è la base di un'industria completamente nuova e, sebbene ci siano molte alternative (Tezos, EOS, Rootstock, NEO), nessuna ha una comunità di sviluppatori o utenti tanto grande e sviluppata come quella che ha Ethereum.

Se volete acquistare o vendere Ethereum, [fatecelo sapere][mail]. Ci fa sempre piacere ricevere commenti o domande, che ci potete fare nella sezione dei commenti qui sotto!

[cc]: https://bitfalls.com/it/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/it/2017/08/20/blockchain-explained-blockchain-works/
[finite]: https://bitfalls.com/2017/09/17/bitcoin-finite-just-myth/
[bubble]: https://bitfalls.com/2017/09/06/bitcoin-bubble/
[wallet]: https://bitfalls.com/2017/09/08/best-ways-protect-cryptocurrency-wallet/
[wallet1]: https://bitfalls.com/2017/08/31/it/what-cryptocurrency-wallet/
[mail]: mailto:contact@bitfalls.com
[erc20]: https://github.com/ethereum/EIPs/pull/610
[pos]: https://bitfalls.com/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
[pow]: https://bitfalls.com/2017/10/23/whats-the-difference-between-proof-of-work-pow-proof-of-stake-pos-and-delegated-pos/
