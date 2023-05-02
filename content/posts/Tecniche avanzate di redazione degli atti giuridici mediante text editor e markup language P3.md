# Tecniche avanzate di redazione degli atti giuridici mediante text editor e markup language (parte II)

> In questi mesi sono preso dalla preparazione ed esecuzione del [Corso PCT accreditato CNF fino agli inizi di Marzo](https://avvocati-e-mac.it/blog/2023/1/31/corso-pct-accreditato-ed-office-hour). Mi sono quindi reso conto che le pubblicazioni vere di articoli sul sito si stanno rarefacendo.
> Ho quindi deciso di “riciclare” la tesina che ho svolto nel 2021 a conclusione del corso di perfezionamento “Coding for lawyers e legal tech. Programmazione per giuristi, intelligenza artificiale e blockchain per il professionista legale del futuro” coordinato dal [prof. Ziccardi](https://ziccardi.eu)
> Vista la mole del testo ho deciso di dividerla in 3 parti che, spero, possano anche essere lette separatamente.
> Se vuoi ricevere il manoscritto completato (finemente impaginato in LaTeX grazie a Pandoc e Markdown) oltre che ricevere questi articoli, [iscriviti alla mia newsletter](https://www.avvocati-e-mac.it/mailinglist), a fine Marzo 2023 inviarò a tutti gli iscritti il PDF (se leggi questo articolo dopo tale data sappi che iscrivendoti alla newsletter avrai la possibilità di leggere anche tutte quelle precedenti).
> Ultimo avvertimento: lo stile, visto a chi mi rivolgevo, non è quello del sito ma più “aulico”.
> Buona lettura.

# Tecniche avanzate di redazione di un atto giuridico

Abbiamo visto quindi che un programma di video-scrittura non è necessario in modo esclusivo per creare e revisionare un documento e che esistono varie soluzioni per produrre in digitale un documento in varie fasi concentrandosi, per ognuna, al raggiungimento dello scopo specifico di quella fase.

Abbiamo inoltre visto alcuni strumenti (programmi) che permettono di fare ciò ma è ancora necessario mettere tutto insieme per un flusso di scrittura digitale utile anche al giurista.

## Premessa metodologica

Prima di entrare nel dettaglio ed affrontare il cuore dell’argomento pare opportuno tuttavia specificare brevemente la metodologia utilizzata per individuare gli strumenti che si indicheranno e che, come è ovvio, non sono gli unici possibili.

Anzitutto si è scelto degli strumenti facilmente reperibili ed in particolare parte del mondo _open-source_. Per quel che qui ci interessa sapere, un software open-source o software libero è un software di cui è disponibile il codice sorgente e può essere modificato ed implementato a piacimento. Ciò porta l’innegabile vantaggio che, con le dovute competenze, è possibile personalizzare detto software per le proprie esigenze e, anche se lo sviluppatore smettesse di aggiornarlo, questo sarebbe comunque a nostra disposizione per il futuro.

L’altro cardine di scelta è stata la possibilità di utilizzare questi strumenti su differenti piattaforme / sistemi operativi. Così facendo è possibile utilizzare il flusso di lavoro indipendentemente dalla piattaforma / sistema operativo che si preferisce utilizzare quotidianamente.

Inoltre, grazie a queste scelte, si evita il problema di c.d. _lock-in_ ovvero di blocco o chiusura di una specifica piattaforma e, quindi, il flusso di lavoro è a prova di futuro e degli eventuali differenti sviluppi tecnologici.

Degna di menzione, poiché pure essendo un’applicazione proprietaria implementa i principi sopra descritti e permette di separare l’attività di scrittura da quella di impaginazione, è **Scrivener** [^scrivener]. Presente sia per piattaforma Windows che per macOS ed iOS, è un’applicazione pensata per scrivere romanzi ovvero grossi progetti ma che può essere facilmente utilizzata per l’ambito lavorativo normale. In ambito giuridico il grosso vantaggio di questa applicazione è che oltre alla gestione della parte di scrittura in _Scrivener_ è possibile includere la parte di ricerca avendo un unico ambiente in cui scrittura e materiale di ricerca sono un tutt’uno.

Fatte quindi queste dovute premesse esaminiamo nel dettaglio gli strumenti da utilizzare e come unire l’uno con l’altro.

## Gli strumenti (i programmi) di base

Come abbiamo visto nei punti che precedono attraverso il _markdown_ è possibile scrivere un documento in modo semplice e con \textit{\LaTeX} è possibile creare dei documenti impaginati secondo le regole tipografiche. È possibile unire questi due mondi?

La risposta è sì, grazie ad un programma: _Pandoc_ [^pandoc].

### Pandoc

_Pandoc_ è un convertitore di documenti gratuito e open source, ampiamente utilizzato come strumento di scrittura (soprattutto nel mondo accademico) e come base per i flussi di lavoro di pubblicazione. È stato creato da _John MacFarlane_, professore di filosofia presso l'Università della California, Berkeley.

Non è qui di interesse approfondire eccessivamente il funzionamento specifico di _Pandoc_ [^pandoc_funzionamento], quel che ci interessa sottolineare è che grazie a questo programma è possibile convertire in modo facile un documento scritto in _markdown_ in un PDF impaginato secondo le regole della tipografia o, nel caso fosse necessario, un documento in formato Microsoft Word (.DOCX).

### Perché non utilizzare direttamente \LaTeX?

Il lettore, legittimamente, potrebbe domandarsi per quale motivo non scrivere direttamente in \LaTeX\ ed aggiungere un passaggio intermedio nella scrittura.

Come accennato nelle premesse \LaTeX\ è un potente linguaggio di _markup_ ma se, come nel mondo dell’ufficio e in quello più umanistico, non è necessario implementare complesse formule matematiche, questo strumento può inizialmente risultare eccessivo. Come si vedrà nel prosieguo, per svolgere alcune funzioni avanzate sarà necessario inserire nei documenti scritti in _markdown_ della sintassi in \LaTeX\, ma queste, nella maggior parte dei casi, risultano marginali rispetto al complessivo testo scritto e specifiche di apposite necessità.

Secondariamente _Pandoc_ è fortemente incentrato sull’uso del _markdown_ ciò permette di avere una maggior compatibilità con altri formati e quindi avere un sistema di inter-operatività. In particolare dovendo spesso interfacciarsi con il standard in cui si scrivono i documenti nel mondo dell’ufficio e legale ovvero _Microsoft Word_.

### YAML e dialetto \LaTeX

La semplicità del formato _markdown_ trova il suo limite nella possibilità di implementare delle formattazioni avanzate. Come detto il _markdown_ ed i suoi ulteriori sviluppi / gusti (in inglese _flavor_) seppur hanno ampliato le basi dello stesso (aggiungendo ad esempio l’implementazione delle tabelle, delle note a piè di pagina ed altro) non permettono una tipo composizione avanzata come \LaTeX.
 
Per permettere una conversione “avanzata” da _markdown_ a \LaTeX, _Pandoc_ utilizza un escamotage: una intestazione YAML [^yaml].

Questa intestazione, che può essere anteposta all’inizio del documento in _markdown_ così come inserita in un documento separato che poi dovrà essere “passato” a _Pandoc_ come parametro per la conversione, permette di impostare una serie di specifiche caratteristiche che, altrimenti, non sarebbero presenti in un normale documento _markdown_. In particolare è possibile passare i parametri per il formato di pagina, la lingua con cui sillabare il testo ed i moduli di \LaTeX\ da caricare ed utilizzare. 

A mero titolo esemplificativo di seguito si mostra l’intestazione YAML di questo stesso documento (Figura 1).

![Immagine d’esempio dell’intestazione YAML di un documento scritto in _markdown_, _Pandoc_ e \LaTeX](UniMi_-_tecniche_avanzare_di_redazione_degli_atti_giuridici_mediane_text_editor_e_markup_language/int_YAML.png) 

## Interfaccia grafica _vs_ interfaccia a riga di comando

Abbiamo quindi visto gli strumenti (i programmi) per creare i documenti e, forse il lettore si sarà accorto, tutti questi strumenti sono pensati per la riga di comando.

L’**interfaccia a riga di comando** è la primissima interfaccia dei computer, precedente addirittura ai monitor a tubo catodico con cui originariamente ci si interfacciava ma successivo al sistema di carte perforate.
Seppur ormai sconosciuta ai più e, per chi la conosce, temuta, l’interfaccia a riga di comando è alla base di tutti i sistemi operativi evoluti che utilizzano un gestore a finestre dell’interfaccia. Il più famoso (anche se non il primo [^primo_windows]) sistema operativo a finestre è _Microsoft Windows_ (_window_ in inglese significa appunto finestra).
Rispetto all’interfaccia grafica di un sistema a finestre, dotato abitualmente di un puntatore per navigare tra le varie finestre dei programmi, l’interfaccia a riga di comando utilizza quale esclusivo input la tastiera.

L’utilizzo dell’interfaccia a riga di comando, inizialmente, è abbastanza frastornante per l’utente inesperto (o abituato all’interfaccia grafica), tuttavia ha degli aspetti interessanti per lo scrittore.

Anzitutto l’interfaccia a riga di comando ha come principale _input_ la tastiera ovvero lo strumento principale di uno scrittore. Se infatti l’interfaccia grafica ha il pregio di rendere l’interazione uomo macchina molto più semplice permettendo di manipolare degli oggetti (le finestre ed i programmi al loro interno) con il tempo le interfacce grafiche si sono notevolmente appesantite diventando una selva di menù e sotto-menù abbastanza complicati da navigare e che, nella maggior parte dei casi, non possono essere utilizzati con il semplice aiuto della tastiera. Non dover alzare le mani dalla tastiera è quindi un notevole vantaggio per lo scrittore digitale che può semplificare l’interazione con la scrittura focalizzandosi su un unico strumento di interazione con il computer.

Secondariamente l’interfaccia a riga di comando è minimale. Se non si conosce un comando non lo si può di fatto usare. Questa assenza di complessità è un vantaggio per lo scrittore anche se, inizialmente, è una barriera abbastanza pesante per poter iniziare ad operare. Questa limitazione se può sembrare un problema, sul lungo periodo, permette allo scrittore digitale di concentrarsi esclusivamente su alcuni programmi della riga di comando senza doversi preoccupare di altri. Con sistemi ad interfaccia grafica, al contrario, lo scrittore digitale interrompe spesso il suo lavoro per cercare questa o quella funzione all’interno di un sotto menù.

Da ultimo l’interfaccia a riga di comando è presente su tutti i sistemi operativi (anche su Windows 10 che da qualche anno può installare una CLI - _Command Line Interface_ ovvero Interfaccia a Riga di Comando). Lo scrittore digitale quindi potrà lavorare in modo uniforme su qualsiasi sistema operativo debba operare.

## L’editor di testi

Un _editor di testi_ è un programma per la composizione di testi. I programmi di video-scrittura sono un genere rispetto alla categoria generale degli editor di testo. Questi ultimi rispetto ai programmi di video-scrittura hanno delle caratteristiche meno “raffinate” ma maggiore flessibilità utilizzando solo testo semplice.

Esiste una infinità di _editor di testo_; abitualmente tutti i sistemi operativi tra i vari programmi gratuiti che incorporano hanno un _editor di testo_: per Windows è Blocco note[^notepad] mentre per macOS è TextEdit[^textedit], ad esempio. Questi programmi sono molto generici ed abitualmente non vengono utilizzati per scrivere grosse quantità di testo. 
Per una utenza più professionale esistono programmi con interfaccia grafica come _VS Code_ di _Microsoft_, _Atom_ sviluppato da _GitHub_ o _Sublime Text_, per citarne alcuni. Tutti questi programmi, tuttavia, non sono a riga di comando ma hanno una specifica interfaccia grafica.
Tali programmi, però, posseggono potenti strumenti per modificare il testo (prevalentemente pensati per il codice ma, come detto, utilizzabili anche per scrivere della normale prosa).  
Un altro vantaggio di questi programmi è il fatto che le loro funzioni di base possono essere espanse grazie ai c.d. _plug-in_ dei mini-programmi sviluppati da soggetti terzi che permettono l’implementazione di specifiche funzionalità.

### Vim, filosofia ed i suoi “modi”

Un simile approccio, ma nel mondo di programmi a riga di comando, lo ha **Vim** ovvero _Vi Improved_.  
La prima versione di _Vim_ è stata rilasciata nel 1991 dal suo creatore Bram Moolenaar. Vim nasce per fornire una versione migliorata di _Vi_ un precedente editor di testi che trova le sue origini nel 1976 e che, a sua volta, è il successore di un altro editor di testi della “preistoria” dell’informatica ovvero _Ed_.

Proprio perché _Vim_ trae le sue origini dai primi programmi per scrivere testo ha delle caratteristiche particolari che altri programmi “moderni” non hanno.

Anzitutto, _Vim_ è pensato per essere usato esclusivamente con la tastiera. Ciò in ragione del fatto che, come già detto, agli albori dell’informatica la tastiera era il principale, se non l’unico, strumento di input dei dati in un computer. Gli antenati di _Vim_, Ed e Vi, erano pensati per questo mondo e _Vim_, ereditandone le caratteristiche e funzionalità, ne ha abbracciato l’eredità.  
Proprio in ragione di questa caratteristica specifica la modalità di funzionamento di _Vim_ è profondamente diversa da quella di altri programmi. In _Vim_ è infatti possibile utilizzare la tastiera sia come strumento per digitare del testo, ma anche per manipolare il testo stesso. Ciò è possibile grazie alle differenti modalità in cui viene eseguito Vim: nella modalità _normale_ (c.d. Normal Mode) le lettere della tastiera vengono utilizzate per impartire comandi a Vim; nella modalità di _inserimento_ (c.d. Insert Mode) la tastiera viene utilizzata per digitare del testo semplice; nella modalità _Visuale_, (c.d. Visual Mode) infine la tastiera permette di selezionare il testo per poi eseguire su di esso delle operazioni.  
Altra particolarità di _Vim_ è la possibilità di concatenare i comandi (che vedremo tra poco) assieme in una sorta di linguaggio. Rispetto infatti ad un normale programma di video-scrittura o editor di testo, in _Vim_ i comandi di base digitati in modalità normale possono essere concatenati l’uno all’altro permettendo di manipolare il testo in modo complesso e strutturato.

A mero titolo di esempio: con la lettera `D` è possibile cancellare un oggetto. Vim riconosce vari oggetti come le parole (stringhe di testo delimitate da spazi vuoti), le frasi (delimitate da . ? e !) o i paragrafi (porzioni di testo suddivise da una riga vuota). Grazie a ciò è possibile digitare un comando come `D2W` per cancellare le 2 parole successive a dove si trova il cursore (`D` sta per _delete_ ovvero cancella, `W` sta per _word_ ovvero parola e `2` indica quanti oggetti “parola” si vuole cancellare).   
Come si vede quindi è possibile digitando 3 lettere, senza alzare le dita dalla tastiera, cancellare una o più parole quando con un normale programma con interfaccia grafica abitualmente si utilizzerebbe il mouse e la tastiera e, di fatto, ci si interromperebbe nell’attività vera e propria di scrittura.  
Questo approccio, inoltre, è molto utile quando, dopo aver revisionato un testo utilizzando strumenti analogici come ad esempio la correzione su carta, si deve manipolare del testo in modo focalizzato saltando da una parte all’altra del documento. 

Secondariamente, ma non per importanza, il fatto di avere queste differente modalità in _Vim_ rende esplicito allo scrittore quando sta scrivendo ed invece quando sta revisionando il testo. Ciò, come visto nei punti che precedono, permette di rendere più strutturata e compartimentata l’attività di scrittura digitale.

Ci sono tuttavia degli svantaggi nell’utilizzo di _Vim_ per scrivere e, come probabilmente il lettore si sarà già accorto, il più grosso è legato alla necessità di imparare il linguaggio dei comandi di _Vim_. Se infatti una volta imparato come utilizzare ed unire i singoli comandi, l’operatore riesce a manipolare il testo scritto in modi impensabili, la precedente fase di apprendimento è sicuramente impegnativa e, inizialmente, frustrante oltre che in parte alienante (le modalità di Vim possono inizialmente lasciare molto perplesso lo scrittore abituato all’utilizzo di una interfaccia grafica). Secondo chi scrive, tuttavia, i vantaggi di utilizzare questo particolare editor di testo sono sicuramente superiori agli svantaggi che, lo si deve ricordare, sono solo iniziali.

Infine _Vim_ è programmabile. Ciò significa che l’utente, grazie alla personalizzazione del .VIMRC, il file di configurazione di _Vim_, può configurare il programma come preferisce. Addirittura è possibile creare delle scorciatoie a tastiera personalizzate.

Da ultimo _Vim_ ha una comunità notevole di utenti che, nel corso del tempo, hanno creato una serie di _plug-in_ per espanderne le sue funzionalità. In particolare esistono vari _plug-in_ pensati appositamente per gli scrittori.

Grazie a tutto ciò _Vim_ diventa un ottimo strumento che si aggiunge ed unisce a quelli sopra individuati per permettere un flusso di scrittura digitale ottimizzato.

# Esempi di atti avanzati generati con la tecnica sopra descritta

A conclusione di questo scritto pare giusto dare qualche breve esempio di come sia possibile utilizzare questi strumenti nel mondo reale.

A tal proposito di seguito si individuano quelli che, quantomeno nel mondo giuridico, sono i casi “tipici” della scrittura di documenti.

## Atti giudiziari

Nel panorama giuridico italiano con l’introduzione dal 2014 dei processi telematici (dapprima con quello civile, poi con quello amministrativo e tributario ed infine quello penale) c’è stata un notevole cambiamento di paradigma.  
Se infatti originariamente i giudizi erano tutti su carta nel corso di un periodo relativamente breve questi si sono convertiti (più o meno con successo) in digitale.

Tale passaggio epocale ha permesso, a chi ha voluto cogliere il cambiamento, di accrescere le possibilità date dalla carta, con inserimento di link ai documenti citati, alla normativa di riferimento  ed altre funzioni presenti esclusivamente su di un documento digitale.

Tale necessità di abbracciare le nuove possibilità degli strumenti digitali sono state anche incentivate dal legislatore che, con l’introduzione del [comma 1-bis dell’art. 4 del D.M. n.55 del 2012](http://www.normattiva.it/uri-res/N2Ls?urn:nir:ministero.giustizia:decreto:2014-03-10;55~art4!vig=) ha riconosciuto un aumento del 30% dei compensi giudiziali liquidati all’avvocato che utilizza appieno questi strumenti nella redazione dei propri atti.

Qui non interessa entrare nel dettaglio di come fare ciò [^blogFilippo] si vuole solo segnalare che grazie a _Markdown_, _Pandoc_ e _LaTeX_ è possibile implementare quanto richiesto dalla normativa.

È infatti possibile: 

* creare link ai documenti allegati (utilizzando le specifiche funzioni del _Markdown_);
* auto generare un indice navigabile dei contenuti del documento sia a “margine” del PDF finale sia all’interno del documento stesso;
* inserire link alla normativa citata utilizzando il progetto [Normattiva.it](https://www.normattiva.it) (<https://www.normattiva.it>);
* inserire immagini (come fatto anche in questo documento) a corredo del testo scritto.

Per quanto poi riguarda l’inserimento dei dati ripetitivi, grazie alle funzioni più avanzate di \LaTeX, è possibile inserire all’interno dell’atto dei segnaposto che possono essere “riempiti” una volta sola (all’inizio dell’atto) e riutilizzati più e più volte [^variabiliPasut].

## Contratti e normativa

Per quanto puoi riguarda la predisposizione di contratti e normativa si può segnalare ancora quanto fatto da _Carlo Piana_ [^git_piana2].

## Riviste scientifiche umanistiche

Infine si segnala anche un altro interessante utilizzo degli strumenti sopra indicati per la produzione di una rivista scientifica [^rivista].

La particolarità di questo approccio è che grazie ad una serie di script gli autori della rivista consegnano i loro elaborati nel formato Microsoft Word e, grazie ad una serie di passaggi, questi documenti vengono convertiti ed impaginati secondo un modello \LaTeX\ predefinito.

# In conclusione

Come visto scrivere in digitale senza utilizzare un programma di video-scrittura è possibile. Questo aiuta lo scrittore digitale a differenziare le varie fasi di creazione del documento digitale. Suddividendo la fase di ideazione, scrittura, revisione ed impaginazione permette a chi produce documenti di dedicarsi in modo specifico alla singola fase della scrittura digitale, permettendo così di ottenere risultati migliori.

I vantaggi dell’approccio illustrato sono innumerevoli: dalla possibilità di lavorare su qualsiasi sistema operativo sia a disposizione dello scrittore, evitare il c.d. _lock-in_, i nostri documenti (essendo scritti in testo semplice) saranno a prova del futuro e, utilizzando il testo semplice, sarà possibile applicare a questo testo svariate automazioni, delegando ad esempio a \LaTeX\ l’impaginazione del documento, infine comprendendo meglio il funzionamento del computer lo potremo utilizzare meglio e con maggior padronanza.

Ciò detto, questo approccio ha anche degli innegabili svantaggi. Richiede anzitutto un investimento di tempo nell’imparare gli strumenti e un flusso di lavoro differente. Inoltre, se questo tipo di scelta è affrontabile da parte di chi lavora da solo, questa soluzione è meno praticabile per chi lavora in gruppo e necessita che anche altri soggetti modifichino il loro flusso di lavoro. Inoltre tale approccio è difficoltoso per chi non è a capo della propria struttura ma è subordinato e deve implementare flussi di lavoro scelti dai propri dirigenti.

Pur a fronte dei limiti descritti, come mostrato al punto precedente, è possibile, con qualche sforzo, integrare il flusso di lavoro descritto con l’utilizzo di _Microsoft Word_ in modo relativamente trasparente all’utente finale [^rivista].

[^scrivener]: È possibile trovare l’applicazione **Scrivener** a questo indirizzo [https://www.literatureandlatte.com/scrivener/overview](https://www.literatureandlatte.com/scrivener/overview). In italiano potete trovare vari articoli ed un webinar tenuto da chi scrive al seguente indirizzo <https://www.avvocati-e-mac.it/blog/tag/Scrivener>.

[^pandoc]: **Pandoc** è una utility a riga di comando che permette di convertire da un formato di linguaggio di _markup_ ad un altro. È reperibile al seguente link: <https://pandoc.org>.

[^pandoc_funzionamento]: Per maggiori **approfondimenti** sul funzionamento di **Pandoc** è possibile consultare l’articolo del 2013 di _ArsTeXnica_ al seguente indirizzo: <https://www.guitex.org/home/images/ArsTeXnica/AT015/pandoc.pdf> o per informazioni più pratiche gli articoli reperibili al seguente link: <https://www.avvocati-e-mac.it/blog/tag/Pandoc>.

[^yaml]: Il YAML un acronimo ricorsivo che deriva da “YAML Ain't Markup Language” è un linguaggio di _markup_ semplice da leggere pensato per la strutturazione di dati. Per esempio ed approfondimenti potete seguire il link a Wikipedia: <https://it.wikipedia.org/wiki/YAML>.

[^primo_windows]: Il primo vero sistema operativo con gestore delle finestre fu lo Xerox Alto poi “copiato” da Apple per il suo Macintosh, Microsoft Windows implementava tale sistema solo successivamente, vincendo tuttavia poi la “battaglia” dei sistemi operativi e diventando lo standard di fatto (per approfondimenti wikipedia: <https://it.wikipedia.org/wiki/Window_manager>)

[^notepad]:  link a descrizione wikipedia: <https://it.wikipedia.org/wiki/Blocco_note>
[^textedit]: link a pagina del supporto Apple per TextEdit: <https://support.apple.com/it-it/guide/textedit/welcome/mac>
[^blogFilippo]: Per maggiori approfondimenti su come creare nel dettaglio atti telematici avanzati si può far riferimento alla serie di articoli scritti dal sottoscritto al seguente link: <https://www.avvocati-e-mac.it/blog/2019/4/1/perch-non-usare-un-programma-di-video-scrittura-per-scrivere-un-atto-telematico>.
[^variabiliPasut]: Link ad articolo dell’avv. Franco Pasut sul punto: <https://francopasut.blogspot.com/2018/10/atti-giudiziari-utilizzare-le-variabili.html>
[^git_piana2]: A questo link <https://www.techeconomy2030.it/2019/02/07/leg-git-usare-git-per-progetti-legali/> è possibile leggere l’articolo pubblicato dall’_avv. Carlo Piana_ per ulteriori approfondimenti.
[^rivista]: Per maggiori approfondimenti e spiegazioni dettagliate potete consultare l’articolo di cui al link che segue: <http://pierog.it/2018/03/markdown-workflow/>
