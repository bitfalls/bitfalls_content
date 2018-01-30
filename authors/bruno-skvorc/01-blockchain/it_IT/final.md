Cos'è la *blockchain*?

Come funziona, perché è popolare e perché sono in molti a dire che rivoluzionerà il mondo?

In questo articolo spiegheremo la tecnologia blockchain con un semplice esempio che risulta valido per la maggior parte delle criptovalute attualmente in circolazione. Non avete familiarità con il concetto di criptovalute? Leggete [qui][cryptocurrencies]!

## Mario e Luigi

Mario deve inviare $100 a suo fratello, Luigi, perché Luigi, essendo Luigi, ha contratto qualche debito dall'altra parte del mondo.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-01.png" alt="Luigi e i debiti" width="350">

Mario entra in banca e dice "Voglio inviare $100 a Luigi". Il cassiere risponde "Numero di conto, per favore", "Documento, per favore" e "fatto", in quest'ordine.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-02.png" alt="Mario che invia soldi a Luigi tramite la banca" width="350">

In questo scenario *centralizzato*, la banca è l'autorità **_centrale_** che gestisce i soldi di Mario e Luigi. Entrambi si fidano del fatto che la banca invii l'importo e si fidano dei numeri che vedono negli estratti conto. Si fidano della banca nonostante tutto ciò che la banca deve fare è cambiare un numero in un database. È tutto digitale, in fin dei conti.

Ma, quando dipendiamo da una tale autorità centrale, questa autorità rappresenta una minaccia. Può sparire con i nostri soldi, può essere disonesta e non aumentare il valore del conto di Luigi facendo però diminuire quello di Mario, tenendosi la differenza, o ancora può essere distratta e commettere un errore. Le nostre finanze dipendono direttamente dalla sua competenza.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-03.png" alt="Un ladro che se ne va con i soldi della banca" width="450">

Uno dei modi per impedire uno scenario del genere è evitare completamente la banca e avere un nostro sistema per tracciare i numeri e il passaggio di questi da un punto al successivo.

Immaginate un foglio di carta sul quale annotiamo lo stato del nostro conto corrente. Se solo Mario e Luigi usassero un tale sistema, sarebbe difficile garantirne l'obiettività: se uno dei due diventa disonesto, il sistema è compromesso. Per questo, un sistema *distribuito* (non-*centralizzato*) deve avere un numero minimo di partecipanti per essere obiettivo: almeno tre.

## Tanti fogli di carta

Immaginiamo di avere 5 partecipanti: Yoshi, Mario, Luigi, Wario e Bowser, e che ognuno abbia il proprio foglio di carta.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-04.png" alt="Ogni partecipante ha il proprio foglio di carta" width="550">

Mario vuole inviare $100 a Luigi. Per farlo, dice a tutti (proclamando ad alta voce): "Sto inviando $100 a Luigi! Prendetene tutti nota!"

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-05.png" alt="Mario invia soldi a Luigi e avverte tutti" width="550">

In quel momento, ogni partecipante controlla il conto di Mario per assicurarsi che possa permettersi di effettuare l'invio a Luigi (sì, lo stato di ogni conto è pubblico) e, in caso positivo, trascrive la transazione sul suo foglio di carta. Le transazioni di questo tipo vengono annotate sui fogli di carta dei partecipanti fino a quando tutti terminano il posto in cui scrivere. In altre parole, **ogni** transazione fra **due persone qualsiasi** viene registrata nel **foglio di carta di ogni partecipante**.

Prima di archiviare il foglio completato in una cartella o in un archivio e iniziarne uno nuovo, completamente vuoto, bisogna sigillarlo con uno speciale codice.

## Sigilli e mining

Questo "sigillo" garantisce che i contenuti dei fogli siano veri.

