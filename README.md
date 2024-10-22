# advwork
Il plugin Advwork è correttamente installabile e utilizzabile per le versioni di Moodle comprese tra la 3.4.9 e la 4.0.12 sulla quale, con php 7.4.28, sono stati fatti i test.
Dalla versione 4.1.X in poi, l’installazione genera un errore alla validazione.
Le versioni di Moodle 4.0.X richiedono una versione di php compresa tra la 7.3.0 e la 8.0.X.
È raccomandato l’uso delle estensioni di php “sodium” e “exif” ed è necessario che la variabile “max_input_vars”, che si trova in php.ini, abbia valore superiore a 5000 per le versioni di php 8.X mentre per le versioni 7.X è solo raccomandato.
Le richieste legate al database in base alla tipologia scelta sono:
- versioni di MySQL superiori alla 5.7,
- versioni di PostgreSQL superiori alla 10,
- versioni di MariaDB superiori alla 10.2.29
Requisiti ottenuti da https://moodledev.io/general/releases/4.0 

La prima cosa da fare è quindi scaricare Moodle. 
Sul sito https://download.moodle.org/windows/ è disponibile per Windows un pacchetto che comprende già Xampp con le impostazioni necessarie al corretto funzionamento della versione scaricata di Moodle; basta quindi scegliere una versione compatibile, come la 4.0.12 da me utilizzata.
Una volta scaricato il file .zip, estrarre il tutto in una nuova cartella del file system (di solito il Disco locale C) che si può chiamare per esempio “moodle”.

In questa cartella si troveranno i seguenti file:
- cartella "server"
- "Start Moodle.exe"
- "Stop Moodle.exe"
 
Cliccando su “Start Moodle.exe” si apre un terminale che inizializza Apache e MariaDB (potrebbe richiedere conferma all’accesso l’antivirus).
Andando poi su un browser all’indirizzo http://localhost/ viene richiesta la lingua da utilizzare, preimpostata a inglese, e se modificata richiederà di scaricare un pacchetto.

Cliccando sul tasto “Next” viene poi richiesto di confermare l’unico indirizzo modificabile sulla pagina, la “Data directory” e proseguire.
 
Sono ora da inserire i dati del database, tra cui il nome, la password e la porta che possono anche essere lasciati come da precompilazione (con password e porta vuoti).

Infine, viene richiesta la conferma di aver letto termini e condizioni e, dopo aver accettato, verranno mostrate delle estensioni di php con dei check su di esse, quelle rosse sono necessarie, quelle gialle sono raccomandate e “ok” significa che sono già correttamente installate. Tramite la versione per Windows di cui sto parlando però, non sarà necessario fare cambiamenti e si può cliccare direttamente sul tasto “Continue”.
Verrà mostrata l’installazione del database e delle sue tabelle.

Deve essere ora creato il profilo amministratore del sito, è possibile modificare le varie informazioni ed è obbligatorio inserire quelle con il punto esclamativo rosso.
L’ultima fase dell’installazione richiede di definire le impostazioni di base del sito, come il suo nome per esteso, quello in forma abbreviata, la mail si supporto e il “no-reply address”. Cliccando “Save changes” verrà mostrato il sito installato e funzionante e si è già loggati con il profilo amministratore precedentemente creato.

Per l’installazione del plugin Advwork è necessario andare nel menù in alto su “Site administration” ->Plugins ->Install plugins.

Cliccare su “Choose a file…” e su “Upload a file” nella schermata che viene aperta, è possibile scegliere il file locale advwork.zip da installare.
Ricordo che è importante per l'installazione del plugin che il file advwork.zip NON venga rinominato.
Proseguendo viene richiesta un'altra conferma dopo la validazione del file e viene eseguito di nuovo un check sulle estensioni di php installate, se poi è tutto corretto, nella pagina di check del plugin, si puo’ cliccare su “Upgrade Moodle database now” e avviare l’installazione (simile a quella di Moodle). Una volta terminato, cliccando sul tasto “Continue”, si devono definire le impostazioni di default di Advwork per completare l’installazione, come il “grade for submission”, “grade for assessment”, la “grading strategy” e il numero di reviews da assegnare ai peer (nel mio caso sono stati 100, 100, Accumulative grading with percentage weights e 3 rispettivamente). 
Per spegnere il processo che tiene attivo il sito in locale, bisogna aprire il file “Stop Moodle.exe”, questo chiuderà il vecchio terminale rimasto aperto fermando i servizi Apache e MariaDB.


Precedenti tesisti sull'argomento:
Jacopo Colozzi A.A. 2021/2022 - Moodle-answer: un sistema docker-wise per sperimentare la Valutazione tra Pari.

Valeria Stramazzo A.A. 2020/2021 - WorkShop 2.0 – Valutazione automatica di Esercizi svolti in un Ambiente di Peer Assessment, basata sulla Modellazione degli Studenti.

Bruno Marino A.A. 2017/2018 - OpenAnswer - Sistema basato sulla peerevaluation per la correzione semi-automatica di esercizi: creazione modulo Moodle e sviluppo report avanzati.

Antonio Lonta A.A. 2016/2017 - Aggiornamento sperimentazione di un sistema per la correzione semiautomatica di domande aperte basato sulla peer-evaluation e sull’intervento del docente.


