Un *wallet* è uno speciale _indirizzo_ che può ricevere [i token di una criptovaluta][cc]. Concettualmente, è simile a un indirizzo di posta elettronica. Ogni [blockchain] ha il suo tipo di wallet, solitamente incompatibile con gli altri (non è possibile inviare bitcoin a un indirizzo Ethereum, ad esempio).

Chiunque può avere tutti i wallet (indirizzi) che vuole e non c'è modo di arrivare a identificare chi c'è dietro a un indirizzo a meno che l'utente lo dichiari pubblicamente. La maggior parte delle blockchain rende pubblicamente accessibili le informazioni sugli indirizzi: il numero di token contenuti e le transazioni passate sono visibili senza restrizioni. Confrontato con un indirizzo email, un wallet è come una casella di posta che tutti possono leggere, ma che solo il proprietario può usare per inviare messaggi.

I token presenti in un indirizzo vengono usati grazie a una _chiave privata_, una combinazione di lettere e numeri matematicamente impossibili da indovinare. Tutti i token vengono "spostati" dall'indirizzo A all'indirizzo B tramite la firma di una transazione con la chiave privata che viene inviata alla blockchain per conferma. È importante notare che nelle criptovalute i token non vengono fisicamente spostati come avviene normalmente. Ciò che accade, invece, è che un certo numero di token si considerano essere presenti nell'indirizzo che è stato dichiarato esserne il proprietario da tutti i partecipanti della blockchain.

Pensate a una persona A che non ha niente in tasca, ma con 200 testimoni che dicono che A ha invece $500. Se la persona A dice "Do i miei $500 alla persona B" davanti a tutti i testimoni, questi informeranno tutti i nuovi arrivati che adesso è B ad avere i $500, non A. Se qualcuno dice il contrario, gli altri lo noteranno e correggeranno la falsa testimonianza. È così che funziona la [blockchain].

Queste transazioni sono firmate con la chiave privata alla quale ha accesso solo il proprietario di un indirizzo. I modi principali per ottenere un wallet (ossia, un indirizzo pubblico e una chiave privata) sono 3:

- generando la chiave e l'indirizzo tramite un _client della blockchain_ (un programma della blockchain della quale vi interessa il token, ad esempio Electrum per Bitcoin, Metamask, MyEtherWallet o Mist per Ethereum).
- usare una soluzione hardware come il [Ledger Nano S][ledger], una chiavetta USB che salva le vostre chiavi private e può contenere una moltitudine di indirizzi per molte criptovalute diverse.
- aprire un account in un sito di scambi di criptovalute, detti _exchange_

La terza opzione è sicuramente la più semplice ma, in virtù del fatto che questi siti tengono per sé la chiave privata generata per il wallet, non avrete mai davvero il controllo del vostro wallet. Se l'exchange sparisce o viene violato, come è già successo con Mt.Gox e Bitfinex, la stessa cosa succederà ai vostri fondi. È fortemente raccomandato spostare i token fuori dall'exchange in un wallet privato appena possibile, dopo averli ottenuti. 

Per sapere come iniziare con ognuna delle criptovalute e come ricevere e inviare i token, leggete [qui][wallet].

[cc]: https://bitfalls.com/it/2017/08/20/cryptocurrency/
[blockchain]: https://bitfalls.com/it/2017/08/20/blockchain-explained-blockchain-works/
[ledger]: https://bitfalls.com/it/shop/ledger-nano-s-bitfalls/
[wallet]: https://bitfalls.com/en/2017/09/01/send-receive-bitcoin/
