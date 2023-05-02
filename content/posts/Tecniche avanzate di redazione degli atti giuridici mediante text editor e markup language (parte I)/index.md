---
title: "Tecniche avanzate di redazione degli atti giuridici mediante text editor e markup language (parte I)"
date: 2023-02-13T09:03:20-08:00
author: Filippo Strozzi
slug: Tecniche-avanzate-di-redazione-degli-atti-giuridici-mediante-text-editor-e-markup-language-parte-I
draft: false
showToc: true
TocOpen: false
cover:
    image: "cover.jpeg"
tags: ["Comandi Rapidi", "Actions"]
---

> In questi mesi sono preso dalla preparazione ed esecuzione del [Corso PCT accreditato CNF fino agli inizi di Marzo](https://avvocati-e-mac.it/blog/2023/1/31/corso-pct-accreditato-ed-office-hour). Mi sono quindi reso conto che le pubblicazioni vere di articoli sul sito si stanno rarefacendo.
> Ho quindi deciso di “riciclare” la tesina che ho svolto nel 2021 a conclusione del corso di perfezionamento “Coding for lawyers e legal tech. Programmazione per giuristi, intelligenza artificiale e blockchain per il professionista legale del futuro” coordinato dal [prof. Ziccardi](https://ziccardi.eu)
> Vista la mole del testo ho deciso di dividerla in 3 parti che, spero, possano anche essere lette separatamente.
> Se vuoi ricevere il manoscritto completato (finemente impaginato in LaTeX grazie a Pandoc e Markdown) oltre che ricevere questi articoli, [iscriviti alla mia newsletter](https://www.avvocati-e-mac.it/mailinglist), a fine Marzo 2023 inviarò a tutti gli iscritti il PDF (se leggi questo articolo dopo tale data sappi che iscrivendoti alla newsletter avrai la possibilità di leggere anche tutte quelle precedenti.
> Ultimo avvertimento: lo stile, visto a chi mi rivolgevo, non è quello del sito ma più “aulico”.
> Buona lettura.



# Il problema dello scrivere in digitale

In un periodo storico in cui si parla di giustizia predittiva, intelligenza artificiale applicata all’esame di una grossa mole di documenti giuridici, sono stati lasciati indietro problemi più pratici e legati all’attività quotidiana, come ad esempio le problematiche legate alla _scrittura di atti giuridici in digitale_.  
Il presente documento cercherà di fotografare l’attuale situazione, le criticità e le possibili soluzioni alternative. Sia noto al lettore che, le tecniche di seguito elencate fanno parte dell’arsenale utilizzato dal sottoscritto quotidianamente e, come tale, chi scrive può essere considerato “tendenzioso” utilizzando il metodo che descrive.

Fatte tali dovute premesse è possibile esaminare il più ampio problema dello scrivere in digitale, per poi addentrarci in quello della scrittura in digitale di atti giuridici.

Il computer è diventato nel corso dell’ultimo ventennio lo strumento per scrivere in digitale. Essendo uno strumento multi-funzionale, nel corso dell’evoluzione ed adozione dei computer nel mondo del lavoro e per uso personale, si sono sviluppati tanti programmi, denominati di video-scrittura, per scrivere un testo direttamente davanti al computer.

Lo standard di fatto per questi programmi è _Microsoft_ **Word**. Esistono altri programmi che implementano funzioni similari, dal software open-source _LibreOffice_ con l’applicazione _Writer_ al programma _Pages_ della _Apple_, ma l’archetipo di funzionamento di questi sistemi applicativi è nella sostanza il medesimo. Sono, infatti, tutti programmi _WYSIWYG_ (_What You See Is What You Get_ ovvero “quel che vedi è quello che ottieni”).

Con tutti questi programmi di video-scrittura viene mostrato all’utilizzatore, sullo schermo del computer, un foglio di carta virtuale all’interno del quale è possibile scrivere ed impaginare il proprio documento, ottenendo a video un risultato simile od uguale a quello della successiva stampa cartacea o digitale del documento stesso.

I vantaggi di un simile sistema nel mondo dell’ufficio sono stati notevoli. Si ricordi che prima dell’avvento di tali programmi la produzione dei documenti avveniva con la macchina da scrivere: prima meccanica e poi elettronica. Di fatto questi programmi hanno permesso di portare nel mondo dell’ufficio (anche grazie all’avvento di idonei sistemi di stampa prima a getto di inchiostro e poi laser) quello che, una volta, era esclusiva della carta stampata e dell’editoria professionale.

Pur a fronte di innegabili vantaggi, i programmi di video-scrittura hanno portato anche degli svantaggi, di cui si cercherà di parlare.

## Formato proprietario e non standard

L’avvento dei programmi di video-scrittura è contestuale e probabilmente causato da un altro evento particolare che ha influenzato e probabilmente influenzerà nel tempo lo sviluppo informatico ed il modo di utilizzare i computer: il monopolio del sistema operativo Windows.

Un computer come noto è uno strumento hardware, meccanico, che deve essere riempito da un applicativo o software, cioè, nello specifico a livello base, da un sistema operativo che permetta di utilizzare l’hardware sottostante. Tra gli anni '80 e '90 del secolo scorso, con l’avvento e l’utilizzo sempre più massiccio del c.d _personal computer_ nel mondo del lavoro si è assistito anche all’avvento del sistema operativo _Windows_ della software house _Microsoft_, che, ora, è installato su circa il 76,6 % dei computer attualmente in circolazione [^mercatoWindows]. Assieme al sistema operativo _Windows_ la _Microsoft_ ha sviluppato una c.d. suite, ovvero un insieme di programmi, pensato per il mondo dell’ufficio, chiamata _Office_ [^ms_Word] (la cui ultima incarnazione nel momento in cui si scrive è _Office 365_) di cui il programma di punta era ed è **Microsoft Word**.

Grazie all’adozione massiccia del sistema operativo _Windows_ il programma di video-scrittura di _Microsoft_ è diventato lo standard di fatto nella creazione e nello scambio delle bozze dei documenti nel mondo dell’ufficio.

Nel corso del tempo le conseguenze di questo monopolio di fatto sono state molte, qui brevemente analizzeremo alcune problematiche importanti ma non esclusive: il formato proprietario e non standard dei file .DOC e .DOCX.

Una delle tecniche da subito implementate dai software commerciali è stata quella di utilizzare formati proprietari per salvare i documenti creati con i loro programmi. Ciò significa che, senza i loro programmi, è impossibile (o quasi) aprire un documento con un altro programma. Questo ha creato un sistema di auto mantenimento del monopolio di fatto. Più uffici o realtà utilizzano il software di una determinata società più chi si affaccia nel mondo della scrittura utilizzerà quel software.

Se questo sistema è comprensibile dal punto di vista commerciale, pone dei profondi problemi dal punto di vista della selezione “innaturale” del programma che si usa per scrivere.

Il programma dominante in un certo “ambiente” spesso non è il miglior programma, se si esamina in particolare _Microsoft Word_, si può giungere alla considerazione opposta, come di seguito si evidenzierà.

## Lo scrittore dattilografo

Deve farsi una breve premessa storica per comprendere l’evoluzione di _Microsoft Word_ e quella dei programmi di video-scrittura.

Nel mondo degli uffici, fino all’avvento massiccio dei computer, a fine degli anni '80 ed inizio degli anni '90 del secolo scorso in America e tra il '90 ed il 2000 in Italia, esisteva una distinzione tra chi scriveva un documento e chi lo “batteva a macchina”. La figura del dattilografo sia negli uffici legali che in qualsiasi ufficio di piccole e medie dimensioni era una presenza essenziale. Era infatti solo attraverso questa figura professionale che la gestione di tutti i documenti “stampati” (sarebbe meglio dire battuti a macchina) poteva avvenire.

Le prime macchine da scrivere digitali hanno ceduto pian piano il passo ai computer per la scrittura dei documenti da ufficio ed i soggetti che per primi hanno utilizzato i programmi di video-scrittura sono stati i dattilografi. Le basi dei programmi di video-scrittura sono nate proprio nell’ottica e per l’utilizzo di una specifica e qualificata categoria professionale. La dattilografia è una disciplina professionale ormai sconosciuta ai più, ma che, tra la seconda metà dell’ottocento e la fine del novecento, è stata fondamentale per gli uffici.

Scrivere digitando il testo su una tastiera con la macchina da scrivere e successivamente fare delle modifiche al documento predisposto richiedeva personale altamente addestrato onde evitare di dover riscrivere un documento a metà dell’opera e scriverlo in tempi ragionevoli.

Con l’avvento del computer dei programmi di video-scrittura tuttavia non fu più necessario avere questa istruzione specifica perché il testo scritto al computer poteva essere riletto, modificato e revisionato infinite volte prima della stampa effettiva.

La “semplicità” (qui intesa come possibilità per chiunque di scrivere e revisionare un documento davanti al computer) tuttavia ha col tempo fatto diminuire la presenza negli ufficio di un dattilografo.

Nel corso dell’ultimo ventennio si è quindi assistito ad un progressivo passaggio della fase di scrittura dalla carta con strumenti analogici al computer. **Lo scrittore è diventato**, senza averne le competenze, **dattilografo**. Addirittura si potrebbe affermare che la dattilografia è scomparsa come professionalità.

## Contenuto e forma uniti

Le conseguenze di questo cambiamento, progressivo ma visibile, sono state e, credo, siano tuttora importanti.

I programmi di video-scrittura infatti sono uno strumento (software) per creare un documento a stampa (ora anche in formato digitale come un PDF) pensato per i dattilografi, cioè per soggetti che dovevano occuparsi di trascrivere un documento, non scriverlo. Lo stesso archetipo del foglio di carta digitale che corrisponde al foglio di carta stampato ne è un chiaro esempio.

Fino all’avvento dei programmi di video-scrittura contenuto e forma (tipografica) erano domini separati nel mondo dell’ufficio, con figure professionali distinte per le differenti fasi (nell’mondo dell’editoria professionale lo sono tuttora) ma oggi questo, nella maggior parte dei casi, non è più così.

Il personale c.d di segreteria (se presente in ufficio) spesso non ha più una formazione specifica in dattilografia e, soprattutto, tutti, dal personale altamente specializzato ai soggetti meno specializzati, scrivono davanti ad un computer.

Spesso chi scrive professionalmente è un auto-didatta della scrittura al computer. Scrivere al computer con un programma di video-scrittura impone (subdolamente) a chi scrive di impaginare il documento.

Questa potrebbe sembrare un’operazione di poco conto, tuttavia così non è.

Scrivere è una attività complessa e richiede concentrazione. Scrivere a computer richiede un superiore  grado di concentrazione. Infatti mentre il percorso di scrittura a mano ci viene insegnato fin dai primi anni di scolarizzazione, quello di scrivere al computer non viene quasi mai insegnato e si apprende solo dopo aver imparato a scrivere a mano.

Se scrivere con carta e penna è un’attività (relativamente) semplice, scrivere al computer espone lo scrittore a varie sfide, spesso non banali.

Anzitutto, lo scrittore deve conoscere i rudimenti dell’utilizzo di un computer, ovvero il sistema operativo così come l’hardware.  
Secondariamente, mentre carta e penna sono strumenti specializzati e finalizzati a scrivere, il computer è uno strumento multifunzionale. Un computer può essere uno strumento di scrittura, certamente, ma può anche essere uno strumento di svago (navigando in internet o guardando video), uno strumento di ricerca, uno strumento per comporre musica, fare calcoli e così via. La versatilità dello strumento computer ne determina anche uno dei più grossi limiti poiché è uno strumento che permette di distrarsi facilmente.  
Da ultimo, in questo periodo di iper-connessione con email e _social network_ che si sono aggiunti alle distrazioni che abbiamo già visto, il computer è diventato uno strumento sempre più problematico per lo scrittore che deve concentrarsi sulla scrittura.

A queste problematiche generali si aggiungono quelle specifiche della video-scrittura.

L’aspetto grafico di un testo, seppur importante, non è il primo aspetto a cui uno scrittore deve dedicarsi. Il primo e più importante scopo dello scrittore è quello di focalizzarsi sul contenuto che uno scritto veicola.  
Tuttavia, come abbiamo visto nei punti precedenti i programmi di video-scrittura non sono nati per scrivere ma per far mettere in “bella copia” dai dattilografi gli scritti prodotti dagli scrittori. La “trappola” dei programmi di video-scrittura è che la loro modalità di base è pensata per il testo stampato ed impaginato, non per scrivere in digitale.

## L’importanza dello strumento che usiamo

Se quindi un programma di video-scrittura non è lo strumento adatto per scrivere in digitale, qual’è quello corretto?

Prima di affrontare il problema in dettaglio pare opportuno fare una breve precisazione.

È convinzione generale che lo strumento che si utilizza per svolgere una determinata attività non influisca sul risultato della stessa, ma che a fare la differenza sia l’utilizzatore e il come lo strumento viene utilizzato.

Tale affermazione non è del tutto vera. Svariati studi scientifici dimostrano l’esatto contrario [^Carr1], ovvero che **lo strumento che utilizziamo modifica profondamente il modo in cui pensiamo e ci rapportiamo all’attività che svolgiamo con esso**. 

Un proverbio inglese recita “if all you have is a hammer, everything looks like a nail” che può essere tradotto in italiano come: _se hai solo un martello, tutto sembra essere un chiodo_. Da studi compiuti, sull’uomo così come sui primati, i neuro-scienziati hanno dimostrato la profonda plasticità del nostro cervello e, di conseguenza, del nostro pensiero, dimostrando come uno strumento ed il suo uso continuo e prolungato nel tempo modifichi profondamente il cervello umano ed i collegamenti neuronali, sia a livello fisico (addirittura aumentando certe regioni del cervello) sia a livello di collegamenti neuronali velocizzando e rafforzando i collegamenti di specifiche aree del cervello utilizzate[^Carr2].

A fronte di queste considerazioni è quindi di primaria importanza ragionare attentamente su quali strumenti digitali si utilizzano per scrivere. Ciò infatti può incidere profondamente sul modo in cui scriviamo.

È tuttavia evidente come, in particolare nel mondo degli uffici, tale scelta non sia affatto ragionata ed anzi segua consuetudini legate alle abitudini dovute più da pratiche commerciali che da scelte meditate.

## Ripensare a qual’è lo strumento digitale corretto per scrivere

Una volta che abbiamo visto come lo strumento non sia solo un mezzo ma come anche plasmi nel profondo il nostro modo di pensare e di “usare” lo strumento, vediamo quali caratteristiche questo strumento dovrebbe avere.

Anzitutto uno strumento deve svolgere una sola cosa e bene: _scrivere e revisionare il testo_. Può sembrare banale, ma la prima cosa che uno strumento di scrittura digitale deve fare è quella di permettere di scrivere facilmente e senza vincoli.

Scrivere in digitale è profondamente diverso dallo scrivere a mano. L’enorme vantaggio del digitale di poter modificare qualsiasi cosa si è digitata, è anche una potenziale maledizione. Permette di modificare ed affinare il proprio scritto all’infinito ma questa assenza di limitazioni a volte non è un beneficio ma uno svantaggio. La potenzialità di fare qualsiasi cosa a volte corrisponde all’opposto, non fare nulla. Uno strumento di scrittura digitale, quando lo si guarda dal punto di visto dello scrivere ovvero formalizzare il proprio pensiero in parole e contenuti, deve permettere di  fare solo quello senza distrazioni.   
Nel mondo della scrittura creativa sono nati negli ultimi anni una serie di programmi appositamente pensati per permettere allo scrittore di non distrarsi [^senzaDistrazioni], proprio per la presenza sempre più crescente della percezione da parte degli utenti finali di tale necessità.

Oltre però ad un ambiente per scrivere facilmente e senza distrazioni un simile programma deve avere un’altra caratteristica specifica e fondamentale: _la possibilità di revisionare il testo in modo efficiente ed effettivo_.

Questo è un punto spesso sottovalutato da molti, ma revisionare un testo digitale in modo rapido e preciso è importante quanto scrivere questo testo forse più importante della stessa parte di scrittura.
La revisione di un testo è sia la parte di _rifinitura del testo scritto_, ovvero quella di rendere il testo più semplice e più chiaro per il lettore, sia quella di _revisione formale_ ovvero quella di correzione degli errori grammaticali e di battitura. È quella parte della scrittura che divide lo scrittore amatoriale o non professionista da quello professionale, è quella parte che differenzia uno scritto mediocre da uno ben realizzato. Manipolare in modo programmatico e strutturato un testo è una possibilità fondamentale che molti sottovalutano.

Un altro punto fondamentale per un programma di scrittura è quello di essere semplice, non nel senso di essere facile da utilizzare, ma di _semplificare il flusso di lavoro dello scrittore_. Come visto poco sopra, la suddivisione in fasi del lavoro di scrittura, se può sembrare un modo di complicare l’attività stessa, è invece un modo per focalizzare e semplificare il lavoro ad una specifica attività. È infatti noto come il c.d. _multi-tasking_ [^multitasking] non sia sostenibile soprattutto per le attività che richiedono un profondo sforzo mentale.
Più in generale, infatti, la creazione di un flusso di lavoro strutturato e irregimentato aiuta ad aumentare la “produttività” [^mondoSenzaEmail].

Sempre seguendo questa strada, è, inoltre, necessario _suddividere la parte di scrittura da quella di impaginazione_. Tale suddivisione ha sia un vantaggio a livello di concentrazione e semplificazione del lavoro dello scrittore sia un vantaggio nella precisione e puntualità del risultato tipografico finale ottenuto. I programmi WYSIWYG, dovendo mostrare a video il risultato finale dell’impaginazione mentre il testo digitato viene prodotto, non sono ottimizzati per avere la migliore impaginazione possibile. Dividere la scrittura di un testo dall’impaginazione dello stesso permette di avere risultati tipografici migliori di quelli di qualsiasi programma di video-scrittura standard.


## Il problema di “imparare” di nuovo

Prima di esaminare la possibile soluzione ai problemi individuati fino ad ora, occorre affrontare quello che è un punto cruciale di questa analisi e che può rendere più semplice il passaggio al metodo che si vuole proporre con questo scritto; chiunque abbia in un qualche modo affrontato la scrittura è abituato ad usare un programma di video-scrittura, pertanto perché imparare una nuova serie di strumenti?

La domanda potrebbe sembrare banale ma è il principale scoglio che deve essere affrontato prima di investire le energie e le risorse necessarie per modificare un flusso di lavoro che, seppur non efficiente, è divenuto “facile”, ovvero richiede poca resistenza e si svolge secondo abitudini e riflessi automatici da parte di chi lo utilizza.

Se infatti ci si rende inconsciamente conto che scrivere con un programma di video-scrittura può non essere il modo migliore di scrivere in digitale (e chi scrive spera che con le argomentazioni che precedono il lettore lo abbia realizzato anche consciamente) ripensare il flusso di lavoro della scrittura digitale richiede degli sforzi iniziali notevoli e, fino a che lo scrittore digitale non prende possesso di questo nuovo flusso di lavoro, richiede indiscutibilmente maggiori sforzi del precedente flusso di lavoro.

Occorre quindi qui sottolineare un altro aspetto fondamentale e spesso sottovalutato dagli scrittori digitali: _il problema della padronanza dello strumento_, quello che gli anglofoni chiamano _mastery_.

Qualsiasi attività manuale o concettuale richiede un grado di padronanza di quella specifica attività. La padronanza di una “arte” come la scrittura è un percorso lungo e complesso che passa dal raffinamento di svariate competenze. Se tuttavia si ritiene utile e giusto fare questo percorso (e chi scrive per passione come chi per lavoro nel corso del tempo ha sicuramente investito in tale preparazione), si comprende bene come imparare “nuovamente” lo strumento con cui si scrive è fondamentale per uno scrittore.

Non solo, è provato da svariate ricerche cognitive che per migliorare le proprie capacità in uno specifico ambito è necessario mantenere la mentalità e l’approccio dell’apprendista [^diventaN1]. Ciò è condizione necessaria per superare quell’altipiano che, dopo un inizio di miglioramento, si raggiunge in qualsiasi forma di attività.

Per lo scrittore digitale, quindi, imparare nuovamente a scrivere in digitale con gli strumenti più adatti è anche una forma di miglioramento che gli permette di aumentare e migliorare la padronanza della scrittura stessa.

[^mercatoWindows]: Come risulta dal sito Statista: <https://www.statista.com/topics/1003/operating-systems/>

[^ms_Word]: Link a Wikipedia per una sommaria informazione: <https://it.wikipedia.org/wiki/Microsoft_Word> 

[^Carr1]: Carr, N. (2011). _Internet ci rende stupidi? Come la rete sta cambiando il nostro cervello._ Italia: Cortina Raffaello. Da pagina 33 a 53.
[^Carr2]: Pool, R., Ericsson, K. A. (2016). _Numero 1 si diventa. Sviluppa il tuo potenziale segreto per migliorare in quasi tutto quello che vuoi._ Italia: Sperling & Kupfer. Pagine da 28 a 34 cita lo studio svolto suoi tassisti londinesi e sulle modiche all’ippocampo.

[^senzaDistrazioni]: A titolo di mero esempio della pletora di applicazioni di questo genere si segnalano quelle individuate nell’articolo di cui al link che segue: <https://www.macitynet.it/Scrivere-senza-distrazioni-i-migliori-programmi-per-Mac/>. Vista la “popolarità” di questa funzione anche software come _Microsoft Word_ hanno implementato una modalità _focus_.

[^mondoSenzaEmail]: Newport, C. (2021). _A World Without Email: Reimagining Work in an Age of Communication Overload._ Stati Uniti: Penguin Publishing Group. Da pagina 179 a 183. Creare delle regole all’inizio permettono poi di coordinarsi meglio. Newport basa i suoi ragionamenti prendendo spunto dalla _Teoria dell’informazione_ di _Claud Shannon_ per maggiori approfondimenti link: <https://it.wikipedia.org/wiki/Teoria_dell'informazione>.

[^diventaN1]: Pool, R., Ericsson, K. A. (2016). _Numero 1 si diventa. Sviluppa il tuo potenziale segreto per migliorare in quasi tutto quello che vuoi._ Italia: Sperling & Kupfer. Pagine da 104 a 108. In vengono spiegati i principi base della _pratica intenzionale_.