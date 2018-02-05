Una delle domande più comuni dei nuovi crypto-entusiasti è come i [wallet][wallet] hardware come il [Ledger Nano S][ledger] possano essere il metodo più sicuro per conservare le [criptovalute][cc]. Cosa succede se il dispositivo viene rubato o distrutto?

In questo post cercheremo di spiegare in modo tecnico (ma, speriamo, umanamente comprensibile) come funziona un dispositivo del genere, cosa fa e come può essere sia flessibile che sicuro.

Prima di tuffarci nelle spiegazioni, è consigliabile leggere [questo breve post][wallet] relativo ai wallet per le criptovalute, così che la terminologia utilizzata nel resto dell'articolo risulti chiara.

## BIP

Quando la [blockchain][bc] ha fatto la sua comparsa come tecnologia dietro ai Bitcoin e un gruppo di programmatori / scienziati ha voluto proporre una nuova caratteristica, hanno dovuto formalizzare e presentare l'idea in modo che fosse leggibile e comprensibile da tutti i partecipanti del network bitcoin. Tali proposte formali erano chiamate _Bitcoin Improvement Proposals_ (proposte di miglioramento di bitcoin) o BIP. [Tutte le BIP](https://github.com/bitcoin/bips) sono discusse pubblicamente prima di essere implementate nella blockchain.