Ma come si ottiene un tale sigillo? Con uno speciale algoritmo (un'operazione matematica) che, quando riceve alcuni dati in ingresso, produce sempre lo stesso risultato *se i dati che riceve sono gli stessi*.

Prendiamo il seguente esempio:

X1 + X2 + ... Xn = Z.

In altre parole, una semplice somma.

Supponiamo che i valori dei nostri fogli siano *vero e valido* (ossia, tutte le transazioni sono confermate) se e solo se una determinata operazione di somma produce il numero 10000.

1000 + 6000 + 3000 = 10000.

In questo caso, i dati in ingresso sono 1000, 6000 e 3000, mentre il _sigillo_ è 10000.

Okay, a questo punto supponiamo che i partecipanti visti sopra si accordino su questo punto: se, sommando tutti i numeri sul foglio e **una specifica** combinazione di altri numeri si ottiene 10000, allora le transazioni su quel foglio sono valide e possono considerarsi confermate.

Ad esempio, se il foglio contiene le seguenti 5 transazioni:

- Mario -> Luigi = 100
- Bowser -> Yoshi = 200
- Yoshi -> Luigi = 100
- Mario -> Yoshi = 500
- Luigi -> Wario = 100

La somma è 1000, quindi stiamo cercando un numero che dia 10000 quando sommato a 1000. Quello che rimane, 9000, può essere ottenuto con molte combinazioni:

- 5000 + 4000
- 1000 + 1000 + 1000 + 1000 + 1000 + 1000 + 1000 + 1000 + 1000
- 2000 + 3000 + 2000 + 2000
- ecc...

Un computer non può intuitivamente dire quali numeri produrranno il numero desiderato. Per ottenere tale risultato, un computer deve _tirare a indovinare_ diverse combinazioni casuali di numeri inferiori a 10000 fino a quando ottiene una combinazione che produce 10000. Così, il primo dei nostri partecipanti che indovina correttamente una combinazione di numeri che producono 10000 quando sommati con tutti i valori delle transazioni dei fogli sarà colui che comunicherà a tutti gli altri il risultato.

Immaginiamo che Yoshi abbia trovato la combinazione 4000 + 5000. Dirà a tutti: "Ho trovato 10000! Provate con 4000 e 5000!" Visto che è molto semplice verificare la correttezza dei numeri di Yoshi inserendoli nell'algoritmo, gli altri partecipanti provvedono a verificarli. I fogli di tutti gli altri partecipanti che adesso, durante questo controllo, producono 10000 quando vengono sommati a 4000 e 5000 convalidano la lista di transazioni. Facendo questo, viene raggiunto il consenso che i fogli siano validi.

Se il foglio di qualcuno **non** produce 1000 quando sommato con 4000 e 5000, abbiamo un problema. Se, ad esempio, Bowser ha registrato - per errore o di proposito - una transazione diversa, nella quale Mario ha dato a Luigi $200 e non $100, allora la somma non corrisponderà ai requisiti.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-07.png" alt="Tutti tranne Bowser confermano i fogli" width="550">

Il foglio di Bowser è quindi considerato non valido e, se vuole continuare a partecipare al sistema, dovrà eliminare il foglio, copiare il foglio valido di qualcun altro e promettere di fare più attenzione in futuro. Inoltre Yoshi, che è quello che ha scoperto la combinazione vincente, ottiene un premio - ad esempio $5 - dal sistema. Questo sistema *produce* dal nulla i $5 da dare in premio al partecipante fortunato.

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-08.png" alt="Yoshi ottiene un premio, Bowser getta via il suo foglio" width="550">

Questa *produzione* di soldi dal nulla viene chiamata *mining* nel mondo delle criptovalute.

Sebbene questo sia un esempio notevolmente semplificato, l'unica vera differenza con la blockchain (a parte il fatto che nella realtà tutto è digitale e automatico) è il fatto che l'algoritmo utilizzato per produrre il *sigillo* è diverso: è più complesso e può accettare sia numeri che lettere, e restituisce codici come `90bdaa79bbccacf8558edcbb30df48d7fc920eeb75a28f883de4100f58a99b49`.  

<img src="https://bitfalls.com/wp-content/uploads/2017/08/blockchain-06.png" alt="Un foglio sigillato" width="350">

I *sigilli* vengono chiamati *hash* e gli algoritmi che li producono - come ad esempio SHA256, che ha prodotto il codice qui sopra - vengono chiamate *funzioni di hashing*. Provate ad aprire [questo link] (http://www.xorbin.com/tools/sha256-hash-calculator) e inserire un testo qualsiasi nel campo. A prescindere dal fatto che digitiate una sola parola o l'intera bibbia, produrrà sempre un hash di esattamente 64 caratteri.

Quindi, per ottenere l'hash che sigilla il nostro foglio, possiamo inserire nell'algoritmo tutte le transazioni presenti nel foglio. Queste diventano quindi un hash. Visto che il numero di combinazioni di caratteri che possiamo passare a un algoritmo è infinito, indovinare i caratteri che sono stati inseriti nell'algoritmo è matematicamente impossibile.

Nello specifico, nella blockchain Bitcoin, il consenso generale della rete e di tutti i suoi partecipanti è che, se un hash prodotto (ottenuto combinando l'hash dell'ultimo foglio e tutte le transazioni del foglio attuale, più una certa quantità di numeri e lettere casuali) inizia con un determinato numero di zeri, allora è valido. Ad esempio, se il foglio 1 ha come hash `0000000000000000058edcbb30df48d7fc920eeb75a28f883de4100f58a99b49`, l'hash valido del foglio 2 sarà quello che (quando le transazioni dell'attuale foglio e alcuni caratteri casuali vengono aggiunti all'hash dell'ultimo foglio) contiene un numero uguale o maggiore di zeri nella parte iniziale.

Per ottenere questa combinazione di caratteri casuali necessari per produrre un nuovo hash valido, un computer deve fare dei tentativi. I computer moderni sono molto veloci e testano migliaia di combinazioni al secondo, ma questo ancora non basta perché quel numero di possibili combinazioni è prossimo a infinito. Fra parentesi, l'hash riportato sopra mostra che la difficoltà di indovinarne uno nuovo è 17, perché all'inizio ci sono 17 zeri. Con il tempo la difficoltà crescerà e i nuovi hash validi avranno bisogno di sempre più zeri davanti.

Quando il foglio di ogni partecipante è contrassegnato come valido all'interno dell'hash, viene messo da parte in una cartella, una sorta di _libro mastro_, e si inizia a usarne un altro.

### Termini della Blockchain

Usando i termini della blockchain...

- un foglio è *un blocco*.
- un blocco contiene molte *transazioni*.
- un blocco segue sempre il blocco precedente, formando una catena. Una catena di blocchi, una _blockchain_. I blocchi convalidati sono messi da parte in un *libro mastro* (_ledger_, sinonimo di *blockchain*).
- i computer che indovinano le combinazioni sono chiamati *nodi*. Un nodo che indovina la combinazione dell'hash ottiene una ricompensa sotto forma di token della blockchain; nel nostro esempio, alcuni Bitcoin.
- indovinare le combinazioni è detto *mining* perché si *scava* alla ricerca di un certo valore all'interno di un mucchio di ipotesi casuali. Invece di usare muscoli e picconi, usiamo l'elettricità, il tempo e il potere di calcolo dei computer. I personaggi della nostra storia sono non a caso tutti all'interno di piccoli go-cart perché si tratta di una gara: il primo che conferma un blocco con un hash valido vince e ottiene la ricompensa. Avviene lo stesso anche nel mondo della blockchain, dove i computer più potenti (o un insieme di computer) vincono le ricompense del blocco.
- l'esistenza di un nuovo hash valido è considerata una **prova di lavoro** (_proof of work_). Questo è un modello usato oggi dalla maggior parte delle criptovalute per fare in modo che indovinare con semplicità o imbrogliare non sia finanziariamente sostenibile a causa dei costi troppo alti dell'elettricità. Alcuni protocolli come Ethereum si stanno spostando verso una **prova di partecipazione** (_proof of stake_) nella quale gli sprechi inutili di elettricità vengono minimizzati e la punizione per la partecipazione non valida è più severa, ma questo è un argomento per un altro post.


## Conclusioni

Tutte le criptovalute sono basate sulla _tecnologia blockchain_. La blockchain è ciò che le rende trasparenti, definitive (impossibili da falsificare o duplicare) e parzialmente limitate nella quantità massima prodotta. A differenza delle valute fiat (USD, Euro, ecc.), le criptovalute non possono semplicemente essere stampate dai loro creatori, tranne nel caso di alcune valute manipolate o truffaldine come Ripple (XRP) e OneCoin - ne parleremo in un altro post.

La tecnologia blockchain permette un controllo distribuito nel sistema finanziario di una società, locale o globale, e aiuta a evitare gli intermediari. Questo è uno dei motivi principali per cui le [criptovalute][cryptocurrencies] sono diventate così tanto popolari. Grazie alla natura distribuita della blockchain e dei milioni di utenti in tutto il mondo che agiscono da contabili e validatori, alcuni considerano le criptovalute come indistruttibili e inarrestabili. Ma, tristemente, non è così, e capiremo perché in un altro articolo (link nella prossima sezione).

## E adesso?

- [Cosa sono le criptovalute][cryptocurrencies] per capire di cosa si tratta e da dove arriva il loro valore
- [Il Bitcoin non è inarrestabile][unstoppable] per scoprire quando è semplice fermare e distruggere una criptovaluta
- [I Bitcoin non sono infiniti][finite] per capire come il limite teorico di 21 milioni di Bitcoin prodotti non è vero, spiegato in termini semplici
- [Bitcoin non significa anonimato][anon] per capire perché spesso la gente dice (sbagliando) che Bitcoin è sinonimo di anonimato ed è qualcosa di utile per il mercato nero e i finanziamenti criminali
- [Cos'è Ethereum?][eth] per iniziare a conoscere la più potente criptovaluta di oggi 

[cryptocurrencies]: https://bitfalls.com/it/2017/08/20/cryptocurrency/
[unstoppable]: https://bitfalls.com/it/2017/08/21/is-bitcoin-unstoppable/
[finite]: https://bitfalls.com/2017/09/17/bitcoin-finite-just-myth/
[anon]: https://bitfalls.com/it/2017/09/18/anonymous-cryptocurrencies-like-bitcoin/
[eth]: https://bitfalls.com/it/2017/09/19/what-ethereum-compare-to-bitcoin/