![Alcune BIP](https://bitfalls.com/wp-content/uploads/2017/09/01-1.png)

Impostando delle solide fondamenta per le nuove idee, questo ha permesso ad altre [blockchain][bc] di adottare le buone idee che ritenevano interessanti e scartare le altre.

_Qui le cose si fanno un po' più tecniche e complesse. Vi promettiamo che, alla fine del post, ne sarà valsa la pena, continuate a leggere!_

Una di queste buone idee è stata la [BIP 39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki). La BIP 39 usa la matematica per capire come usare un set di 24 normali parole per ottenere un _seed_, un grande numero casuale dal quale vengono poi generate altre chiavi per i [wallet di criptovalute][wallet].

_**Curiosità:** Se vi interessa dare un'occhiata a questa lista di parole, guardate [qui] (https://github.com/bitcoin/bips/blob/master/bip-0039/bip-0039-wordlists.md)._

La BIP 39 definisce anche un modo per rendere sicure queste 24 parole con una passphrase addizionale che conta come parola numero 25. Se non è selezionata una passphrase ne viene usata una vuota, e quindi si tratta sempre di 24 parole + 1 passphrase (vuota o meno che sia).

_**Curiosità:** Questa passphrase è diversa dalle password che normalmente si usano perché non viene prodotto alcun messaggio di errore se viene utilizzata quella errata. Qualsiasi passphrase combinata con 24 parole produce un seed valido, utilizzato in scenari di negabilità plausibile - un meccanismo di protezione da estorsione che spiegheremo più tardi._

Questo seed è utilizzato per generare una _root key_ - una combinazione non indovinabile di lettere e numeri - per ogni criptovaluta alla quale siete interessati. Ogni [blockchain][bc] ha il proprio metodo di generazione della root key a partire dal seed, e nell'esempio dei bitcoin viene dalla [BIP 32] (https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki) che porta ad avere chiavi come questa: `xprv9s21ZrQH143K3QTDL4LXw2F7HEK3wJUD2nW2nRk4stbPy6cq3jPPqjiChkVvvNKmPGJxWUtg6LnF5kejMRNNU3TGtRBeJgk33yuGBxrMPHi`. 

Questa chiave viene poi utilizzata per generare varie chiavi private che diventano [wallet di criptovalute][wallet] per una certa blockchain.

Confusi?

![Una persona confusa](https://bitfalls.com/wp-content/uploads/2017/09/02.jpg)

Tutto si riduce a questo: La BIP 29 viene usata per scegliere una certa combinazione di parole, protetta o meno da una passphrase, che vengono utilizzate per generare i wallet con una formula come quella descritta nella BIP 32.

Ma tutto questo, quindi, cos'ha a che fare con un dispositivo come il Ledger?

## Ledger

Alla prima accensione, il Ledger genera il suddetto seed a 256 bit. Questo numero verrà usato per calcolare le 24 parole che verranno visualizzate sul display del dispositivo.

![Le parole visualizzate sul display del dispositivo](https://bitfalls.com/wp-content/uploads/2017/09/04.jpg)

L'utente si deve annotare queste 24 parole in un foglio di carta che può trovare nella scatola del Ledger e tenerle al sicuro, lontane dal Ledger.

Inoltre, il Ledger richiede che venga utilizzato un PIN che può avere dalle 4 alle 8 cifre. Se, dopo l'impostazione iniziale, il PIN viene sbagliato per 3 volte, il Ledger distruggerà tutti i dati in esso presenti.

Se il Ledger viene distrutto, rubato o perso, il proprietario può usare le parole presenti nel foglio di carta per ripristinarne i contenuti - su un altro Ledger o in un wallet software come [MyEtherWallet] [mew], tornando ad avere accesso a fondi e indirizzi. Questo è possibile perché tutto quello che serve per rigenerare la root key sono queste 24 parole e la passphrase (se impostata).

È importante ribadire che, dalla stessa combinazione di 24 parole, viene sempre generata la stessa root key, e da tale root key vengono sempre generati gli stessi indirizzi. Di conseguenza, per recuperare **tutti** i wallet generati tramite la BIP 39, tutto quello che serve è una combinazione di 24 parole inserite in un software o hardware che supporta tale metodo di generazione.

### Negabilità plausibile

Prima abbiamo accennato alla protezione da estorsione, vediamo cos'è.

Il Ledger non chiederà la passphrase quando lo accendete, ma solo il PIN. La passphrase non può nemmeno essere impostata quando accendete il dispositivo per la prima volta, potete aggiungerla solo in seguito dalle impostazioni.

![Collegare una passphrase al PIN](https://bitfalls.com/wp-content/uploads/2017/09/03-1.jpg)

Questo vi permette di collegare un PIN separato a una passphrase per averne due (o più). Ogni PIN sarà legato alla propria passphrase e, in virtù del fatto che ogni gruppo di 24 parole + passphrase producono sempre un seed valido (non c'è alcun avviso di "password errata"), è semplice definire un falso PIN-esca da dare a qualcuno che vi sta costringendo a rivelarglielo.

In un caso simile, inserire il PIN-esca secondario non distruggerà i dati del Ledger ma aprirà i wallet corrispondenti a tale passphrase quando aggiunto alle vostre 24 parole. Un malintenzionato non può sapere che gli avete dato il PIN errato, e avrà accesso solo a indirizzi fasulli. Per fare sembrare tutto più reale, aggiungete qualche minuscola quantità di criptovalute agli indirizzi per farli sembrare reali: i saldi a zero non sono convincenti.

### La probabilità di indovinare le chiavi

Molta gente si chiede quanto può essere semplice indovinare le 24 parole e ottenere in tal modo accesso al wallet di qualcuno, soprattutto in virtù del fatto che la BIP 39 non usa tutto il dizionario ma solo 2048 parole.

Le possibilità sono 2^256, ossia 115792089237316195423570985008687907853269984665640564039457584007913129639936 possibili combinazioni per le 24 parole. Supponendo di avere un computer dalla potenza di calcolo attualmente impossibile, in grado di indovinare 100 **miliardi** di combinazioni al secondo, servirebbero:

    115792089237316195423570985008687907853269984665640564039457584007913129639936 / 100000000000000 = 1157920892373161954235709850086879078532699846656405640394575840 secondi
    
In pratica, circa 36717430000000000000536992568032848736216424136408984408 anni, e solo con un computer più potente di qualsiasi cosa sia mai stata immaginata dal genere umano.

E se si conoscono tutte le parole, ma non il loro ordine? In tal caso, il numero di combinazioni possibile è 24! (fattoriale di 24).

    24! = 620448401733239439360000
    
Il computer visto sopra avrebbe bisogno di:

    620448401733239439360000 / 100000000000000 = 6204484017 secondi
    
Corrispondenti a 196,6 anni.

Quindi, anche sapendo **tutte** le parole della combinazione ma dovendo indovinarne l'ordine, servirebbero 200 anni con un computer di potenza inimmaginabile per gli standard odierni. Se non sapete quali parole dovete indovinare, il numero deve essere moltiplicato per 2048 per ogni parola mancante. Quindi, nel caso appena visto, non sapere una sola parola aumenterebbe il tempo necessario per indovinare la combinazione di 400.000 anni.

## Conclusioni

Il Ledger è un metodo incredibilmente sicuro dove tenere le proprie criptovalute. Supera in prestazioni di qualsiasi tipo di dispositivo USB nel quale potete salvare le vostre chiavi.

Il dispositivo ha un suo processore interno che calcola le chiavi, il che significa che la root key non lascerà mai il dispositivo, e questo lo mantiene al sicuro da potenziali virus o malware che possono effettuare transazioni automatiche dal computer tramite il quale lo state usando. Inoltre, il Ledger richiede anche una conferma hardware extra per ogni transazione: dovete premere un pulsante sul dispositivo ogni volta che inviate dei fondi, altrimenti non funzionerà. Non si possono sottrarre furtivamente fondi con un Ledger.

Se perdete o rompete il vostro Ledger è semplicissimo riottenere i vostri fondi inserendo semplicemente le 24 parole ottenute durante la prima configurazione. Queste parole devono essere tenute al sicuro e lontane da occhi indiscreti.

Potete usare il nostro shop online per acquistare il [Ledger marchiato Bitfalls][ledger] a un prezzo inferiore di quello al [dettaglio](https://ledgerwallet.com/products/ledger-nano-s). È anche possibile acquistare il Ledger con opzioni extra come criptovalute già al suo interno o un'ora di conferenza via Skype insieme al dispositivo, durante la quale vi spiegheremo tutto quello che serve sapere sul dispositivo e vi aiuteremo a configurarlo.

Per qualsiasi domanda, ci potete contattare anche [via email][mail]. Fatevi sentire!

[ledger]: https://bitfalls.com/product/ledger-nano-s-bitfalls/
[cc]: https://bitfalls.com/it/2017/08/20/cryptocurrency/
[bc]: https://bitfalls.com/it/2017/08/20/blockchain-explained-blockchain-works/
[wallet]: https://bitfalls.com/it/2017/08/31/what-cryptocurrency-wallet/
[startbtc]: https://bitfalls.com/2017/09/01/send-receive-bitcoin/
[mew]: https://myetherwallet.com
[mail]: mailto:contact@bitfalls.com
